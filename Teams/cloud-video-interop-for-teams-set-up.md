---
title: Настройка взаимодействия облачных видео для групп Майкрософт
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: srividhc
description: В этой статье объясняется, как планирование и настройка взаимодействия видео облаке для пользователей в вашей организации.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b51bcd5cd5813c317c79a5f89656e11423d91412
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462542"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="ae148-103">Настройка взаимодействия облачных видео для групп Майкрософт</span><span class="sxs-lookup"><span data-stu-id="ae148-103">Set up Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="ae148-104">После того как [выбранных на вашей партнерами видео взаимодействия облаке](cloud-video-interop.md)необходимо спланировать развертывание, Настройка get подготовки содержатся дополнительные сведения и ключу клиента партнеров и разрешения для видео взаимодействия приложений в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ae148-104">After you have [chosen on your Cloud Video Interop partner(s)](cloud-video-interop.md), you will need to plan your deployment, get set up with provisioning details and partner tenant key, and consent to the video interop app in your organization.</span></span> <span data-ttu-id="ae148-105">Ниже описывается процесс.</span><span class="sxs-lookup"><span data-stu-id="ae148-105">The following diagram outlines the process.</span></span> 

![Развертывание CVI в организации](media/deploying-cvi.png)

## <a name="plan"></a><span data-ttu-id="ae148-107">Планирование</span><span class="sxs-lookup"><span data-stu-id="ae148-107">Plan</span></span>

<span data-ttu-id="ae148-108">См [Облачных взаимодействие видео для групп Майкрософт](cloud-video-interop.md) сведения об идентификации партнера или партнеров для использования в организации.</span><span class="sxs-lookup"><span data-stu-id="ae148-108">See [Cloud Video Interop for Microsoft Teams](cloud-video-interop.md) for information about identifying a partner or partners to use in your organization.</span></span> 

<span data-ttu-id="ae148-109">Чтобы спланировать широкий Включение пользователей на основе и одновременно/сайтов:</span><span class="sxs-lookup"><span data-stu-id="ae148-109">To plan for user based/concurrent/site wide enablement:</span></span> 

- <span data-ttu-id="ae148-110">Выбрать модель/сервер модели развертывания для использования</span><span class="sxs-lookup"><span data-stu-id="ae148-110">Pick a deployment model/hosted model for your use</span></span>
- <span data-ttu-id="ae148-111">Выберите план лицензирования идеально подходит для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ae148-111">Select the license plan ideal for your organization.</span></span> 
- <span data-ttu-id="ae148-112">Планирование загрузки виртуальных машин является вы разместили инфраструктуры видео.</span><span class="sxs-lookup"><span data-stu-id="ae148-112">Plan for capacity of VMs is you are hosting your video infrastructure.</span></span>

## <a name="configure"></a><span data-ttu-id="ae148-113">Настройка</span><span class="sxs-lookup"><span data-stu-id="ae148-113">Configure</span></span> 

<span data-ttu-id="ae148-114">Чтобы настроить взаимодействие видео облако, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ae148-114">To configure Cloud Video Interop, follow these steps.</span></span> 

1. <span data-ttu-id="ae148-115">Получите сведения о конфигурации из партнеров и партнерами, у вас есть выбранной (ключу клиента, коды...).</span><span class="sxs-lookup"><span data-stu-id="ae148-115">Obtain configuration info from the partner/partners you have chosen (tenant key, appIds…).</span></span> <span data-ttu-id="ae148-116">Можно использовать один или несколько видео взаимодействия партнеров в вашей организации</span><span class="sxs-lookup"><span data-stu-id="ae148-116">You can use one or more video interop partners in your organization</span></span> 

2. <span data-ttu-id="ae148-117">Убедитесь, что сеть настроена правильно.</span><span class="sxs-lookup"><span data-stu-id="ae148-117">Ensure that your network is configured correctly.</span></span> <span data-ttu-id="ae148-118">Настройка основанный на стандартах видео брандмауэра для обхода сети периметра для поддержки.</span><span class="sxs-lookup"><span data-stu-id="ae148-118">Configure your standards-based video firewall for perimeter network traversal to support.</span></span> <span data-ttu-id="ae148-119">Например:</span><span class="sxs-lookup"><span data-stu-id="ae148-119">For example:</span></span> 
    - <span data-ttu-id="ae148-120">Cisco Каналах e</span><span class="sxs-lookup"><span data-stu-id="ae148-120">Cisco VCS-e</span></span>                  
    - <span data-ttu-id="ae148-121">Polycom RPAD</span><span class="sxs-lookup"><span data-stu-id="ae148-121">Polycom RPAD</span></span>

