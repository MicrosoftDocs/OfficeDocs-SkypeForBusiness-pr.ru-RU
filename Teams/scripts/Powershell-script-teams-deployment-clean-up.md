---
title: Пример сценария PowerShell — помощь с очисткой развертывания Microsoft Teams
ms.reviewer: ''
author: kenwith
ms.author: kenwith
manager: serdars
audience: admin
ms.date: 03/21/2018
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
description: Вы можете использовать этот сценарий, чтобы очистить Microsoft Teams на целевых компьютерах или для конкретных пользователей.
localization_priority: Normal
ms.openlocfilehash: aa5ba0c6e94510449e1afd9c2fc03524c1846f9c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36242878"
---
<a name="powershell-script-sample---microsoft-teams-deployment-clean-up"></a><span data-ttu-id="97fd8-103">Пример сценария PowerShell — очистка развертывания Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="97fd8-103">PowerShell Script Sample - Microsoft Teams deployment clean up</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="97fd8-104">Этот сценарий PowerShell можно использовать для очистки Microsoft Teams на целевых компьютерах или для конкретных пользователей.</span><span class="sxs-lookup"><span data-stu-id="97fd8-104">This PowerShell script can be leveraged for the cleanup of Microsoft Teams from target machines or users.</span></span> <span data-ttu-id="97fd8-105">Его следует запустить для каждого пользователя на целевом компьютере.</span><span class="sxs-lookup"><span data-stu-id="97fd8-105">It should be executed for every user on a targeted machine.</span></span> 


## <a name="sample-script"></a><span data-ttu-id="97fd8-106">Пример сценария</span><span class="sxs-lookup"><span data-stu-id="97fd8-106">Sample script</span></span>

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
        Remove-Item -Path $TeamsPath -Recurse
                    
    }
}
catch
{
    Write-Error -ErrorRecord $_
    exit /b 1
}
````


