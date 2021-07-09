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
description: Узнайте, как включить для Телефон (Майкрософт) прямую маршрутику системы.
ms.openlocfilehash: 86132778226702577068d9502ae46cba949667c6
ms.sourcegitcommit: 5df33e7fe912426e3e158b3be7334e05dc3803a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2021
ms.locfileid: "53345715"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="3b186-103">Включить для пользователей прямую маршрутику, голосовую и голосовую почту</span><span class="sxs-lookup"><span data-stu-id="3b186-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="3b186-104">В этой статье описано, как включить для телефонная система прямую маршрутику.</span><span class="sxs-lookup"><span data-stu-id="3b186-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="3b186-105">Это шаг 2 из следующих действий по настройке прямой маршрутии:</span><span class="sxs-lookup"><span data-stu-id="3b186-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="3b186-106">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="3b186-106">Step 1.</span></span> [<span data-ttu-id="3b186-107">Подключение SBC с Телефон (Майкрософт) и проверьте подключение</span><span class="sxs-lookup"><span data-stu-id="3b186-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="3b186-108">**Шаг 2. Включить для пользователей прямую маршрутику, голосовую и голосовую почту**   (эта статья)</span><span class="sxs-lookup"><span data-stu-id="3b186-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**   (this article)</span></span>
- <span data-ttu-id="3b186-109">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="3b186-109">Step 3.</span></span> [<span data-ttu-id="3b186-110">Настройка перенастройки голосовой маршрутии</span><span class="sxs-lookup"><span data-stu-id="3b186-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="3b186-111">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="3b186-111">Step 4.</span></span> [<span data-ttu-id="3b186-112">Перевод чисел в альтернативный формат</span><span class="sxs-lookup"><span data-stu-id="3b186-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="3b186-113">Сведения о всех действиях, необходимых для настройки прямой маршрутии, см. в этой [ссылке.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="3b186-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="3b186-114">Когда вы будете готовы включить прямую маршрутику для пользователей, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="3b186-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="3b186-115">Создайте пользователя в Microsoft 365 или Office 365 и назначьте телефонная система лицензию.</span><span class="sxs-lookup"><span data-stu-id="3b186-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="3b186-116">Убедитесь, что пользователь находится в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="3b186-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="3b186-117">Настройте номер телефона и в включить корпоративную голосовую и голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="3b186-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="3b186-118">Назначьте Teams режим только пользователям.</span><span class="sxs-lookup"><span data-stu-id="3b186-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="3b186-119">Создание пользователя и назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="3b186-119">Create a user and assign the license</span></span>

<span data-ttu-id="3b186-120">Существует два варианта создания нового пользователя в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="3b186-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="3b186-121">Однако корпорация Майкрософт рекомендует вашей организации выбрать один из вариантов, чтобы избежать проблем с маршрутией:</span><span class="sxs-lookup"><span data-stu-id="3b186-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="3b186-122">Создайте пользователя в локальной службе Active Directory и синхронизируйте его с облаком.</span><span class="sxs-lookup"><span data-stu-id="3b186-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="3b186-123">См. [интеграцию локального каталога с Azure Active Directory.](/azure/active-directory/connect/active-directory-aadconnect)</span><span class="sxs-lookup"><span data-stu-id="3b186-123">See [Integrate your on-premises directories with Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="3b186-124">Создайте пользователя непосредственно в Центр администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b186-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="3b186-125">См. добавление пользователей по отдельности или массово [в Microsoft 365 или Office 365 — справка для администраторов.](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</span><span class="sxs-lookup"><span data-stu-id="3b186-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="3b186-126">Если развертывание Skype для бизнеса Online сосуществовает с локальной Skype для бизнеса 2015 или Lync 2010 или 2013, единственным вариантом является создание пользователя в локальной службе Active Directory и синхронизация пользователя с облаком (вариант 1).</span><span class="sxs-lookup"><span data-stu-id="3b186-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="3b186-127">Сведения о требованиях к лицензиям см. [в лицензировании](direct-routing-plan.md#licensing-and-other-requirements) и других требованиях в [области Планирование прямой маршрутии.](direct-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="3b186-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online"></a><span data-ttu-id="3b186-128">Убедитесь, что пользователь находится в Сети</span><span class="sxs-lookup"><span data-stu-id="3b186-128">Ensure that the user is homed online</span></span> 

<span data-ttu-id="3b186-129">Этот шаг относится к Skype для бизнеса Server Корпоративная голосовая связь, которые были перенесены Teams прямую маршрутику.</span><span class="sxs-lookup"><span data-stu-id="3b186-129">This step is applicable to Skype for Business Server Enterprise Voice enabled users being migrated to Teams Direct Routing.</span></span>

<span data-ttu-id="3b186-130">Прямая маршрутная маршрутия требует, чтобы пользователь был домашним в Интернете.</span><span class="sxs-lookup"><span data-stu-id="3b186-130">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="3b186-131">Чтобы проверить это, обратитесь к параметру RegistrarPool, который должен иметь значение в infra.lync.com домене.</span><span class="sxs-lookup"><span data-stu-id="3b186-131">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span> <span data-ttu-id="3b186-132">Кроме того, при переносе пользователей на прямую маршрутизу рекомендуется (но не обязательно) изменять управление LineURI из локальной в веб Teams-ю.</span><span class="sxs-lookup"><span data-stu-id="3b186-132">It's also recommended, but not required, to change management of the LineURI from on-premises to online when migrating users to Teams Direct Routing.</span></span> 

1. <span data-ttu-id="3b186-133">Подключение сеанс Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b186-133">Connect a Skype for Business Online PowerShell session.</span></span>

2. <span data-ttu-id="3b186-134">Выдай команду:</span><span class="sxs-lookup"><span data-stu-id="3b186-134">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    <span data-ttu-id="3b186-135">Если для onPremLineUriManuallySet за установлено число False, а для lineUri — номер <E.164>, этот номер телефона был назначен локально и синхронизирован с O365.</span><span class="sxs-lookup"><span data-stu-id="3b186-135">In case OnPremLineUriManuallySet is set to False and LineUri is populated with a <E.164 phone number>, the phone number was assigned on-premises and synchronized to O365.</span></span> <span data-ttu-id="3b186-136">Если вы хотите управлять номером телефона в Интернете, очистите параметр с помощью локальной оболочки Skype для бизнеса Management Shell и синхронизируются с O365, прежде чем настраивать номер телефона с помощью Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b186-136">If you want manage the phone number online, clean the parameter using on-premises Skype for Business Management Shell and synchronize to O365, before configuring the phone number using Skype for Business Online PowerShell.</span></span> 

1. <span data-ttu-id="3b186-137">Команда Skype для бизнеса командной оболочки:</span><span class="sxs-lookup"><span data-stu-id="3b186-137">From Skype for Business Management Shell issue the command:</span></span> 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null
    ``` 
 > [!NOTE]
 > <span data-ttu-id="3b186-138">Не устанавливайте для EnterpriseVoiceEnabled состояние False, так как это не требуется, и это может привести к проблемам нормализации набора, если используются устаревшие телефоны Skype для бизнеса и гибридная конфигурация клиента настроена с использованием UseOnPremDialPlan $True.</span><span class="sxs-lookup"><span data-stu-id="3b186-138">Do not set EnterpriseVoiceEnabled to False as there is no requirement to do so and this can lead to dial plan normalization issues if legacy Skype for Business phones are in use and the Tenant hybrid configuration is set with UseOnPremDialPlan $True.</span></span> 
    
   <span data-ttu-id="3b186-139">После синхронизации изменений с Office 365 ожидаемым `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` выходом будет:</span><span class="sxs-lookup"><span data-stu-id="3b186-139">After the changes have synced to Office 365 the expected output of `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` would be:</span></span>

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```
 > [!NOTE]
 > <span data-ttu-id="3b186-140">Для декодирования локальной среды Skype для бизнеса управлять всеми атрибутами телефона пользователя в [Интернете.](/skypeforbusiness/hybrid/decommission-on-prem-overview)</span><span class="sxs-lookup"><span data-stu-id="3b186-140">All user's phone attributes must be managed online before you [decomission your on-premises Skype for Business environment](/skypeforbusiness/hybrid/decommission-on-prem-overview).</span></span> 

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online"></a><span data-ttu-id="3b186-141">Настройка номера телефона и включить корпоративную голосовую и голосовую почту в Интернете</span><span class="sxs-lookup"><span data-stu-id="3b186-141">Configure the phone number and enable enterprise voice and voicemail online</span></span> 

<span data-ttu-id="3b186-142">После создания пользователя и назначенной лицензии необходимо настроить его параметры телефона в Сети.</span><span class="sxs-lookup"><span data-stu-id="3b186-142">After you have created the user and assigned a license, the next step is to configure the user's online phone settings.</span></span> 

 
1. <span data-ttu-id="3b186-143">Подключение сеанс Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3b186-143">Connect a Skype for Business Online PowerShell session.</span></span> 

2. <span data-ttu-id="3b186-144">Если вы управляете номером телефона пользователя локально, выдав команду:</span><span class="sxs-lookup"><span data-stu-id="3b186-144">If managing the user's phone number on-premises, issue the command:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
3. <span data-ttu-id="3b186-145">Если вы управляете номером телефона пользователя в Интернете, выдав команду:</span><span class="sxs-lookup"><span data-stu-id="3b186-145">If managing the user's phone number online, issue the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    <span data-ttu-id="3b186-146">Например, чтобы добавить номер телефона пользователя "Низкий уровень", введите следующую запись:</span><span class="sxs-lookup"><span data-stu-id="3b186-146">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    <span data-ttu-id="3b186-147">Если у пользователей "Низкий уровень" и "Стейси Квинн" одинаковые базовые номера с уникальными расширениями, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="3b186-147">If the users "Spencer Low" and "Stacy Quinn" share the same base number with unique extensions, enter the following</span></span>
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1001" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1002" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="3b186-148">Рекомендуется, но не обязательно, чтобы используемый номер телефона был настроен как полный номер телефона E.164 с кодом страны.</span><span class="sxs-lookup"><span data-stu-id="3b186-148">It's recommended, but not required, that the phone number used is configured as a full E.164 phone number with country code.</span></span> <span data-ttu-id="3b186-149">Поддерживается настройка номеров телефонов с расширениями, которые будут использоваться для искомых пользователей, если при подступе к базовому номеру возвращается несколько результатов.</span><span class="sxs-lookup"><span data-stu-id="3b186-149">It is supported to configure phone numbers with extensions which will be used to lookup users when the lookup against the base number returns more than one result.</span></span> <span data-ttu-id="3b186-150">Это позволяет компаниям настраивать номера телефонов с одинаковым базовым номером и уникальными расширениями.</span><span class="sxs-lookup"><span data-stu-id="3b186-150">This allows companies to configure phone numbers with the same base number and unique extensions.</span></span> <span data-ttu-id="3b186-151">Для успешного подстроки в приглашении должно быть включено полное число с расширением:</span><span class="sxs-lookup"><span data-stu-id="3b186-151">For lookup to be successful, the invite must include the full number with extension as follows:</span></span>
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > <span data-ttu-id="3b186-152">Если номер телефона пользователя управляется локально, настройте его с помощью локальной Skype для бизнеса или панели управления.</span><span class="sxs-lookup"><span data-stu-id="3b186-152">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="3b186-153">Настройка отправки звонков непосредственно на голосовую почту</span><span class="sxs-lookup"><span data-stu-id="3b186-153">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="3b186-154">Прямая маршрутия позволяет прекратить звонок пользователю и отправить его непосредственно в голосовую почту пользователя.</span><span class="sxs-lookup"><span data-stu-id="3b186-154">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="3b186-155">Если вы хотите отправить звонок непосредственно в голосовую почту, вложите непрозрачной=app:голосовой почты в заглавный URI запроса.</span><span class="sxs-lookup"><span data-stu-id="3b186-155">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="3b186-156">Например, "sip:user@yourdomain.com;opaque=app:voicemail".</span><span class="sxs-lookup"><span data-stu-id="3b186-156">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="3b186-157">В этом случае Teams не получит уведомление о вызове, звонок будет напрямую подключен к голосовой почте пользователя.</span><span class="sxs-lookup"><span data-stu-id="3b186-157">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="3b186-158">Назначьте Teams режим только пользователям, чтобы обеспечить доступ к звонкам в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3b186-158">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="3b186-159">Прямая маршрутия требует, чтобы Teams режиме только для входящих звонков в клиенте Teams маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="3b186-159">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="3b186-160">Чтобы перейти в Teams, назначьте им экземпляр UpgradeToTeams TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="3b186-160">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="3b186-161">Дополнительные сведения см. в [стратегии обновления для ИТ-администраторов.](upgrade-to-teams-on-prem-implement.md)</span><span class="sxs-lookup"><span data-stu-id="3b186-161">For more information, see [Upgrade strategies for IT administrators](upgrade-to-teams-on-prem-implement.md).</span></span> <span data-ttu-id="3b186-162">Если в вашей организации используется Skype для бизнеса Server или Skype для бизнеса Online, см. статью о взаимосвязи между Skype и [Teams:](migration-interop-guidance-for-teams-with-skype.md)миграция и взаимодействия с Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="3b186-162">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3b186-163">См. также</span><span class="sxs-lookup"><span data-stu-id="3b186-163">See also</span></span>

[<span data-ttu-id="3b186-164">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="3b186-164">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="3b186-165">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="3b186-165">Configure Direct Routing</span></span>](direct-routing-configure.md)
