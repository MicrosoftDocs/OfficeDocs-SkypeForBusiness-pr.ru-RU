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
ms.openlocfilehash: 002f2bc8408536d79274c5e9b001f5e2a5eb55b3
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768347"
---
# <a name="install-microsoft-teams-powershell"></a>Установка Microsoft Teams PowerShell

В этой статье объясняется, как установить модуль Microsoft Teams PowerShell с помощью [PowerShellGet.](/powershell/scripting/gallery/installing-psget) Эти инструкции работают на [платформах Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS и Windows.

## <a name="requirements"></a>Требования

Для Teams PowerShell требуется PowerShell 5.1 или более высокого уровня на всех платформах. Установите последнюю [версию PowerShell,](/powershell/scripting/install/installing-powershell) доступную для вашей операционной системы.

> [!NOTE]
> Для лучшей работы рекомендуется использовать PowerShell 5.1.

## <a name="install-the-teams-powershell-module"></a>Установка модуля Teams PowerShell

> [!NOTE]
> Для лучшей работы используйте как общедоступные, так и общедоступные модули предварительной версии. Они не предназначены для совместной работы.


Используйте **командлеты PowerShellGet** для установки модуля Teams PowerShell. Установка модуля для всех пользователей в системе требует повышенных привилегий. Начните сеанс PowerShell с администратором **"Запуск"** в Windows или используйте команду `sudo` в macOS или Linux:

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

## <a name="sign-in"></a>Вход

Чтобы приступить к работе с Teams PowerShell, войте учетные данные Azure.

> [!NOTE]
> Если вы используете последний общедоступный предварительный выпуск [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a>Вход с использованием многофационной проверки подлинности и современной проверки подлинности

 Если в вашей учетной записи используется многофакторная проверка подлинности, воспользуйтесь действиями, которые данной статьи.

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>
```

## <a name="update-teams-powershell"></a>Обновление Teams PowerShell

Чтобы обновить Teams PowerShell, откройте новую командную команду PowerShell с повышенными уровнями и запустите следующую команду:

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Если teams PowerShell уже импортируется в сеанс PowerShell, обновление модуля не будет работать. Закроем PowerShell и снова откройте новый сеанс PowerShell с повышенными уровнями.


## <a name="uninstall-teams-powershell"></a>Удалить Teams PowerShell

Чтобы удалить Teams PowerShell, откройте новую командную команду PowerShell с повышенными уровнями и запустите следующую команду:

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> Если teams PowerShell уже импортируется в сеанс PowerShell, при этом не удастся это делать. Закроем PowerShell и снова откройте новый сеанс PowerShell с повышенными уровнями.

## <a name="install-teams-powershell-public-preview"></a>Установка открытой предварительной версии Teams PowerShell

> [!NOTE]
> Если вы используете общедоступный предварительный выпуск Teams PowerShell, настоятельно рекомендуем сначала удалить Соединитель Skype для бизнеса Online.

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

## <a name="next-steps"></a>Дальнейшие действия

Теперь вы готовы управлять Teams с помощью Teams PowerShell. Для начала работы см. управление Teams с [помощью Teams PowerShell.](teams-powershell-managing-teams.md)

## <a name="related-topics"></a>Статьи по теме

[Управление Teams с помощью Teams PowerShell](teams-powershell-managing-teams.md)

[Заметки о выпуске Teams PowerShell](teams-powershell-release-notes.md)

[Справочник по командлетам Microsoft Teams](/powershell/teams/?view=teams-ps)

[Справочник по cmdlet в Skype для бизнеса](/powershell/skype/intro?view=skype-ps)
