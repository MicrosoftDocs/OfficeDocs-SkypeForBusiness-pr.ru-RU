---
title: Создание политик местоположения в Skype для бизнеса Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
description: Прочтите сведения о настройке политик расположения экстренных служб (E9-1-1) в Скайп enhanced Business Server корпоративной голосовой связи.
ms.openlocfilehash: 7635199810e21f33bdbe30d5bf6f229987fa8c77
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="create-location-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="89c53-103">Создание политик местоположения в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="89c53-103">Create location policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="89c53-104">Прочтите сведения о настройке политик расположения экстренных служб (E9-1-1) в Скайп enhanced Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="89c53-104">Read this topic to learn how to configure enhanced emergency service (E9-1-1) location policies in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="89c53-105">Скайп для Business Server использует политику расположения для включения Скайп пользователей для E9-1-1 во время регистрации клиента.</span><span class="sxs-lookup"><span data-stu-id="89c53-105">Skype for Business Server uses a location policy to enable Skype for Business clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="89c53-106">Политика расположения содержит параметры, которые определяют порядок реализации E911.</span><span class="sxs-lookup"><span data-stu-id="89c53-106">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span> <span data-ttu-id="89c53-107">Дополнительные сведения содержатся в разделе [планирование политики расположения для Скайп для Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="89c53-107">For more information, see [Plan location policies for Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span>
  
