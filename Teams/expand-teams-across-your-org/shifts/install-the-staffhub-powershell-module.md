---
title: Установка модуля StaffHub PowerShell
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 04/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Сведения о том, как установить и подключить модуль Microsoft StaffHub PowerShell.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6eab331c8d8b2213225ad8c7ee216f9f6ec2b51
ms.sourcegitcommit: 55da03c85237b43b848e7ff9b427304c2d9e568f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "34681883"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Установка модуля Microsoft StaffHub PowerShell

> [!IMPORTANT]
> Начиная с 1 октября 2019 г. Корпорация Microsoft StaffHub будет прекращена. Мы создаем возможности StaffHub в Microsoft Teams. Сегодня команды включают в себя приложение смен для управления планированием и дополнительные возможности, которые будут вычислены с течением времени. StaffHub перестанет работать для всех пользователей 1 октября 2019 г. Каждый, кто пытается открыть StaffHub, будет показывать сообщение, направленное на загрузку групп. Дополнительные сведения можно найти в [статье Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).  

Выполните действия, описанные в этой статье, чтобы установить и подключить модуль Microsoft StaffHub PowerShell. Это необходимо для управления StaffHub с помощью PowerShell, а также для перемещения команд StaffHub в Microsoft Teams.

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Установка модуля Microsoft StaffHub PowerShell

1. Скачайте [модуль PowerShell StaffHub](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha). 
2. Откройте Windows PowerShell 3,0 или более поздней версии в качестве администратора. Для этого нажмите кнопку **Пуск**, введите **Windows PowerShell**, щелкните правой кнопкой мыши **Windows PowerShell**, а затем выберите команду **Запуск от имени администратора**.
3. Выполните следующее:

    ```
    $ENV:PSModulePath
    ```
    

4. Проверьте путь к папке в выходных данных и убедитесь в том, что все папки в пути существуют на компьютере, прежде чем переходить к следующему шагу. Если папки отсутствуют, создайте их.
5. Чтобы разрешить установку модуля PowerShell StaffHub, выполните указанные ниже действия.

```
Set-ExecutionPolicy RemoteSigned
```

6. Выполните указанные ниже действия, &lt;где&gt; путь — это путь в выходных данных, начиная с шага 2. Например, путь может выглядеть так, как C:\Users\User1\Documents\WindowsPowerShell\Modules.

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.5-alpha -AllowPrerelease
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Подключение к модулю PowerShell Microsoft StaffHub

1. Выполните следующее:

    ```
    Connect-StaffHub
    ```

2. После появления соответствующего запроса войдите в систему как глобальный администратор.

## <a name="related-topics"></a>Статьи по теме

- [Справочник по Microsoft StaffHub PowerShell](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [Перемещение групп Microsoft StaffHub в приложение "Смены" в Teams](move-staffhub-teams-to-shifts-in-teams.md)
