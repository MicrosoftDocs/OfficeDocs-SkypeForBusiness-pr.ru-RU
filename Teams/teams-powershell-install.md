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

В этой статье объясняется, как установить модуль Microsoft Teams PowerShell с помощью [PowerShellGet.](/powershell/scripting/gallery/installing-psget) Эти инструкции работают на [платформах Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS и Windows Windows.

## <a name="requirements"></a>Требования

Teams Для работы PowerShell требуется PowerShell 5.1 или более высокого уровня на всех платформах. Установите последнюю [версию PowerShell,](/powershell/scripting/install/installing-powershell) доступную для вашей операционной системы.

> [!NOTE]
> Для лучшей работы рекомендуется использовать PowerShell 5.1.

## <a name="install-the-teams-powershell-module"></a>Установка модуля Teams PowerShell

> [!NOTE]
> Для лучшей работы используйте модули Общего доступа или Общедоступная предварительная версия, но не оба. Они не предназначены для совместной работы.


Установите модуль **PowerShell** с Teams PowerShell с помощью командлетов PowerShell. Установка модуля для всех пользователей в системе требует повышенных привилегий. Запустите сеанс PowerShell с **помощью** команды Запуск от Windows или воспользуйтесь `sudo` командой в macOS или Linux:

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

Чтобы **продолжить** **установку, ответьте** Да или Да для всех.

## <a name="sign-in"></a>Вход

Чтобы приступить к работе с Teams PowerShell, войте учетные данные Azure.

> [!NOTE]
> Если вы используете последний общедоступный предварительный [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать Skype для бизнеса Online Connector.

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a>Вход с использованием MFA и современной проверки подлинности

 Если в вашей учетной записи используется многофакторная проверка подлинности, воспользуйтесь действиями из этого раздела.

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
> Если Teams powerShell уже импортируется в сеанс PowerShell, обновление модуля не будет работать. Закроем PowerShell и снова откройте новый сеанс PowerShell с повышенными уровнями.


## <a name="uninstall-teams-powershell"></a>Удалить Teams PowerShell

Чтобы удалить Teams PowerShell, откройте новую командную команду PowerShell с повышенными уровнями и запустите следующую команду:

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> Если Teams PowerShell уже импортируется в сеанс PowerShell, при этом не удастся его выустановить. Закроем PowerShell и снова откройте новый сеанс PowerShell с повышенными уровнями.

## <a name="install-teams-powershell-public-preview"></a>Установка Teams предварительной версии PowerShell

> [!NOTE]
> Если вы используете общедоступный предварительный просмотр Teams PowerShell, настоятельно рекомендуем сначала удалить Skype для бизнеса Online Connector.

Установка общего предварительного Teams PowerShell для всех пользователей в системе требует повышенных привилегий. Запустите сеанс PowerShell с **помощью** команды Запуск от Windows или воспользуйтесь `sudo` командой в macOS или Linux.

Если вы используете PowerShell 5.1, необходимо предварительно обновить **модуль PowerShellGet.** После обновления **PowerShellGet**, закрытия и повторного открытия сеанса PowerShell с повышенными уровнями для обеспечения загрузки последней версии **PowerShellGet.**

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Чтобы установить Teams предварительной версии PowerShell, запустите команду PowerShell ниже.

> [!NOTE]
> Последнюю предварительную версию можно найти в [коллекции PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) или в PowerShell с помощью команд "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="next-steps"></a>Дальнейшие действия

Теперь вы можете управлять Teams помощью Teams PowerShell. См. [Teams управления Teams PowerShell.](teams-powershell-managing-teams.md)

## <a name="related-topics"></a>Статьи по теме

[Управление Teams с помощью Teams PowerShell](teams-powershell-managing-teams.md)

[Teams Заметки о выпуске PowerShell](teams-powershell-release-notes.md)

[Microsoft Teams ссылки на cmdlet](/powershell/teams/?view=teams-ps)

[Skype для бизнеса ссылки на cmdlet](/powershell/skype/intro?view=skype-ps)
