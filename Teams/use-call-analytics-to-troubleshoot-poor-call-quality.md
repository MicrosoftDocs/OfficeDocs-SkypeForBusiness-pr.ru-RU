---
title: Использование аналитики звонков для устранения проблем с качеством звонка
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 03/08/2019
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service:
- skype-for-business-online
- msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
ms.custom:
- Reporting
description: Используйте вызова анализа сведений о устройств, сети и подключения к для диагностики проблем пользователей с группами Майкрософт и Скайп для собраний и вызовы бизнеса.
ms.openlocfilehash: b020ae52b9cb7906484c6a0a5403e626ebab68a8
ms.sourcegitcommit: f3b41e7abafc84571bd9e8267d41decc0fe78e4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2019
ms.locfileid: "30494239"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a><span data-ttu-id="680d5-103">Использование аналитики звонков для устранения проблем с качеством звонка</span><span class="sxs-lookup"><span data-stu-id="680d5-103">Use Call Analytics to troubleshoot poor call quality</span></span>

<span data-ttu-id="680d5-104">Вызов Analytics призвана помочь в устранении звонка или подключения проблем с группами Майкрософт и Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="680d5-104">Call Analytics helps you troubleshoot call or connection problems with Microsoft Teams and Skype for Business.</span></span> <span data-ttu-id="680d5-105">Аналитика вызова отображаются подробные сведения о устройств, сетей и связи для звонков и собраний с каждого пользователя в учетную запись Office 365.</span><span class="sxs-lookup"><span data-stu-id="680d5-105">Call Analytics shows detailed information about the devices, networks, and connectivity for the calls and meetings of each user in your Office 365 account.</span></span> <span data-ttu-id="680d5-106">Если сборка, веб-сайтов и клиентов добавлена информация для вызова аналитика, он также будет отображаться для каждого вызова и сеанса.</span><span class="sxs-lookup"><span data-stu-id="680d5-106">If building, site, and tenant information has been added to Call Analytics, it will also be shown for each call and session.</span></span> <span data-ttu-id="680d5-107">Сведения, недоступные с помощью вызова аналитики, которые помогут понять, почему пользователь имеет плохой или приглашения качества.</span><span class="sxs-lookup"><span data-stu-id="680d5-107">Information available via Call Analytics can help you figure out why a user had a poor call or meeting experience.</span></span> 
  
## <a name="call-analytics-permissions"></a><span data-ttu-id="680d5-108">Разрешения Analytics звонка</span><span class="sxs-lookup"><span data-stu-id="680d5-108">Call Analytics permissions</span></span>

<span data-ttu-id="680d5-109">Как администратор вы получаете полный доступ ко всем возможностям аналитических вызова.</span><span class="sxs-lookup"><span data-stu-id="680d5-109">As the admin, you get full access to all the features of Call Analytics.</span></span> <span data-ttu-id="680d5-110">Кроме того можно назначить роли Azure Active Directory для персонала службы поддержки.</span><span class="sxs-lookup"><span data-stu-id="680d5-110">In addition, you can assign Azure Active Directory roles to support staff.</span></span> <span data-ttu-id="680d5-111">Назначение групп communications поддержки специалист по роли для пользователей, имеющих ограниченный Просмотр аналитических вызова.</span><span class="sxs-lookup"><span data-stu-id="680d5-111">Assign the Teams communications support specialist role to users who should have a limited view of Call Analytics.</span></span> <span data-ttu-id="680d5-112">Назначение групп communications поддержки инженер роли для пользователей, которым требуется доступ ко всем функциям звонков аналитики.</span><span class="sxs-lookup"><span data-stu-id="680d5-112">Assign the Teams communications support engineer role to users who need access to the full functionality of Call Analytics.</span></span> <span data-ttu-id="680d5-113">Оба уровни разрешений запретить доступ к остальной части центра администрирования группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="680d5-113">Both permission levels prevent access to the rest of the Microsoft Teams admin center.</span></span>

