---
title: Установка Microsoft Teams PowerShell
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Узнайте, как использовать элементы управления PowerShell для управления Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58d64a64fd7c9714e84042e4e1aa1be3eb4505db
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2022
ms.locfileid: "65682010"
---
# <a name="install-microsoft-teams-powershell-module"></a>Установка Microsoft Teams PowerShell

В этой статье объясняется, как установить модуль Microsoft Teams PowerShell с помощью коллекция PowerShell. Модуль Microsoft Teams PowerShell поддерживается на всех Windows платформ. Mac и Linux не поддерживаются.

## <a name="requirements"></a>Требования

Microsoft Teams PowerShell требуется PowerShell 5.1 или более поздней версии на всех платформах. Установите последнюю [версию PowerShell](/powershell/scripting/install/installing-powershell) , доступную для вашей операционной системы.

Чтобы проверить версию PowerShell, выполните следующую команду в сеансе PowerShell:

```powershell
$PSVersionTable.PSVersion
```

Рекомендуется использовать командлет Install-Module для установки Microsoft Teams PowerShell.

Если коллекция PowerShell (PSGallery) не настроен в качестве доверенного репозитория **для PowerShellGet**, при первом использовании PSGallery вы увидите следующее сообщение:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Ответ **"Да****" или "Да" для всех**, чтобы продолжить установку.

## <a name="installing-using-the-powershellgallery"></a>Установка с помощью PowerShellGallery

Microsoft Teams PowerShell в настоящее время поддерживается для использования с PowerShell 5.1 в Windows. Чтобы установить модуль, выполните следующие действия.

- Обновите [Windows PowerShell версии 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell). Если вы используете версию Windows 10 1607 или более поздней версии, у вас уже установлен PowerShell 5.1.
- Установите [платформа .NET Framework 4.7.2 или более](/dotnet/framework/install) поздней версии.
- Выполните следующую команду, чтобы установить последнюю версию PowerShellGet:

  ```powershell
  Install-Module -Name PowerShellGet -Force -AllowClobber
  ```

- Установите модуль Teams PowerShell.

  ```powershell
  Install-Module -Name MicrosoftTeams -Force -AllowClobber
  ```

## <a name="offline-installation"></a>Автономная установка

В некоторых средах невозможно подключиться к коллекция PowerShell. В таких ситуациях выполните следующие действия [по установке вручную](https://aka.ms/psgallery-manualdownload).

## <a name="sign-in"></a>Вход

Чтобы начать работу с Microsoft Teams PowerShell, войдите с помощью учетных данных Azure.

```PowerShell
Connect-MicrosoftTeams
```

## <a name="update-teams-powershell-module"></a>Обновление Teams PowerShell

Чтобы обновить любой модуль PowerShell, следует использовать тот же метод, который использовался для установки модуля. Например, если вы изначально использовали Install-Module, для получения последней версии следует использовать [Update-Module](/powershell/module/powershellget/update-module) .

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Если Teams PowerShell уже импортирован в сеанс PowerShell, обновление модуля завершится ошибкой. Закройте PowerShell и повторно откройте новый сеанс PowerShell с повышенными привилегиями.

## <a name="uninstall-teams-powershell"></a>Удаление Teams PowerShell

Чтобы удалить Microsoft Teams PowerShell, откройте новую командную строку PowerShell и выполните следующую команду:

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions
```

## <a name="next-steps"></a>Дальнейшие действия

Теперь вы можете управлять Microsoft Teams с помощью Microsoft Teams PowerShell. Чтобы [приступить к работе, Teams управление Teams PowerShell](teams-powershell-managing-teams.md).

## <a name="related-topics"></a>Статьи по теме

[Управление Teams с помощью Teams PowerShell](teams-powershell-managing-teams.md)

[Teams о выпуске PowerShell](teams-powershell-release-notes.md)

[Microsoft Teams командлета](/powershell/teams/)

[Skype для бизнеса командлета](/powershell/skype/intro)
