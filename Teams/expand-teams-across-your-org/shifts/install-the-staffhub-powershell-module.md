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
description: Узнайте, как установить и подключитесь к модуля Microsoft StaffHub PowerShell.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe419348d966d9ddfc5c16eee29d9a5005cd6db8
ms.sourcegitcommit: a505869a3cc2fe6fe4ee18bcbe99bf980aa91a86
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "31555137"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a>Установка модуля Microsoft StaffHub PowerShell

> [!IMPORTANT]
> Начиная с 1 октября 2019, Microsoft StaffHub будет из эксплуатации. Мы создаем StaffHub возможностей в группами Майкрософт. В настоящее время группы включает в себя приложение смены для управление планированием и дополнительные возможности будут развернуты со временем. StaffHub перестанет работать для всех пользователей на 1 октября 2019. Кто-то пытается открыть StaffHub отображается сообщение, предлагая загрузить групп. Для получения дополнительных сведений см [Microsoft StaffHub из эксплуатации](microsoft-staffhub-to-be-retired.md).  

Для установки и подключитесь к модуля Microsoft StaffHub PowerShell, выполните действия в этой статье. Вам понадобится управление StaffHub с помощью PowerShell, а также для перемещения ваших команд StaffHub группами Майкрософт.

## <a name="install-the-microsoft-staffhub-powershell-module"></a>Установка модуля Microsoft StaffHub PowerShell

1. Загрузите [модуль StaffHub PowerShell](https://www.powershellgallery.com/packages/MicrosoftStaffHub/1.0.0-alpha). 
2. Откройте Windows PowerShell 3.0 или более поздней версии с правами администратора. Для этого нажмите кнопку **Пуск**, введите **Windows PowerShell**, щелкните правой кнопкой мыши **Windows PowerShell**и выберите **Запуск от имени администратора**.
3. Выполните следующее:

    ```
    $ENV:PSModulePath
    ```

4. Проверьте путь к папке, в выходные данные и убедитесь в том, что всех папок в поле путь существует на компьютере, прежде чем перейти к следующему шагу. Если папки не указаны, их создания.
5. Выполните следующие действия, где &lt;путь&gt; — это путь, в выходные данные на шаге 2. Например путь может иметь вид C:\Users\User1\Documents\WindowsPowerShell\Modules.

    ```
    Save-Module -Name PowerShellGet -Path <path> -RequiredVersion 1.6.6
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    Save-Module -Name MicrosoftStaffHub -Path <path> -RequiredVersion 1.0.2
    Install-Module -Name MicrosoftStaffHub -RequiredVersion 1.0.2
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a>Подключение к модуля Microsoft StaffHub PowerShell

1. Выполните следующее:

    ```
    Connect-StaffHub
    ```

2. Если появится запрос, войдите в систему как глобальный администратор.

## <a name="related-topics"></a>Связанные разделы

- [Справочник по Microsoft StaffHub PowerShell](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [Перемещение групп Microsoft StaffHub в приложение "Смены" в Teams](move-staffhub-teams-to-shifts-in-teams.md)
