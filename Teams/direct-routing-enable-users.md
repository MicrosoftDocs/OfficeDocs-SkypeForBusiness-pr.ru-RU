---
title: Разрешить пользователям прямую маршрутизацию
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
description: Сведения о том, как включить прямую маршрутизацию для пользователей Microsoft Phone System.
ms.openlocfilehash: 5739797649c639e3259c6972da665ae0ced4b4bf
ms.sourcegitcommit: 0a9c5c01b37a93eecc369ca0ed49ae18f6a5065b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655486"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="bf55f-103">Предоставление пользователям прямой маршрутизации, голоса и голосовой почты</span><span class="sxs-lookup"><span data-stu-id="bf55f-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="bf55f-104">В этой статье описано, как разрешить пользователям использовать прямую маршрутизацию телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="bf55f-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="bf55f-105">Это шаг 2 описанных ниже действий для настройки прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="bf55f-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="bf55f-106">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="bf55f-106">Step 1.</span></span> [<span data-ttu-id="bf55f-107">Соединение SBC с телефонной системой Microsoft и проверка соединения</span><span class="sxs-lookup"><span data-stu-id="bf55f-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="bf55f-108">**Шаг 2. Предоставление пользователям прямой маршрутизации, голоса и голосовой почты**   (в этой статье)</span><span class="sxs-lookup"><span data-stu-id="bf55f-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**   (this article)</span></span>
- <span data-ttu-id="bf55f-109">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="bf55f-109">Step 3.</span></span> [<span data-ttu-id="bf55f-110">Настройка голосовой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="bf55f-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="bf55f-111">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="bf55f-111">Step 4.</span></span> [<span data-ttu-id="bf55f-112">Перевод чисел в альтернативный формат</span><span class="sxs-lookup"><span data-stu-id="bf55f-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="bf55f-113">Сведения о всех шагах, необходимых для настройки прямой маршрутизации, приведены в статье [Настройка прямого маршрута](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="bf55f-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="bf55f-114">Когда вы будете готовы предоставить пользователям прямую маршрутизацию, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="bf55f-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="bf55f-115">Создайте пользователя в Microsoft 365 или Office 365 и назначьте лицензию на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="bf55f-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="bf55f-116">Убедитесь в том, что пользователь размещен в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="bf55f-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="bf55f-117">Настройте номер телефона и включите поддержку корпоративной голосовой и голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="bf55f-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="bf55f-118">Назначение пользователю режима "только для Teams".</span><span class="sxs-lookup"><span data-stu-id="bf55f-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="bf55f-119">Создание пользователя и назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="bf55f-119">Create a user and assign the license</span></span> 

<span data-ttu-id="bf55f-120">Существует два способа создания нового пользователя в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="bf55f-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="bf55f-121">Тем не менее Корпорация Майкрософт рекомендует выбирать один из вариантов для устранения проблем с маршрутизацией.</span><span class="sxs-lookup"><span data-stu-id="bf55f-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="bf55f-122">Создайте пользователя в локальной службе каталогов Active Directory и синхронизируйте пользователя с облаком.</span><span class="sxs-lookup"><span data-stu-id="bf55f-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="bf55f-123">Откройте раздел [интеграция локальных каталогов с Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="bf55f-123">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="bf55f-124">Непосредственное создание пользователя в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bf55f-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="bf55f-125">В разделе [Добавление пользователей по отдельности или массово в microsoft 365 или Office 365 — Справка для администраторов](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="bf55f-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="bf55f-126">Если развертывание Skype для бизнеса Online осуществляется с помощью Skype для бизнеса 2015 или Lync 2010 или 2013 локально, единственным поддерживаемым вариантом будет создание пользователя в локальной службе каталогов Active Directory и синхронизация пользователя с облаком (вариант 1).</span><span class="sxs-lookup"><span data-stu-id="bf55f-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="bf55f-127">Сведения о требованиях к лицензиям можно найти в разделе [Лицензирование и другие требования](direct-routing-plan.md#licensing-and-other-requirements) в [прямом маршруте планирование](direct-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="bf55f-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a><span data-ttu-id="bf55f-128">Убедитесь в том, что пользователь подключен к сети, а номер телефона не синхронизируется локально (применимо для пользователей, поддерживающих голосовую связь в Skype для бизнеса Server), перенесены в Team Direct Routing.</span><span class="sxs-lookup"><span data-stu-id="bf55f-128">Ensure that the user is homed online and phone number is not being synced from on-premises (applicable for Skype for Business Server Enterprise Voice enabled users being migrated to Teams Direct Routing)</span></span>

<span data-ttu-id="bf55f-129">Для прямой маршрутизации требуется, чтобы пользователь был подключен к сети.</span><span class="sxs-lookup"><span data-stu-id="bf55f-129">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="bf55f-130">Вы можете проверить, просматривая параметр RegistrarPool, который должен иметь значение в домене infra.lync.com.</span><span class="sxs-lookup"><span data-stu-id="bf55f-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span> <span data-ttu-id="bf55f-131">Для параметра OnPremLineUriManuallySet также должно быть задано значение true.</span><span class="sxs-lookup"><span data-stu-id="bf55f-131">OnPremLineUriManuallySet parameter should also to be set to True.</span></span> <span data-ttu-id="bf55f-132">Это достигается путем настройки номера телефона и включения корпоративной голосовой и голосовой почты в Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf55f-132">This is achieved by configuring the phone number and enable enterprise voice and voicemail using Skype for Business Online PowerShell.</span></span>

1. <span data-ttu-id="bf55f-133">Подключитесь к сеансу PowerShell Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="bf55f-133">Connect a Skype for Business Online PowerShell session.</span></span>

2. <span data-ttu-id="bf55f-134">Выдайте команду:</span><span class="sxs-lookup"><span data-stu-id="bf55f-134">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    <span data-ttu-id="bf55f-135">В случае, если OnPremLineUriManuallySet имеет значение false и LineUri заполняется <E. 164 номера телефона>, очистите параметры с помощью локальной оболочки управления Skype для бизнеса, прежде чем настраивать номер телефона с помощью Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bf55f-135">In case OnPremLineUriManuallySet is set to False and LineUri is populated with a <E.164 phone number>, please clean the parameters using on-premises Skype for Business Management Shell, before configuring the phone number using Skype for Business Online PowerShell.</span></span> 

1. <span data-ttu-id="bf55f-136">С помощью командной консоли Skype для бизнеса, выполните команду:</span><span class="sxs-lookup"><span data-stu-id="bf55f-136">From Skype for Business Management Shell issue the command:</span></span> 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   <span data-ttu-id="bf55f-137">После синхронизации изменений в Office 365 ожидаемый результат будет `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bf55f-137">After the changes have synced to Office 365 the expected output of `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` would be:</span></span>

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="bf55f-138">Настройка номера телефона и включение корпоративной голосовой и голосовой почты</span><span class="sxs-lookup"><span data-stu-id="bf55f-138">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="bf55f-139">После создания пользователя и назначения лицензии следует настроить номер телефона пользователя и голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="bf55f-139">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="bf55f-140">Чтобы добавить номер телефона и включить голосовую почту, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="bf55f-140">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="bf55f-141">Подключитесь к сеансу PowerShell Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="bf55f-141">Connect a Skype for Business Online PowerShell session.</span></span> 

2. <span data-ttu-id="bf55f-142">Выдайте команду:</span><span class="sxs-lookup"><span data-stu-id="bf55f-142">Issue the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    <span data-ttu-id="bf55f-143">Например, чтобы добавить номер телефона пользователя "Spencer Low", введите следующее:</span><span class="sxs-lookup"><span data-stu-id="bf55f-143">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    <span data-ttu-id="bf55f-144">Если пользователи "Spencer Low" и "Stacy Quinn" имеют один и тот же базовый номер с уникальными расширениями, введите следующее:</span><span class="sxs-lookup"><span data-stu-id="bf55f-144">If the users "Spencer Low" and "Stacy Quinn" share the same base number with unique extensions, enter the following</span></span>
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="bf55f-145">Рекомендуется (но не обязательно) использовать номер телефона, указанный в качестве полного номера в формате E. 164 с кодом страны.</span><span class="sxs-lookup"><span data-stu-id="bf55f-145">It's recommended, but not required, that the phone number used is configured as a full E.164 phone number with country code.</span></span> <span data-ttu-id="bf55f-146">Поддерживается настройка номеров телефонов с расширениями, которые будут использоваться для поиска пользователей, если подстановка для базового числа возвращает более одного результата.</span><span class="sxs-lookup"><span data-stu-id="bf55f-146">It is supported to configure phone numbers with extensions which will be used to lookup users when the lookup against the base number returns more than one result.</span></span> <span data-ttu-id="bf55f-147">Это позволяет компаниям настраивать телефонные номера с использованием одинакового базового номера и уникальных расширений.</span><span class="sxs-lookup"><span data-stu-id="bf55f-147">This allows companies to configure phone numbers with the same base number and unique extensions.</span></span> <span data-ttu-id="bf55f-148">Чтобы подсчитаться успешным, приглашение должно содержать полный номер с расширением следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bf55f-148">For lookup to be successful, the invite must include the full number with extension as follows:</span></span>
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > <span data-ttu-id="bf55f-149">Если в качестве номера телефона пользователя используется локальный, используйте локальную среду управления и панель управления Skype для бизнеса, чтобы настроить номер телефона пользователя.</span><span class="sxs-lookup"><span data-stu-id="bf55f-149">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="bf55f-150">Настройка отправки звонков непосредственно в голосовую почту</span><span class="sxs-lookup"><span data-stu-id="bf55f-150">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="bf55f-151">Прямая маршрутизация позволяет прекратить звонок пользователю и отправить его прямо на голосовую почту пользователя.</span><span class="sxs-lookup"><span data-stu-id="bf55f-151">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="bf55f-152">Если вы хотите отправить звонок прямо на голосовую почту, прикрепите непрозрачный = App: голосовой почте к заголовку URI запроса.</span><span class="sxs-lookup"><span data-stu-id="bf55f-152">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="bf55f-153">Например, "SIP: user@yourdomain. com; непрозрачный = App: голосовой почты".</span><span class="sxs-lookup"><span data-stu-id="bf55f-153">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="bf55f-154">В этом случае пользователь Teams не получит уведомление о звонке, Звонок будет подключен непосредственно к голосовой почте пользователя.</span><span class="sxs-lookup"><span data-stu-id="bf55f-154">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="bf55f-155">Назначение режима "только для Teams" для пользователей, которые должны обеспечивать звонки в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bf55f-155">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="bf55f-156">Для прямой маршрутизации необходимо, чтобы пользователи были в режиме "только Teams", чтобы обеспечить поступление входящих звонков в клиенте Teams.</span><span class="sxs-lookup"><span data-stu-id="bf55f-156">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="bf55f-157">Чтобы перевести пользователей в режиме "только Teams", назначьте им экземпляр "UpgradeToTeams" для TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="bf55f-157">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="bf55f-158">Дополнительные сведения можно найти в [статье Руководство по обновлению для ИТ – администраторов](upgrade-to-teams-on-prem-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bf55f-158">For more information, see [Upgrade guidance for IT administrators](upgrade-to-teams-on-prem-overview.md).</span></span> <span data-ttu-id="bf55f-159">Если в вашей организации используется Skype для бизнеса Server или Skype для бизнеса Online, ознакомьтесь со статьей сведения о взаимодействии между Skype и Teams, а также о том, как [Переход и взаимодействие осуществляется в Skype для бизнеса](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="bf55f-159">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bf55f-160">См. также</span><span class="sxs-lookup"><span data-stu-id="bf55f-160">See also</span></span>

[<span data-ttu-id="bf55f-161">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="bf55f-161">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="bf55f-162">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="bf55f-162">Configure Direct Routing</span></span>](direct-routing-configure.md)
