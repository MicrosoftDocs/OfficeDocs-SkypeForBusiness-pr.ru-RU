---
title: Настройка параметров вызова для пользователей
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
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
description: Узнайте, как настроить параметры пользователя для переадресации и делегирования вызовов.
ms.openlocfilehash: 7d1ab3252461d57a99956c90a011a43620c76bea
ms.sourcegitcommit: 18e66d54a9e349d4516253addc85cc12892c69a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2022
ms.locfileid: "68851850"
---
# <a name="configure-call-settings-for-your-users"></a>Настройка параметров вызова для пользователей

В этой статье описывается, как администратор может изменить параметры переадресации и делегирования вызовов для пользователей. Вы можете изменить эти параметры, например, если:

- Пользователь находится в отпуске по болезни, и вам нужно убедиться, что входящие звонки пользователю перенаправляются коллеге.
- Необходимо проверить параметры переадресации звонков для всех пользователей в отделе и, возможно, исправить их соответствующим образом.
- Был нанят новый помощник, и вам нужно добавить помощника в качестве делегата для группы сотрудников.

Вы можете использовать Центр администрирования Teams или командлеты Teams PowerShell для просмотра и изменения параметров звонков для пользователей.

Чтобы задать параметры звонка для пользователя, у пользователя должна быть назначена лицензия на телефонную систему Майкрософт.

## <a name="use-the-teams-admin-center"></a>Использование Центра администрирования Teams

Вы можете использовать Центр администрирования Teams для настройки параметров переадресации и без ответа, группового приема звонков и делегирования звонков для пользователей.

Чтобы настроить параметры немедленной переадресации звонков, выполните следующие действия.

1. В Центре администрирования Teams перейдите в раздел **Пользователи** > **Управление пользователями** и выберите пользователя.

2. На странице сведений о пользователе перейдите на вкладку **Голос** .

3. В разделе **Правила ответов на вызовы** выберите **Быть немедленно переадресованным** и выберите соответствующий тип и назначение переадресации звонков.

Чтобы настроить одновременный звонок, на той же странице выберите **Позвонить устройствам пользователя**. В раскрывающемся списке **Также разрешить** выберите соответствующий параметр одновременных звонков.

Чтобы настроить параметры без ответа, на той же странице выберите соответствующий параметр в раскрывающемся списке **Если без ответа** . В раскрывающемся списке **Круг для этого количества секунд перед перенаправлением** укажите количество секунд ожидания.

Конфигурация делегирования вызовов и группового приема звонков интегрируются в параметры переадресации и без ответа путем выбора соответствующего типа. Например, чтобы настроить, что вызовы также должны вызывать делегатов пользователя, на той же странице выберите **Делегирование вызовов** в разделе **Также разрешить**. Затем добавьте соответствующих делегатов, выбрав **Добавить пользователей** и нажав кнопку **Сохранить**.

В этом видео показано, как просмотреть и изменить параметры голоса для пользователя.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE546F7?autoplay=false]

## <a name="use-powershell"></a>Использование PowerShell

PowerShell можно использовать для настройки параметров переадресации звонков и делегирования для пользователей.  Вы будете использовать следующие командлеты, доступные в модуле Teams PowerShell версии 4.0 или более поздней:

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings) — показывает параметры переадресации вызовов, делегаты и сведения о делегировании для пользователя.
- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings) — задает параметры переадресации вызовов для пользователя.
- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate) — добавляет новый делегат с разрешениями для пользователя.
- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate) — изменяет разрешения для существующего делегата.
- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate) — удаляет делегат от пользователя.

### <a name="display-call-forward-and-delegation-settings-for-a-user"></a>Отображение параметров переадресации звонков и делегирования для пользователя

Чтобы отобразить текущие параметры переадресации и делегирования для пользователя, используйте командлет Get-CsUserCallingSettings, как показано в следующем примере:

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
Delegates                 : Id:sip:user2@contoso.com
Delegators                :
CallGroupOrder            : InOrder
CallGroupTargets          : {}
GroupMembershipDetails    :
GroupNotificationOverride : Ring

(Get-CsUserCallingSettings -Identity user1@contoso.com).Delegates

Id             : sip:user2@contoso.com
MakeCalls      : True
ManageSettings : True
ReceiveCalls   : True
```

В выходных данных показано, что пользователь user1 имеет настроенный одновременный звонок для делегатов. Неотвеченные звонки отправляются на голосовую почту через 20 секунд. Пользователь 2 определяется как делегат со всеми разрешениями делегата.

### <a name="set-call-forward-settings-for-a-user"></a>Настройка параметров переадресации звонков для пользователя

Чтобы перенаправить все вызовы user1 в user2, используйте командлет Set-CsUserCallingSettings, как показано в следующем примере:

```PowerShell
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType SingleTarget -ForwardingTarget user2@contoso.com
```

Чтобы одновременно позвонить всем делегатам для user3, используйте командлет Set-CsUserCallingSettings, как показано в следующем примере:

```PowerShell
Set-CsUserCallingSettings -Identity user3@contoso.com -IsForwardingEnabled $true -ForwardingType Simultaneous -ForwardingTargetType MyDelegates
```

В следующем примере командлет Set-CsUserCallingSettings используется для настройки группы вызовов для user4 с user5 и user6 в качестве участников. Все вызовы членам группы перенаправляются в определенном порядке:

```PowerShell
$cgm = @("user5@contoso.com","user6@contoso.com")

Set-CsUserCallingSettings -Identity user4@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm

Set-CsUserCallingSettings -Identity user4@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

Дополнительные примеры см. в разделе [Set-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings).

### <a name="add-a-calling-delegate-for-a-user"></a>Добавление вызывающего делегата для пользователя

Чтобы добавить user2 в качестве делегата для user1 со всеми разрешенными разрешениями, используйте командлет New-CsUserCallingDelegate, как показано в следующем примере:

```PowerShell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

### <a name="change-calling-delegate-permissions"></a>Изменение разрешений делегата вызова

Чтобы изменить разрешения делегата( например, чтобы запретить пользователю user2 совершать вызовы для user1), используйте командлет Set-CsUserCallingDelegate, как показано в следующем примере:

```PowerShell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

### <a name="remove-a-calling-delegate-for-a-user"></a>Удаление вызывающего делегата для пользователя

Чтобы удалить user2 в качестве делегата для user1, используйте командлет Remove-CsUserCallingDelegate, как показано в следующем примере:

```PowerShell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```

## <a name="additional-notes"></a>Дополнительные примечания

- Поведение по умолчанию для пользователя, у которого никогда не были изменены правила ответа на вызовы пользователем или администратором клиента, состоит в том, что неотвеченные вызовы перенаправляются в голосовую почту через 30 секунд. Параметры, отображаемые для пользователя в Центре team Администратор или Teams PowerShell, будут отображаться без ответа целевой объект как нет и задержка в 20 секунд.

## <a name="related-topics"></a>См. также

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings)
- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings)
- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate)
- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate)
- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate)
