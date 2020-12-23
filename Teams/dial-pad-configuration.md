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
# <a name="dial-pad-configuration"></a><span data-ttu-id="3d763-103">Настройка панели набора номера</span><span class="sxs-lookup"><span data-stu-id="3d763-103">Dial pad configuration</span></span>

<span data-ttu-id="3d763-104">В клиенте Teams панель набора номера позволяет пользователям получать доступ к функциям телефонной сети общего присоединения (STN).</span><span class="sxs-lookup"><span data-stu-id="3d763-104">In the Teams client, the dial pad enables users to access Public Switched Telephone Network (PSTN) functionality.</span></span> <span data-ttu-id="3d763-105">Панель набора номера доступна для пользователей с лицензией на телефонную систему, если они настроены правильно.</span><span class="sxs-lookup"><span data-stu-id="3d763-105">The dial pad is available for users with a Phone System license, provided they are configured properly.</span></span> <span data-ttu-id="3d763-106">Для показа панели набора номера требуются следующие условия:</span><span class="sxs-lookup"><span data-stu-id="3d763-106">The following criteria are all required for the dial pad to show:</span></span>

- <span data-ttu-id="3d763-107">У пользователя есть лицензия на телефонную систему (MCOEV)</span><span class="sxs-lookup"><span data-stu-id="3d763-107">User has an enabled Phone System (“MCOEV”) license</span></span>
- <span data-ttu-id="3d763-108">У пользователя есть план звонков Майкрософт или включена прямая маршрутия</span><span class="sxs-lookup"><span data-stu-id="3d763-108">User has Microsoft Calling Plan or is enabled for Direct Routing</span></span>
- <span data-ttu-id="3d763-109">Пользователь включил Корпоративная голосовая связь учетной записи</span><span class="sxs-lookup"><span data-stu-id="3d763-109">User has Enterprise Voice enabled</span></span>
- <span data-ttu-id="3d763-110">Пользователь находится на веб-сайте, а не в локальной сети Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3d763-110">User is homed online and not in Skype for Business on premises</span></span>
- <span data-ttu-id="3d763-111">Пользователь включил политику звонков Teams</span><span class="sxs-lookup"><span data-stu-id="3d763-111">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="3d763-112">В следующих разделах описано, как с помощью PowerShell проверить условия.</span><span class="sxs-lookup"><span data-stu-id="3d763-112">The following sections describe how to use PowerShell to check the criteria.</span></span> <span data-ttu-id="3d763-113">В большинстве случаев необходимо искать различные свойства в результатах Get-CsOnlineUser.</span><span class="sxs-lookup"><span data-stu-id="3d763-113">In most cases, you need to look at various properties in the output of the Get-CsOnlineUser cmdlet.</span></span> <span data-ttu-id="3d763-114">В примерах $user имя-пользователя или SIP-адрес пользователя.</span><span class="sxs-lookup"><span data-stu-id="3d763-114">Examples assume $user is either the UPN or sip address of the user.</span></span>

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a><span data-ttu-id="3d763-115">У пользователя есть лицензия на телефонную систему (MCOEV)</span><span class="sxs-lookup"><span data-stu-id="3d763-115">User has an enabled Phone System (“MCOEV”) license</span></span>

<span data-ttu-id="3d763-116">Убедитесь, что в назначенном плане для пользователя показан атрибут **CapabilityStatus** с атрибутом Enabled, а в плане возможностей **— MCOEV** (лицензия на телефонную систему).</span><span class="sxs-lookup"><span data-stu-id="3d763-116">You must ensure that the assigned plan for the user shows the **CapabilityStatus attribute set to Enabled** and the **Capability Plan set to MCOEV** (Phone System license).</span></span> <span data-ttu-id="3d763-117">Вы можете увидеть MCOEV, MCOEV1 и так далее.</span><span class="sxs-lookup"><span data-stu-id="3d763-117">You might see MCOEV, MCOEV1, and so on.</span></span> <span data-ttu-id="3d763-118">Все они допустимы, если план возможностей начинается с MCOEV.</span><span class="sxs-lookup"><span data-stu-id="3d763-118">All are acceptable--as long as the Capability Plan starts with MCOEV.</span></span>

<span data-ttu-id="3d763-119">Чтобы проверить правильность атрибутов, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3d763-119">To check that the attributes are set correctly, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="3d763-120">Результат будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3d763-120">The output will look like the following.</span></span> <span data-ttu-id="3d763-121">Вам нужно только проверить **атрибуты CapabilityStatus** и **capability Plan:**</span><span class="sxs-lookup"><span data-stu-id="3d763-121">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

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


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a><span data-ttu-id="3d763-122">У пользователя включен план звонков Майкрософт ИЛИ включена прямая маршрутия</span><span class="sxs-lookup"><span data-stu-id="3d763-122">User has Microsoft Calling Plan OR is enabled for Direct Routing</span></span>

<span data-ttu-id="3d763-123">**Если у пользователя есть** план звонков Майкрософт, убедитесь, что **атрибуту CapabilityStatus** назначено "Включено" и что для плана возможностей установлено имя **MCOPSTN.**</span><span class="sxs-lookup"><span data-stu-id="3d763-123">**If the user has Microsoft Calling Plan**, you must ensure that the **CapabilityStatus attribute is set to Enabled**, and that the **Capability Plan is set to MCOPSTN**.</span></span> <span data-ttu-id="3d763-124">Вы можете увидеть MCOPSTN1, MCOPSTN2 и так далее.</span><span class="sxs-lookup"><span data-stu-id="3d763-124">You might see MCOPSTN1, MCOPSTN2, and so on.</span></span> <span data-ttu-id="3d763-125">Все они являются допустимыми, если план возможностей начинается с MCOPSTN.</span><span class="sxs-lookup"><span data-stu-id="3d763-125">All are acceptable--as long as the Capability Plan starts with MCOPSTN.</span></span>

