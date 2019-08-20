---
title: Установка модуля StaffHub PowerShell
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Сведения о том, как установить и подключить модуль Microsoft StaffHub PowerShell.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ce0d1acec923d09591e8f81b3f500ee9a910f5c
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464669"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Установка модуля Microsoft StaffHub PowerShell

> [!IMPORTANT]
> Начиная с 1 октября 2019 г. Корпорация Microsoft StaffHub будет прекращена. Мы создаем возможности StaffHub в Microsoft Teams. Сегодня команды включают в себя приложение смен для управления планированием и дополнительные возможности, которые будут вычислены с течением времени. StaffHub перестанет работать для всех пользователей 1 октября 2019 г. Каждый, кто пытается открыть StaffHub, будет показывать сообщение, направленное на загрузку групп. Дополнительные сведения можно найти в [статье Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).  

Выполните действия, описанные в этой статье, чтобы установить и подключить модуль Microsoft StaffHub PowerShell. Это необходимо для управления StaffHub с помощью PowerShell, а также для перемещения команд StaffHub в Microsoft Teams.

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Установка модуля Microsoft StaffHub PowerShell

1. Откройте Windows PowerShell 3,0 или более поздней версии в качестве администратора. Для этого нажмите кнопку **Пуск**, введите **Windows PowerShell**, щелкните правой кнопкой мыши **Windows PowerShell**, а затем выберите команду **Запуск от имени администратора**.
    > [!NOTE]
    > Чтобы получить последнюю версию Windows PowerShell, ознакомьтесь со статьей [Установка Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell). 
2. Чтобы установить текущую стабильную версию модуля PowerShell StaffHub, выполните указанные ниже действия.

    ```
    Install-Module -Name MicrosoftStaffHub
    ```
    
    Эту команду можно выполнить, только если вам нужно установить последнюю версию, которая может быть более стабильной, чем текущая стабильная версия:`Install-Module -Name MicrosoftStaffHub -AllowPrerelease`

     > [!NOTE]
     > Если при установке последней версии появляется сообщение об ошибке, вы можете выполнить следующие действия:`Install-Module PowershellGet -Force`

3. Вы можете увидеть сообщение с предупреждением:

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

Введите `Y` текст и `Enter`нажмите кнопку.
 
4. Выйдите из Windows PowerShell.

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Подключение к модулю PowerShell Microsoft StaffHub

1. Выполните следующее:

    ```
    Connect-StaffHub
    ```

2. После появления соответствующего запроса войдите в систему как глобальный администратор.

## <a name="related-topics"></a>Статьи по теме

- [Справочник по Microsoft StaffHub PowerShell](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [Перемещение групп Microsoft StaffHub в приложение "Смены" в Teams](move-staffhub-teams-to-shifts-in-teams.md)
