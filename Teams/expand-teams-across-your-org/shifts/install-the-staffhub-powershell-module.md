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
description: Сведения о том, как установить и подключиться к предварительной версии модуля Microsoft StaffHub PowerShell.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: aa7f84342b2d4ae16cf801be513e1ae9d6440802
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569214"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Установка модуля Microsoft StaffHub PowerShell

> [!IMPORTANT]
> Вступление в силу 31 декабря 2019 г. Корпорация Microsoft StaffHub будет прекращена. Мы создаем возможности StaffHub в Microsoft Teams. Сегодня команды включают в себя приложение смен для управления планированием и дополнительные возможности, которые будут вычислены с течением времени. StaffHub перестанет работать для всех пользователей 31 декабря 2019 г. Каждый, кто пытается открыть StaffHub, будет показывать сообщение, направленное на загрузку групп. Дополнительные сведения можно найти в [статье Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).  

Выполните действия, описанные в этой статье, чтобы установить и подключиться к предварительной версии модуля Microsoft StaffHub PowerShell. Это необходимо для того, чтобы [переместить StaffHub Teams в Teams](move-staffhub-teams-to-shifts-in-teams.md).

## <a name="install-the-prerelease-version-of-the-microsoft-staffhub-powershell-module"></a>Установка предварительной версии модуля PowerShell Microsoft StaffHub

1. Откройте Windows PowerShell 3,0 или более поздней версии в качестве администратора. Для этого нажмите кнопку **Пуск**, введите **Windows PowerShell**, щелкните правой кнопкой мыши **Windows PowerShell**, а затем выберите команду **Запуск от имени администратора**.
    > [!NOTE]
    > Чтобы получить последнюю версию Windows PowerShell, ознакомьтесь со статьей [Установка Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell). 
2. Чтобы установить предварительную версию модуля PowerShell StaffHub, выполните указанные ниже действия.

    ```
    Install-Module -Name MicrosoftStaffHub -AllowPrerelease
    ```
3. Вы можете увидеть сообщение с предупреждением:

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

    Введите `Y`текст и нажмите кнопку `Enter`.
 
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