<span data-ttu-id="3d763-126">Чтобы проверить атрибуты, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3d763-126">To check the attributes, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="3d763-127">Результат будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3d763-127">The output will look like the following.</span></span> <span data-ttu-id="3d763-128">Вам нужно только проверить **атрибуты CapabilityStatus** и **capability Plan:**</span><span class="sxs-lookup"><span data-stu-id="3d763-128">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

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

<span data-ttu-id="3d763-129">**Если для пользователя включена** прямая маршрутизация, ему должно быть назначено ненулевое значение для OnlineVoiceRoutingPolicy.</span><span class="sxs-lookup"><span data-stu-id="3d763-129">**If the user is enabled for Direct Routing**, the user must be assigned a non-null value for OnlineVoiceRoutingPolicy.</span></span> <span data-ttu-id="3d763-130">Чтобы проверить атрибут, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3d763-130">To check the attribute, use the following command:</span></span>
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

<span data-ttu-id="3d763-131">Выходные данные должны иметь ненулевую величину, например:</span><span class="sxs-lookup"><span data-stu-id="3d763-131">The output should have a non-null value, for example:</span></span>

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a><span data-ttu-id="3d763-132">Пользователь включил Корпоративная голосовая связь учетной записи</span><span class="sxs-lookup"><span data-stu-id="3d763-132">User has Enterprise Voice enabled</span></span>

<span data-ttu-id="3d763-133">Чтобы проверить, включен ли Корпоративная голосовая связь, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3d763-133">To check if the user has Enterprise Voice enabled, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

<span data-ttu-id="3d763-134">Результат должен выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="3d763-134">The output should look like:</span></span>

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a><span data-ttu-id="3d763-135">Пользователь находится на веб-сайте, а не в локальной сети Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3d763-135">User is homed online and not in Skype for Business on premises</span></span>

<span data-ttu-id="3d763-136">Чтобы обеспечить размещение пользователя в сети, а не локальной службы Skype для бизнеса, регистратор Не должен иметь значение NULL, а hostingProvider должен содержать значение, которое начинается с sipfed.online.</span><span class="sxs-lookup"><span data-stu-id="3d763-136">To ensure the user is homed online and not in Skype for Business on premises, the RegistrarPool must not be null and the HostingProvider must contain a value that starts with “sipfed.online.”</span></span>  <span data-ttu-id="3d763-137">Чтобы проверить значения, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3d763-137">To check the values, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

<span data-ttu-id="3d763-138">Выходные данные должны быть примерно такие же:</span><span class="sxs-lookup"><span data-stu-id="3d763-138">The output should be similar to:</span></span>

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a><span data-ttu-id="3d763-139">Пользователь включил политику звонков Teams</span><span class="sxs-lookup"><span data-stu-id="3d763-139">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="3d763-140">Для эффективного действия пользователя TeamsCallingPolicy должно быть установлено разрешение AllowPrivateCalling на true.</span><span class="sxs-lookup"><span data-stu-id="3d763-140">The user’s effective TeamsCallingPolicy must have AllowPrivateCalling set to true.</span></span>  <span data-ttu-id="3d763-141">По умолчанию пользователи наследуют глобальную политику, для которой значение AllowPrivateCallingPolicy по умолчанию является истинным.</span><span class="sxs-lookup"><span data-stu-id="3d763-141">By default, users inherit the global policy, which has AllowPrivateCallingPolicy set to true by default.</span></span>

<span data-ttu-id="3d763-142">Чтобы получить Для пользователя TeamsCallingPolicy и проверить, установлено ли для allowPrivateCalling истинное, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3d763-142">To get the TeamsCallingPolicy for a user and to check that AllowPrivateCalling is set to true, use the following command:</span></span>

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

<span data-ttu-id="3d763-143">Результат должен выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="3d763-143">The output should look like:</span></span>

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

## <a name="additional-notes"></a><span data-ttu-id="3d763-144">Дополнительные заметки</span><span class="sxs-lookup"><span data-stu-id="3d763-144">Additional notes</span></span>

-   <span data-ttu-id="3d763-145">Возможно, вам потребуется перезапустить клиент Teams после внесения каких-либо из этих изменений конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3d763-145">You may need to restart the Teams client after making any of these configuration changes.</span></span>

-   <span data-ttu-id="3d763-146">Если вы недавно обновили любое из этих критериев, возможно, потребуется подождать несколько часов, пока клиент получит новые параметры.</span><span class="sxs-lookup"><span data-stu-id="3d763-146">If you recently updated any of the above criteria, you may need to wait a few hours for the client to receive the new settings.</span></span>

-   <span data-ttu-id="3d763-147">Если вы по-прежнему не видите панель набора номера, проверьте, нет ли ошибки в регистрации, используя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3d763-147">If you still don’t see the dial pad, check if there is a provisioning error by using the following command:</span></span>

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    <span data-ttu-id="3d763-148">Если с этого времени больше 24 часов, но проблемы по-прежнему возникают, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="3d763-148">If it has been more than 24 hours and you are still seeing problems, contact Support.</span></span>


