---
title: Настройка панели набора номера Teams
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
description: Узнайте, как настроить панель набора номера в клиенте Teams, чтобы пользователи могли получать доступ к функциям телефонной сети общего присоединения (STN).
ms.openlocfilehash: 44fcbb766cadaa4b31aa065fae80fdcd48c5453f
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012424"
---
# <a name="dial-pad-configuration"></a>Настройка панели набора номера

В клиенте Teams панель набора номера позволяет пользователям получать доступ к функциям телефонной сети общего присоединения (STN). Панель набора номера доступна для пользователей с лицензией на телефонную систему, если они настроены правильно. Для показа панели набора номера требуются следующие условия:

- У пользователя есть лицензия на телефонную систему (MCOEV)
- У пользователя есть план звонков Майкрософт или включена прямая маршрутия
- Пользователь включил Корпоративная голосовая связь учетной записи
- Пользователь находится на веб-сайте, а не в локальной сети Skype для бизнеса
- Пользователь включил политику звонков Teams

В следующих разделах описано, как с помощью PowerShell проверить условия. В большинстве случаев необходимо искать различные свойства в результатах Get-CsOnlineUser. В примерах $user имя-пользователя или SIP-адрес пользователя.

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>У пользователя есть лицензия на телефонную систему (MCOEV)

Убедитесь, что в назначенном плане для пользователя показан атрибут **CapabilityStatus** с атрибутом Enabled, а в плане возможностей **— MCOEV** (лицензия на телефонную систему). Вы можете увидеть MCOEV, MCOEV1 и так далее. Все они допустимы, если план возможностей начинается с MCOEV.

Чтобы проверить правильность атрибутов, используйте следующую команду:

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

Результат будет выглядеть следующим образом: Вам нужно только проверить **атрибуты CapabilityStatus** и **capability Plan:**

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


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a>У пользователя включен план звонков Майкрософт ИЛИ включена прямая маршрутия

**Если у пользователя есть** план звонков Майкрософт, убедитесь, что **атрибуту CapabilityStatus** назначено "Включено" и что для плана возможностей установлено имя **MCOPSTN.** Вы можете увидеть MCOPSTN1, MCOPSTN2 и так далее. Все они являются допустимыми, если план возможностей начинается с MCOPSTN.

Чтобы проверить атрибуты, используйте следующую команду:

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

Результат будет выглядеть следующим образом: Вам нужно только проверить **атрибуты CapabilityStatus** и **capability Plan:**

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

**Если для пользователя включена** прямая маршрутизация, ему должно быть назначено ненулевое значение для OnlineVoiceRoutingPolicy. Чтобы проверить атрибут, используйте следующую команду:
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

Выходные данные должны иметь ненулевую величину, например:

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>Пользователь включил Корпоративная голосовая связь учетной записи

Чтобы проверить, включен ли Корпоративная голосовая связь, используйте следующую команду:

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

Результат должен выглядеть так:

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>Пользователь находится на веб-сайте, а не в локальной сети Skype для бизнеса

Чтобы обеспечить размещение пользователя в сети, а не локальной службы Skype для бизнеса, регистратор Не должен иметь значение NULL, а hostingProvider должен содержать значение, которое начинается с sipfed.online.  Чтобы проверить значения, используйте следующую команду:

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

Выходные данные должны быть примерно такие же:

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>Пользователь включил политику звонков Teams

Для эффективного действия пользователя TeamsCallingPolicy должно быть установлено разрешение AllowPrivateCalling на true.  По умолчанию пользователи наследуют глобальную политику, для которой значение AllowPrivateCallingPolicy по умолчанию является истинным.

Чтобы получить Для пользователя TeamsCallingPolicy и проверить, установлено ли для allowPrivateCalling истинное, используйте следующую команду:

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

Результат должен выглядеть так:

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

-   Возможно, вам потребуется перезапустить клиент Teams после внесения каких-либо из этих изменений конфигурации.

-   Если вы недавно обновили любое из этих критериев, возможно, потребуется подождать несколько часов, пока клиент получит новые параметры.

-   Если вы по-прежнему не видите панель набора номера, проверьте, нет ли ошибки в регистрации, используя следующую команду:

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    Если с этого времени больше 24 часов, но проблемы по-прежнему возникают, обратитесь в службу поддержки.