<span data-ttu-id="680d5-114">Специалистов по поддержке Communications обрабатывать основные проблемы с качеством вызовов.</span><span class="sxs-lookup"><span data-stu-id="680d5-114">Communications support specialists handle basic call-quality problems.</span></span> <span data-ttu-id="680d5-115">Они не изучения проблем с собрания.</span><span class="sxs-lookup"><span data-stu-id="680d5-115">They don't investigate issues with meetings.</span></span> <span data-ttu-id="680d5-116">Вместо этого они собирать сведения и затем переведите ее в сотрудник службы поддержки коммуникаций.</span><span class="sxs-lookup"><span data-stu-id="680d5-116">Instead, they collect related information and then escalate to a communications support engineer.</span></span> <span data-ttu-id="680d5-117">Сотрудники службы поддержки Communications просматривать сведения в журналах подробные звонок, скрыты от communications специалистов по поддержке.</span><span class="sxs-lookup"><span data-stu-id="680d5-117">Communications support engineers see information in detailed call logs that's hidden from communications support specialists.</span></span> <span data-ttu-id="680d5-118">В следующей таблице приведены обзорные сведения о доступных для коммуникаций коммуникаций и специалистов по поддержке сотрудники службы поддержки при использовании вызова аналитики.</span><span class="sxs-lookup"><span data-stu-id="680d5-118">The following table gives an overview of information available to communications support specialists and communications support engineers when they use Call Analytics.</span></span>

<span data-ttu-id="680d5-119">Уровень разрешений, назначенных пользователю определяет, какой тип данных у вас есть доступ к в аналитике звонков:</span><span class="sxs-lookup"><span data-stu-id="680d5-119">The permissions level assigned to you determines what type of information you have access to in Call Analytics:</span></span>
  
- <span data-ttu-id="680d5-120">**Группы службы администратора или администратора communications группам**: у вас есть доступ к информации в аналитике звонков и в центре администрирования группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="680d5-120">**Teams service administrator or Teams communications administrator**: You have access to all the information in Call Analytics and in the Microsoft Teams admin center.</span></span>
    
- <span data-ttu-id="680d5-121">**Связи групп поддержки специалист по**: просматривать ограниченный набор данных в аналитике вызова.</span><span class="sxs-lookup"><span data-stu-id="680d5-121">**Teams communications support specialist**: You see a limited set of data in Call Analytics.</span></span> <span data-ttu-id="680d5-122">Вы можете устранить неполадки вызовов, но вы будете передать проблем, связанных с собрания сотрудник службы поддержки communications групп.</span><span class="sxs-lookup"><span data-stu-id="680d5-122">You can troubleshoot calls, but you'll hand off problems with meetings to a Teams communications support engineer.</span></span> <span data-ttu-id="680d5-123">У вас нет доступа к остальной части центра администрирования группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="680d5-123">You don't have access to the rest of the Microsoft Teams admin center.</span></span>
    
- <span data-ttu-id="680d5-124">**Communications групп поддержки Инженер службы поддержки**: все данные, доступные в аналитике звонков и устранению неполадок с звонков и собрания.</span><span class="sxs-lookup"><span data-stu-id="680d5-124">**Teams communications support engineer**: You see all available data in Call Analytics and can help troubleshoot problems with both calls and meetings.</span></span> <span data-ttu-id="680d5-125">У вас нет доступа к остальной части центра администрирования группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="680d5-125">You don't have access to the rest of the Microsoft Teams admin center.</span></span>
    
> [!NOTE]
> <span data-ttu-id="680d5-126">Роли specialist поддержки communications эквивалентно поддержки уровня 1 и роль Инженер службы поддержки communications эквивалентно поддержки второго уровня.</span><span class="sxs-lookup"><span data-stu-id="680d5-126">The communications support specialist role is equivalent to tier 1 support and the communications support engineer role is equivalent to tier 2 support.</span></span>

