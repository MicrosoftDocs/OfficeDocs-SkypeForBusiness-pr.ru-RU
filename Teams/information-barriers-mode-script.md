---
title: Изменение режимов информационных барьеров с помощью сценария PowerShell
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
ms.reviewer: smahadevan
ms.service: msteams
audience: admin
description: Используйте этот сценарий PowerShell после развертывания информационных барьеров, чтобы обновить режим от открытого до неявного для всех групп в клиенте.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3030f40ed61eb2e0e86967132d9575de8334a6c6
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767654"
---
# <a name="change-information-barriers-modes-with-a-powershell-script"></a>Изменение режимов информационных барьеров с помощью сценария PowerShell

Используйте этот сценарий PowerShell для обновления режима информационных барьеров (IB) для Teams групп в клиенте. После развертывания информационных барьеров необходимо обновить режим для этих групп. Группам, которые были готовы перед тем, как включить IB, назначен режим *"Открыть".* В *режиме* "Открыть" нет применимых политик IB. После того как вы в включить IB, *Неявный* становится режимом по умолчанию для всех новых групп, которые вы создаете. Тем не менее в существующих группах по-прежнему *остается настройка режима* "Открыть". Запустите этот сценарий, чтобы изменить существующие группы на *неявный* режим.

В этом сценарии для обновления режима используется командлет [Get-UnifiedGroup,](/powershell/module/exchange/Set-UnifiedGroup) который находится в модуле Exchange Online PowerShell. Дополнительные сведения об управлении Teams помощью PowerShell см. в Teams [PowerShell.](./teams-powershell-overview.md)

## <a name="sample-script"></a>Пример сценария

Для запуска этого сценария вам потребуется использовать учетную запись организации или учебного заведения, которая назначена роли глобального администратора для вашего клиента.

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