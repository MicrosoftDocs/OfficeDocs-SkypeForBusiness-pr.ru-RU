---
title: Пример сценария PowerShell — приводятся сведения, с помощью команды Microsoft Deployment очистки
author: ninadara
ms.author: ninadara
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
description: Используйте этот сценарий PowerShell для очистки группами Майкрософт на конечных компьютерах или для отдельных пользователей.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: e159c06a27151523e52db5bf7e0aa2eab33620a9
ms.sourcegitcommit: dba47a65b0725806c98702bb7362a1b105cc93df
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2018
ms.locfileid: "21249194"
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a>Пример сценария PowerShell — Очистка развертывания групп Майкрософт
-------------------------------------------------------------------------

Этот сценарий PowerShell можно выполнять для очистки группами Майкрософт целевые компьютеры или пользователей. Должны быть выполнены для каждого пользователя на целевой компьютер. 


## <a name="sample-script"></a>Пример сценария

````powershell
<#
.SYNOPSIS
This script allows you to uninstall the Microsoft Teams app and remove Teams directory for a user.
.DESCRIPTION
Use this script to clear the installed Microsoft Teams application. Run this PowerShell script for each user profile for which the Teams App was installed on a machine. After the PowerShell has executed on all user profiles, Teams can be redeployed.
#>

$TeamsPath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams')
$TeamsUpdateExePath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams', 'Update.exe')

try
{
    if (Test-Path -Path $TeamsUpdateExePath) {
        Write-Host "Uninstalling Teams process"

        # Uninstall app
        $proc = Start-Process -FilePath $TeamsUpdateExePath -ArgumentList "-uninstall -s" -PassThru
        $proc.WaitForExit()
    }
    if (Test-Path -Path $TeamsPath) {
        Write-Host "Deleting Teams directory"
        Remove-Item –Path $TeamsPath -Recurse
    }
}
catch
{
    Write-Error -ErrorRecord $_
    exit /b 1
}

````


