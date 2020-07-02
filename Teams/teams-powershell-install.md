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
description: Сведения об использовании элементов управления PowerShell для управления Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 849b22d09c79e97c5eaaeab4dee96b1d432970cb
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944140"
---
# <a name="install-microsoft-teams-powershell"></a>Установка Microsoft Teams PowerShell

В этой статье объясняется, как установить модуль Microsoft Teams PowerShell с помощью [PowerShellGet](/powershell/scripting/gallery/installing-psget). Эти инструкции применимы к [облачной оболочке Azure](/azure/cloud-shell/overview), Linux, macOS и платформам Windows.

## <a name="requirements"></a>Требования

Оболочки PowerShell для Teams работают с PowerShell 6.2.4 и более поздними версиями на всех платформах. Кроме того, она поддерживается в PowerShell 5,1 для Windows. Установите [последнюю версию PowerShell](/powershell/scripting/install/installing-powershell) , доступную для вашей операционной системы. В среде PowerShell 6.2.4 и более поздних версий отсутствуют дополнительные требования для Teams PowerShell.

> [!WARNING]
> Обнаружены проблемы с PowerShell 7 и Teams PowerShell. Для оптимальной работы мы рекомендуем использовать PowerShell 5,1.

## <a name="install-the-teams-powershell-module"></a>Установка модуля PowerShell Teams

> [!NOTE]
> Для оптимальной работы используйте либо общие, либо общедоступные модули предварительного просмотра, а не оба. Они не предназначены для совместной работы.


Для установки модуля PowerShell Teams используйте командлеты **PowerShellGet** . Установка модуля для всех пользователей системы требует повышенных привилегий. Запустите сеанс PowerShell с помощью команды " **Запуск от имени администратора** " в Windows или используйте `sudo` команду на macOS или Linux:

```powershell
Install-Module MicrosoftTeams
```

По умолчанию коллекция PowerShell (PSGallery) не настроена как доверенный репозиторий для **PowerShellGet**. При первом использовании PSGallery появляется следующее сообщение:

```output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Ответьте `Yes` на вопрос или `Yes to All` продолжите установку.


## <a name="install-teams-powershell-public-preview"></a>Установка общедоступной предварительной версии PowerShell для Teams

> [!NOTE]
> Если вы используете общедоступную версию предварительной версии оболочки Teams PowerShell, настоятельно рекомендуем сначала удалить соединитель Skype для бизнеса Online.

Для установки общедоступного модуля предварительной версии PowerShell для всех пользователей системы требуются повышенные полномочия. Запустите сеанс PowerShell с помощью команды " **Запуск от имени администратора** " в Windows или используйте `sudo` команду на macOS или Linux.

Если вы используете PowerShell 5,1, необходимо сначала обновить модуль **PowerShellGet** . После обновления **PowerShellGet**закройте и снова откройте сеанс PowerShell с повышенными привилегиями, чтобы убедиться в том, что вы загрузили последнюю версию **powershellget** .

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Чтобы установить общедоступную версию оболочки PowerShell для Teams, выполните команду PowerShell ниже.

```powershell
Install-Module MicrosoftTeams -AllowPrerelease
```

## <a name="install-the-skype-for-business-online-connector"></a>Установка соединителя Skype для бизнеса Online

> [!WARNING]
> В настоящее время Skype для бизнеса Online входит в общедоступный предварительный просмотр Teams PowerShell. После того как мы сделали эту функцию в окончательном выпуске Teams PowerShell, соединитель Skype для бизнеса Online больше не будет доступен.

Скачайте и установите [модуль PowerShell для Skype для бизнеса](https://www.microsoft.com/download/details.aspx?id=39366), а затем выполните следующую команду в PowerShell.

```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a>Вход

Для начала работы с Teams PowerShell выполните вход с помощью учетных данных Azure.

> [!NOTE]
> Если вы используете последнюю версию [общедоступного предварительного просмотра для Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), вам не нужно устанавливать соединитель Skype для бизнеса Online.

```powershell
$credential = Get-Credentials

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credentials $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credentials $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a>Обновление команд PowerShell

Чтобы обновить Teams PowerShell, откройте новую командную команду PowerShell с повышенными привилегиями и выполните указанные ниже действия.

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Если командная группа PowerShell уже импортирована в сеанс PowerShell, обновление модуля завершится сбоем. Закройте PowerShell и повторно откройте новый сеанс PowerShell с повышенными привилегиями.


## <a name="uninstall-teams-powershell"></a>Удаление команд оболочки PowerShell



Чтобы удалить Teams PowerShell, откройте новую командную команду PowerShell с повышенными привилегиями и выполните указанные ниже действия.

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> Если командная группа PowerShell уже импортирована в сеанс PowerShell, то при удалении модуля произойдет сбой. Закройте PowerShell и повторно откройте новый сеанс PowerShell с повышенными привилегиями.

## <a name="next-steps"></a>Дальнейшие действия

Теперь вы можете управлять группами с помощью PowerShell Teams. Чтобы приступить к работе, ознакомьтесь со статьей [Управление группами с помощью PowerShell Teams](teams-powershell-managing-teams.md) .

## <a name="related-topics"></a>Статьи по теме

[Управление группами с помощью PowerShell Teams](teams-powershell-managing-teams.md)

[Заметки о выпуске оболочки PowerShell для Teams](teams-powershell-release-notes.md)

[Справочник по командлетам Microsoft Teams](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Справочник по командлетам Skype для бизнеса](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
