---
title: Пример сценария PowerShell. Очистка развертывания Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: Используйте этот сценарий PowerShell для удаления Teams и удаления папки Teams для пользователей.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d7875cb01b928567d5883f36e21eb2f0de0bccf6
ms.sourcegitcommit: 4c4f2f220832cae3efb3f6f3c74795300d661295
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2022
ms.locfileid: "66825693"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a>Пример сценария PowerShell. Очистка развертывания Teams

Используйте этот сценарий для удаления Teams. Этот скрипт удаляет Teams и удаляет папку Teams для пользователя. Выполните этот сценарий для каждого профиля пользователя, в котором teams был установлен на компьютере.


## <a name="sample-script"></a>Пример сценария

````powershell
<#
.SYNOPSIS
This script uninstalls the Teams app and removes the Teams directory for a user.
.DESCRIPTION
Use this script to remove and clear the Teams app from a computer. Run this PowerShell script for each user profile in which Teams was installed on the computer. After you run this script for all user profiles, redeploy Teams.
#>

$TeamsPath = [System.IO.Path]::Combine($env:LOCALAPPDATA, 'Microsoft', 'Teams')
$TeamsUpdateExePath = [System.IO.Path]::Combine($TeamsPath, 'Update.exe')

try
{
    if ([System.IO.File]::Exists($TeamsUpdateExePath)) {
        Write-Host "Uninstalling Teams process"

        # Uninstall app
        $proc = Start-Process $TeamsUpdateExePath "-uninstall -s" -PassThru
        $proc.WaitForExit()
    }
    Write-Host "Deleting Teams directory"
    Remove-Item –path $TeamsPath -recurse
}
catch
{
    Write-Output "Uninstall failed with exception $_.exception.message"
    exit /b 1
}

````

## <a name="related-topics"></a>См. также

- [Установите Microsoft Teams с помощью Microsoft Endpoint Configuration Manager](../msi-deployment.md)
- [Развертывание Teams с Приложения Microsoft 365](/deployoffice/teams-install)
