---
title: Пример сценария PowerShell — помощь с очисткой развертывания Microsoft Teams
ms.reviewer: ''
author: Lester-Hewett
ms.author: lehewe
manager: serdars
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
description: Вы можете использовать этот сценарий, чтобы очистить Microsoft Teams на целевых компьютерах или для конкретных пользователей.
localization_priority: Normal
ms.openlocfilehash: a047326a1598ea497318b77ce27c09c6807f25dc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201681"
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a>Пример сценария PowerShell — очистка развертывания Microsoft Teams
-------------------------------------------------------------------------

Этот сценарий PowerShell можно использовать для очистки Microsoft Teams на целевых компьютерах или для конкретных пользователей. Его следует запустить для каждого пользователя на целевом компьютере. 


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


