---
title: Пример сценария PowerShell— Teams очистки развертывания
author: cichur
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.reviewer: amitsri
ms.service: msteams
audience: admin
description: Используйте этот сценарий PowerShell, чтобы удалить Teams и удалить Teams папку для пользователей.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4853cf99bc6d600f8673df065c3dee3e0068207b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767157"
---
# <a name="powershell-script-sample---teams-deployment-clean-up"></a>Пример сценария PowerShell: очистка Teams развертывания

Используйте этот сценарий для удаления Teams. Этот сценарий удаляет Teams и удаляет папку Teams пользователя. Запустите этот сценарий для каждого профиля пользователя, в Teams был установлен на компьютере.


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

## <a name="related-topics"></a>Статьи по теме

- [Установите Microsoft Teams с помощью Microsoft Endpoint Configuration Manager](../msi-deployment.md)
- [Развертывание Teams с помощью Приложения Microsoft 365](/deployoffice/teams-install)
