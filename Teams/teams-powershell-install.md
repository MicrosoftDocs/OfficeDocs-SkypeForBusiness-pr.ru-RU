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
ms.openlocfilehash: 966dd62a9917c616c53fc57e13ca468e64acf218
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824940"
---
# <a name="install-microsoft-teams-powershell"></a>Установка Microsoft Teams PowerShell

В этой статье объясняется, как установить модуль Microsoft Teams PowerShellскую версию [с помощью PowerShellGet.](/powershell/scripting/gallery/installing-psget) Эти инструкции относятся к платформам Azure Оболочки [Azure,](/azure/cloud-shell/overview)Linux, macOS и Windows.

## <a name="requirements"></a>Требования

Для всех платформ для Teams требуется PowerShell 5.1 или более поздней версии. Установите [последнюю версию PowerShell для](/powershell/scripting/install/installing-powershell) вашей операционной системы.

> [!WARNING]
> С помощью PowerShell 7 и Teams есть известные проблемы. Для оптимальной работы мы рекомендуем использовать PowerShell 5.1.

## <a name="install-the-teams-powershell-module"></a>Установка модуля PowerShell

> [!NOTE]
> Для оптимальной работы используйте общий доступность (GA) или открытый модули общедоступной версии (не оба варианта). Они не должны совместно работать.


Установите **модуль Teams PowerShellGet с** помощью командлетов PowerShellGet. Для установки модуля для всех пользователей в системе требуется повышенные права. Запустите сеанс PowerShell с помощью **команды "Запуск от** имени администратора" в Windows или `sudo` используйте команду в macOS или Linux:

```powershell
Install-Module MicrosoftTeams
```

По умолчанию коллекция PowerShell (PSGallery) не настроена как надежный репозиторий **для PowerShellGet.** При первом использовании PSGallery вы увидите следующее сообщение:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Ответы **"Да"** или **"Все" для** продолжения установки.


## <a name="install-teams-powershell-public-preview"></a>Установка общедоступной предварительной версии Teams PowerShell

> [!NOTE]
> Если вы используете общедоступную предварительную версию Teams PowerShell, настоятельно рекомендуем сначала удалить Skype для бизнеса Online Connector.

Для установки модуля предварительной версии Teams PowerShell для всех пользователей в системе необходимы повышенные права. Запустите сеанс PowerShell, используя **команду "Запуск от** имени администратора" в Windows или `sudo` используйте команду в macOS или Linux.

Если вы используете PowerShell 5.1, необходимо обновить модуль **PowerShellGet.** После обновления **PowerShellGet**закройте и снова откройте сеанс PowerShellGet, чтобы убедиться, **что PowerShellGet** загружен.

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Чтобы установить общедоступную предварительную версию Teams PowerShell, выполните следующую команду PowerShell:

> [!NOTE]
> Последнюю предварительную версию [в коллекции PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) или PowerShell можно найти с помощью команды "Найти-модуль MicrosoftTeams -AllowPrerelease"

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.3-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a>Установка соединителя Skype для бизнеса Online

> [!WARNING]
> Skype для бизнеса Online Connector в настоящее время входит в общедоступную версию Teams PowerShell. После развертывания этой функции в географическом выпуске Teams PowerShell соединитель Skype для бизнеса Online больше не будет доступен.

Скачайте и [установите модуль Skype для бизнеса PowerShell,](https://www.microsoft.com/download/details.aspx?id=39366)а затем выполните в PowerShell следующую команду:

```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a>Вход

Чтобы приступить к работе с Teams PowerShell, войдите с учетными данными Azure.

> [!NOTE]
> Если вы используете последнюю предварительную [версию Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)вам не нужно устанавливать соединитель Skype для бизнеса Online.

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a>Обновление Teams PowerShell

Чтобы обновить Teams PowerShell, откройте новую командную строку PowerShell с повышенными возможностями PowerShell и выполните следующую команду:

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Если Команды PowerShell уже были импортированы в сеанс PowerShell, произойдет сбой. Закройте PowerShell и снова откройте новый сеанс PowerShell.


## <a name="uninstall-teams-powershell"></a>Удаление Teams PowerShell



Чтобы удалить команды PowerShell, откройте новую командную строку PowerShell с повышенными возможностями PowerShell и выполните следующую команду:

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> Если Teams PowerShell уже была импортирована в сеанс PowerShell, удаление модуля завершится сбоем. Закройте PowerShell и снова откройте новый сеанс PowerShell.

## <a name="next-steps"></a>Дальнейшие действия

Теперь вы готовы управлять Командами с помощью команд PowerShell. [Узнайте, как управлять Командами с помощью Teams PowerShell,](teams-powershell-managing-teams.md) чтобы приступить к работе.

## <a name="related-topics"></a>См. также

[Управление командами с помощью Teams PowerShell](teams-powershell-managing-teams.md)

[Заметки о выпуске Командной оболочки Teams PowerShell](teams-powershell-release-notes.md)

[Справочник по командлету Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Справочник командлета Skype для бизнеса](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
