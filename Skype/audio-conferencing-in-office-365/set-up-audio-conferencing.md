---
title: "Настройка аудиоконференций в Skype для бизнеса и Microsoft Teams"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
- LIL_Placement
description: "Узнайте, как для настройки конференц-связи или аудио для пользователей в вашей организации, которым необходимо присоединиться к конференции с помощью телефона. "
ms.openlocfilehash: fd427abf14d3d705bc9f846f32a27d9be62967e8
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2018
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a><span data-ttu-id="08dcf-103">Настройка аудиоконференций в Skype для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="08dcf-103">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>

<span data-ttu-id="08dcf-104">В некоторых случаях пользователям в организации требуется телефон, чтобы присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="08dcf-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="08dcf-105">Скайп для бизнеса и группами Майкрософт включить функцию аудиоконференций для только что этой ситуации!</span><span class="sxs-lookup"><span data-stu-id="08dcf-105">Skype for Business and Microsoft Teams include the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="08dcf-106">Люди могут вызывать в Скайп для бизнеса или группами Майкрософт собраний с помощью телефона, вместо использования Скайп для бизнеса или группами Майкрософт приложения на мобильном устройстве или Компьютере.</span><span class="sxs-lookup"><span data-stu-id="08dcf-106">People can call in to Skype for Business or Microsoft Teams meetings using a phone, instead of using the Skype for Business or Microsoft Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="08dcf-107">Необходимо настроить звук конференц-связи для пользователей, которые планируется расписание или привести собрания.</span><span class="sxs-lookup"><span data-stu-id="08dcf-107">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="08dcf-108">Участники собрания присоединяются к не требуется никаких лицензий на их или другие программы установки.</span><span class="sxs-lookup"><span data-stu-id="08dcf-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="08dcf-109">Часто задаваемые вопросы о конференц-связи звук в разделе [распространенные вопросы аудио конференц-связи](audio-conferencing-common-questions.md).</span><span class="sxs-lookup"><span data-stu-id="08dcf-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>
  
## <a name="step-1-buy-and-assign-licenses"></a><span data-ttu-id="08dcf-110">Шаг 1. Покупка и назначение лицензий</span><span class="sxs-lookup"><span data-stu-id="08dcf-110">Step 1: Buy and assign licenses</span></span>
<span data-ttu-id="08dcf-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="08dcf-111"></span></span>

