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
ms.openlocfilehash: e9120dcbcd4b1a82eb864f545efdbadc42481794
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "42158010"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="1976d-103">Предоставление пользователям прямой маршрутизации, голоса и голосовой почты</span><span class="sxs-lookup"><span data-stu-id="1976d-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="1976d-104">В этой статье описано, как разрешить пользователям использовать прямую маршрутизацию телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="1976d-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="1976d-105">Это шаг 2 описанных ниже действий для настройки прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="1976d-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="1976d-106">Шаг 1.</span><span class="sxs-lookup"><span data-stu-id="1976d-106">Step 1.</span></span> [<span data-ttu-id="1976d-107">Соединение SBC с телефонной системой Microsoft и проверка соединения</span><span class="sxs-lookup"><span data-stu-id="1976d-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="1976d-108">**Шаг 2. Предоставление пользователям прямой маршрутизации, голоса и голосовой почты** (в этой статье)</span><span class="sxs-lookup"><span data-stu-id="1976d-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**    (This article)</span></span>
- <span data-ttu-id="1976d-109">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="1976d-109">Step 3.</span></span> [<span data-ttu-id="1976d-110">Настройка голосовой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="1976d-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="1976d-111">Шаг 4.</span><span class="sxs-lookup"><span data-stu-id="1976d-111">Step 4.</span></span> [<span data-ttu-id="1976d-112">Перевод чисел в альтернативный формат</span><span class="sxs-lookup"><span data-stu-id="1976d-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="1976d-113">Сведения о всех шагах, необходимых для настройки прямой маршрутизации, приведены в статье [Настройка прямого маршрута](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="1976d-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="1976d-114">Когда вы будете готовы предоставить пользователям прямую маршрутизацию, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="1976d-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="1976d-115">Создание пользователя в Office 365 и назначение лицензии на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="1976d-115">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="1976d-116">Убедитесь в том, что пользователь размещен в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="1976d-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="1976d-117">Настройте номер телефона и включите поддержку корпоративной голосовой и голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="1976d-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="1976d-118">Назначение пользователю режима "только для Teams".</span><span class="sxs-lookup"><span data-stu-id="1976d-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="1976d-119">Создание пользователя в Office 365 и назначение лицензии</span><span class="sxs-lookup"><span data-stu-id="1976d-119">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="1976d-120">Существует два способа создания нового пользователя в Office 365.</span><span class="sxs-lookup"><span data-stu-id="1976d-120">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="1976d-121">Тем не менее Корпорация Майкрософт рекомендует выбирать один из вариантов для устранения проблем с маршрутизацией.</span><span class="sxs-lookup"><span data-stu-id="1976d-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="1976d-122">Создайте пользователя в локальной службе каталогов Active Directory и синхронизируйте пользователя с облаком.</span><span class="sxs-lookup"><span data-stu-id="1976d-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="1976d-123">Откройте раздел [интеграция локальных каталогов с Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="1976d-123">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="1976d-124">Создайте пользователя прямо на портале администратора Office 365.</span><span class="sxs-lookup"><span data-stu-id="1976d-124">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="1976d-125">В разделе [Добавление пользователей по отдельности или массово в Office 365 — Справка для администраторов](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="1976d-125">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="1976d-126">Если развертывание Skype для бизнеса Online осуществляется с помощью Skype для бизнеса 2015 или Lync 2010 или 2013 локально, единственным поддерживаемым вариантом будет создание пользователя в локальной службе каталогов Active Directory и синхронизация пользователя с облаком (вариант 1).</span><span class="sxs-lookup"><span data-stu-id="1976d-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="1976d-127">Сведения о требованиях к лицензиям можно найти в разделе [Лицензирование и другие требования](direct-routing-plan.md#licensing-and-other-requirements) в [прямом маршруте планирование](direct-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="1976d-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="1976d-128">Убедитесь в том, что пользователь размещен в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="1976d-128">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="1976d-129">Для прямой маршрутизации требуется, чтобы пользователь был подключен в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="1976d-129">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="1976d-130">Вы можете проверить, просматривая параметр Регистрарпул, который должен иметь значение в домене infra.lync.com.</span><span class="sxs-lookup"><span data-stu-id="1976d-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="1976d-131">Подключитесь к удаленной оболочке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1976d-131">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="1976d-132">Выдайте команду:</span><span class="sxs-lookup"><span data-stu-id="1976d-132">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
    ``` 

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="1976d-133">Настройка номера телефона и включение корпоративной голосовой и голосовой почты</span><span class="sxs-lookup"><span data-stu-id="1976d-133">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="1976d-134">После создания пользователя и назначения лицензии следует настроить номер телефона пользователя и голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="1976d-134">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="1976d-135">Чтобы добавить номер телефона и включить голосовую почту, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="1976d-135">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="1976d-136">Подключитесь к удаленному сеансу PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1976d-136">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="1976d-137">Введите команду:</span><span class="sxs-lookup"><span data-stu-id="1976d-137">Enter the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```

    <span data-ttu-id="1976d-138">Например, чтобы добавить номер телефона пользователя "Спенцер Low", введите следующее:</span><span class="sxs-lookup"><span data-stu-id="1976d-138">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="1976d-139">Номер телефона должен быть настроен как полный E. 164 номер телефона с кодом страны.</span><span class="sxs-lookup"><span data-stu-id="1976d-139">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

      > [!NOTE]
      > <span data-ttu-id="1976d-140">Если в качестве номера телефона пользователя используется локальный, используйте локальную среду управления и панель управления Skype для бизнеса, чтобы настроить номер телефона пользователя.</span><span class="sxs-lookup"><span data-stu-id="1976d-140">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="1976d-141">Настройка отправки звонков непосредственно в голосовую почту</span><span class="sxs-lookup"><span data-stu-id="1976d-141">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="1976d-142">Прямая маршрутизация позволяет прекратить звонок пользователю и отправить его прямо на голосовую почту пользователя.</span><span class="sxs-lookup"><span data-stu-id="1976d-142">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="1976d-143">Если вы хотите отправить звонок прямо на голосовую почту, прикрепите непрозрачный = App: голосовой почте к заголовку URI запроса.</span><span class="sxs-lookup"><span data-stu-id="1976d-143">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="1976d-144">Например, "SIP: user@yourdomain. com; непрозрачный = App: голосовой почты".</span><span class="sxs-lookup"><span data-stu-id="1976d-144">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="1976d-145">В этом случае пользователь Teams не получит уведомление о звонке, Звонок будет подключен непосредственно к голосовой почте пользователя.</span><span class="sxs-lookup"><span data-stu-id="1976d-145">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="1976d-146">Назначение режима "только для Teams" для пользователей, которые должны обеспечивать звонки в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1976d-146">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="1976d-147">Для прямой маршрутизации необходимо, чтобы пользователи были в режиме "только Teams", чтобы обеспечить поступление входящих звонков в клиенте Teams.</span><span class="sxs-lookup"><span data-stu-id="1976d-147">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="1976d-148">Чтобы перевести пользователей в режиме "только Teams", назначьте им экземпляр "Упградетотеамс" для Теамсупградеполици.</span><span class="sxs-lookup"><span data-stu-id="1976d-148">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="1976d-149">Дополнительные сведения можно найти в [статье Руководство по обновлению для ИТ – администраторов](upgrade-to-teams-on-prem-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1976d-149">For more information, see [Upgrade guidance for IT administrators](upgrade-to-teams-on-prem-overview.md).</span></span> <span data-ttu-id="1976d-150">Если в вашей организации используется Skype для бизнеса Server или Skype для бизнеса Online, ознакомьтесь со статьей сведения о взаимодействии между Skype и Teams, а также о том, как [Переход и взаимодействие осуществляется в Skype для бизнеса](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="1976d-150">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1976d-151">См. также</span><span class="sxs-lookup"><span data-stu-id="1976d-151">See also</span></span>

[<span data-ttu-id="1976d-152">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="1976d-152">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="1976d-153">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="1976d-153">Configure Direct Routing</span></span>](direct-routing-configure.md)