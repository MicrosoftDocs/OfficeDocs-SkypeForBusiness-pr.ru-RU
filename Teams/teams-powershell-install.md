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
ms.openlocfilehash: 99af6bc71bdd25375f6165f1e645bf4626dd3123
ms.sourcegitcommit: 2044fdcb0c5db10dbc77c5d66e382c1b927ccdc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2022
ms.locfileid: "63039977"
---
# <a name="install-microsoft-teams-powershell-module"></a>Установка Microsoft Teams PowerShell

В этой статье объясняется, как установить Microsoft Teams PowerShell с помощью коллекции PowerShell. Модуль Microsoft Teams PowerShell поддерживается на всех Windows платформах. Mac и Linux не поддерживаются.

## <a name="requirements"></a>Требования

Microsoft Teams powerShell требуется PowerShell 5.1 или более высокого уровня на всех платформах. Установите  [наижайшую версию PowerShellavailable](/powershell/scripting/install/installing-powershell)  для своей операционной системы. 

Чтобы проверить версию PowerShell, в сеансе PowerShell запустите следующую команду: 

```powershell
$PSVersionTable.PSVersion 
```
Рекомендуется использовать командлет Install-Module для установки Microsoft Teams PowerShell. 
 
Если галерея PowerShell (PSGallery) не настроена как надежный репозиторий **для PowerShellGet**, при первом использовании PSGallery вы увидите следующее сообщение:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Чтобы **продолжить** установку **, ответьте** Да или Да для всех.

## <a name="installing-using-the-powershellgallery"></a>Установка с помощью PowerShellGallery

Microsoft Teams powerShell в настоящее время поддерживается для использования с PowerShell 5.1 в Windows. Чтобы установить модуль, выполните указанные здесь действия. 

- [Обновим Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell). Если вы на Windows 10 1607 или более высокой версии, у вас уже установлен PowerShell 5.1. 
- Установите [платформа .NET Framework 4.7.2](/dotnet/framework/install) или более поздней. 
- Чтобы установить последнюю версию PowerShellGet, запустите следующую команду:
 
```powershell
Install-Module -Name PowerShellGet -Force -AllowClobber
```
- Установите модуль Teams PowerShell.

```powershell
Install-Module -Name MicrosoftTeams -Force -AllowClobber
```

## <a name="offline-installation"></a>Установка в автономном режиме 

В некоторых средах невозможно подключиться к коллекции PowerShell. В таких ситуациях выполните указанные здесь [действия по установке вручную](https://aka.ms/psgallery-manualdownload).  

## <a name="sign-in"></a>Вход

Чтобы приступить к работе с модулем Microsoft Teams PowerShell, войте свою учетную запись Azure.

```PowerShell
Connect-MicrosoftTeams 
``` 

## <a name="update-teams-powershell-module"></a>Обновление Teams PowerShell

Чтобы обновить любой модуль PowerShell, используйте тот же способ, который использовался для установки модуля. Например, если вы изначально использовали install-Module, для получения последней версии следует использовать [Update-Module](/powershell/module/powershellget/update-module) .  

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Если Teams powerShell уже импортируется в сеанс PowerShell, обновление модуля не удастся. Закроем PowerShell и снова откройте новый сеанс PowerShell с повышенными уровнями.


## <a name="uninstall-teams-powershell"></a>Удалить Teams PowerShell

Чтобы удалить Microsoft Teams PowerShell, откройте новую командную команду PowerShell и запустите следующую команду: 

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions 
```

## <a name="next-steps"></a>Дальнейшие действия 

Теперь вы можете управлять Microsoft Teams помощью Microsoft Teams PowerShell. См[. Teams управлением Teams PowerShell](teams-powershell-managing-teams.md). 

## <a name="related-topics"></a>Статьи по теме

[Управление Teams с помощью Teams PowerShell](teams-powershell-managing-teams.md)

[Teams powerShell заметки о выпуске](teams-powershell-release-notes.md)

[Microsoft Teams ссылки на cmdlet](/powershell/teams/?view=teams-ps)

[Skype для бизнеса ссылки на cmdlet](/powershell/skype/intro?view=skype-ps)
