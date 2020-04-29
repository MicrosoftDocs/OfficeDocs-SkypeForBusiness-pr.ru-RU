---
title: Настройка взаимодействия Microsoft Teams с облачными видеослужбами
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: В этой статье объясняется, как спланировать и настроить облачную видеосвязь для пользователей в вашей организации.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e937e7825000d02156c1f5ede2671711006cbdd
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825107"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="89261-103">Настройка взаимодействия Microsoft Teams с облачными видеослужбами</span><span class="sxs-lookup"><span data-stu-id="89261-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="89261-104">После [выбора партнеров по облачной](cloud-video-interop.md)видеосвязи вам потребуется планирование развертывания, Настройка с помощью сведений о подготовке и ключа клиента-партнера, а также согласие на работу с приложением для видеосвязи в Организации.</span><span class="sxs-lookup"><span data-stu-id="89261-104">After you have [chosen your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="89261-105">На приведенной ниже схеме описан процесс.</span><span class="sxs-lookup"><span data-stu-id="89261-105">The following diagram outlines the process.</span></span> 

![Развертывание CVI в Организации](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="89261-107">Планирование</span><span class="sxs-lookup"><span data-stu-id="89261-107">Plan</span></span>

<span data-ttu-id="89261-108">Сведения о том, как идентифицировать партнера или партнеров для использования в вашей организации, можно найти в разделе [облачное видео взаимодействие для Microsoft Teams](cloud-video-interop.md) .</span><span class="sxs-lookup"><span data-stu-id="89261-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="89261-109">Для планирования включения на уровне пользователей (параллельных и на всех сайтах) выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="89261-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="89261-110">Выбор модели развертывания или размещенной модели для использования</span><span class="sxs-lookup"><span data-stu-id="89261-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="89261-111">Выберите план лицензирования, оптимальный для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="89261-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="89261-112">Планирование мощности виртуальных машин — вы размещаете свою видеоинфраструктуру.</span><span class="sxs-lookup"><span data-stu-id="89261-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="89261-113">Настройка</span><span class="sxs-lookup"><span data-stu-id="89261-113">Configure</span></span> 

<span data-ttu-id="89261-114">Чтобы настроить облачное видеовзаимодействие, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="89261-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="89261-115">Получение сведений о конфигурации между выбранными партнерами и партнерами (ключ клиента, appIds...).</span><span class="sxs-lookup"><span data-stu-id="89261-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="89261-116">Вы можете использовать одного или нескольких партнеров по видеосвязи в Организации</span><span class="sxs-lookup"><span data-stu-id="89261-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="89261-117">Убедитесь, что сеть настроена правильно.</span><span class="sxs-lookup"><span data-stu-id="89261-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="89261-118">Настройте брандмауэр на основе стандартов видеосвязи, чтобы обеспечить поддержку обхода сети периметра.</span><span class="sxs-lookup"><span data-stu-id="89261-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="89261-119">Например:</span><span class="sxs-lookup"><span data-stu-id="89261-119">For example:</span></span> 
    - <span data-ttu-id="89261-120">Cisco VCS-e</span><span class="sxs-lookup"><span data-stu-id="89261-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="89261-121">Polycom RPAD</span><span class="sxs-lookup"><span data-stu-id="89261-121">Polycom RPAD</span></span>

3. <span data-ttu-id="89261-122">Настройка Объединенных комнат с помощью Exchange и OTD.</span><span class="sxs-lookup"><span data-stu-id="89261-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="89261-123">В большинстве случаев необходимо настроить и настроить в среде дополнительный ретранслятор.</span><span class="sxs-lookup"><span data-stu-id="89261-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="89261-124">Обеспечения</span><span class="sxs-lookup"><span data-stu-id="89261-124">Provision</span></span>
 
<span data-ttu-id="89261-125">Ключ клиента будет использоваться для связи со службой Partner.</span><span class="sxs-lookup"><span data-stu-id="89261-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="89261-126">В следующем примере 813878896@t.plcm.vc — ключ клиента.</span><span class="sxs-lookup"><span data-stu-id="89261-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![Пример ключа клиента](media/tenant-key-example.png) 

<span data-ttu-id="89261-128">Для подготовки ключа клиента вам потребуется выполнить следующие командлеты, а также включить функцию выбора пользователей или всей Организации для создания собраний с помощью координат видеовзаимодействия.</span><span class="sxs-lookup"><span data-stu-id="89261-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="89261-129">\*\* [Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):\*\* Корпорация Майкрософт предоставляет предварительно созданные политики для каждого из наших поддерживаемых партнеров, которые позволят вам назначать партнеров, которые используются для облачной видеобеседы.</span><span class="sxs-lookup"><span data-stu-id="89261-129">**[Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="89261-130">Этот командлет позволяет определить готовые политики, которые можно использовать в Организации.</span><span class="sxs-lookup"><span data-stu-id="89261-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="89261-131">Вы можете назначить эту политику для одного или нескольких пользователей, использующих командлет Grant-CsTeamsVideoInteropServicePolicy.</span><span class="sxs-lookup"><span data-stu-id="89261-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="89261-132">\*\* [Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):\*\* Командлет Grant-CsTeamsVideoInteropServicePolicy позволяет назначать уже созданную политику для использования в организации или назначать ее конкретным пользователям.</span><span class="sxs-lookup"><span data-stu-id="89261-132">**[Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="89261-133">\*\* [New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):\*\* С помощью New-CsVideoInteropServiceProvider вы можете указать сведения о поддерживаемом партнере CVI, который вы хотели бы использовать в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="89261-133">**[New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="89261-134">\*\* [Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):\*\* С помощью Set-CsVideoInteropServiceProvider можно обновить сведения о поддерживаемом партнере CVI, который использует ваша организация.</span><span class="sxs-lookup"><span data-stu-id="89261-134">**[Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="89261-135">\*\* [Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):\*\* Получение всех поставщиков, настроенных для использования в Организации.</span><span class="sxs-lookup"><span data-stu-id="89261-135">**[Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="89261-136">\*\* [Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):\*\* С помощью Remove-CsVideoInteropServiceProvider удалите все сведения о поставщике, которые больше не используются вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="89261-136">**[Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="89261-137">Согласны</span><span class="sxs-lookup"><span data-stu-id="89261-137">Consent</span></span>

<span data-ttu-id="89261-138">Чтобы присоединиться к собраниям Организации с помощью службы Partner Service, вам потребуется разрешение на предоставление разрешений для мобильных устройств с видеоконференциями (VTCs).</span><span class="sxs-lookup"><span data-stu-id="89261-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="89261-139">Эта ссылка на согласие также будет предоставлена вашим партнером.</span><span class="sxs-lookup"><span data-stu-id="89261-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="89261-140">После выполнения этих действий пользователи, которые по отдельности включаются с помощью командлета Grant выше, или всех пользователей в Организации, если они включены, получат VTCные координаты во всех собраниях Teams, которые они расписаний.</span><span class="sxs-lookup"><span data-stu-id="89261-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="89261-141">Любые VTC могут присоединиться к собраниям с помощью этих координат.</span><span class="sxs-lookup"><span data-stu-id="89261-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="89261-142">Имя</span><span class="sxs-lookup"><span data-stu-id="89261-142">Name</span></span>|<span data-ttu-id="89261-143">Краткое описание разрешения приложения</span><span class="sxs-lookup"><span data-stu-id="89261-143">Application Permission Short Description</span></span>| <span data-ttu-id="89261-144">Описание</span><span class="sxs-lookup"><span data-stu-id="89261-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="89261-145">Calls. JoinGroupCall. ALL</span><span class="sxs-lookup"><span data-stu-id="89261-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="89261-146">Присоединение групповых звонков и собраний в виде приложения (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="89261-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="89261-147">Позволяет приложению присоединиться к групповой связи и запланированным собраниям в вашей организации без пользователя, выполнившего вход.</span><span class="sxs-lookup"><span data-stu-id="89261-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="89261-148">Приложение будет объединено с правами пользователя каталога на собрания в вашем клиенте.</span><span class="sxs-lookup"><span data-stu-id="89261-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="89261-149">Calls. JoinGroupCallasGuest. ALL</span><span class="sxs-lookup"><span data-stu-id="89261-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="89261-150">Присоединение групповых звонков и собраний в качестве гостевых пользователей (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="89261-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="89261-151">Позволяет приложению анонимно присоединять групповые звонки и запланированные собрания в Организации без пользователя, выполнившего вход.</span><span class="sxs-lookup"><span data-stu-id="89261-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="89261-152">Приложение будет объединено в качестве гостя для собраний в вашем клиенте.</span><span class="sxs-lookup"><span data-stu-id="89261-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="89261-153">Calls. AccessMedia. ALL</span><span class="sxs-lookup"><span data-stu-id="89261-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="89261-154">Получение доступа к потокам мультимедиа во время звонка в виде приложения (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="89261-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="89261-155">Позволяет приложению получать прямой доступ к потокам мультимедиа во время звонка без пользователя, выполнившего вход.</span><span class="sxs-lookup"><span data-stu-id="89261-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="89261-156">OnlineMeetings. Read. ALL</span><span class="sxs-lookup"><span data-stu-id="89261-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="89261-157">Чтение сведений о собрании по сети (ознакомительная версия)</span><span class="sxs-lookup"><span data-stu-id="89261-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="89261-158">Позволяет приложению читать сведения о собрании по сети в вашей организации без пользователя, выполнившего вход.</span><span class="sxs-lookup"><span data-stu-id="89261-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="89261-159">Задание</span><span class="sxs-lookup"><span data-stu-id="89261-159">Schedule</span></span>

<span data-ttu-id="89261-160">Затем запланируйте собрание группы с помощью координат видеовзаимодействия.</span><span class="sxs-lookup"><span data-stu-id="89261-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="89261-161">Включенный пользователь может планировать собрания Teams с помощью:</span><span class="sxs-lookup"><span data-stu-id="89261-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="89261-162">Надстройка "собрание Teams для Outlook"</span><span class="sxs-lookup"><span data-stu-id="89261-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="89261-163">Клиент Teams для настольных ПК и мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="89261-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="89261-164">Join</span><span class="sxs-lookup"><span data-stu-id="89261-164">Join</span></span>

<span data-ttu-id="89261-165">Вы можете присоединиться к собраниям Teams с устройствами VTC следующими способами:</span><span class="sxs-lookup"><span data-stu-id="89261-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="89261-166">Интерактивный автоответчик (интерактивный голосовой отклик)</span><span class="sxs-lookup"><span data-stu-id="89261-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="89261-167">Вы можете звонить на интерактивный автоответчик партнера с помощью tenantkey@domain.</span><span class="sxs-lookup"><span data-stu-id="89261-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="89261-168">После того как вы войдете в интерактивный автоответчик партнера, вам будет предложено ввести VTC conferenceId, после чего вы сможете подключиться к собранию Teams.</span><span class="sxs-lookup"><span data-stu-id="89261-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="89261-169">Прямой набор номера</span><span class="sxs-lookup"><span data-stu-id="89261-169">Direct dial</span></span>
    - <span data-ttu-id="89261-170">Вы можете напрямую звонить на собрание Teams без взаимодействия с интерактивный автоответчик партнера с помощью функции прямого набора номера с помощью полной строки tenantkey. VTC ConferenceId@domain.</span><span class="sxs-lookup"><span data-stu-id="89261-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="89261-171">Один сенсорный Звонок</span><span class="sxs-lookup"><span data-stu-id="89261-171">One-touch dial</span></span>
    - <span data-ttu-id="89261-172">Если вы используете объединенную комнату рабочих групп, вы можете использовать возможности набора номера, предложенные вашим партнером (без ввода строки набора номера).</span><span class="sxs-lookup"><span data-stu-id="89261-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="89261-173">Наконец, с помощью звука, видео и совместного использования контента можно привлекать пользователей Teams к вашим собраниям.</span><span class="sxs-lookup"><span data-stu-id="89261-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span> 
