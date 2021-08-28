---
title: Teams набора номера
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: Узнайте, как настроить панель набора номера в клиенте Teams, чтобы пользователи могли получать доступ к функциям телефонной сети общего присоединения.
ms.openlocfilehash: 6f67aeda059505ec5c1e78d117407f0e9703f732
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627621"
---
# <a name="dial-pad-configuration"></a>Настройка панели набора номера

В клиенте Teams панель набора номера позволяет пользователям получать доступ к функциям телефонной сети общего присоединения (STN). Панель набора номера доступна для пользователей с телефонная система, если они настроены правильно. Для показа панели набора номера необходимы следующие условия:

- У пользователя есть включенная телефонная система "MCOEV".
- У пользователя есть план звонков Майкрософт или включена прямая маршрутия
- Пользователь включил Корпоративная голосовая связь
- Пользователь находится в Интернете, а не в локальной Skype для бизнеса.
- Для пользователя включена Teams звонков

В следующих разделах описано, как проверить условия с помощью PowerShell. В большинстве случаев необходимо посмотреть на различные свойства в результатах Get-CsOnlineUser. В примерах $user имя-имя пользователя или SIP-адрес пользователя.

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>У пользователя есть включенная телефонная система "MCOEV".

Убедитесь, что в назначенном плане для пользователя для атрибута **CapabilityStatus** заказано имя Enabled, а для плана возможностей — **MCOEV** (телефонная система лицензия). Вы можете увидеть MCOEV, MCOEV1 и другие. Все это допустимо, если план возможностей начинается с MCOEV.

Чтобы проверить правильность атрибутов, воспользуйтесь следующей командой:

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

Результат будет выглядеть следующим образом: Вам нужно только проверить **атрибуты CapabilityStatus** и **Capability Plan:**

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

Если у пользователя есть план звонков **(Майкрософт),** убедитесь, что для атрибута **CapabilityStatus** за установлено имя Enabled (Включено), а для плана возможностей — **MCOPSTN ( MCOPSTN).** Вы можете увидеть MCOPSTN1, MCOPSTN2 и другие. Все они допустимы, если план возможностей начинается с MCOPSTN.

Чтобы проверить атрибуты, используйте следующую команду:

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

Результат будет выглядеть следующим образом: Вам нужно только проверить **атрибуты CapabilityStatus** и **Capability Plan:**

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

**Если для пользователя включена** прямая маршрутизация, ему должно быть назначено ненулевую стоимость для OnlineVoiceRoutingPolicy. Чтобы проверить атрибут, используйте следующую команду:
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

Выходные данные должны иметь ненулевую величину, например:

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a>Пользователь включил Корпоративная голосовая связь

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
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>Пользователь находится в Интернете, а не в локальной Skype для бизнеса.

Чтобы гарантировать, что пользователь размещен в Интернете, а не в локальной Skype для бизнеса, registrarPool не должен иметь значение NULL, а HostingProvider должен содержать значение, которое начинается с sipfed.online.  Чтобы проверить значения, используйте следующую команду:

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

Результат должен быть примерно таким:

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>Для пользователя включена Teams звонков

Для эффективной работы пользователя в TeamsCallingPolicy должно быть установлено разрешение AllowPrivateCalling на true.  По умолчанию пользователи наследуют глобальную политику, для которой по умолчанию за установлено значение AllowPrivateCallingPolicy true.

Чтобы получить TeamsCallingPolicy для пользователя и проверить, что для allowPrivateCalling за установлено true, используйте следующую команду:

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

-   После внесения каких-либо изменений конфигурации может потребоваться перезапустить Teams клиента.

-   Если вы недавно обновили любое из этих критериев, может потребоваться подождать несколько часов, пока клиент получит новые параметры.

-   Если вы по-прежнему не видите панель набора номера, проверьте, нет ли ошибки при подготовкае, используя следующую команду:

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    Если на это время было больше 24 часов и проблемы по-прежнему возникают, обратитесь в службу поддержки.


