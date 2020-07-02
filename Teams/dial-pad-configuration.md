---
title: Настройка панели набора номера в Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: Узнайте, как настроить панель набора номера в клиенте Teams, чтобы пользователи могли получать доступ к функциям коммутируемой телефонной сети.
ms.openlocfilehash: 44fcbb766cadaa4b31aa065fae80fdcd48c5453f
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012424"
---
# <a name="dial-pad-configuration"></a>Настройка панели набора номера

В клиенте Teams панель набора номера позволяет пользователям получить доступ к функциям общественной коммутируемой телефонной сети (PSTN). Панель набора номера доступна для пользователей с лицензией на телефонную систему при условии, что они настроены должным образом. Для набора номера должны отображаться следующие условия:

- У пользователя есть лицензия на доступ к телефонной системе ("MCOEV")
- У пользователя есть план звонков (Майкрософт) или включена прямая маршрутизация
- Для пользователя включена Корпоративная голосовая связь
- Пользователь подключен к Интернету, а не в Skype для бизнеса в локальной среде
- У пользователя включена политика вызова Teams

В следующих разделах описано, как использовать PowerShell для проверки условий. В большинстве случаев необходимо просмотреть различные свойства в выходных данных командлета Get-CsOnlineUser. В примерах предполагается, что $user является либо адресом участника-пользователя, либо SIP.

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>У пользователя есть лицензия на доступ к телефонной системе ("MCOEV")

Необходимо убедиться в том, что назначенный план для пользователя показывает, что для **атрибута CapabilityStatus задано значение Enabled** , а **для плана возможностей задано значение MCOEV** (лицензия на телефонную систему). Возможно, вы видите MCOEV, MCOEV1 и т. д. Все это приемлемо, пока план возможностей начинается с MCOEV.

Для проверки правильности настройки атрибутов используйте следующую команду:

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

Выходные данные будут выглядеть так, как показано ниже. Для проверки атрибутов **CapabilityStatus** и **плана возможностей** требуется только:

```
<Plan SubscribedPlanId="2f9eda01-4630-4a5c-bdb3-cf195f22d240"  
   ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
   CapabilityStatus="Enabled"  
   AssignedTimestamp="2020-04-21T18:31:13Z" 
   ServicePlanId="4828c8ec-dc2e-4779-b502-87ac9ce28ab7" 
   xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11"> 
  <Capability> 
     <Capability Plan="MCOEV" 
     xmlns="http://schemas.microsoft.com/online/MCO/2009/01"/> 
  </Capability>
</Plan>
```


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a>У пользователя есть план звонков (Майкрософт) или включена прямая маршрутизация

**Если у пользователя есть план звонков Microsoft**, необходимо убедиться, что **для атрибута CapabilityStatus задано значение Enabled**и **для этого плана возможностей задано значение MCOPSTN**. Возможно, вы видите MCOPSTN1, MCOPSTN2 и т. д. Все это приемлемо, пока план возможностей начинается с MCOPSTN.

Для проверки атрибутов используйте следующую команду:

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

Выходные данные будут выглядеть так, как показано ниже. Для проверки атрибутов **CapabilityStatus** и **плана возможностей** требуется только:

```  
<Plan SubscribedPlanId="71d1258e-a4e6-443f-884e-0f3d6f644bb1" 
ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
CapabilityStatus="Enabled"    
AssignedTimestamp="2018-09-18T18:41:42Z" 
ServicePlanId="5a10155d-f5c1-411a-a8ec-e99aae125390" 
xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11">
 <Capability>
    <Capability Plan="MCOPSTN2" 
    xmlns="http://schemas.microsoft.com/online/MCO/2009/01" />
 </Capability>
</Plan>
  ```

**Если пользователю разрешена прямая маршрутизация**, пользователю должно быть присвоено значение, отличное от NULL, для OnlineVoiceRoutingPolicy. Для проверки атрибута используйте следующую команду:
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

Результат должен иметь значение, отличное от NULL, например:

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>Для пользователя включена Корпоративная голосовая связь

Чтобы проверить, включен ли на предприятии корпоративный голосовой интерфейс, введите следующую команду:

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

Результат должен выглядеть следующим образом:

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>Пользователь подключен к Интернету, а не в Skype для бизнеса в локальной среде

Чтобы пользователь был подключен к сети, а не в Skype для бизнеса локально, RegistrarPool не должен иметь значение null, и HostingProvider должно содержать значения, начинающиеся со слова "sipfed. Online".  Для проверки значений используйте следующую команду:

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

Результат должен выглядеть примерно так:

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>У пользователя включена политика вызова Teams

У действующего TeamsCallingPolicy пользователя должно быть AllowPrivateCalling установлено значение true.  По умолчанию пользователи наследуют глобальную политику, в которой для AllowPrivateCallingPolicy установлено значение true по умолчанию.

Чтобы получить TeamsCallingPolicy для пользователя и убедиться, что для AllowPrivateCalling установлено значение true, используйте следующую команду:

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

Результат должен выглядеть следующим образом:

```
Identity                   : Global
Description                :
AllowPrivateCalling        : True
AllowWebPSTNCalling        : True
AllowVoicemail             : UserOverride
AllowCallGroups            : True
AllowDelegation            : True
AllowCallForwardingToUser  : True
AllowCallForwardingToPhone : True
PreventTollBypass          : False
BusyOnBusyEnabledType      : Disabled
MusicOnHoldEnabledType     : Enabled
``` 

## <a name="additional-notes"></a>Дополнительные заметки

-   Возможно, потребуется перезапустить клиент Teams после внесения каких – либо изменений в конфигурацию.

-   Если вы недавно обновили указанные выше условия, вам может потребоваться подождать несколько часов, пока клиент не получит новые параметры.

-   Если панель набора номера по-прежнему не отображается, проверьте, есть ли ошибки в процессе подготовки с помощью следующей команды:

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    Если вы по-прежнему не видите 24 часа, обратитесь в службу поддержки.


