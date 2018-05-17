---
title: Качество связи Analytics звонков использовать для устранения неполадок низкого уровня Скайп для бизнеса
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Используйте вызова анализа сведений о устройств, сети и подключения к для диагностики проблем пользователей с Скайп для собраний и вызовы бизнеса.
ms.openlocfilehash: cb887a1c582c9547616c2133c2f175ac634e2da8
ms.sourcegitcommit: 5a0b3fe49b64f08979c89443f66b15827034e755
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2018
---
# <a name="use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality"></a><span data-ttu-id="e4991-103">Качество связи Analytics звонков использовать для устранения неполадок низкого уровня Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e4991-103">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>

<span data-ttu-id="e4991-104">Вызов Analytics поможет диагностировать проблемы соединение или звонок с Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e4991-104">Call Analytics helps you to troubleshoot call or connection problems with Skype for Business.</span></span> <span data-ttu-id="e4991-105">Аналитика вызова отображаются подробные сведения о устройств, сетей и связи для звонков и собраний с каждого пользователя в вашей Скайп для учетной записи Business.</span><span class="sxs-lookup"><span data-stu-id="e4991-105">Call Analytics shows detailed information about the devices, networks, and connectivity for the calls and meetings of each user in your Skype for Business account.</span></span> <span data-ttu-id="e4991-106">Если сборка, веб-сайтов и клиентов добавлена информация для вызова аналитика, он также будет отображаться для каждого вызова и сеанса.</span><span class="sxs-lookup"><span data-stu-id="e4991-106">If building, site, and tenant information has been added to Call Analytics, it will also be shown for each call and session.</span></span> <span data-ttu-id="e4991-107">Сведения, недоступные с помощью вызова аналитики, которые помогут понять, почему пользователь имеет плохой или приглашения качества.</span><span class="sxs-lookup"><span data-stu-id="e4991-107">Information available via Call Analytics can help you figure out why a user had a poor call or meeting experience.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e4991-p102">На данный момент доступна лишь предварительная версия средства аналитики звонков. Описание и изображения в этой статье могут не соответствовать фактическому интерфейсу.</span><span class="sxs-lookup"><span data-stu-id="e4991-p102">Call Analytics is currently in preview. Text and images described here may not match your experience.</span></span>
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a><span data-ttu-id="e4991-110">Устранение проблемы с качеством звонок с помощью вызова аналитики</span><span class="sxs-lookup"><span data-stu-id="e4991-110">Troubleshoot call quality problems using Call Analytics</span></span>

<span data-ttu-id="e4991-111">Уровень разрешений, назначенных пользователю определяет, какой тип данных у вас есть доступ к в аналитике звонков:</span><span class="sxs-lookup"><span data-stu-id="e4991-111">The permissions level assigned to you determines what type of information you have access to in Call Analytics:</span></span>
  
- <span data-ttu-id="e4991-112">**Скайп для администрирования бизнес**: у вас есть доступ к информации в аналитике звонков и в Скайп по центру администрирования бизнес.</span><span class="sxs-lookup"><span data-stu-id="e4991-112">**Skype for Business admin**: You have access to all the information in Call Analytics and in the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="e4991-113">**Служба технической поддержки агента с разрешениями уровня 1**: просматривать ограниченный набор данных в аналитике вызова.</span><span class="sxs-lookup"><span data-stu-id="e4991-113">**Helpdesk agent with Tier 1 permissions**: You see a limited set of data in Call Analytics.</span></span> <span data-ttu-id="e4991-114">Вы можете устранить неполадки вызовов, но будет сдать проблем, связанных с собраний агенту второго уровня.</span><span class="sxs-lookup"><span data-stu-id="e4991-114">You can troubleshoot calls, but you'll hand off problems with meetings to a Tier 2 agent.</span></span> <span data-ttu-id="e4991-115">У вас нет доступа к остальной части Скайп по центру администрирования бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e4991-115">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="e4991-116">**Служба технической поддержки агента с разрешениями уровня 2**: все данные, доступные в аналитике звонков и устранению неполадок с звонков и собрания.</span><span class="sxs-lookup"><span data-stu-id="e4991-116">**Helpdesk agent with Tier 2 permissions**: You see all available data in Call Analytics and can help troubleshoot problems with both calls and meetings.</span></span> <span data-ttu-id="e4991-117">У вас нет доступа к остальной части Скайп по центру администрирования бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e4991-117">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
<span data-ttu-id="e4991-118">Если вам требуется помощь разрешения видеть ваше Скайп для администрирования бизнес.</span><span class="sxs-lookup"><span data-stu-id="e4991-118">See your Skype for Business admin if you need help with permissions.</span></span>
  
 <span data-ttu-id="e4991-119">**Откройте вызова Analytics агентом служба технической поддержки первого уровня или уровня 2**</span><span class="sxs-lookup"><span data-stu-id="e4991-119">**Open Call Analytics as a Tier 1 or Tier 2 helpdesk agent**</span></span>
  
