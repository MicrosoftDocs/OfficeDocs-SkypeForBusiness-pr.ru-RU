---
title: Настройка параметров звонка для пользователей
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System - seo-marvel-apr2020
description: Узнайте, как настроить пользовательские параметры для переад вызовов и делегирования параметров.
ms.openlocfilehash: 5443ad958d23753b1d67d42782ddab41d9d6d080
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2022
ms.locfileid: "63689175"
---
# <a name="configure-call-settings-for-your-users"></a>Настройка параметров звонка для пользователей

В этой статье описано, как администратор может изменять параметры переадминирования и делегирования  вызовов для пользователей. Эти параметры можно изменить, например, если:

- Пользователь не на больничных, и вам необходимо обеспечить переадваровку входящих звонков коллеге.

- Вам необходимо проверить параметры переадваровки для всех пользователей в отделе и при необходимости исправить их.

- Новый помощник уже работает, и вам нужно добавить его в качестве делегата для группы сотрудников.

Вы можете использовать Teams администрирования или Teams PowerShell для просмотра и изменения параметров звонка для пользователей.

Чтобы настроить параметры звонка для пользователя, ему должна быть назначена Телефон (Майкрософт) "Система".

## <a name="use-the-teams-admin-center"></a>Использование центра Teams администрирования

В Центре администрирования Teams настроить групповые вызовы и делегировать их делегированию для пользователей. 

> [!NOTE]
> В настоящее время параметр настройки параметров переадминистрировать вызовы не доступен в Teams центре администрирования.

Чтобы настроить групповую настройку звонка:

1. В Teams администрирования перейдите к **странице ПользователиУправляемые** >  **пользователи** и выберите пользователя.

2. На странице сведений о пользователе перейдите на **вкладку Голосовая** почта.

3. В **группе Групповые вызовы** выберите **Добавить людей**. 

4. Укажите параметры **задержки и заказа звонка**.

Чтобы настроить делегирование, на той же странице перейдите **к** делегированию зовов и выберите **Добавить людей**.

## <a name="use-powershell"></a>Использование PowerShell

Вы можете использовать PowerShell для настройки параметров переад вызовов и делегирования параметров для пользователей.  Вы будете использовать следующие командлеты, доступные в Teams PowerShell версии 4.0 или более поздней версии:

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps) — показывает параметры переадреации звонка, представителей и сведения о делегаторе для пользователя.

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings?view=teams-ps) — настраивает параметры переадстройки звонка для пользователя.

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate?view=teams-ps) — добавляет нового представителя с разрешениями для пользователя.

-   [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate?view=teams-ps) — изменение разрешений для существующего представителя.

-   [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate?view=teams-ps) — удаляет представителя от пользователя.


### <a name="display-call-forward-and-delegation-settings-for-a-user"></a>Отображение параметров переад вызовов и делегирования для пользователя

Чтобы отобразить текущие параметры переад вызовов и делегирования для пользователя, используйте Get-CsUserCallingSettings, как показано в следующем примере:

```PowerShell
Get-CsUserCallingSettings -Identity user1@contoso.com
SipUri                    : sip:opr1@contoso.com
IsForwardingEnabled       : True
ForwardingType            : Simultaneous
ForwardingTarget          :
ForwardingTargetType      : MyDelegates
IsUnansweredEnabled       : True
UnansweredTarget          :
UnansweredTargetType      : Voicemail
UnansweredDelay           : 00:00:20
Delegates                 : Id:user2@contoso.com
Delegators                : 
CallGroupOrder            : InOrder
CallGroupTargets          : {}
GroupMembershipDetails    :
GroupNotificationOverride : Ring

(Get-CsUserCallingSettings -Identity user1@contoso.com).Delegates

Id             : user2@contoso.com
MakeCalls      : True
ManageSettings : True
ReceiveCalls   : True
```

Результат показывает, что пользователь1 одновременно звонит настроенным представителям. Неотвеченные звонки отправляются на голосовую почту через 20 секунд. Пользователь2 определяется как представитель со всеми разрешениями представителя.


### <a name="set-call-forward-settings-for-a-user"></a>Настройка параметров переад вызовов для пользователя

Чтобы переадросить все звонки для пользователя1 пользователю2, используйте Set-CsUserCallingSettings, как показано в следующем примере: 

```PowerShell
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType SingleTarget -ForwardingTarget user2@contoso.com
```

Чтобы одновременно звонить всем делегатам для пользователя user3, используйте Set-CsUserCallingSettings, как показано в следующем примере: 

```PowerShell
Set-CsUserCallingSettings -Identity user3@contoso.com -IsForwardingEnabled $true -ForwardingType Simultaneous -ForwardingTargetType MyDelegates
```

В следующем примере Set-CsUserCallingSettings для настройки группы  вызовов для пользователя4 с пользователями5 и пользователями6 в качестве участников. Все звонки участникам группы переадпределяются в том порядке, в который они определены: 

```PowerShell
$cgm = @("user5@contoso.com","user6@contoso.com")

Set-CsUserCallingSettings -Identity user4@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm

Set-CsUserCallingSettings -Identity user4@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

Дополнительные примеры см [. в примере Set-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps).

### <a name="add-a-calling-delegate-for-a-user"></a>Добавление делегата по звонкам для пользователя

Чтобы добавить пользователя2 в качестве делегата для пользователя1 со всеми разрешенными разрешениями, используйте New-CsUserCallingDelegate, как показано в следующем примере: 

```PowerShell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

### <a name="change-calling-delegate-permissions"></a>Изменение разрешений делегирования звонков

Чтобы изменить разрешения представителя (например, чтобы пользователь2 не мог звонить пользователю1), используйте Set-CsUserCallingDelegate, как показано в следующем примере: 

```PowerShell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

### <a name="remove-a-calling-delegate-for-a-user"></a>Удаление делегата по звонкам для пользователя

Чтобы удалить пользователя2 в качестве делегата для пользователя1, используйте Remove-CsUserCallingDelegate, как показано в следующем примере: 

```PowerShell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```


## <a name="related-topics"></a>См. также

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps) 

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings?view=teams-ps) 

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate?view=teams-ps) 

-   [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate?view=teams-ps) 

-   [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate?view=teams-ps) 
