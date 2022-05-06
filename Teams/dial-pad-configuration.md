---
title: Teams конфигурации панели набора номера
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
description: Узнайте, как настроить панель набора номера в клиенте Teams, чтобы пользователи могли получить доступ к функциям телефонной сети общего пользования (ТСОП).
ms.openlocfilehash: 7fc2622ce0fda97ce608e13d67ff786431a30aa5
ms.sourcegitcommit: 140c34f20f9cd48d7180ff03fddd60f5d1d3459f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2022
ms.locfileid: "65248931"
---
# <a name="dial-pad-configuration"></a>Конфигурация панели набора номера

В Teams клиенте панель набора номера позволяет пользователям получать доступ к функциям телефонной сети общего пользования (ТСОП). Панель набора номера доступна для пользователей с телефонная система лицензией при условии, что они настроены правильно. Для отображения панели набора номера требуются следующие критерии:

- У пользователя есть включенная телефонная система (MCOEV).
- У пользователя есть план звонков Майкрософт, Operator Connect или включена прямая маршрутизация
- Пользователь включил Корпоративная голосовая связь
- Пользователь размещен в Сети, а не Skype для бизнеса локально
- Пользователь включил Teams звонков

В следующих разделах описывается, как использовать PowerShell для проверки критериев. В большинстве случаев необходимо просмотреть различные свойства в выходных данных Get-CsOnlineUser командлета. В примерах $user имя участника-пользователя или SIP-адрес пользователя.

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a>У пользователя есть включенная телефонная система (MCOEV).

Убедитесь, что назначенный план для пользователя отображает атрибут **CapabilityStatus**, для которого задано значение "Включено", а для параметра "Возможность" — **значение MCOEV** (телефонная система лицензия). Вы можете увидеть MCOEV, MCOEV1 и т. д. Все они допустимы, если возможность начинается с MCOEV.

Чтобы убедиться, что атрибуты задано правильно, используйте следующую команду:

```
(Get-CsOnlineUser -Identity $user).AssignedPlan
```

Выходные данные будут выглядеть следующим образом. Вам нужно только проверить **CapabilityStatus** и **атрибуты capability** :

```
AssignedTimestamp   Capability      CapabilityStatus ServiceInstance                          ServicePlanId
-----------------   ----------      ---------------- ---------------                          -------------
07-02-2020 12:28:48 MCOEV           Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 4828c8ec-dc2e-4779-b502-…
07-02-2020 12:28:48 Teams           Enabled          TeamspaceAPI/NA001                       57ff2da0-773e-42df-b2af-…
```


## <a name="user-has-microsoft-calling-plan-operator-connect-or-is-enabled-for-direct-routing"></a>У пользователя есть план звонков Майкрософт, Operator Connect OR включена прямая маршрутизация

**Если у пользователя есть** план звонков Майкрософт, убедитесь, что для атрибута **CapabilityStatus** задано значение Enabled и что для параметра **Capability задано значение MCOPSTN**. Вы можете увидеть MCOPSTN1, MCOPSTN2 и т. д. Все они допустимы, если возможность начинается с MCOPSTN.

Чтобы проверить атрибуты, используйте следующую команду:

```
(Get-CsOnlineUser -Identity $user).AssignedPlan
```

Выходные данные будут выглядеть следующим образом. Вам нужно только проверить **CapabilityStatus** и **атрибуты capability** :

```  
AssignedTimestamp   Capability      CapabilityStatus ServiceInstance                          ServicePlanId
-----------------   ----------      ---------------- ---------------                          -------------
07-02-2020 12:28:48 MCOEV           Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 4828c8ec-dc2e-4779-b502-…
07-02-2020 12:28:48 MCOPSTN2        Enabled          MicrosoftCommunicationsOnline/NOAM-4A-S7 5a10155d-f5c1-411a-a8ec-…
07-02-2020 12:28:48 Teams           Enabled          TeamspaceAPI/NA001                       57ff2da0-773e-42df-b2af-…
```
**Если пользователь включен для** Operator Connect, он должен иметь значение, отличное от NULL, для TeamsCarrierEmergencyCallRoutingPolicy. Чтобы проверить атрибут, используйте следующую команду:
  
```
Get-CsOnlineUser -Identity $user|Select TeamsCarrierEmergencyCallRoutingPolicy
```

Выходные данные должны иметь значение, отличное от NULL, например:

```
TeamsCarrierEmergencyCallRoutingPolicy
--------------------------------------
Synergy_98d1a5cb-d3e6-4306-885e-69a95f2da5c3
```

**Если пользователь включен для** прямой маршрутизации, пользователю должно быть назначено значение, отличное от NULL, для OnlineVoiceRoutingPolicy. Чтобы проверить атрибут, используйте следующую команду:
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

Выходные данные должны иметь значение, отличное от NULL, например:

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

Выходные данные должны выглядеть следующим образом:

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a>Пользователь размещен в Сети, а не Skype для бизнеса локально

Чтобы убедиться, что пользователь размещен в сети, а не в Skype для бизнеса локально, RegistrarPool не должен иметь значение NULL, а HostingProvider должен содержать значение, которое начинается с "sipfed.online".  Чтобы проверить значения, используйте следующую команду:

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

Выходные данные должны выглядеть примерно так:

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a>Пользователь включил Teams звонков

Для действующего пользователя TeamsCallingPolicy должно быть установлено значение AllowPrivateCalling, равное true.  По умолчанию пользователи наследуют глобальную политику, для которой allowPrivateCallingPolicy по умолчанию имеет значение true.

Чтобы получить TeamsCallingPolicy для пользователя и убедиться, что параметр AllowPrivateCalling имеет значение true, используйте следующую команду:

```
if (($p=Get-CsUserPolicyAssignment -Identity $user -PolicyType TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity Global} else {Get-CsTeamsCallingPolicy -Identity $p.PolicyName}
```

Выходные данные должны выглядеть следующим образом:

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

-   Может потребоваться перезапустить клиент Teams после внесения каких-либо из этих изменений конфигурации.

-   Если вы недавно обновили любой из указанных выше условий, может потребоваться подождать несколько часов, пока клиент получит новые параметры.

-   Если панель набора номера по-прежнему не отображается, проверьте наличие ошибки подготовки с помощью следующей команды:

  ```
  Get-CsOnlineUser -Identity $user|Select UserValidationErrors
  ```

-    Если это было более 24 часов и вы по-прежнему видите проблемы, обратитесь в службу поддержки.


