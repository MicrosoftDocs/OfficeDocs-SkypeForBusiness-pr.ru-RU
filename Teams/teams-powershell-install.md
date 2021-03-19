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
ms.openlocfilehash: e6ba8545159f8b18ebe39e49356f64378f946b29
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874809"
---
# <a name="install-microsoft-teams-powershell"></a>Установка Microsoft Teams PowerShell

В этой статье объясняется, как установить модуль Microsoft Teams PowerShell с помощью [PowerShellGet.](/powershell/scripting/gallery/installing-psget) Эти инструкции работают на [платформах Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS и Windows.

## <a name="requirements"></a>Требования

Для Teams PowerShell требуется PowerShell 5.1 или более высокого уровня на всех платформах. Установите последнюю [версию PowerShell,](/powershell/scripting/install/installing-powershell) доступную для вашей операционной системы.

> [!WARNING]
> Известные проблемы с PowerShell 7 и Teams PowerShell. Для лучшей работы рекомендуется использовать PowerShell 5.1.

## <a name="install-the-teams-powershell-module"></a>Установка модуля Teams PowerShell

> [!NOTE]
> Для лучшей работы используйте как общедоступные, так и общедоступные модули предварительного просмотра. Они не предназначены для совместной работы.


Используйте **командлеты PowerShellGet** для установки модуля Teams PowerShell. Установка модуля для всех пользователей в системе требует повышенных привилегий. Начните сеанс PowerShell с использованием команды **"Запуск** от администратора" в Windows или воспользуйтесь командой `sudo` в macOS или Linux:

```powershell
Install-Module MicrosoftTeams
```

По умолчанию галерея PowerShell (PSGallery) не настроена как надежный репозиторий **для PowerShellGet.** При первом использовании PSGallery вы увидите следующее сообщение:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Чтобы **продолжить установку,** **ответьте** "Да" или "Да" для всех.


## <a name="install-teams-powershell-public-preview"></a>Установка открытой предварительной версии Teams PowerShell

> [!NOTE]
> Если вы используете общедоступный предварительный выпуск Teams PowerShell, настоятельно рекомендуем сначала удалить соединитель Skype для бизнеса Online.

Установка открытого предварительного модуля Teams PowerShell для всех пользователей в системе требует повышенных привилегий. Начните сеанс PowerShell с использованием команды **"Запуск** от администратора" в Windows или используйте команду `sudo` в macOS или Linux.

Если вы используете PowerShell 5.1, необходимо предварительно обновить модуль **PowerShellGet.** После обновления **PowerShellGet** закроете и снова откроете сеанс PowerShell с повышенными уровнями, чтобы убедиться, что будет загружена последняя версия **PowerShellGet.**

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Чтобы установить общедоступный предварительный просмотр Teams PowerShell, запустите команду PowerShell ниже.

> [!NOTE]
> Последнюю предварительную версию можно найти в [коллекции PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) или в PowerShell с помощью команд "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions".

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a>Установка соединителя Skype для бизнеса Online

> [!NOTE]
>
> Соединитель Skype для бизнеса Online сейчас входит в состав последнего модуля Teams PowerShell.
> Если вы используете последний общедоступный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.


```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in"></a>Вход

Чтобы приступить к работе с Teams PowerShell, войте учетные данные Azure.

> [!NOTE]
> Если вы используете последний общедоступный предварительный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать Соединитель Skype для бизнеса Online.

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a>Вход с использованием MFA и современной проверки подлинности

 Если в вашей учетной записи используется многофакторная проверка подлинности, воспользуйтесь действиями, которые необходимо предпринять в этом разделе.

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession
Import-PsSession $session
```

## <a name="update-teams-powershell"></a>Обновление Teams PowerShell

Чтобы обновить Teams PowerShell, откройте новую командную команду PowerShell с повышенными уровнями и запустите следующую команду:

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Если teams PowerShell уже импортируется в сеанс PowerShell, обновление модуля будет невозмауэром. Закроем PowerShell и снова откройте новый сеанс PowerShell с повышенными уровнями.


## <a name="uninstall-teams-powershell"></a>Удалить Teams PowerShell



Чтобы удалить Teams PowerShell, откройте новую командную команду PowerShell с повышенными уровнями и запустите следующую команду:

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> Если teams PowerShell уже импортируется в сеанс PowerShell, при этом не удастся это делать. Закроем PowerShell и снова откройте новый сеанс PowerShell с повышенными уровнями.

## <a name="next-steps"></a>Дальнейшие действия

Теперь вы готовы управлять Teams с помощью Teams PowerShell. Для начала работы см. управление Teams с [помощью Teams PowerShell.](teams-powershell-managing-teams.md)

## <a name="related-topics"></a>Связанные статьи

[Управление Teams с помощью Teams PowerShell](teams-powershell-managing-teams.md)

[Заметки о выпуске Teams PowerShell](teams-powershell-release-notes.md)

[Справочник по командлетам Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Справочник по cmdlet в Skype для бизнеса](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
