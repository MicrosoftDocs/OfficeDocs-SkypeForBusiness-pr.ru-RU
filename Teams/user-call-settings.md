---
title: Настройка параметров зова для пользователей
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
description: Узнайте, как настроить пользовательские параметры для переадресации и делегирования вызовов.
ms.openlocfilehash: 64907043448f44ff861ede026d0a4343899ad98b
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272234"
---
# <a name="configure-call-settings-for-your-users"></a>Настройка параметров зова для пользователей

В этой статье описывается, как администратор может изменять параметры переадресации  вызовов и делегирования для пользователей. Может потребоваться изменить эти параметры, например, если:

- Пользователь находится в неавтном отпуске, и необходимо убедиться, что входящие звонки пользователю перенаправляться коллеге.
- Необходимо проверить параметры переадресации параметров для всех пользователей в отделе и, возможно, исправить их соответствующим образом.
- На работу был нанят новый помощник, и вам нужно добавить его в качестве делегата для группы сотрудников.

Вы можете использовать Центр администрирования Teams или командлеты Teams PowerShell для просмотра и изменения параметров параметров зова для пользователей.

Чтобы задать параметры звонков для пользователя, у пользователя должна быть назначена лицензия телефонной системы Майкрософт.

## <a name="use-the-teams-admin-center"></a>Использование Центра администрирования Teams

Центр администрирования Teams можно использовать для настройки параметров переадресации и неотвеченных параметров, группового ответа на звонок и делегирования зовов для пользователей.

Чтобы настроить параметры прямого переадресации параметров параметров переадресации параметров:

1. В Центре администрирования Teams перейдите в раздел **"Управление** >  пользователями **" и** выберите пользователя.

2. На странице сведений о пользователе перейдите на **вкладку "Голос** ".

3. В **разделе "Правила ответа на звонок**" выберите "Сразу **переадресация**" и выберите соответствующий тип и назначение переадресации зова.

Чтобы настроить одновременный звонок, на той же странице выберите **"Позвонить устройствам пользователя"**. В **раскрывающемся списке "Также разрешить** " выберите соответствующий параметр одновременного звонка.

Чтобы настроить неотвеченные параметры, на той же странице выберите соответствующий параметр в раскрывающемся списке **"Если без** ответа". В **круге за это много секунд перед** перенаправлением раскрывающегося списка укажите время ожидания в секундах.

Конфигурация делегирования вызовов и группового ответа на вызовы интегрируются в параметры переадресации вызовов и неотвеченные параметры, выбрав соответствующий тип. Например, чтобы настроить, что вызовы также должны звонить делегатам пользователя, на той же странице выберите "Делегирование вызовов **" в** разделе **"Также разрешить"**. Затем добавьте соответствующих делегатов, нажав кнопку **"** Добавить людей" и нажав кнопку **"Сохранить"**.

## <a name="use-powershell"></a>Использование PowerShell

С помощью PowerShell можно настроить параметры переадресации и делегирования параметров для пользователей.  Вы будете использовать следующие командлеты, доступные в модуле Teams PowerShell версии 4.0 или более поздней:

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings) — отображает параметры переадресации звонков, делегаты и сведения о делегировании для пользователя.
- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings) — задает параметры переадресации вызовов для пользователя.
- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate) — добавляет новый делегат с разрешениями для пользователя.
- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate) — изменяет разрешения для существующего делегата.
- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate) — удаляет делегат из пользователя.

### <a name="display-call-forward-and-delegation-settings-for-a-user"></a>Отображение параметров пересылки зова и делегирования для пользователя

Чтобы отобразить текущие параметры переадресации вызовов и делегирования для пользователя, используйте командлет Get-CsUserCallingSettings, как показано в следующем примере:

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

Выходные данные показывают, что user1 имеет одновременный звонок для настроенных делегатов. Неотвеченные звонки отправляются в голосовую почту через 20 секунд. User2 определяется как делегат со всеми разрешениями делегата.

### <a name="set-call-forward-settings-for-a-user"></a>Настройка параметров переадресации зова для пользователя

Чтобы переадресовывать все вызовы user1 к user2, используйте Set-CsUserCallingSettings, как показано в следующем примере:

```PowerShell
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType SingleTarget -ForwardingTarget user2@contoso.com
```

Чтобы одновременно звонить всем делегатам для user3, используйте командлет Set-CsUserCallingSettings, как показано в следующем примере:

```PowerShell
Set-CsUserCallingSettings -Identity user3@contoso.com -IsForwardingEnabled $true -ForwardingType Simultaneous -ForwardingTargetType MyDelegates
```

В следующем примере Set-CsUserCallingSettings командлет для настройки группы вызовов для user4 с user5 и user6 в качестве участников. Все вызовы членов группы переадресуются в том порядке, в котором они определены:

```PowerShell
$cgm = @("user5@contoso.com","user6@contoso.com")

Set-CsUserCallingSettings -Identity user4@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm

Set-CsUserCallingSettings -Identity user4@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

Дополнительные примеры см. в [разделе Set-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings).

### <a name="add-a-calling-delegate-for-a-user"></a>Добавление вызывающего делегата для пользователя

Чтобы добавить user2 в качестве делегата для user1 со всеми разрешенными разрешениями, используйте командлет New-CsUserCallingDelegate, как показано в следующем примере:

```PowerShell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

### <a name="change-calling-delegate-permissions"></a>Изменение разрешений делегата вызова

Чтобы изменить разрешения делегата (например, чтобы не разрешать пользователю User2 совершать вызовы для user1), используйте командлет Set-CsUserCallingDelegate, как показано в следующем примере:

```PowerShell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

### <a name="remove-a-calling-delegate-for-a-user"></a>Удаление вызывающего делегата для пользователя

Чтобы удалить user2 в качестве делегата для user1, используйте командлет Remove-CsUserCallingDelegate, как показано в следующем примере:

```PowerShell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```

## <a name="related-topics"></a>Статьи по теме

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings)
- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings)
- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate)
- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate)
- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate)