<span data-ttu-id="89c53-108">Вы задаете политики расположения с помощью Скайп для панели управления бизнеса или с помощью командлета [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="89c53-108">You define location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="89c53-109">Скайп для Business Server теперь поддерживает конфигурации нескольких аварийного номера для клиента.</span><span class="sxs-lookup"><span data-stu-id="89c53-109">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="89c53-110">Если вы хотите настроить несколько аварийного номера, необходимо выполнить сведения в [Планирование нескольких аварийного номера в Скайп для Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) и [настроить несколько аварийного номера в Скайп для бизнеса 2015](configure-multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="89c53-110">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business 2015](configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="89c53-p103">Глобальную политику расположения можно редактировать, кроме того, можно создавать новые именованные политики расположения. Клиент получает глобальную политику, если он расположен не в подсети, для которой имеется связанная локальная политика, или если локальная политика не назначена ему напрямую. Именованные политики назначаются подсетям или пользователям.  </span><span class="sxs-lookup"><span data-stu-id="89c53-p103">You can edit the global location policy and create new tagged location policies. A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy. Tagged policies are assigned to subnets or users.</span></span> 
  
<span data-ttu-id="89c53-114">Чтобы создать политику расположения, следует использовать учетную запись, являющуюся членом группы RTCUniversalServerAdmins или административной роли CsVoiceAdministrator или обладает эквивалентными правами и разрешениями администратора.</span><span class="sxs-lookup"><span data-stu-id="89c53-114">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>
  
<span data-ttu-id="89c53-115">Дополнительные сведения содержатся в разделе [планирование политики расположения для Скайп для Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="89c53-115">For more information, see [Plan location policies for Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/location-policies.md).</span></span> <span data-ttu-id="89c53-116">Командлеты в этой процедуре используют заданную политику расположения и приведенные ниже значения.</span><span class="sxs-lookup"><span data-stu-id="89c53-116">Cmdlets in this procedure use a location policy defined using the following values.</span></span> <span data-ttu-id="89c53-117">Полное описание командлета параметры и значения в разделе [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="89c53-117">For a complete description of cmdlet parameters and values, see [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps).</span></span>
  
|<span data-ttu-id="89c53-118">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="89c53-118">**Element**</span></span>|<span data-ttu-id="89c53-119">**Значение**</span><span class="sxs-lookup"><span data-stu-id="89c53-119">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="89c53-120">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="89c53-120">EnhancedEmergencyServicesEnabled</span></span>  <br/> |<span data-ttu-id="89c53-121">**True**</span><span class="sxs-lookup"><span data-stu-id="89c53-121">**True**</span></span> <br/> |
|<span data-ttu-id="89c53-122">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="89c53-122">LocationRequired</span></span>  <br/> |<span data-ttu-id="89c53-123">**Заявление об отказе**</span><span class="sxs-lookup"><span data-stu-id="89c53-123">**Disclaimer**</span></span> <br/> |
|<span data-ttu-id="89c53-124">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="89c53-124">EnhancedEmergencyServiceDisclaimer</span></span>  <br/> |<span data-ttu-id="89c53-p105">Политика вашей компании требует задать расположение. В противном случае в экстренной ситуации соответствующие службы не смогут определить ваше расположение. Задайте расположение.</span><span class="sxs-lookup"><span data-stu-id="89c53-p105">Your company policy requires you to set a location. If you do not set a location, emergency services will not be able to locate you in an emergency. Please set a location.</span></span>  <br/> |
|<span data-ttu-id="89c53-128">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="89c53-128">UseLocationForE911Only</span></span>  <br/> |<span data-ttu-id="89c53-129">**False**</span><span class="sxs-lookup"><span data-stu-id="89c53-129">**False**</span></span> <br/> |
|<span data-ttu-id="89c53-130">Параметра PstnUsage</span><span class="sxs-lookup"><span data-stu-id="89c53-130">PstnUsage</span></span>  <br/> |<span data-ttu-id="89c53-131">**EmergencyUsage**</span><span class="sxs-lookup"><span data-stu-id="89c53-131">**EmergencyUsage**</span></span> <br/> |
|<span data-ttu-id="89c53-132">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="89c53-132">EmergencyDialString</span></span>  <br/> |<span data-ttu-id="89c53-133">**911**</span><span class="sxs-lookup"><span data-stu-id="89c53-133">**911**</span></span> <br/> |
|<span data-ttu-id="89c53-134">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="89c53-134">EmergencyDialMask</span></span>  <br/> |<span data-ttu-id="89c53-135">**112**</span><span class="sxs-lookup"><span data-stu-id="89c53-135">**112**</span></span> <br/> |
|<span data-ttu-id="89c53-136">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="89c53-136">NotificationUri</span></span>  <br/> |<span data-ttu-id="89c53-137">**SIP:Security@litwareinc.com**</span><span class="sxs-lookup"><span data-stu-id="89c53-137">**sip:security@litwareinc.com**</span></span> <br/> |
|<span data-ttu-id="89c53-138">URI конференции</span><span class="sxs-lookup"><span data-stu-id="89c53-138">ConferenceUri</span></span>  <br/> |<span data-ttu-id="89c53-139">**SIP:+14255550123@litwareinc.com**</span><span class="sxs-lookup"><span data-stu-id="89c53-139">**sip:+14255550123@litwareinc.com**</span></span> <br/> |
|<span data-ttu-id="89c53-140">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="89c53-140">ConferenceMode</span></span>  <br/> |<span data-ttu-id="89c53-141">**twoway**</span><span class="sxs-lookup"><span data-stu-id="89c53-141">**twoway**</span></span> <br/> |
|<span data-ttu-id="89c53-142">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="89c53-142">LocationRefreshInterval</span></span>  <br/> |<span data-ttu-id="89c53-143">**2**</span><span class="sxs-lookup"><span data-stu-id="89c53-143">**2**</span></span> <br/> |
   
### <a name="to-create-location-policies"></a><span data-ttu-id="89c53-144">Создание политик расположения</span><span class="sxs-lookup"><span data-stu-id="89c53-144">To create location policies</span></span>

1. <span data-ttu-id="89c53-145">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="89c53-145">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="89c53-146">Командлет CsLocationPolicy завершится с ошибкой, если значение для параметра **PstnUsage** не будет содержаться в глобальном списке параметров PstnUsage.</span><span class="sxs-lookup"><span data-stu-id="89c53-146">CsLocationPolicy will fail if the setting for **PstnUsage** is not already in the Global list of PstnUsages.</span></span>
  
2. <span data-ttu-id="89c53-147">Чтобы изменить глобальную политику расположения, можно дополнительно выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="89c53-147">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>
    
   ```
   Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

   ```

3. <span data-ttu-id="89c53-148">Выполните следующие действия, чтобы создать именованную политику расположения.</span><span class="sxs-lookup"><span data-stu-id="89c53-148">Run the following to create a tagged Location Policy.</span></span>
    
   ```
   New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

   ```

4. <span data-ttu-id="89c53-149">Выполните следующий командлет, чтобы применить именованную политику расположения, созданную в шаге 3, к политике пользователя.</span><span class="sxs-lookup"><span data-stu-id="89c53-149">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>
    
   ```
   (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond
   ```