3. <span data-ttu-id="ae148-122">Настройка интегрированной комнат с exchange и OTD.</span><span class="sxs-lookup"><span data-stu-id="ae148-122">Configure integrated rooms with exchange and OTD.</span></span> <span data-ttu-id="ae148-123">В большинстве случаев дополнительные ретрансляции потребуется настроить и настроен в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="ae148-123">In most cases, additional relay would need to be set up and configured in your environment.</span></span>


## <a name="provision"></a><span data-ttu-id="ae148-124">Подготовка к работе</span><span class="sxs-lookup"><span data-stu-id="ae148-124">Provision</span></span>
 
<span data-ttu-id="ae148-125">Ключу клиента будут исходящего подключения к службе партнера.</span><span class="sxs-lookup"><span data-stu-id="ae148-125">The tenant key will be the dial out to the partner service.</span></span> <span data-ttu-id="ae148-126">В следующем примере 813878896@t.plcm.vc — ключ клиента.</span><span class="sxs-lookup"><span data-stu-id="ae148-126">In the following example, 813878896@t.plcm.vc is the tenant key.</span></span> 

![Пример ключа клиента](media/tenant-key-example.png) 

<span data-ttu-id="ae148-128">Необходимо выполнить следующие командлеты для подготовки ключу клиента, а также обеспечивают создание собраний с видео взаимодействия координаты окно выбора пользователей или всей организации.</span><span class="sxs-lookup"><span data-stu-id="ae148-128">You will need to execute the following cmdlets to provision the tenant key, and also enable select users or your whole organization to create meetings with video interop coordinates.</span></span>

 
- <span data-ttu-id="ae148-129">\*\* [Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):\*\* Корпорация Майкрософт предоставляет предварительно построенного политик для каждого из наших поддерживаемые партнеров, которые позволяют назначить которого партнерами для облачных видео взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="ae148-129">**[Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for cloud video interop.</span></span>

    <span data-ttu-id="ae148-130">Этот командлет позволяет определить предварительно построенного политик, которые можно использовать в организации.</span><span class="sxs-lookup"><span data-stu-id="ae148-130">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="ae148-131">Один или несколько пользователей использование командлета Grant-CsTeamsVideoInteropServicePolicy можно назначить эту политику.</span><span class="sxs-lookup"><span data-stu-id="ae148-131">You can assign this policy to one or more of your users leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
 
- <span data-ttu-id="ae148-132">\*\* [Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):\*\* Командлет Grant-CsTeamsVideoInteropServicePolicy позволяет назначить предварительно построенного политику для использования в вашей организации или назначьте политику к определенным пользователям.</span><span class="sxs-lookup"><span data-stu-id="ae148-132">**[Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** The Grant-CsTeamsVideoInteropServicePolicy cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
 
- <span data-ttu-id="ae148-133">\*\* [Новый CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):\*\* Используйте New-CsVideoInteropServiceProvider, чтобы указать сведения о поддерживаемых CVI партнеров, вашей организации требуется использовать.</span><span class="sxs-lookup"><span data-stu-id="ae148-133">**[New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** Use the New-CsVideoInteropServiceProvider to specify information about a supported CVI partner your organization would like to use.</span></span>
 
- <span data-ttu-id="ae148-134">\*\* [Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):\*\* Set-CsVideoInteropServiceProvider используется для обновления сведений о поддерживаемых CVI партнеров, используемых вашей организацией.</span><span class="sxs-lookup"><span data-stu-id="ae148-134">**[Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** Use the Set-CsVideoInteropServiceProvider to update information about a supported CVI partner your organization uses.</span></span>
 
- <span data-ttu-id="ae148-135">\*\* [Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):\*\* Получение всех поставщиков, которые были настроены для использования в организации.</span><span class="sxs-lookup"><span data-stu-id="ae148-135">**[Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** Get all of the providers that have been configured for use within the organization.</span></span>
 
- <span data-ttu-id="ae148-136">\*\* [Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):\*\* Командлет Remove-CsVideoInteropServiceProvider для удаления все сведения о поставщике о поставщике, который больше не используется в организации.</span><span class="sxs-lookup"><span data-stu-id="ae148-136">**[Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider to remove all provider information about a provider that your organization no longer uses.</span></span>  
 
## <a name="consent"></a><span data-ttu-id="ae148-137">Разрешения</span><span class="sxs-lookup"><span data-stu-id="ae148-137">Consent</span></span>

<span data-ttu-id="ae148-138">Необходимо предоставить разрешение разрешения для устройств видеоконференций (VTCs) для присоединения к собраниям вашей организацией через службу партнера.</span><span class="sxs-lookup"><span data-stu-id="ae148-138">You will need to provide permission consent for the video teleconferencing devices (VTCs) to join your organizations meetings via the partner service.</span></span> <span data-ttu-id="ae148-139">Этой ссылке согласия будет предоставляться также партнером.</span><span class="sxs-lookup"><span data-stu-id="ae148-139">This consent link will also be provided by your partner.</span></span>  
 
<span data-ttu-id="ae148-140">После выполнения этих действий пользователей, которым разрешена с помощью командлета Grant выше или всех пользователей в организации по отдельности, если включена клиента, будут иметь координаты VTC в всех собраниях групп, которые они запланировать.</span><span class="sxs-lookup"><span data-stu-id="ae148-140">When these steps are complete, the users who are individually enabled via the Grant cmdlet above, or all of the users in the organization if the tenant is enabled, will have VTC coordinates in all the Teams meetings that they schedule.</span></span> <span data-ttu-id="ae148-141">Любой VTC можно объединить эти собрания при помощи этих координат.</span><span class="sxs-lookup"><span data-stu-id="ae148-141">Any VTC can join these meetings via those coordinates.</span></span>


|<span data-ttu-id="ae148-142">Имя</span><span class="sxs-lookup"><span data-stu-id="ae148-142">Name</span></span>|<span data-ttu-id="ae148-143">Краткое описание разрешений приложения</span><span class="sxs-lookup"><span data-stu-id="ae148-143">Application Permission Short Description</span></span>| <span data-ttu-id="ae148-144">Описание</span><span class="sxs-lookup"><span data-stu-id="ae148-144">Description</span></span>|
|--|--|---|
|<span data-ttu-id="ae148-145">Calls.JoinGroupCall.All</span><span class="sxs-lookup"><span data-stu-id="ae148-145">Calls.JoinGroupCall.All</span></span>|<span data-ttu-id="ae148-146">Присоединяйтесь к сообществу звонки из группы и собраний как приложения (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="ae148-146">Join Group Calls and Meetings as an app (preview)</span></span>|<span data-ttu-id="ae148-147">Позволяет приложениям Присоединяйтесь к сообществу звонки из группы и запланированные собрания в вашей организации без пользователь выполнил вход.</span><span class="sxs-lookup"><span data-stu-id="ae148-147">Allows the app to join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="ae148-148">Приложение будет присоединен с правами пользователя каталог на собрания в вашего клиента.</span><span class="sxs-lookup"><span data-stu-id="ae148-148">The app will be joined with the privileges of a directory user to meetings in your tenant.</span></span>|
|<span data-ttu-id="ae148-149">Calls.JoinGroupCallasGuest.All</span><span class="sxs-lookup"><span data-stu-id="ae148-149">Calls.JoinGroupCallasGuest.All</span></span>|<span data-ttu-id="ae148-150">Присоединение звонки из группы и собрания в качестве гостя пользователя (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="ae148-150">Join Group Calls and Meetings as a guest user (preview)</span></span>|<span data-ttu-id="ae148-151">Позволяет приложениям анонимно присоединиться к звонки из группы и запланированные собрания в вашей организации без пользователь выполнил вход.</span><span class="sxs-lookup"><span data-stu-id="ae148-151">Allows the app to anonymously join group calls and scheduled meetings in your organization, without a signed-in user.</span></span>  <span data-ttu-id="ae148-152">Приложение будет присоединен как гости к собраниям клиента.</span><span class="sxs-lookup"><span data-stu-id="ae148-152">The app will be joined as a guest to meetings in your tenant.</span></span>|
|<span data-ttu-id="ae148-153">Calls.AccessMedia.All</span><span class="sxs-lookup"><span data-stu-id="ae148-153">Calls.AccessMedia.All</span></span>|<span data-ttu-id="ae148-154">Access мультимедийных потоков в вызове как приложения (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="ae148-154">Access media streams in a call as an app (preview)</span></span>|<span data-ttu-id="ae148-155">Позволяет приложение, чтобы получить прямой доступ к мультимедийных потоков в ходе звонка, без пользователь выполнил вход.</span><span class="sxs-lookup"><span data-stu-id="ae148-155">Allows the app to get direct access to media streams in a call, without a signed-in user.</span></span>|
|<span data-ttu-id="ae148-156">OnlineMeetings.Read.All</span><span class="sxs-lookup"><span data-stu-id="ae148-156">OnlineMeetings.Read.All</span></span>|<span data-ttu-id="ae148-157">Сведения о чтения собрание по сети (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="ae148-157">Read Online Meeting details (preview)</span></span>|<span data-ttu-id="ae148-158">Позволяет приложениям для чтения сведений о собрание по сети в вашей организации без пользователь выполнил вход.</span><span class="sxs-lookup"><span data-stu-id="ae148-158">Allows the app to read Online Meeting details in your organization, without a signed-in user.</span></span>|

## <a name="schedule"></a><span data-ttu-id="ae148-159">Расписание</span><span class="sxs-lookup"><span data-stu-id="ae148-159">Schedule</span></span>

<span data-ttu-id="ae148-160">Рассмотрим процедуру планируйте собрания групп с видео взаимодействия координаты.</span><span class="sxs-lookup"><span data-stu-id="ae148-160">Next, schedule Teams meeting with video interop coordinates.</span></span> <span data-ttu-id="ae148-161">Включенные пользователи могут планировать собрания групп с помощью:</span><span class="sxs-lookup"><span data-stu-id="ae148-161">The enabled user can schedule teams meetings via:</span></span>
- [<span data-ttu-id="ae148-162">Команды на собрания надстройки для Outlook</span><span class="sxs-lookup"><span data-stu-id="ae148-162">Teams Meeting add-in for Outlook</span></span>](teams-add-in-for-outlook.md)
- <span data-ttu-id="ae148-163">Группы клиентских настольных компьютеров и мобильных устройств</span><span class="sxs-lookup"><span data-stu-id="ae148-163">Teams client desktop and mobile</span></span>


## <a name="join"></a><span data-ttu-id="ae148-164">Join</span><span class="sxs-lookup"><span data-stu-id="ae148-164">Join</span></span>

<span data-ttu-id="ae148-165">Присоединение к собраниям группами с VTC устройство можно следующими способами:</span><span class="sxs-lookup"><span data-stu-id="ae148-165">You can join Teams meetings with your VTC devices in the following ways:</span></span>
 
- <span data-ttu-id="ae148-166">IVR (интерактивная голосовой ответ)</span><span class="sxs-lookup"><span data-stu-id="ae148-166">IVR (Interactive voice Response)</span></span>
    - <span data-ttu-id="ae148-167">Можно удаленного IVR партнера с помощью tenantkey@domain.</span><span class="sxs-lookup"><span data-stu-id="ae148-167">You can dial in to the partner's IVR using the tenantkey@domain.</span></span> 
    - <span data-ttu-id="ae148-168">После перехода в партнера IVR, будет предложено ввести conferenceId VTC, в которой будет затем установлено соединение собрания групп.</span><span class="sxs-lookup"><span data-stu-id="ae148-168">Once you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="ae148-169">Прямой</span><span class="sxs-lookup"><span data-stu-id="ae148-169">Direct dial</span></span>
    - <span data-ttu-id="ae148-170">Позвонить в собрание группы можно напрямую без взаимодействия с IVR партнера с помощью прямой компонент с помощью полной строки tenantkey. VTC ConferenceId@domain.</span><span class="sxs-lookup"><span data-stu-id="ae148-170">You can directly dial into the Teams meeting without interacting with the partner’s IVR by using the direct dial feature using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="ae148-171">Номера одним нажатием</span><span class="sxs-lookup"><span data-stu-id="ae148-171">One-touch dial</span></span>
    - <span data-ttu-id="ae148-172">При наличии интегрированной комнаты групп, можно использовать одним нажатием телефонным возможности, предоставляемые партнеру (без необходимости введите любую строку звонков).</span><span class="sxs-lookup"><span data-stu-id="ae148-172">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

<span data-ttu-id="ae148-173">И, наконец взаимодействовать с группами пользователей в собраниях, аудио, видео и содержимого совместного использования.</span><span class="sxs-lookup"><span data-stu-id="ae148-173">Finally, engage with Teams users in your meetings using audio, video, and content sharing.</span></span> 