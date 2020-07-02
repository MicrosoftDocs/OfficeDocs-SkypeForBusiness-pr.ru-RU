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
# <a name="dial-pad-configuration"></a><span data-ttu-id="45b37-103">Настройка панели набора номера</span><span class="sxs-lookup"><span data-stu-id="45b37-103">Dial pad configuration</span></span>

<span data-ttu-id="45b37-104">В клиенте Teams панель набора номера позволяет пользователям получить доступ к функциям общественной коммутируемой телефонной сети (PSTN).</span><span class="sxs-lookup"><span data-stu-id="45b37-104">In the Teams client, the dial pad enables users to access Public Switched Telephone Network (PSTN) functionality.</span></span> <span data-ttu-id="45b37-105">Панель набора номера доступна для пользователей с лицензией на телефонную систему при условии, что они настроены должным образом.</span><span class="sxs-lookup"><span data-stu-id="45b37-105">The dial pad is available for users with a Phone System license, provided they are configured properly.</span></span> <span data-ttu-id="45b37-106">Для набора номера должны отображаться следующие условия:</span><span class="sxs-lookup"><span data-stu-id="45b37-106">The following criteria are all required for the dial pad to show:</span></span>

- <span data-ttu-id="45b37-107">У пользователя есть лицензия на доступ к телефонной системе ("MCOEV")</span><span class="sxs-lookup"><span data-stu-id="45b37-107">User has an enabled Phone System (“MCOEV”) license</span></span>
- <span data-ttu-id="45b37-108">У пользователя есть план звонков (Майкрософт) или включена прямая маршрутизация</span><span class="sxs-lookup"><span data-stu-id="45b37-108">User has Microsoft Calling Plan or is enabled for Direct Routing</span></span>
- <span data-ttu-id="45b37-109">Для пользователя включена Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="45b37-109">User has Enterprise Voice enabled</span></span>
- <span data-ttu-id="45b37-110">Пользователь подключен к Интернету, а не в Skype для бизнеса в локальной среде</span><span class="sxs-lookup"><span data-stu-id="45b37-110">User is homed online and not in Skype for Business on premises</span></span>
- <span data-ttu-id="45b37-111">У пользователя включена политика вызова Teams</span><span class="sxs-lookup"><span data-stu-id="45b37-111">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="45b37-112">В следующих разделах описано, как использовать PowerShell для проверки условий.</span><span class="sxs-lookup"><span data-stu-id="45b37-112">The following sections describe how to use PowerShell to check the criteria.</span></span> <span data-ttu-id="45b37-113">В большинстве случаев необходимо просмотреть различные свойства в выходных данных командлета Get-CsOnlineUser.</span><span class="sxs-lookup"><span data-stu-id="45b37-113">In most cases, you need to look at various properties in the output of the Get-CsOnlineUser cmdlet.</span></span> <span data-ttu-id="45b37-114">В примерах предполагается, что $user является либо адресом участника-пользователя, либо SIP.</span><span class="sxs-lookup"><span data-stu-id="45b37-114">Examples assume $user is either the UPN or sip address of the user.</span></span>

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a><span data-ttu-id="45b37-115">У пользователя есть лицензия на доступ к телефонной системе ("MCOEV")</span><span class="sxs-lookup"><span data-stu-id="45b37-115">User has an enabled Phone System (“MCOEV”) license</span></span>

<span data-ttu-id="45b37-116">Необходимо убедиться в том, что назначенный план для пользователя показывает, что для **атрибута CapabilityStatus задано значение Enabled** , а **для плана возможностей задано значение MCOEV** (лицензия на телефонную систему).</span><span class="sxs-lookup"><span data-stu-id="45b37-116">You must ensure that the assigned plan for the user shows the **CapabilityStatus attribute set to Enabled** and the **Capability Plan set to MCOEV** (Phone System license).</span></span> <span data-ttu-id="45b37-117">Возможно, вы видите MCOEV, MCOEV1 и т. д.</span><span class="sxs-lookup"><span data-stu-id="45b37-117">You might see MCOEV, MCOEV1, and so on.</span></span> <span data-ttu-id="45b37-118">Все это приемлемо, пока план возможностей начинается с MCOEV.</span><span class="sxs-lookup"><span data-stu-id="45b37-118">All are acceptable--as long as the Capability Plan starts with MCOEV.</span></span>

<span data-ttu-id="45b37-119">Для проверки правильности настройки атрибутов используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="45b37-119">To check that the attributes are set correctly, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="45b37-120">Выходные данные будут выглядеть так, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="45b37-120">The output will look like the following.</span></span> <span data-ttu-id="45b37-121">Для проверки атрибутов **CapabilityStatus** и **плана возможностей** требуется только:</span><span class="sxs-lookup"><span data-stu-id="45b37-121">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

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


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a><span data-ttu-id="45b37-122">У пользователя есть план звонков (Майкрософт) или включена прямая маршрутизация</span><span class="sxs-lookup"><span data-stu-id="45b37-122">User has Microsoft Calling Plan OR is enabled for Direct Routing</span></span>