<span data-ttu-id="680d5-127">Дополнительные сведения о роли администраторов группам роли [группами Майкрософт использования администрирования для управления группами](using-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="680d5-127">For more information about Teams admin roles, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="680d5-128">Подробное сравнение поддержка связи групп специалист и коммуникаций групп поддержки инженер по роли см [Set up вызова аналитики](set-up-call-analytics.md#set-call-analytics-permissions)</span><span class="sxs-lookup"><span data-stu-id="680d5-128">For a detailed comparison of the Teams communications support specialist and Teams communications support engineer roles, see [Set up Call Analytics](set-up-call-analytics.md#set-call-analytics-permissions)</span></span> 
  
<span data-ttu-id="680d5-129">Видит рабочих групп и Скайп для администратора предприятия, если вам требуется помощь разрешения.</span><span class="sxs-lookup"><span data-stu-id="680d5-129">See your Teams and Skype for Business admin if you need help with permissions.</span></span>
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a><span data-ttu-id="680d5-130">Устранение проблемы с качеством звонок с помощью вызова аналитики</span><span class="sxs-lookup"><span data-stu-id="680d5-130">Troubleshoot call quality problems using Call Analytics</span></span>

1. <span data-ttu-id="680d5-131">Вход с помощью поддержка связи группы или групп учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="680d5-131">Sign in with your Teams communications support or Teams admin credentials.</span></span>

2. <span data-ttu-id="680d5-132">В веб-браузере перейдите к *https://admin.teams.microsoft.com*.</span><span class="sxs-lookup"><span data-stu-id="680d5-132">In your web browser go to *https://admin.teams.microsoft.com*.</span></span>
    
3. <span data-ttu-id="680d5-133">На панели **мониторинга**, **Поиск пользователей**в начните вводить имя или sip-адрес пользователя, чьи вызовы для устранения неполадок или выберите **Просмотр пользователей** , чтобы просмотреть список пользователей.</span><span class="sxs-lookup"><span data-stu-id="680d5-133">On the **Dashboard**, in **User Search**, start typing either the name or sip address of the user whose calls you want to troubleshoot or select **View users** to see a list of users.</span></span>
    
    ![Снимок экрана поля поиска пользователя аналитических звонков в центре администрирования группами Майкрософт.](media/use-call-analytics-to-troubleshoot-image-1.png)
  
4. <span data-ttu-id="680d5-135">Выберите пользователя в списке.</span><span class="sxs-lookup"><span data-stu-id="680d5-135">Select the user from the list.</span></span>

5. <span data-ttu-id="680d5-136">Выберите **журнал звонков**и выберите звонок или собрания, для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="680d5-136">Select **Call history**, and then select the call or meeting that you want to troubleshoot.</span></span>
    
    ![Снимок экрана показана страница Журнал звонков для пользователя.](media/use-call-analytics-to-troubleshoot-image-2.png)
  
6. <span data-ttu-id="680d5-138">Перейдите на вкладку **Дополнительно** и затем найдите желтый и красный элементов, которые указывают на наличие проблем вызовов плохого качества или подключения.</span><span class="sxs-lookup"><span data-stu-id="680d5-138">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="680d5-139">В сведения о сеансе для каждого вызова или собрания незначительные проблемы отображаются в желтый цвет.</span><span class="sxs-lookup"><span data-stu-id="680d5-139">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="680d5-140">(Например, на следующем снимке экрана приведены значения параметра желтого цвета средний уровень колебаний, максимальное число дрожания и средний коэффициент потерь пакетов.) Если что-то желтый, находится вне обычного диапазона и могут вызывать проблемы, но он вряд ли будет основные причины проблемы.</span><span class="sxs-lookup"><span data-stu-id="680d5-140">(For example, in the following screenshot, the values are in yellow for Average jitter, Max jitter, and Average packet loss rate.) If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="680d5-141">Если что-то красного, указывает на серьезную проблему, и это скорее всего главной причиной вызовов плохого качества для данного сеанса.</span><span class="sxs-lookup"><span data-stu-id="680d5-141">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
    
    ![<span data-ttu-id="680d5-142">Снимок экрана показана вкладку Дополнительно журнал звонков пользователя</span><span class="sxs-lookup"><span data-stu-id="680d5-142">Screenshot shows the Advanced tab of a user's Call history</span></span> ](media/use-call-analytics-to-troubleshoot-image-3.png)
  
<span data-ttu-id="680d5-143">В редких случаях качество взаимодействия данных не будет получено для звуковых сеансов.</span><span class="sxs-lookup"><span data-stu-id="680d5-143">In rare cases, quality of experience data isn't received for audio sessions.</span></span> <span data-ttu-id="680d5-144">Часто причиной Удаление вызова и подключение с завершение работы клиента.</span><span class="sxs-lookup"><span data-stu-id="680d5-144">Often this is caused by the call dropping and connection with the client terminating.</span></span> <span data-ttu-id="680d5-145">В этом случае оценка сеанса является **недоступной**.</span><span class="sxs-lookup"><span data-stu-id="680d5-145">When this occurs, the session rating is **unavailable**.</span></span>
  
<span data-ttu-id="680d5-146">Для звуковых сеансов, есть ли у качества взаимодействия (QoE) данных в следующей таблице описываются основные проблемы, допускающие сеанса как **низкого уровня**.</span><span class="sxs-lookup"><span data-stu-id="680d5-146">For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as **poor**.</span></span>
  
|<span data-ttu-id="680d5-147">**Ошибка**</span><span class="sxs-lookup"><span data-stu-id="680d5-147">**Issue**</span></span>|<span data-ttu-id="680d5-148">**Область**</span><span class="sxs-lookup"><span data-stu-id="680d5-148">**Area**</span></span>|<span data-ttu-id="680d5-149">**Описание**</span><span class="sxs-lookup"><span data-stu-id="680d5-149">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="680d5-150">Вызов программы установки</span><span class="sxs-lookup"><span data-stu-id="680d5-150">Call setup</span></span>  <br/> |<span data-ttu-id="680d5-151">Сеанс</span><span class="sxs-lookup"><span data-stu-id="680d5-151">Session</span></span>  <br/> |<span data-ttu-id="680d5-152">Код ошибки Ms-diag 20-29 указывает не удалось звонок.</span><span class="sxs-lookup"><span data-stu-id="680d5-152">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="680d5-153">Пользователь не может присоединиться к звонка или собрания.</span><span class="sxs-lookup"><span data-stu-id="680d5-153">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="680d5-154">Сети звука классификации процента звонков низкого качества</span><span class="sxs-lookup"><span data-stu-id="680d5-154">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="680d5-155">Сеанс</span><span class="sxs-lookup"><span data-stu-id="680d5-155">Session</span></span>  <br/> |<span data-ttu-id="680d5-156">Возникли неполадки с сетью качества (например, потеря пакетов, дрожание, Замедление nmos, время приема-Передачи или соотношение скрытых).</span><span class="sxs-lookup"><span data-stu-id="680d5-156">Network quality issues (such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio) were encountered.</span></span> <span data-ttu-id="680d5-157">Дополнительные сведения об условиях, используемый для классификации неполадки вызовов в этом [блоге Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133)см.</span><span class="sxs-lookup"><span data-stu-id="680d5-157">For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).</span></span>  <br/> |
|<span data-ttu-id="680d5-158">Устройство не работает</span><span class="sxs-lookup"><span data-stu-id="680d5-158">Device not functioning</span></span>  <br/> |<span data-ttu-id="680d5-159">Устройства</span><span class="sxs-lookup"><span data-stu-id="680d5-159">Device</span></span>  <br/> | <span data-ttu-id="680d5-160">Устройство не работает правильно.</span><span class="sxs-lookup"><span data-stu-id="680d5-160">A device isn't functioning correctly.</span></span> <span data-ttu-id="680d5-161">Устройство, не работает соотношения являются:</span><span class="sxs-lookup"><span data-stu-id="680d5-161">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="680d5-162">DeviceRenderNotFunctioningEventRatio > = 0,005</span><span class="sxs-lookup"><span data-stu-id="680d5-162">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="680d5-163">DeviceCaptureNotFunctioningEventRatio > = 0,005</span><span class="sxs-lookup"><span data-stu-id="680d5-163">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="680d5-164">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="680d5-164">Related topics</span></span>
[<span data-ttu-id="680d5-165">Настройка аналитики звонков</span><span class="sxs-lookup"><span data-stu-id="680d5-165">Set up Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="680d5-166">Аналитика звонков и панель мониторинга качества звонков</span><span class="sxs-lookup"><span data-stu-id="680d5-166">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
