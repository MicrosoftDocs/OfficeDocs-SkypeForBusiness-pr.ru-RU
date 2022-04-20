---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: 3d4ec38f0007460fa119e69eadc79cd9c51887ee
ms.sourcegitcommit: 2ce3e95401ac06c0370a54862372a94ec6291d01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2022
ms.locfileid: "64976025"
---
1. Установите PowerShell версии 7 или более поздней. Пошаговые инструкции см. в [статье об установке PowerShell Windows](/powershell/scripting/install/installing-powershell-on-windows).

1. Запустите PowerShell в режиме администратора.
1. Установите модуль Microsoft Graph PowerShell.

    ```powershell
    Install-Module Microsoft.Graph
    Import-Module Microsoft.Graph
    ```

    Убедитесь, что это версия 1.6.1 или более поздняя.

    ```powershell
    Get-InstalledModule Microsoft.Graph 
    ```

1. Установите модуль Teams Предварительной версии PowerShell.

    ```powershell
    Install-Module -Name MicrosoftTeams -AllowPrerelease -Force
    Import-Module MicrosoftTeams 
    ```

    Убедитесь, что он имеет версию не ниже 4.1.0 и содержит командлеты соединителя Shifts.

    ```powershell
    Get-Command -Module MicrosoftTeams -Name *teamsshiftsconnection* 
    ```

1. Задайте выход Из PowerShell при возникновении ошибки при выполнении скрипта.

    ```powershell
    $ErrorActionPreference = "Stop" 
    ```

1. Включите сценарии для выполнения в Windows.

    ```powershell
    Set-ExecutionPolicy bypass 
    ```