<span data-ttu-id="45b37-123">**Если у пользователя есть план звонков Microsoft**, необходимо убедиться, что **для атрибута CapabilityStatus задано значение Enabled**и **для этого плана возможностей задано значение MCOPSTN**.</span><span class="sxs-lookup"><span data-stu-id="45b37-123">**If the user has Microsoft Calling Plan**, you must ensure that the **CapabilityStatus attribute is set to Enabled**, and that the **Capability Plan is set to MCOPSTN**.</span></span> <span data-ttu-id="45b37-124">Возможно, вы видите MCOPSTN1, MCOPSTN2 и т. д.</span><span class="sxs-lookup"><span data-stu-id="45b37-124">You might see MCOPSTN1, MCOPSTN2, and so on.</span></span> <span data-ttu-id="45b37-125">Все это приемлемо, пока план возможностей начинается с MCOPSTN.</span><span class="sxs-lookup"><span data-stu-id="45b37-125">All are acceptable--as long as the Capability Plan starts with MCOPSTN.</span></span>

<span data-ttu-id="45b37-126">Для проверки атрибутов используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="45b37-126">To check the attributes, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="45b37-127">Выходные данные будут выглядеть так, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="45b37-127">The output will look like the following.</span></span> <span data-ttu-id="45b37-128">Для проверки атрибутов **CapabilityStatus** и **плана возможностей** требуется только:</span><span class="sxs-lookup"><span data-stu-id="45b37-128">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

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

<span data-ttu-id="45b37-129">**Если пользователю разрешена прямая маршрутизация**, пользователю должно быть присвоено значение, отличное от NULL, для OnlineVoiceRoutingPolicy.</span><span class="sxs-lookup"><span data-stu-id="45b37-129">**If the user is enabled for Direct Routing**, the user must be assigned a non-null value for OnlineVoiceRoutingPolicy.</span></span> <span data-ttu-id="45b37-130">Для проверки атрибута используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="45b37-130">To check the attribute, use the following command:</span></span>
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

<span data-ttu-id="45b37-131">Результат должен иметь значение, отличное от NULL, например:</span><span class="sxs-lookup"><span data-stu-id="45b37-131">The output should have a non-null value, for example:</span></span>

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a><span data-ttu-id="45b37-132">Для пользователя включена Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="45b37-132">User has Enterprise Voice enabled</span></span>

<span data-ttu-id="45b37-133">Чтобы проверить, включен ли на предприятии корпоративный голосовой интерфейс, введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="45b37-133">To check if the user has Enterprise Voice enabled, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

<span data-ttu-id="45b37-134">Результат должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="45b37-134">The output should look like:</span></span>

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a><span data-ttu-id="45b37-135">Пользователь подключен к Интернету, а не в Skype для бизнеса в локальной среде</span><span class="sxs-lookup"><span data-stu-id="45b37-135">User is homed online and not in Skype for Business on premises</span></span>

<span data-ttu-id="45b37-136">Чтобы пользователь был подключен к сети, а не в Skype для бизнеса локально, RegistrarPool не должен иметь значение null, и HostingProvider должно содержать значения, начинающиеся со слова "sipfed. Online".</span><span class="sxs-lookup"><span data-stu-id="45b37-136">To ensure the user is homed online and not in Skype for Business on premises, the RegistrarPool must not be null and the HostingProvider must contain a value that starts with “sipfed.online.”</span></span>  <span data-ttu-id="45b37-137">Для проверки значений используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="45b37-137">To check the values, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

<span data-ttu-id="45b37-138">Результат должен выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="45b37-138">The output should be similar to:</span></span>

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a><span data-ttu-id="45b37-139">У пользователя включена политика вызова Teams</span><span class="sxs-lookup"><span data-stu-id="45b37-139">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="45b37-140">У действующего TeamsCallingPolicy пользователя должно быть AllowPrivateCalling установлено значение true.</span><span class="sxs-lookup"><span data-stu-id="45b37-140">The user’s effective TeamsCallingPolicy must have AllowPrivateCalling set to true.</span></span>  <span data-ttu-id="45b37-141">По умолчанию пользователи наследуют глобальную политику, в которой для AllowPrivateCallingPolicy установлено значение true по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="45b37-141">By default, users inherit the global policy, which has AllowPrivateCallingPolicy set to true by default.</span></span>

<span data-ttu-id="45b37-142">Чтобы получить TeamsCallingPolicy для пользователя и убедиться, что для AllowPrivateCalling установлено значение true, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="45b37-142">To get the TeamsCallingPolicy for a user and to check that AllowPrivateCalling is set to true, use the following command:</span></span>

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

<span data-ttu-id="45b37-143">Результат должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="45b37-143">The output should look like:</span></span>

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

## <a name="additional-notes"></a><span data-ttu-id="45b37-144">Дополнительные заметки</span><span class="sxs-lookup"><span data-stu-id="45b37-144">Additional notes</span></span>

-   <span data-ttu-id="45b37-145">Возможно, потребуется перезапустить клиент Teams после внесения каких – либо изменений в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="45b37-145">You may need to restart the Teams client after making any of these configuration changes.</span></span>

-   <span data-ttu-id="45b37-146">Если вы недавно обновили указанные выше условия, вам может потребоваться подождать несколько часов, пока клиент не получит новые параметры.</span><span class="sxs-lookup"><span data-stu-id="45b37-146">If you recently updated any of the above criteria, you may need to wait a few hours for the client to receive the new settings.</span></span>

-   <span data-ttu-id="45b37-147">Если панель набора номера по-прежнему не отображается, проверьте, есть ли ошибки в процессе подготовки с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="45b37-147">If you still don’t see the dial pad, check if there is a provisioning error by using the following command:</span></span>

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    <span data-ttu-id="45b37-148">Если вы по-прежнему не видите 24 часа, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="45b37-148">If it has been more than 24 hours and you are still seeing problems, contact Support.</span></span>


