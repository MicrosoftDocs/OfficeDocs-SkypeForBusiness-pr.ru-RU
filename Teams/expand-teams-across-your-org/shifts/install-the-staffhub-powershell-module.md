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
ms.openlocfilehash: 179276a049a30f1d049521cc3b4db326b988667c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36246183"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Установка модуля Microsoft StaffHub PowerShell

> [!IMPORTANT]
> Начиная с 1 октября 2019 г. Корпорация Microsoft StaffHub будет прекращена. Мы создаем возможности StaffHub в Microsoft Teams. Сегодня команды включают в себя приложение смен для управления планированием и дополнительные возможности, которые будут вычислены с течением времени. StaffHub перестанет работать для всех пользователей 1 октября 2019 г. Каждый, кто пытается открыть StaffHub, будет показывать сообщение, направленное на загрузку групп. Дополнительные сведения можно найти в [статье Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).  

Выполните действия, описанные в этой статье, чтобы установить и подключить модуль Microsoft StaffHub PowerShell. Это необходимо для управления StaffHub с помощью PowerShell, а также для перемещения команд StaffHub в Microsoft Teams.

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Установка модуля Microsoft StaffHub PowerShell

1. Скачайте [модуль PowerShell StaffHub](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha). 
2. Откройте Windows PowerShell 3,0 или более поздней версии в качестве администратора. Для этого нажмите кнопку **Пуск**, введите **Windows PowerShell**, щелкните правой кнопкой мыши **Windows PowerShell**, а затем выберите команду **Запуск от имени администратора**.
    > [!NOTE]
    > Чтобы получить последнюю версию Windows PowerShell, ознакомьтесь со статьей [Установка Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell). 
3. Выполните следующее:

    ```
    $ENV:PSModulePath
    ```
    

4. Проверьте путь к папке в выходных данных и убедитесь в том, что все папки в пути существуют на компьютере, прежде чем переходить к следующему шагу. Если папки отсутствуют, создайте их.
5. Чтобы разрешить установку модуля PowerShell StaffHub, выполните следующие действия:

    ```
    Set-ExecutionPolicy RemoteSigned
    ```

6. Выполните указанные ниже действия, &lt;где&gt; путь — это путь в выходных данных, начиная с шага 2. Например, путь может выглядеть так, как C:\Users\User1\Documents\WindowsPowerShell\Modules.

    Не забудьте выполнить каждую команду отдельно.

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.5-alpha -AllowPrerelease
    ```
7. Выйдите из Windows PowerShell.
8. Откройте Windows PowerShell 3,0 или более поздней версии в качестве глобального администратора, а затем выполните указанные ниже действия.

    ```
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
