---
title: Настройка взаимодействия Microsoft Teams с облачными видеослужбами
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: В этой статье объясняется, как спланировать и настроить cloud Video Interop для пользователей в организации.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64d790e775ac0d76de48a71de8d165656f2e6927
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102605"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="251fc-103">Настройка взаимодействия Microsoft Teams с облачными видеослужбами</span><span class="sxs-lookup"><span data-stu-id="251fc-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="251fc-104">После того как вы наберите партнеров [Cloud Video Interop](cloud-video-interop.md), вам потребуется спланировать развертывание, получить сведения о его подготовках и ключ клиента партнера, а также получить согласие на использование приложения для видеосвязи в организации.</span><span class="sxs-lookup"><span data-stu-id="251fc-104">After you have [chosen your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="251fc-105">На схеме ниже описан процесс.</span><span class="sxs-lookup"><span data-stu-id="251fc-105">The following diagram outlines the process.</span></span> 

![Развертывание CVI в организации](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="251fc-107">Планирование</span><span class="sxs-lookup"><span data-stu-id="251fc-107">Plan</span></span>

<span data-ttu-id="251fc-108">Сведения о том, как Microsoft Teams партнеров, которые будут использовать в вашей организации, см. в Microsoft Teams Cloud [Video Interop.](cloud-video-interop.md)</span><span class="sxs-lookup"><span data-stu-id="251fc-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="251fc-109">Чтобы спланировать учет пользователей или одновременное/широкое влияние сайта:</span><span class="sxs-lookup"><span data-stu-id="251fc-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="251fc-110">Выберите модель развертывания или размещенную модель для своего использования</span><span class="sxs-lookup"><span data-stu-id="251fc-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="251fc-111">Выберите план лицензии, идеально подходит для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="251fc-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="251fc-112">Планирование пропускной способности ВМ-объектов — размещение инфраструктуры видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="251fc-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="251fc-113">Настройка</span><span class="sxs-lookup"><span data-stu-id="251fc-113">Configure</span></span> 

<span data-ttu-id="251fc-114">Чтобы настроить cloud Video Interop, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="251fc-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="251fc-115">Получите сведения о конфигурации у выбранных партнеров (ключ клиента, appIds...).</span><span class="sxs-lookup"><span data-stu-id="251fc-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="251fc-116">Вы можете использовать одного или несколько партнеров по видеосвязи в организации</span><span class="sxs-lookup"><span data-stu-id="251fc-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="251fc-117">Убедитесь, что сеть настроена правильно.</span><span class="sxs-lookup"><span data-stu-id="251fc-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="251fc-118">Настройте видео брандмауэр на основе стандартов для обхода сети периметра для поддержки.</span><span class="sxs-lookup"><span data-stu-id="251fc-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="251fc-119">Например:</span><span class="sxs-lookup"><span data-stu-id="251fc-119">For example:</span></span> 
    - <span data-ttu-id="251fc-120">Cisco VCS-e</span><span class="sxs-lookup"><span data-stu-id="251fc-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="251fc-121">Polycom RPAD</span><span class="sxs-lookup"><span data-stu-id="251fc-121">Polycom RPAD</span></span>

3. <span data-ttu-id="251fc-122">Настройте интегрированные комнаты с помощью exchange и OTD.</span><span class="sxs-lookup"><span data-stu-id="251fc-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="251fc-123">В большинстве случаев в вашей среде требуется настроить дополнительную ретранслятор.</span><span class="sxs-lookup"><span data-stu-id="251fc-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="251fc-124">Предоставление</span><span class="sxs-lookup"><span data-stu-id="251fc-124">Provision</span></span>
 
<span data-ttu-id="251fc-125">Ключом клиента будет телефонный выход в службу партнера.</span><span class="sxs-lookup"><span data-stu-id="251fc-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="251fc-126">В следующем примере 813878896@t.plcm.vc ключом клиента.</span><span class="sxs-lookup"><span data-stu-id="251fc-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![Пример ключа клиента](media/tenant-key-example.png) 

<span data-ttu-id="251fc-128">Для создания ключа клиента вам потребуется выполнить следующие cmdlets, а также включить выбор пользователей или всю организацию для создания собраний с координатами видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="251fc-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="251fc-129">**[Get-CsTeamsVideoInteropServicepolicy:](/powershell/module/skype/get-csteamsvideointeropservicepolicy)** Корпорация Майкрософт предоставляет предварительно заранее запланированы политики для каждого из наших поддерживаемых партнеров, которые позволяют назначать партнеров для облачного видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="251fc-129">**[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="251fc-130">Он позволяет определить предварительно заранее сконструированы политики, которые можно использовать в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="251fc-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="251fc-131">Эту политику можно назначить одному или несколько пользователям, которые Grant-CsTeamsVideoInteropServicePolicy управления.</span><span class="sxs-lookup"><span data-stu-id="251fc-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="251fc-132">**[Grant-CsTeamsVideoInteropServicePolicy:](/powershell/module/skype/grant-csteamsvideointeropservicepolicy)** С помощью Grant-CsTeamsVideoInteropServicePolicy вы можете назначить предварительно построенную политику для использования в организации или назначить ее определенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="251fc-132">**[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="251fc-133">**[New-CsVideoInteropServiceProvider:](/powershell/module/skype/new-csvideointeropserviceprovider)** С помощью New-CsVideoInteropServiceProvider укажите сведения о поддерживаемом партнере CVI, который будет использовать ваша организация.</span><span class="sxs-lookup"><span data-stu-id="251fc-133">**[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="251fc-134">**[Set-CsVideoInteropServiceProvider:](/powershell/module/skype/set-csvideointeropserviceprovider)** С помощью Set-CsVideoInteropServiceProvider сведения о поддерживаемом партнере CVI, который использует ваша организация.</span><span class="sxs-lookup"><span data-stu-id="251fc-134">**[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="251fc-135">**[Get-CsVideoInteropServiceProvider:](/powershell/module/skype/get-csvideointeropserviceprovider)** Получите всех поставщиков, настроенных для использования в организации.</span><span class="sxs-lookup"><span data-stu-id="251fc-135">**[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="251fc-136">**[Remove-CsVideoInteropServiceProvider:](/powershell/module/skype/remove-csvideointeropserviceprovider)** Используйте Remove-CsVideoInteropServiceProvider, чтобы удалить все сведения о поставщике, которые больше не используются в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="251fc-136">**[Remove-CsVideoInteropServiceProvider](/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="251fc-137">Согласия</span><span class="sxs-lookup"><span data-stu-id="251fc-137">Consent</span></span>

<span data-ttu-id="251fc-138">Вам потребуется предоставить разрешение для устройств телеконференции видео (VTCs), чтобы присоединяться к собраниям организации с помощью партнерской службы.</span><span class="sxs-lookup"><span data-stu-id="251fc-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="251fc-139">Эту ссылку на согласие также предоставляет ваш партнер.</span><span class="sxs-lookup"><span data-stu-id="251fc-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="251fc-140">После выполнения этих действий у пользователей, которые включены по отдельности с помощью вышеуказанного cmdlet Grant, или у всех пользователей в организации, если клиент включен, будут координаты VTC во всех Teams собраниях, которые они запланируют.</span><span class="sxs-lookup"><span data-stu-id="251fc-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="251fc-141">Любой VTC может присоединиться к этим собраниям через эти координаты.</span><span class="sxs-lookup"><span data-stu-id="251fc-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="251fc-142">Имя</span><span class="sxs-lookup"><span data-stu-id="251fc-142">Name</span></span>|<span data-ttu-id="251fc-143">Краткое описание разрешений приложений</span><span class="sxs-lookup"><span data-stu-id="251fc-143">Application Permission Short Description</span></span>| <span data-ttu-id="251fc-144">Описание</span><span class="sxs-lookup"><span data-stu-id="251fc-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="251fc-145">Calls.JoinGroupCall.All</span><span class="sxs-lookup"><span data-stu-id="251fc-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="251fc-146">Присоединиться к групповым звонкам и собраниям как приложению (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="251fc-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="251fc-147">Позволяет приложению присоединяться к групповым звонкам и запланированным собраниям в организации без участия пользователя, выписав учетные данные.</span><span class="sxs-lookup"><span data-stu-id="251fc-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="251fc-148">Приложение будет присоединяться к собраниям в клиенте с привилегиями пользователя каталога.</span><span class="sxs-lookup"><span data-stu-id="251fc-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="251fc-149">Calls.JoinGroupCallasGuest.All</span><span class="sxs-lookup"><span data-stu-id="251fc-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="251fc-150">Присоединиться к групповым звонкам и собраниям в качестве гостевого пользователя (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="251fc-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="251fc-151">Позволяет приложению анонимно присоединяться к групповым звонкам и запланированным собраниям в вашей организации без участия пользователя, выписав учетные данные.</span><span class="sxs-lookup"><span data-stu-id="251fc-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="251fc-152">Приложение будет присоединяться как гость к собраниям в вашем клиенте.</span><span class="sxs-lookup"><span data-stu-id="251fc-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="251fc-153">Calls.AccessMedia.All</span><span class="sxs-lookup"><span data-stu-id="251fc-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="251fc-154">Доступ к потокам мультимедиа во время звонка в приложении (предварительный просмотр)</span><span class="sxs-lookup"><span data-stu-id="251fc-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="251fc-155">Позволяет приложению получать прямой доступ к потокам мультимедиа во время звонка, не входя в приложение.</span><span class="sxs-lookup"><span data-stu-id="251fc-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="251fc-156">OnlineMeetings.Read.All</span><span class="sxs-lookup"><span data-stu-id="251fc-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="251fc-157">Прочитать сведения о собрании по сети (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="251fc-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="251fc-158">Позволяет приложению читать сведения о собрании по сети в вашей организации без пользователя, выписав учетные данные.</span><span class="sxs-lookup"><span data-stu-id="251fc-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="251fc-159">Расписание</span><span class="sxs-lookup"><span data-stu-id="251fc-159">Schedule</span></span>

<span data-ttu-id="251fc-160">Затем запланировать Teams с координатами видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="251fc-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="251fc-161">Включенный пользователь может планировать собрания команд с помощью:</span><span class="sxs-lookup"><span data-stu-id="251fc-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="251fc-162">Teams Надстройка собрания для Outlook</span><span class="sxs-lookup"><span data-stu-id="251fc-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="251fc-163">Teams для настольных компьютеров и мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="251fc-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="251fc-164">Join</span><span class="sxs-lookup"><span data-stu-id="251fc-164">Join</span></span>

<span data-ttu-id="251fc-165">Вы можете присоединиться Teams к собраниям с помощью устройств VTC следующими способами:</span><span class="sxs-lookup"><span data-stu-id="251fc-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="251fc-166">IVR (интерактивный голосовой ответ)</span><span class="sxs-lookup"><span data-stu-id="251fc-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="251fc-167">Вы можете позвонить в IVR партнера с помощью tenantkey@domain.</span><span class="sxs-lookup"><span data-stu-id="251fc-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="251fc-168">Когда вы станете партнером IVR, вам будет предложено ввести VTC conferenceId, который подключит вас к Teams собранию.</span><span class="sxs-lookup"><span data-stu-id="251fc-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="251fc-169">Прямой набор номера</span><span class="sxs-lookup"><span data-stu-id="251fc-169">Direct dial</span></span>
    - <span data-ttu-id="251fc-170">Вы можете напрямую Teams собрание, не взаимодействуя с IVR партнера, используя функцию прямого набора номера, используя полную строку клиента. VTC ConferenceId@domain.</span><span class="sxs-lookup"><span data-stu-id="251fc-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="251fc-171">Телефонная связь с одним касанием</span><span class="sxs-lookup"><span data-stu-id="251fc-171">One-touch dial</span></span>
    - <span data-ttu-id="251fc-172">Если у вас встроенная Teams, вы можете использовать функции набора одним касанием, предлагаемые партнером (без необходимости ввести строку набора).</span><span class="sxs-lookup"><span data-stu-id="251fc-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="251fc-173">Наконец, вы Teams участвовать в собраниях с помощью аудио- и видеосвязи, а также обмена содержимым.</span><span class="sxs-lookup"><span data-stu-id="251fc-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span>