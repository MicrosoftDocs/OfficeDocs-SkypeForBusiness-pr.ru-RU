---
title: Включить для пользователей прямую маршрутику
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Узнайте, как включить прямую маршрутику по системе Microsoft Phone System.
ms.openlocfilehash: 5739797649c639e3259c6972da665ae0ced4b4bf
ms.sourcegitcommit: 0a9c5c01b37a93eecc369ca0ed49ae18f6a5065b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655486"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="f2ef3-103">Включить для пользователей прямую маршрутику, голосовую и голосовую почту</span><span class="sxs-lookup"><span data-stu-id="f2ef3-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="f2ef3-104">В этой статье описано, как включить для пользователей прямую маршрутику телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="f2ef3-105">Это шаг 2 из следующих действий по настройке прямой маршрутинга:</span><span class="sxs-lookup"><span data-stu-id="f2ef3-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="f2ef3-106">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-106">Step 1.</span></span> [<span data-ttu-id="f2ef3-107">Подключение SBC к телефонной системе Майкрософт и проверка подключения</span><span class="sxs-lookup"><span data-stu-id="f2ef3-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="f2ef3-108">**Шаг 2. Включить для пользователей прямую маршрутику, голосовую и голосовую почту**   (в этой статье)</span><span class="sxs-lookup"><span data-stu-id="f2ef3-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**   (this article)</span></span>
- <span data-ttu-id="f2ef3-109">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-109">Step 3.</span></span> [<span data-ttu-id="f2ef3-110">Настройка голосовой маршрутии</span><span class="sxs-lookup"><span data-stu-id="f2ef3-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="f2ef3-111">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-111">Step 4.</span></span> [<span data-ttu-id="f2ef3-112">Перевод чисел в альтернативный формат</span><span class="sxs-lookup"><span data-stu-id="f2ef3-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="f2ef3-113">Сведения о всех шагах, необходимых для настройки прямой маршрутинга, см. в этой [ссылке.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="f2ef3-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="f2ef3-114">Когда вы будете готовы включить прямую маршрутику для пользователей, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f2ef3-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="f2ef3-115">Создайте пользователя в Microsoft 365 или Office 365 и назначьте лицензию на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="f2ef3-116">Убедитесь, что пользователь находится в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="f2ef3-117">Настройте номер телефона и в включить корпоративную голосовую и голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="f2ef3-118">Назначьте режим "Только Teams" пользователям.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="f2ef3-119">Создание пользователя и назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="f2ef3-119">Create a user and assign the license</span></span> 

<span data-ttu-id="f2ef3-120">Существует два варианта создания пользователя в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="f2ef3-121">Однако корпорация Майкрософт рекомендует использовать один из вариантов, чтобы избежать проблем с маршрутией:</span><span class="sxs-lookup"><span data-stu-id="f2ef3-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="f2ef3-122">Создайте пользователя в локальной службе Active Directory и синхронизируйте его с облаком.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="f2ef3-123">Узнайте, [как интегрировать свои локальное каталоги с Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)</span><span class="sxs-lookup"><span data-stu-id="f2ef3-123">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="f2ef3-124">Создайте пользователя непосредственно в Центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="f2ef3-125">См. ["Добавление пользователей по отдельности или массово в Microsoft 365 или Office 365 — справка для администраторов".](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</span><span class="sxs-lookup"><span data-stu-id="f2ef3-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="f2ef3-126">Если ваши системы развертывания Skype для бизнеса Online сосуществят со Skype для бизнеса 2015 или локальной службой Lync 2010 или 2013, поддерживается только создание пользователя в локальной службе Active Directory и его синхронизация с облаком (вариант 1).</span><span class="sxs-lookup"><span data-stu-id="f2ef3-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="f2ef3-127">Сведения о лицензионных требованиях см. в [лицензиях](direct-routing-plan.md#licensing-and-other-requirements) и других требованиях плана [прямой маршрутинга.](direct-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="f2ef3-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a><span data-ttu-id="f2ef3-128">Убедитесь, что пользователь находится в сети и телефонные номера не синхронизируются из локальной сети (применимо к skype для бизнеса Server Корпоративная голосовая связь пользователей, переносимых в прямую маршрутинг Teams)</span><span class="sxs-lookup"><span data-stu-id="f2ef3-128">Ensure that the user is homed online and phone number is not being synced from on-premises (applicable for Skype for Business Server Enterprise Voice enabled users being migrated to Teams Direct Routing)</span></span>

<span data-ttu-id="f2ef3-129">Прямая маршрутная маршрутия требует, чтобы пользователь был в интернете.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-129">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="f2ef3-130">Чтобы проверить это, обратитесь к параметру RegistrarPool, который должен иметь значение в infra.lync.com домене.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span> <span data-ttu-id="f2ef3-131">Для параметра OnPremLineUriManuallySet также должно быть задано true.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-131">OnPremLineUriManuallySet parameter should also to be set to True.</span></span> <span data-ttu-id="f2ef3-132">Для этого нужно настроить номер телефона и включить корпоративную голосовую и голосовую почту с помощью Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-132">This is achieved by configuring the phone number and enable enterprise voice and voicemail using Skype for Business Online PowerShell.</span></span>

1. <span data-ttu-id="f2ef3-133">Подключите сеанс PowerShell в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-133">Connect a Skype for Business Online PowerShell session.</span></span>

2. <span data-ttu-id="f2ef3-134">Выдача команды:</span><span class="sxs-lookup"><span data-stu-id="f2ef3-134">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    <span data-ttu-id="f2ef3-135">Если для onPremLineUriManuallySet задано число False и LineUri заполнен номером <E.164>, очистите параметры с помощью локальной оболочки управления Skype для бизнеса, прежде чем настраивать номер телефона с помощью Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-135">In case OnPremLineUriManuallySet is set to False and LineUri is populated with a <E.164 phone number>, please clean the parameters using on-premises Skype for Business Management Shell, before configuring the phone number using Skype for Business Online PowerShell.</span></span> 

1. <span data-ttu-id="f2ef3-136">В командной оболочке Skype для бизнеса выдают команду:</span><span class="sxs-lookup"><span data-stu-id="f2ef3-136">From Skype for Business Management Shell issue the command:</span></span> 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   <span data-ttu-id="f2ef3-137">После синхронизации изменений с Office 365 ожидается `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` выход:</span><span class="sxs-lookup"><span data-stu-id="f2ef3-137">After the changes have synced to Office 365 the expected output of `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` would be:</span></span>

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="f2ef3-138">Настройка номера телефона и включить корпоративную голосовую и голосовую почту</span><span class="sxs-lookup"><span data-stu-id="f2ef3-138">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="f2ef3-139">После создания пользователя и назначенной лицензии необходимо настроить его номер телефона и голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-139">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="f2ef3-140">Чтобы добавить номер телефона и включить голосовую почту:</span><span class="sxs-lookup"><span data-stu-id="f2ef3-140">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="f2ef3-141">Подключите сеанс PowerShell в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-141">Connect a Skype for Business Online PowerShell session.</span></span> 

2. <span data-ttu-id="f2ef3-142">Выдача команды:</span><span class="sxs-lookup"><span data-stu-id="f2ef3-142">Issue the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    <span data-ttu-id="f2ef3-143">Например, чтобы добавить номер телефона пользователя "Низкий", введите следующее:</span><span class="sxs-lookup"><span data-stu-id="f2ef3-143">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    <span data-ttu-id="f2ef3-144">Если у пользователей "Низкий" и "Стейки Квинн" одно и то же базовое число с уникальными расширениями, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="f2ef3-144">If the users "Spencer Low" and "Stacy Quinn" share the same base number with unique extensions, enter the following</span></span>
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="f2ef3-145">Рекомендуется, но не обязательно, чтобы используемый номер телефона был настроен как полный номер телефона E.164 с кодом страны.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-145">It's recommended, but not required, that the phone number used is configured as a full E.164 phone number with country code.</span></span> <span data-ttu-id="f2ef3-146">Можно настроить номера телефонов с расширениями, которые будут использоваться для искомого пользователя, когда при подстройке для базового номера будет возвращено несколько результатов.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-146">It is supported to configure phone numbers with extensions which will be used to lookup users when the lookup against the base number returns more than one result.</span></span> <span data-ttu-id="f2ef3-147">Это позволяет компаниям настраивать номера телефонов с одинаковыми базовыми номерами и уникальными расширениями.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-147">This allows companies to configure phone numbers with the same base number and unique extensions.</span></span> <span data-ttu-id="f2ef3-148">Для успешного подстройки в приглашение должно быть включено полное число с расширением:</span><span class="sxs-lookup"><span data-stu-id="f2ef3-148">For lookup to be successful, the invite must include the full number with extension as follows:</span></span>
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > <span data-ttu-id="f2ef3-149">Если номер телефона пользователя управляется локально, настройте его с помощью локальной панели управления Skype для бизнеса или панели управления.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-149">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="f2ef3-150">Настройка отправки звонков непосредственно на голосовую почту</span><span class="sxs-lookup"><span data-stu-id="f2ef3-150">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="f2ef3-151">Прямая маршрутия позволяет прекратить звонок пользователю и отправить его непосредственно в голосовую почту пользователя.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-151">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="f2ef3-152">Если вы хотите перенаправлять звонок напрямую в голосовую почту, вложите непрозрак=app:voicemail в закавляю URI запроса.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-152">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="f2ef3-153">Например: "sip:user@yourdomain.com;opaque=app:voicemail".</span><span class="sxs-lookup"><span data-stu-id="f2ef3-153">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="f2ef3-154">В этом случае пользователь Teams не получит уведомление о вызове, звонок будет напрямую подключен к голосовой почте пользователя.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-154">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="f2ef3-155">Назначение пользователям режима "Только teams", чтобы обеспечить доступ к звонкам в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f2ef3-155">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="f2ef3-156">Прямая маршрутка требует, чтобы пользователи были в режиме "Только Teams", чтобы входящие звонки направлялись в клиент Teams.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-156">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="f2ef3-157">Чтобы перейти в режим только Teams, назначьте им экземпляр UpgradeToTeams teamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="f2ef3-157">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="f2ef3-158">Дополнительные сведения см. в [руководстве по обновлению для ИТ-администраторов.](upgrade-to-teams-on-prem-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f2ef3-158">For more information, see [Upgrade guidance for IT administrators](upgrade-to-teams-on-prem-overview.md).</span></span> <span data-ttu-id="f2ef3-159">Если в вашей организации используется Skype для бизнеса Server или Skype для бизнеса Online, см. сведения о взаимодействиях между Skype и Teams в следующей статье: перенос и взаимодействия со Skype для [бизнеса.](migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="f2ef3-159">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f2ef3-160">См. также</span><span class="sxs-lookup"><span data-stu-id="f2ef3-160">See also</span></span>

[<span data-ttu-id="f2ef3-161">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="f2ef3-161">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="f2ef3-162">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="f2ef3-162">Configure Direct Routing</span></span>](direct-routing-configure.md)
