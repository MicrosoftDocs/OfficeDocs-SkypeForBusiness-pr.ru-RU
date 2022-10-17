---
title: Политика сетевого роуминга
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
search.appverid: MET150
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
description: Узнайте, как управлять настройками политики сетевого роуминга Teams.
ms.openlocfilehash: f8b1d78754c5f608aa76d9261b2164abc4de9194
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2022
ms.locfileid: "68585070"
---
# <a name="manage-video-and-media-settings-with-the-network-roaming-policy"></a>Управление настройками видео и мультимедиа с помощью политики сетевого роуминга

Помимо управления настройками видео и мультимедиа с помощью политик собраний, теперь вы можете динамически управлять использованием следующих атрибутов, применяемых клиентом Microsoft Teams с помощью TeamsNetworkRoamingPolicy. 

- IP-видео
- Скорость потока медиаданных

Эта политика позволяет назначать настройки сетевым сайтам. Клиент Teams будет динамически выбирать настройки в зависимости от того, к какому сетевому сайту он подключается. Когда клиент Teams выполняет вход с сетевого сайта с назначенной политикой роуминга, будет использоваться эта политика. Если политика не назначена, будут использоваться значения, назначенные в политике собраний. Дополнительные сведения о настройках звука и видео политики собраний см. в статье [Настройки политики собраний для звука и видео](meeting-policies-audio-and-video.md).

## <a name="configure-the-teamsnetworkroamingpolicy"></a>Настройка TeamsNetworkRoamingPolicy

Чтобы настроить TeamsNetworkRoamingPolicy, используйте следующие командлеты PowerShell.

- [Get-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/get-csteamsnetworkroamingpolicy)
- [New-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/new-csteamsnetworkroamingpolicy)
- [Set-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/set-csteamsnetworkroamingpolicy)
- [Remove-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/remove-csteamsnetworkroamingpolicy)

TeamsNetworkRoamingPolicy содержит указанные ниже параметры.

- AllowIPVideo. Этот параметр определяет, можно ли включать видео во время собраний, проводимых пользователем в индивидуальных и групповых звонках, начатых пользователем.

- MediaBitRateKb. Этот параметр определяет общую среднюю скорость передачи звука, видео и демонстраций приложений на основе видео в звонках и собраниях для пользователя.

После настройки политики назначьте ее одному или несколько сетевым сайтам с помощью командлета [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) следующим образом.

```PowerShell
 Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy LowBandwidthSite
 ``` 
 
 Чтобы удалить политику с сетевого сайта, используйте следующий командлет.
 
 ```PowerShell
 Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy $null
 ```

To enable the network roaming policy for users who are not enterprise voice enabled, you must also enable the AllowNetworkConfigurationSettingsLookup setting in TeamsMeetingPolicy. This setting is off by default.

Дополнительные сведения о создании сетевых сайтов см. в статье [Параметры сети для облачных функций голосовой связи](cloud-voice-network-settings.md). 

## <a name="examples"></a>Примеры

```PowerShell
New-CsTeamsNetworkRoamingPolicy -Identity LowBandwidthSite -AllowIPVideo $false -MediaBitRateKb 1000
```

```PowerShell
Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy LowBandwidthSite
```

## <a name="supported-clients"></a>Поддерживаемые клиенты

- Windows 
- Компьютер MacOS

## <a name="known-issues"></a>Известные проблемы

При указании New- и Get-CsTeamsNetworkRoamingPolicy в Teams Online PowerShell версии 2.0.0 вы увидите отображение дополнительных данных.


## <a name="related-topics"></a>Статьи по теме

- [Get-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/get-csteamsnetworkroamingpolicy)
- [New-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/new-csteamsnetworkroamingpolicy)
- [Set-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/set-csteamsnetworkroamingpolicy)
- [Remove-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/remove-csteamsnetworkroamingpolicy)
- [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite)
