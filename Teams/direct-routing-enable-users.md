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
description: Узнайте, как включить для Телефон (Майкрософт) прямой маршрутии Системы.
ms.openlocfilehash: 7d2b7c4b5d6268d1498a47537e0edbbf892198aa
ms.sourcegitcommit: cae94cd5761baafde51aea1137e6d164722eead9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2021
ms.locfileid: "53075372"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="54ca7-103">Включить для пользователей прямую маршрутику, голосовую и голосовую почту</span><span class="sxs-lookup"><span data-stu-id="54ca7-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="54ca7-104">В этой статье описано, как включить для телефонная система прямую маршрутику.</span><span class="sxs-lookup"><span data-stu-id="54ca7-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="54ca7-105">Это шаг 2 из следующих действий по настройке прямой маршрутии:</span><span class="sxs-lookup"><span data-stu-id="54ca7-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="54ca7-106">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="54ca7-106">Step 1.</span></span> [<span data-ttu-id="54ca7-107">Подключение SBC с Телефон (Майкрософт) и проверьте подключение</span><span class="sxs-lookup"><span data-stu-id="54ca7-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="54ca7-108">**Шаг 2. Включить для пользователей прямую маршрутику, голосовую и голосовую почту**   (эта статья)</span><span class="sxs-lookup"><span data-stu-id="54ca7-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**   (this article)</span></span>
- <span data-ttu-id="54ca7-109">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="54ca7-109">Step 3.</span></span> [<span data-ttu-id="54ca7-110">Настройка голосовой маршрутии</span><span class="sxs-lookup"><span data-stu-id="54ca7-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="54ca7-111">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="54ca7-111">Step 4.</span></span> [<span data-ttu-id="54ca7-112">Перевод чисел в альтернативный формат</span><span class="sxs-lookup"><span data-stu-id="54ca7-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="54ca7-113">Сведения о всех действиях, необходимых для настройки прямой маршрутистики, см. в этой [ссылке.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="54ca7-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="54ca7-114">Когда вы будете готовы включить прямую маршрутику для пользователей, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="54ca7-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="54ca7-115">Создайте пользователя в Microsoft 365 или Office 365 и назначьте телефонная система лицензию.</span><span class="sxs-lookup"><span data-stu-id="54ca7-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="54ca7-116">Убедитесь, что пользователь находится в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="54ca7-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="54ca7-117">Настройте номер телефона и в включить корпоративную голосовую и голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="54ca7-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="54ca7-118">Назначьте Teams режим только пользователям.</span><span class="sxs-lookup"><span data-stu-id="54ca7-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="54ca7-119">Создание пользователя и назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="54ca7-119">Create a user and assign the license</span></span> 

<span data-ttu-id="54ca7-120">Существует два варианта создания нового пользователя в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="54ca7-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="54ca7-121">Однако корпорация Майкрософт рекомендует вашей организации выбрать один из вариантов, чтобы избежать проблем с маршрутией:</span><span class="sxs-lookup"><span data-stu-id="54ca7-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="54ca7-122">Создайте пользователя в локальной службе Active Directory и синхронизируйте его с облаком.</span><span class="sxs-lookup"><span data-stu-id="54ca7-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="54ca7-123">См. [интеграцию локального каталога с Azure Active Directory.](/azure/active-directory/connect/active-directory-aadconnect)</span><span class="sxs-lookup"><span data-stu-id="54ca7-123">See [Integrate your on-premises directories with Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="54ca7-124">Создайте пользователя непосредственно в Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="54ca7-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="54ca7-125">См. добавление пользователей по отдельности или массово [в Microsoft 365 или Office 365 — справка для администраторов.](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</span><span class="sxs-lookup"><span data-stu-id="54ca7-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="54ca7-126">Если развертывание Skype для бизнеса Online сосуществовает с локальной Skype для бизнеса 2015 или Lync 2010 или 2013, единственным вариантом является создание пользователя в локальной службе Active Directory и синхронизация пользователя с облаком (вариант 1).</span><span class="sxs-lookup"><span data-stu-id="54ca7-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="54ca7-127">Сведения о требованиях к лицензиям см. [в лицензировании](direct-routing-plan.md#licensing-and-other-requirements) и других требованиях в [области Планирование прямой маршрутии.](direct-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="54ca7-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a><span data-ttu-id="54ca7-128">Убедитесь, что пользователь находится в Сети и телефонные номера не синхронизируются из локальной сети (применимо для пользователей Skype для бизнеса Server Корпоративная голосовая связь с поддержкой переноса в Teams Direct Routing)</span><span class="sxs-lookup"><span data-stu-id="54ca7-128">Ensure that the user is homed online and phone number is not being synced from on-premises (applicable for Skype for Business Server Enterprise Voice enabled users being migrated to Teams Direct Routing)</span></span>

<span data-ttu-id="54ca7-129">Прямая маршрутная маршрутия требует, чтобы пользователь был домашним в Интернете.</span><span class="sxs-lookup"><span data-stu-id="54ca7-129">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="54ca7-130">Чтобы проверить это, обратитесь к параметру RegistrarPool, который должен иметь значение в infra.lync.com домене.</span><span class="sxs-lookup"><span data-stu-id="54ca7-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span> <span data-ttu-id="54ca7-131">Для параметра OnPremLineUriManuallySet также должно быть задано true.</span><span class="sxs-lookup"><span data-stu-id="54ca7-131">OnPremLineUriManuallySet parameter should also to be set to True.</span></span> <span data-ttu-id="54ca7-132">Для этого нужно настроить номер телефона и включить корпоративную голосовую и голосовую почту с Skype для бизнеса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54ca7-132">This is achieved by configuring the phone number and enable enterprise voice and voicemail using Skype for Business Online PowerShell.</span></span>

1. <span data-ttu-id="54ca7-133">Подключение сеанс Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54ca7-133">Connect a Skype for Business Online PowerShell session.</span></span>

2. <span data-ttu-id="54ca7-134">Выдай команду:</span><span class="sxs-lookup"><span data-stu-id="54ca7-134">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    <span data-ttu-id="54ca7-135">Если для параметра OnPremLineUriManuallySet задано число False, а для параметра LineUri используется номер <E.164>, очистите параметры с помощью локальной оболочки Skype для бизнеса Management Shell, прежде чем настраивать номер телефона с помощью Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54ca7-135">In case OnPremLineUriManuallySet is set to False and LineUri is populated with a <E.164 phone number>, please clean the parameters using on-premises Skype for Business Management Shell, before configuring the phone number using Skype for Business Online PowerShell.</span></span> 

1. <span data-ttu-id="54ca7-136">Команда Skype для бизнеса командной оболочки:</span><span class="sxs-lookup"><span data-stu-id="54ca7-136">From Skype for Business Management Shell issue the command:</span></span> 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   <span data-ttu-id="54ca7-137">После синхронизации изменений с Office 365 ожидаемым `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` выходом будет:</span><span class="sxs-lookup"><span data-stu-id="54ca7-137">After the changes have synced to Office 365 the expected output of `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` would be:</span></span>

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="54ca7-138">Настройка номера телефона и включить корпоративную голосовую и голосовую почту</span><span class="sxs-lookup"><span data-stu-id="54ca7-138">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="54ca7-139">После создания пользователя и назначенной лицензии необходимо настроить его номер телефона и голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="54ca7-139">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="54ca7-140">Чтобы добавить номер телефона и включить голосовую почту:</span><span class="sxs-lookup"><span data-stu-id="54ca7-140">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="54ca7-141">Подключение сеанс Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="54ca7-141">Connect a Skype for Business Online PowerShell session.</span></span> 

2. <span data-ttu-id="54ca7-142">Выдай команду:</span><span class="sxs-lookup"><span data-stu-id="54ca7-142">Issue the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    <span data-ttu-id="54ca7-143">Например, чтобы добавить номер телефона пользователя "Низкий уровень", введите следующую запись:</span><span class="sxs-lookup"><span data-stu-id="54ca7-143">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    <span data-ttu-id="54ca7-144">Если у пользователей "Низкий уровень" и "Стейси Квинн" одинаковые базовые номера с уникальными расширениями, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="54ca7-144">If the users "Spencer Low" and "Stacy Quinn" share the same base number with unique extensions, enter the following</span></span>
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1001" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1002" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="54ca7-145">Рекомендуется, но не обязательно, чтобы используемый номер телефона был настроен как полный номер телефона E.164 с кодом страны.</span><span class="sxs-lookup"><span data-stu-id="54ca7-145">It's recommended, but not required, that the phone number used is configured as a full E.164 phone number with country code.</span></span> <span data-ttu-id="54ca7-146">Поддерживается настройка номеров телефонов с расширениями, которые будут использоваться для искомых пользователей, если при подступе к базовому номеру возвращается несколько результатов.</span><span class="sxs-lookup"><span data-stu-id="54ca7-146">It is supported to configure phone numbers with extensions which will be used to lookup users when the lookup against the base number returns more than one result.</span></span> <span data-ttu-id="54ca7-147">Это позволяет компаниям настраивать номера телефонов с одинаковым базовым номером и уникальными расширениями.</span><span class="sxs-lookup"><span data-stu-id="54ca7-147">This allows companies to configure phone numbers with the same base number and unique extensions.</span></span> <span data-ttu-id="54ca7-148">Для успешного подстроки в приглашении должно быть включено полное число с расширением:</span><span class="sxs-lookup"><span data-stu-id="54ca7-148">For lookup to be successful, the invite must include the full number with extension as follows:</span></span>
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > <span data-ttu-id="54ca7-149">Если номер телефона пользователя управляется локально, настройте его с помощью локальной Skype для бизнеса или панели управления.</span><span class="sxs-lookup"><span data-stu-id="54ca7-149">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="54ca7-150">Настройка отправки звонков непосредственно на голосовую почту</span><span class="sxs-lookup"><span data-stu-id="54ca7-150">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="54ca7-151">Прямая маршрутия позволяет прекратить звонок и отправить его непосредственно в голосовую почту пользователя.</span><span class="sxs-lookup"><span data-stu-id="54ca7-151">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="54ca7-152">Если вы хотите отправить звонок непосредственно в голосовую почту, вложите непрозрачной=app:voicemail в заглавный URI запроса.</span><span class="sxs-lookup"><span data-stu-id="54ca7-152">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="54ca7-153">Например, "sip:user@yourdomain.com;opaque=app:voicemail".</span><span class="sxs-lookup"><span data-stu-id="54ca7-153">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="54ca7-154">В этом случае Teams не получит уведомление о вызове, звонок будет напрямую подключен к голосовой почте пользователя.</span><span class="sxs-lookup"><span data-stu-id="54ca7-154">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="54ca7-155">Назначьте Teams режим только пользователям, чтобы обеспечить доступ к звонкам Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="54ca7-155">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="54ca7-156">Прямая маршрутия требует, чтобы Teams режиме только для входящих звонков в клиенте Teams маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="54ca7-156">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="54ca7-157">Чтобы перейти в Teams, назначьте им экземпляр UpgradeToTeams TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="54ca7-157">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="54ca7-158">Дополнительные сведения см. в [стратегии обновления для ИТ-администраторов.](upgrade-to-teams-on-prem-implement.md)</span><span class="sxs-lookup"><span data-stu-id="54ca7-158">For more information, see [Upgrade strategies for IT administrators](upgrade-to-teams-on-prem-implement.md).</span></span> <span data-ttu-id="54ca7-159">Если в вашей организации используется Skype для бизнеса Server или Skype для бизнеса Online, см. статью о взаимосвязи между Skype и [Teams:](migration-interop-guidance-for-teams-with-skype.md)миграция и взаимодействия с Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="54ca7-159">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="54ca7-160">См. также</span><span class="sxs-lookup"><span data-stu-id="54ca7-160">See also</span></span>

[<span data-ttu-id="54ca7-161">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="54ca7-161">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="54ca7-162">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="54ca7-162">Configure Direct Routing</span></span>](direct-routing-configure.md)
