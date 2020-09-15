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
ms.openlocfilehash: f89133b5205dc77f8045c484b97d3049773c28e2
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814548"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="97d1a-103">Предоставление пользователям прямой маршрутизации, голоса и голосовой почты</span><span class="sxs-lookup"><span data-stu-id="97d1a-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="97d1a-104">В этой статье описано, как разрешить пользователям использовать прямую маршрутизацию телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="97d1a-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="97d1a-105">Это шаг 2 описанных ниже действий для настройки прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="97d1a-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="97d1a-106">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="97d1a-106">Step 1.</span></span> [<span data-ttu-id="97d1a-107">Соединение SBC с телефонной системой Microsoft и проверка соединения</span><span class="sxs-lookup"><span data-stu-id="97d1a-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="97d1a-108">**Шаг 2. Предоставление пользователям прямой маршрутизации, голоса и голосовой почты**   (в этой статье)</span><span class="sxs-lookup"><span data-stu-id="97d1a-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**   (this article)</span></span>
- <span data-ttu-id="97d1a-109">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="97d1a-109">Step 3.</span></span> [<span data-ttu-id="97d1a-110">Настройка голосовой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="97d1a-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="97d1a-111">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="97d1a-111">Step 4.</span></span> [<span data-ttu-id="97d1a-112">Перевод чисел в альтернативный формат</span><span class="sxs-lookup"><span data-stu-id="97d1a-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="97d1a-113">Сведения о всех шагах, необходимых для настройки прямой маршрутизации, приведены в статье [Настройка прямого маршрута](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="97d1a-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="97d1a-114">Когда вы будете готовы предоставить пользователям прямую маршрутизацию, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="97d1a-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="97d1a-115">Создайте пользователя в Microsoft 365 или Office 365 и назначьте лицензию на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="97d1a-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="97d1a-116">Убедитесь в том, что пользователь размещен в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="97d1a-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="97d1a-117">Настройте номер телефона и включите поддержку корпоративной голосовой и голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="97d1a-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="97d1a-118">Назначение пользователю режима "только для Teams".</span><span class="sxs-lookup"><span data-stu-id="97d1a-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="97d1a-119">Создание пользователя и назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="97d1a-119">Create a user and assign the license</span></span> 

<span data-ttu-id="97d1a-120">Существует два способа создания нового пользователя в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="97d1a-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="97d1a-121">Тем не менее Корпорация Майкрософт рекомендует выбирать один из вариантов для устранения проблем с маршрутизацией.</span><span class="sxs-lookup"><span data-stu-id="97d1a-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="97d1a-122">Создайте пользователя в локальной службе каталогов Active Directory и синхронизируйте пользователя с облаком.</span><span class="sxs-lookup"><span data-stu-id="97d1a-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="97d1a-123">Откройте раздел [интеграция локальных каталогов с Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="97d1a-123">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="97d1a-124">Непосредственное создание пользователя в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="97d1a-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="97d1a-125">В разделе [Добавление пользователей по отдельности или массово в microsoft 365 или Office 365 — Справка для администраторов](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="97d1a-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="97d1a-126">Если развертывание Skype для бизнеса Online осуществляется с помощью Skype для бизнеса 2015 или Lync 2010 или 2013 локально, единственным поддерживаемым вариантом будет создание пользователя в локальной службе каталогов Active Directory и синхронизация пользователя с облаком (вариант 1).</span><span class="sxs-lookup"><span data-stu-id="97d1a-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="97d1a-127">Сведения о требованиях к лицензиям можно найти в разделе [Лицензирование и другие требования](direct-routing-plan.md#licensing-and-other-requirements) в [прямом маршруте планирование](direct-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="97d1a-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a><span data-ttu-id="97d1a-128">Убедитесь в том, что пользователь подключен к сети, а номер телефона не синхронизируется локально (применимо для пользователей, поддерживающих голосовую связь в Skype для бизнеса Server), перенесены в Team Direct Routing.</span><span class="sxs-lookup"><span data-stu-id="97d1a-128">Ensure that the user is homed online and phone number is not being synced from on-premises (applicable for Skype for Business Server Enterprise Voice enabled users being migrated to Teams Direct Routing)</span></span>

<span data-ttu-id="97d1a-129">Для прямой маршрутизации требуется, чтобы пользователь был подключен к сети.</span><span class="sxs-lookup"><span data-stu-id="97d1a-129">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="97d1a-130">Вы можете проверить, просматривая параметр RegistrarPool, который должен иметь значение в домене infra.lync.com.</span><span class="sxs-lookup"><span data-stu-id="97d1a-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span> <span data-ttu-id="97d1a-131">Для параметра OnPremLineUriManuallySet также должно быть задано значение true.</span><span class="sxs-lookup"><span data-stu-id="97d1a-131">OnPremLineUriManuallySet parameter should also to be set to True.</span></span> <span data-ttu-id="97d1a-132">Это достигается путем настройки номера телефона и включения корпоративной голосовой и голосовой почты в Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97d1a-132">This is achieved by configuring the phone number and enable enterprise voice and voicemail using Skype for Business Online PowerShell.</span></span>

1. <span data-ttu-id="97d1a-133">Подключитесь к сеансу PowerShell Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="97d1a-133">Connect a Skype for Business Online PowerShell session.</span></span>

2. <span data-ttu-id="97d1a-134">Выдайте команду:</span><span class="sxs-lookup"><span data-stu-id="97d1a-134">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    <span data-ttu-id="97d1a-135">В случае, если OnPremLineUriManuallySet имеет значение false и LineUri заполняется <E. 164 номера телефона>, очистите параметры с помощью локальной оболочки управления Skype для бизнеса, прежде чем настраивать номер телефона с помощью Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97d1a-135">In case OnPremLineUriManuallySet is set to False and LineUri is populated with a <E.164 phone number>, please clean the parameters using on-premises Skype for Business Management Shell, before configuring the phone number using Skype for Business Online PowerShell.</span></span> 

1. <span data-ttu-id="97d1a-136">С помощью командной консоли Skype для бизнеса, выполните команду:</span><span class="sxs-lookup"><span data-stu-id="97d1a-136">From Skype for Business Management Shell issue the command:</span></span> 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   <span data-ttu-id="97d1a-137">После синхронизации изменений в Office 365 ожидаемый результат будет `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="97d1a-137">After the changes have synced to Office 365 the expected output of `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` would be:</span></span>

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="97d1a-138">Настройка номера телефона и включение корпоративной голосовой и голосовой почты</span><span class="sxs-lookup"><span data-stu-id="97d1a-138">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="97d1a-139">После создания пользователя и назначения лицензии следует настроить номер телефона пользователя и голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="97d1a-139">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="97d1a-140">Чтобы добавить номер телефона и включить голосовую почту, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="97d1a-140">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="97d1a-141">Подключитесь к сеансу PowerShell Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="97d1a-141">Connect a Skype for Business Online PowerShell session.</span></span> 

2. <span data-ttu-id="97d1a-142">Выдайте команду:</span><span class="sxs-lookup"><span data-stu-id="97d1a-142">Issue the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```
    
    <span data-ttu-id="97d1a-143">Например, чтобы добавить номер телефона пользователя "Spencer Low", введите следующее:</span><span class="sxs-lookup"><span data-stu-id="97d1a-143">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="97d1a-144">Номер телефона должен быть настроен как полный E. 164 номер телефона с кодом страны.</span><span class="sxs-lookup"><span data-stu-id="97d1a-144">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="97d1a-145">Если в качестве номера телефона пользователя используется локальный, используйте локальную среду управления и панель управления Skype для бизнеса, чтобы настроить номер телефона пользователя.</span><span class="sxs-lookup"><span data-stu-id="97d1a-145">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="97d1a-146">Настройка отправки звонков непосредственно в голосовую почту</span><span class="sxs-lookup"><span data-stu-id="97d1a-146">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="97d1a-147">Прямая маршрутизация позволяет прекратить звонок пользователю и отправить его прямо на голосовую почту пользователя.</span><span class="sxs-lookup"><span data-stu-id="97d1a-147">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="97d1a-148">Если вы хотите отправить звонок прямо на голосовую почту, прикрепите непрозрачный = App: голосовой почте к заголовку URI запроса.</span><span class="sxs-lookup"><span data-stu-id="97d1a-148">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="97d1a-149">Например, "SIP: user@yourdomain. com; непрозрачный = App: голосовой почты".</span><span class="sxs-lookup"><span data-stu-id="97d1a-149">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="97d1a-150">В этом случае пользователь Teams не получит уведомление о звонке, Звонок будет подключен непосредственно к голосовой почте пользователя.</span><span class="sxs-lookup"><span data-stu-id="97d1a-150">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="97d1a-151">Назначение режима "только для Teams" для пользователей, которые должны обеспечивать звонки в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="97d1a-151">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="97d1a-152">Для прямой маршрутизации необходимо, чтобы пользователи были в режиме "только Teams", чтобы обеспечить поступление входящих звонков в клиенте Teams.</span><span class="sxs-lookup"><span data-stu-id="97d1a-152">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="97d1a-153">Чтобы перевести пользователей в режиме "только Teams", назначьте им экземпляр "UpgradeToTeams" для TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="97d1a-153">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="97d1a-154">Дополнительные сведения можно найти в [статье Руководство по обновлению для ИТ – администраторов](upgrade-to-teams-on-prem-overview.md).</span><span class="sxs-lookup"><span data-stu-id="97d1a-154">For more information, see [Upgrade guidance for IT administrators](upgrade-to-teams-on-prem-overview.md).</span></span> <span data-ttu-id="97d1a-155">Если в вашей организации используется Skype для бизнеса Server или Skype для бизнеса Online, ознакомьтесь со статьей сведения о взаимодействии между Skype и Teams, а также о том, как [Переход и взаимодействие осуществляется в Skype для бизнеса](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="97d1a-155">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="97d1a-156">См. также</span><span class="sxs-lookup"><span data-stu-id="97d1a-156">See also</span></span>

[<span data-ttu-id="97d1a-157">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="97d1a-157">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="97d1a-158">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="97d1a-158">Configure Direct Routing</span></span>](direct-routing-configure.md)
