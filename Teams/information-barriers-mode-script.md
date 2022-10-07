---
title: Изменение режимов информационных барьеров с помощью скрипта PowerShell
description: Используйте этот сценарий PowerShell после развертывания информационных барьеров, чтобы обновить режим с открытого до неявного для всех групп в клиенте.
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
ms.reviewer: smahadevan
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- tier2
- purview-compliance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 63403c5e5ee495a7a110aa9239868fd6a9bb5803
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2022
ms.locfileid: "68047129"
---
# <a name="change-information-barriers-modes-with-a-powershell-script"></a>Изменение режимов информационных барьеров с помощью скрипта PowerShell

Используйте этот сценарий PowerShell для обновления режима информационных барьеров (IB) для всех групп, подключенных к Teams в клиенте. После развертывания информационных барьеров необходимо обновить режим для этих групп. Группам, подготовленным перед включением IB, назначается режим *открытия* . В *режиме* открытия нет применимых политик IB. После включения IB *неявный параметр* становится режимом по умолчанию для всех новых групп, которые вы создаете. Однако существующие группы по-прежнему поддерживают *конфигурацию открытого* режима. Запустите этот сценарий, чтобы изменить существующие группы на *неявный* режим.

В этом сценарии для обновления режима используется командлет [Get-UnifiedGroup](/powershell/module/exchange/Set-UnifiedGroup), который находится в Exchange Online PowerShell. Дополнительные сведения об управлении Teams с помощью PowerShell см. в [обзоре Teams PowerShell](./teams-powershell-overview.md).

## <a name="sample-script"></a>Пример сценария

Для выполнения этого сценария необходимо использовать рабочую или учебную учетную запись, которой назначена роль глобального администратора для клиента.

```powershell
<#
.SYNOPSIS
This script updates the information barrier mode for all Teams-connected groups in your tenant at the same time.
.DESCRIPTION
Use this script to update the info barrier mode from open to implicit across the groups in your tenant.
#>

$teams = Get-UnifiedGroup -Filter {ResourceProvisioningOptions -eq "Team"} -ResultSize Unlimited

Write-Output ([string]::Format("Number of Teams = {0}", @($teams).Length))

$teamsToUpdate = New-Object System.Collections.ArrayList

foreach($team in $teams)
{
  if ($team.InformationBarrierMode -eq "Open")
  {
    $teamsToUpdate.Add($team.ExternalDirectoryObjectId) | out-null
  }
}

Write-Output ([string]::Format("Number of Teams to be backfilled = {0}", @($teamsToUpdate).Length))

$outfile = "BackfillFailedTeams.csv"

if (!(Test-Path "$outfile"))
{
  $newcsv = {} | Select "ExternalDirectoryObjectId", "ExceptionDetails" | Export-Csv $outfile -NoTypeInformation  
}
else
{
  $dateTime = Get-Date
  $newEntry = "{0},{1}" -f "New session started", $dateTime
  $newEntry | add-content $outfile
}

$SuccessfullyBackfilledGroup = 0

for($i = 0; $i -lt @($teamsToUpdate).Length; $i++)
{
  Invoke-Command { Set-UnifiedGroup $teamsToUpdate[$i] -InformationBarrierMode "Implicit" } -ErrorVariable ErrorOutput

  if ($ErrorOutput)
  {
    # saving the errors in a csv file
    $errorBody = $ErrorOutput[0].ToString() -replace "`n"," " -replace "`r"," " -replace ",", " "
    $newEntry = "{0},{1}" -f $teamsToUpdate[$i].ToString(), '"' + $errorBody + '"'
    $newEntry | add-content $outfile
  }
  else
  {
    $SuccessfullyBackfilledGroup++
  }

  if (($i+1) % 100 -eq 0)
  {
    # print the number of teams backfilled after the batch of 100 updates
    Write-Output ([string]::Format("Number of Teams processed= {0}", $i+1)) 
  }
}

Write-Output ([string]::Format("Backfill completed. Groups backfilled: {0}, Groups failed to backfill: {1}", $SuccessfullyBackfilledGroup, @($teamsToUpdate).Length - $SuccessfullyBackfilledGroup))

if (!($SuccessfullyBackfilledGroup -eq @($teamsToUpdate).Length))
{
  Write-Output ([string]::Format("Check the failed teams in BackfillFailedTeams.csv, retry to backfill the failed teams.")) 
}

```