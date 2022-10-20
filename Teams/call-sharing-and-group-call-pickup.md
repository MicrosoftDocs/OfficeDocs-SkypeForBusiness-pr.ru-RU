---
title: Общие звонки и ответ на групповые звонки
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 02/19/2019
ms.reviewer: jenstr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: Общий доступ к звонкам и групповой выбор звонков в Microsoft Teams позволяют пользователям делиться входящими звонками с коллегами, чтобы звонки можно было записывать, когда пользователь недоступен.
ms.openlocfilehash: 420378ce6d75523bf51b18c17e733d13a76ad877
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/20/2022
ms.locfileid: "68613851"
---
# <a name="call-sharing-and-group-call-pickup"></a>Общие звонки и ответ на групповые звонки

Функции общего доступа к звонкам и группового выбора звонков в Microsoft Teams позволяют пользователям делиться своими входящие звонки с коллегами, чтобы коллеги могли отвечать на звонки, которые происходят, когда пользователь недоступен.

Получение группового звонка менее нарушает работу получателей, чем другие формы предоставления общего доступа к звонкам, так как пользователи могут настроить способ получения уведомлений о входящем общем звонке и решить, следует ли отвечать на него. Порядок, в котором участники группы вызовов получают уведомления о входящем вызове, можно указать как одновременный или по порядку (с 5 или менее участниками).

> [!IMPORTANT]
> Пользователи, владелец группы вызовов и ее участники должны находиться в режиме развертывания "Только Teams". Дополнительные сведения о режимах развертывания Teams см. в статье "Общие сведения о [Microsoft Teams и](teams-and-skypeforbusiness-coexistence-and-interoperability.md) Skype для бизнеса сосуществование и взаимодействие".

## <a name="license-required"></a>Требуется лицензия

Пользователям должна быть назначена лицензия Телефонная система Microsoft Teams system для настройки и использования общего доступа к звонкам и группового ответа на вызовы. Дополнительные сведения о модели лицензирования см. в статье "Ниже приведены сведения о [телефонной системе"](/MicrosoftTeams/here-s-what-you-get-with-phone-system).

## <a name="limitations"></a>Ограничения

Пользователь может быть владельцем только одной группы вызовов. Каждая настроенная группа вызовов может содержать не более 25 пользователей или 32 768 символов. Пользователь может быть членом не более 25 групп вызовов.

Обратите внимание, что мобильные устройства будут получать уведомления только в том случае, если они настроены для баннера и мелодии звонка.

## <a name="enable-the-use-of-group-call-pickup"></a>Включение группового ответа на звонок

Чтобы включить группы вызовов, настройте для пользователя параметр **AllowCallGroups Для TeamsCallingPolicy** . Вы можете использовать Центр администрирования Teams или PowerShell. Если этот параметр включен, пользователь может настроить свои группы вызовов в клиенте Teams. 

Важно! Если вы отключаете группы  вызовов для пользователей, необходимо очистить связи между группами вызовов для пользователей в Центре администрирования Teams, чтобы избежать неправильной маршрутизации  вызовов. 

## <a name="use-teams-admin-center"></a>Использование Центра администрирования Teams

Сведения о настройке группового ответа на звонок для пользователей с помощью Центра администрирования Teams см. в разделе "Настройка параметров зова [для пользователей"](/MicrosoftTeams/user-call-settings).

## <a name="use-powershell"></a>Использование PowerShell

Чтобы настроить группы  вызовов для пользователей, используйте следующие командлеты модуля Teams PowerShell:

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings)

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings)

### <a name="examples"></a>Примеры

В следующем примере создается группа вызовов для user1@contoso.com с user2@contoso.com и user3@contoso.com и устанавливается немедленная переадресация вызовов в группу вызовов для user1@contoso.com:

```powershell
$cgm = @("sip:user2@contoso.com","sip:user3@contoso.com")
Set-CsUserCallingSettings -Identity user1@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

В следующем примере показано, как обновить группу вызовов user1@contoso.com добавить user5@contoso.com и удалить user6@contoso.com:

```powershell
$ucs = Get-CsUserCallingSettings -Identity user1@contoso.com
$cgt = {$ucs.CallGroupTargets}.Invoke()
$cgt.Add("sip:user5@contoso.com")
$cgt.Remove("sip:user6@contoso.com")
Set-CsUserCallingSettings -Identity user1@contoso.com -CallGroupOrder $ucs.CallGroupOrder -CallGroupTargets $cgt
```

## <a name="more-information"></a>Дополнительные сведения

[Переадресация  вызовов и одновременный звонок в Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)

[Политика звонков Teams](/MicrosoftTeams/teams-calling-policy)

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)