1. <span data-ttu-id="e4991-120">Перейдите в центр администрирования Office 365 и вход с помощью учетной записи рабочего или школы.</span><span class="sxs-lookup"><span data-stu-id="e4991-120">Go to the Office 365 admin center and sign in using your work or school account.</span></span> <span data-ttu-id="e4991-121">В веб-браузере перейдите к *https://adminportal.services.skypeforbusiness.com*.</span><span class="sxs-lookup"><span data-stu-id="e4991-121">Then in your web browser go to *https://adminportal.services.skypeforbusiness.com*.</span></span>
    
2. <span data-ttu-id="e4991-122">**Поиск пользователей**в начните вводить имя или sip-адрес пользователя, звонки, следует выполнить устранение неполадок и затем выберите пользователя в списке.</span><span class="sxs-lookup"><span data-stu-id="e4991-122">In **User Search**, start typing either the name or sip address of the user whose calls you want to troubleshoot and then select the user from the list.</span></span>
    
    ![Снимок экрана поля поиска пользователя аналитических звонков в Скайп по центру администрирования бизнес.](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. <span data-ttu-id="e4991-124">В **журнал звонков**выберите звонок или собрания, для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="e4991-124">In **Call history**, select the call or meeting that you want to troubleshoot.</span></span>
    
    ![Снимок экрана показана страница Журнал звонков для пользователя с помощью информации, например сведений о контакте пользователя, сводка качества 7 дней и действия для собраний и звонки и обзор даты и времени, получателей и качество звука](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. <span data-ttu-id="e4991-126">Перейдите на вкладку **Дополнительно** и затем найдите желтый и красный элементов, которые указывают на наличие проблем вызовов плохого качества или подключения.</span><span class="sxs-lookup"><span data-stu-id="e4991-126">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="e4991-127">В сведения о сеансе для каждого вызова или собрания незначительные проблемы отображаются в желтый цвет.</span><span class="sxs-lookup"><span data-stu-id="e4991-127">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="e4991-128">(Например, на следующем снимке экрана приведены значения параметра желтого цвета средний уровень колебаний, максимальное число дрожания и средний коэффициент потерь пакетов.) Если что-то желтый, находится вне обычного диапазона и могут вызывать проблемы, но он вряд ли будет основные причины проблемы.</span><span class="sxs-lookup"><span data-stu-id="e4991-128">(For example, in the following screenshot, the values are in yellow for Average jitter, Max jitter, and Average packet loss rate.) If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="e4991-129">Если что-то красного, указывает на серьезную проблему, и это скорее всего главной причиной вызовов плохого качества для данного сеанса.</span><span class="sxs-lookup"><span data-stu-id="e4991-129">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
    
    ![Снимке экрана показан вкладку Дополнительно журнал звонков пользователя с разделом входящие сетевые развернуть, чтобы отобразить отображение данных для средний уровень колебаний, максимальный уровень дрожания и средний коэффициент потерь пакетов в желтый цвет, что означает, что они являются незначительные проблемы.](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
<span data-ttu-id="e4991-131">В редких случаях качество взаимодействия данных не будет получено для звуковых сеансов.</span><span class="sxs-lookup"><span data-stu-id="e4991-131">In rare cases, quality of experience data isn't received for audio sessions.</span></span> <span data-ttu-id="e4991-132">Часто причиной Удаление вызова и подключение с завершение работы клиента.</span><span class="sxs-lookup"><span data-stu-id="e4991-132">Often this is caused by the call dropping and connection with the client terminating.</span></span> <span data-ttu-id="e4991-133">В этом случае оценка сеанса: «недоступна».</span><span class="sxs-lookup"><span data-stu-id="e4991-133">When this occurs, the session rating is "unavailable".</span></span>
  
<span data-ttu-id="e4991-134">Для звуковых сеансов, есть ли у качества взаимодействия (QoE) данных в следующей таблице описываются основные проблемы, допускающие сеанса как «плохих».</span><span class="sxs-lookup"><span data-stu-id="e4991-134">For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as "poor."</span></span>
  
|<span data-ttu-id="e4991-135">**Ошибка**</span><span class="sxs-lookup"><span data-stu-id="e4991-135">**Issue**</span></span>|<span data-ttu-id="e4991-136">**Область**</span><span class="sxs-lookup"><span data-stu-id="e4991-136">**Area**</span></span>|<span data-ttu-id="e4991-137">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e4991-137">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e4991-138">Вызов программы установки</span><span class="sxs-lookup"><span data-stu-id="e4991-138">Call setup</span></span>  <br/> |<span data-ttu-id="e4991-139">Сеанс</span><span class="sxs-lookup"><span data-stu-id="e4991-139">Session</span></span>  <br/> |<span data-ttu-id="e4991-140">Код ошибки Ms-diag 20-29 указывает не удалось звонок.</span><span class="sxs-lookup"><span data-stu-id="e4991-140">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="e4991-141">Пользователь не может присоединиться к звонка или собрания.</span><span class="sxs-lookup"><span data-stu-id="e4991-141">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="e4991-142">Сети звука классификации процента звонков низкого качества</span><span class="sxs-lookup"><span data-stu-id="e4991-142">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="e4991-143">Сеанс</span><span class="sxs-lookup"><span data-stu-id="e4991-143">Session</span></span>  <br/> |<span data-ttu-id="e4991-144">Проблемы качества сети были обнаружены в областях потери пакетов, дрожание, Замедление nmos, время приема-Передачи, или скрытого отношение.</span><span class="sxs-lookup"><span data-stu-id="e4991-144">Network quality issues were encountered in areas such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio.</span></span> <span data-ttu-id="e4991-145">Дополнительные сведения об условиях, используемый для классификации неполадки вызовов в этом [блоге Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133)см.</span><span class="sxs-lookup"><span data-stu-id="e4991-145">For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).</span></span>  <br/> |
|<span data-ttu-id="e4991-146">Устройство не работает</span><span class="sxs-lookup"><span data-stu-id="e4991-146">Device not functioning</span></span>  <br/> |<span data-ttu-id="e4991-147">Устройства</span><span class="sxs-lookup"><span data-stu-id="e4991-147">Device</span></span>  <br/> | <span data-ttu-id="e4991-148">Устройство не работает правильно.</span><span class="sxs-lookup"><span data-stu-id="e4991-148">A device isn't functioning correctly.</span></span> <span data-ttu-id="e4991-149">Устройство, не работает соотношения являются:</span><span class="sxs-lookup"><span data-stu-id="e4991-149">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="e4991-150">DeviceRenderNotFunctioningEventRatio > = 0,005</span><span class="sxs-lookup"><span data-stu-id="e4991-150">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="e4991-151">DeviceCaptureNotFunctioningEventRatio > = 0,005</span><span class="sxs-lookup"><span data-stu-id="e4991-151">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="e4991-152">See also</span><span class="sxs-lookup"><span data-stu-id="e4991-152">Related topics</span></span>
[<span data-ttu-id="e4991-153">Настройка средства аналитики звонков в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e4991-153">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="e4991-154">Вызов аналитики и панель мониторинга качества звонка</span><span class="sxs-lookup"><span data-stu-id="e4991-154">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 