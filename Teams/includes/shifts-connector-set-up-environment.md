---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: c612f8d8e0f48249d9eabe19c5ae7513b0ae9d75
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593701"
---
1. Установите PowerShell версии 7 или более поздней. Пошаговую инструкцию см. в этой [Windows.](/powershell/scripting/install/installing-powershell-on-windows)

1. Запустите PowerShell в режиме администратора.
1. Установите модуль Microsoft Graph PowerShell.

    ```powershell
    Install-Module Microsoft.Graph
    Import-Module Microsoft.Graph
    ```

    Убедитесь, что это версия 1.6.1 или более поздней.

    ```powershell
    Get-InstalledModule Microsoft.Graph 
    ```

1. Установите модуль Teams Preview PowerShell.

    ```powershell
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force
    Import-Module MicrosoftTeams 
    ```

    Убедитесь, что это версия не ниже 4.1.0 и содержит cmdlets соединителя Shifts.

    ```powershell
    Get-Command -Module MicrosoftTeams -Name *teamsshiftsconnection* 
    ```
 
1. Установите модуль MSAL PowerShell.

    ```powershell
    Install-Module -Name MSAL.PS
    Import-Module MSAL.PS
    ```

1. Установите powerShell на выход, если при запуске сценария возникает ошибка.

    ```powershell
    $ErrorActionPreference = "Stop" 
    ```

1. В этой области можно включить сценарии для Windows.

    ```powershell
    Set-ExecutionPolicy bypass 
    ```