<span data-ttu-id="08dcf-112">Должны быть [роли администраторов об Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) для выполнения этого шага.</span><span class="sxs-lookup"><span data-stu-id="08dcf-112">You must be an [About Office 365 admin roles](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform this step.</span></span>
  
1. <span data-ttu-id="08dcf-113">Узнайте, доступен ли звук конференц-связи в Office 365 в вашей стране или регионе.</span><span class="sxs-lookup"><span data-stu-id="08dcf-113">Find out if Audio Conferencing in Office 365 is available in your country/region.</span></span> <span data-ttu-id="08dcf-114">[Доступность страны и региона для конференц-связи аудио и вызов планов](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="08dcf-114">[Country and region availability for Audio Conferencing and Calling Plans](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> 
    
2. <span data-ttu-id="08dcf-115">Узнайте, какие лицензии, которые необходимо купить для конференц-связи звук, и они будут затратами.</span><span class="sxs-lookup"><span data-stu-id="08dcf-115">Learn which licenses you need to buy for Audio Conferencing, and how much they will cost.</span></span> <span data-ttu-id="08dcf-116">Просмотреть [Скайп для бизнеса и группами Майкрософт дополнительный компонент лицензирования](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)и приобрести лицензии.</span><span class="sxs-lookup"><span data-stu-id="08dcf-116">See [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md), and buy the licenses.</span></span> 
    
3. <span data-ttu-id="08dcf-117">[Назначение и удаление лицензий на Office 365 для бизнеса](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) , приобретенных для пользователей в вашей организации, которые будет расписание или ведущий сотрудник собраний.</span><span class="sxs-lookup"><span data-stu-id="08dcf-117">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
4. <span data-ttu-id="08dcf-118">Если вы приобрели лицензии дополнительный компонент **Звук конференц-связи** и коммуникаций кредитов лицензии, назначьте их слишком.</span><span class="sxs-lookup"><span data-stu-id="08dcf-118">If you purchased **Audio Conferencing** add-on licenses and Communications Credits licenses, assign them too.</span></span> <span data-ttu-id="08dcf-119">Сведения содержатся в разделе [Назначение Скайп для бизнеса и группами Майкрософт лицензий](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="08dcf-119">For instructions, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
    
## <a name="step-2-decide-on-your-audio-conferencing-provider"></a><span data-ttu-id="08dcf-120">Шаг 2: Выбор в поставщике аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="08dcf-120">Step 2: Decide on your audio conferencing provider</span></span>
<span data-ttu-id="08dcf-121"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="08dcf-121"></span></span>

<span data-ttu-id="08dcf-122">Поставщика аудиоконференций предоставляет *звукового конференц-канала*.</span><span class="sxs-lookup"><span data-stu-id="08dcf-122">An audio conferencing provider supplies an *audio conferencing bridge*.</span></span> <span data-ttu-id="08dcf-123">Мост конференц-связи задает телефонные номера телефонов, контакты и конференции идентификаторы для собраний.</span><span class="sxs-lookup"><span data-stu-id="08dcf-123">The conferencing bridge sets your dial-in phone numbers, PINs, and conference IDs for meetings.</span></span> <span data-ttu-id="08dcf-124">Принятие решения об использовании Майкрософт или стороннего поставщика:</span><span class="sxs-lookup"><span data-stu-id="08dcf-124">Decide whether to use Microsoft or a third-party audio conferencing provider:</span></span>
  
> [!NOTE]
> <span data-ttu-id="08dcf-125">Группами Майкрософт пользователи не могут пользовательского поставщика аудиоконференций сторонних производителей.</span><span class="sxs-lookup"><span data-stu-id="08dcf-125">Microsoft Teams users can't user a third-party audio conferencing provider.</span></span> 
  
- <span data-ttu-id="08dcf-126">**Microsoft в качестве поставщика аудиоконференций**: простой решение для аудиоконференций, выберите Microsoft в качестве поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="08dcf-126">**Microsoft as your audio conferencing provider**: If you want the easiest solution for audio conferencing, choose Microsoft as your audio conferencing provider.</span></span>
    
- <span data-ttu-id="08dcf-127">**Третья сторона в качестве поставщика аудиоконференций**: Если вы находитесь в стране, где аудиоконференций в Office 365 недоступен, качество службы не будет замечательных из-за его местоположение или у вас есть существующий контракт, выберите звук сторонних производителей Поставщик конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="08dcf-127">**Third party as your audio conferencing provider**: If you are in a country where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract, choose a third-party audio conferencing provider.</span></span> <span data-ttu-id="08dcf-128">Чтобы найти поставщика, перейдите к [Microsoft точно указать](http://go.microsoft.com/fwlink/?LinkId=797530).</span><span class="sxs-lookup"><span data-stu-id="08dcf-128">To find a provider, go to [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).</span></span>
    
> [!TIP]
> <span data-ttu-id="08dcf-129">В организации разные пользователи могут использовать разных поставщиков аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="08dcf-129">In your organization, you can have some people who use Microsoft as their audio conferencing provider, and others who use a third-party provider.</span></span> <span data-ttu-id="08dcf-130">Однако это будет более сложным, можно настроить и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="08dcf-130">But this will be more complicated for you to set up and manage.</span></span> 
  
<span data-ttu-id="08dcf-131">Подробное сравнение Microsoft в качестве звукового поставщика и стороннего поставщика [аудиоконференций поставщиков](compare-audio-conferencing-providers.md)сравнить.</span><span class="sxs-lookup"><span data-stu-id="08dcf-131">For a detailed comparison between Microsoft as your audio provider and a third-party provider, see [Compare audio conferencing providers](compare-audio-conferencing-providers.md).</span></span> 
  
## <a name="step-3-assign-the-audio-conferencing-provider-to-people-who-lead-or-schedule-meetings"></a><span data-ttu-id="08dcf-132">Шаг 3: Назначение поставщика аудиоконференций людям, которые привести или планировать собрания</span><span class="sxs-lookup"><span data-stu-id="08dcf-132">Step 3: Assign the audio conferencing provider to people who lead or schedule meetings</span></span>
<span data-ttu-id="08dcf-133"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="08dcf-133"></span></span>

<span data-ttu-id="08dcf-134">Теперь, когда вы решили в поставщике аудиоконференций, им необходимо назначить поставщика для пользователей в вашей организации, привести или планировать собрания.</span><span class="sxs-lookup"><span data-stu-id="08dcf-134">Now that you've decided on your audio conferencing provider, you need to assign the provider to people in your organization who lead or schedule meetings.</span></span> <span data-ttu-id="08dcf-135">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="08dcf-135">Do one of the following:</span></span> 
  
- <span data-ttu-id="08dcf-136">[Назначение Microsoft в качестве поставщика аудиоконференций](assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="08dcf-136">[Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
    
- <span data-ttu-id="08dcf-137">[Назначение независимых производителей в качестве поставщика аудиоконференций](assign-a-third-party-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="08dcf-137">[Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md).</span></span>
    
## <a name="step-4-set-up-meeting-invitations"></a><span data-ttu-id="08dcf-138">Шаг 4: Настройка приглашения на собрания</span><span class="sxs-lookup"><span data-stu-id="08dcf-138">Step 4: Set up meeting invitations</span></span>
<span data-ttu-id="08dcf-139"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="08dcf-139"></span></span>

<span data-ttu-id="08dcf-140">Следующие шаги являются **необязательными**, однако их следует выполнять как много администраторов:</span><span class="sxs-lookup"><span data-stu-id="08dcf-140">The following steps are **optional**, but a lot of admins like to do them:</span></span>
  
1. <span data-ttu-id="08dcf-141">[Настройка приглашения на собрания](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span><span class="sxs-lookup"><span data-stu-id="08dcf-141">[Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span> <span data-ttu-id="08dcf-142">Номеру телефона, задайте для пользователя будет автоматически добавляется в приглашения на собрания, отправляемые участникам.</span><span class="sxs-lookup"><span data-stu-id="08dcf-142">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to attendees.</span></span> <span data-ttu-id="08dcf-143">Тем не менее можно добавить свои собственные справки и юридических ссылок, текстовое сообщение и рисунок небольшого предприятия.</span><span class="sxs-lookup"><span data-stu-id="08dcf-143">However, you can add your own help and legal links, a text message, and small company graphic.</span></span>
    
2. <span data-ttu-id="08dcf-144">[Набор номера телефона аудиоконференции для организации, которые включены в приглашения на собрания](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="08dcf-144">[Set the Audio Conferencing phone numbers for meeting organizers that are included on invites](set-the-phone-numbers-included-on-invites.md).</span></span> <span data-ttu-id="08dcf-145">Это номер телефона, который будет отображаться в собрание, запланированное для пользователя.</span><span class="sxs-lookup"><span data-stu-id="08dcf-145">This is the phone number that will show up in the meeting that is scheduled by the user.</span></span>
    
3. <span data-ttu-id="08dcf-146">[Задайте auto attendant языков звукового конференц-связи](set-auto-attendant-languages-for-audio-conferencing.md) , автосекретаря аудиоконференций для приветствовать абонента, когда они звонить на номер телефона аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="08dcf-146">[Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md) that the audio conferencing auto attendant uses to greet a caller when they dial in to an Audio Conferencing phone number.</span></span> <span data-ttu-id="08dcf-147">Этот шаг применяется только в том случае, если вы используете Microsoft как звука поставщика.</span><span class="sxs-lookup"><span data-stu-id="08dcf-147">This step only applies if you're using Microsoft as your audio provider.</span></span>
    
4. <span data-ttu-id="08dcf-148">[Задать длину ПИН-кода для собраний аудио конференц-связи](set-the-pin-length-for-audio-conferencing-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="08dcf-148">[Set the length of the PIN for Audio Conferencing meetings](set-the-pin-length-for-audio-conferencing-meetings.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="08dcf-149">Этот компонент еще не доступен для клиентов с помощью Office 365 обслуживается 21Vianet в Китае.</span><span class="sxs-lookup"><span data-stu-id="08dcf-149">This feature is not yet available to customers using Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="08dcf-150">[Дополнительные сведения об Office 365, которой с 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE)Дополнительные сведения см.</span><span class="sxs-lookup"><span data-stu-id="08dcf-150">To learn more, see [Learn about Office 365 operated by 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE).</span></span> 
  
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="08dcf-151">See also</span><span class="sxs-lookup"><span data-stu-id="08dcf-151">Related topics</span></span>

[<span data-ttu-id="08dcf-152">Общие вопросы по аудиоконференциям</span><span class="sxs-lookup"><span data-stu-id="08dcf-152">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
  
[<span data-ttu-id="08dcf-153">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="08dcf-153">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="08dcf-154">Номера телефонов для аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="08dcf-154">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="08dcf-155">Установка параметров собраний по сети и конференц-связь</span><span class="sxs-lookup"><span data-stu-id="08dcf-155">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)

