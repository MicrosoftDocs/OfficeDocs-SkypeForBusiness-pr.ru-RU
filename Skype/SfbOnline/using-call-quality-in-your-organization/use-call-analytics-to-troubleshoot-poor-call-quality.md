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
ms.openlocfilehash: b7f900509506433bd2c863fb6c0c33c4f71f2ab5
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2018
---
# <a name="use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality"></a><span data-ttu-id="1ffa7-103">Качество связи Analytics звонков использовать для устранения неполадок низкого уровня Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="1ffa7-103">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>

<span data-ttu-id="1ffa7-104">Вызов Analytics поможет диагностировать проблемы соединение или звонок с Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-104">Call Analytics helps you to troubleshoot call or connection problems with Skype for Business.</span></span> <span data-ttu-id="1ffa7-105">Аналитика вызова отображаются подробные сведения о устройств, сетей и связи для звонков и собраний с каждого пользователя в вашей Скайп для учетной записи Business.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-105">Call Analytics shows detailed information about the devices, networks, and connectivity for the calls and meetings of each user in your Skype for Business account.</span></span> <span data-ttu-id="1ffa7-106">Если сборка, веб-сайтов и клиентов добавлена информация для вызова аналитика, он также будет отображаться для каждого вызова и сеанса.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-106">If building, site, and tenant information has been added to Call Analytics, it will also be shown for each call and session.</span></span> <span data-ttu-id="1ffa7-107">Сведения, недоступные с помощью вызова аналитики, которые помогут понять, почему пользователь имеет плохой или приглашения качества.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-107">Information available via Call Analytics can help you figure out why a user had a poor call or meeting experience.</span></span> 
  
    > [!NOTE]
    > Call Analytics is currently in preview. Text and images described here may not match your experience. 
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a><span data-ttu-id="1ffa7-108">Устранение проблемы с качеством звонок с помощью вызова аналитики</span><span class="sxs-lookup"><span data-stu-id="1ffa7-108">Troubleshoot call quality problems using Call Analytics</span></span>

<span data-ttu-id="1ffa7-109">Уровень разрешений, назначенных пользователю определяет, какой тип данных у вас есть доступ к в аналитике звонков:</span><span class="sxs-lookup"><span data-stu-id="1ffa7-109">The permissions level assigned to you determines what type of information you have access to in Call Analytics:</span></span>
  
- <span data-ttu-id="1ffa7-110">**Скайп для администрирования бизнес**: у вас есть доступ к информации в аналитике звонков и в Скайп по центру администрирования бизнес.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-110">**Skype for Business admin**: You have access to all the information in Call Analytics and in the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="1ffa7-111">**Служба технической поддержки агента с разрешениями уровня 1**: просматривать ограниченный набор данных в аналитике вызова.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-111">**Helpdesk agent with Tier 1 permissions**: You see a limited set of data in Call Analytics.</span></span> <span data-ttu-id="1ffa7-112">Вы можете устранить неполадки вызовов, но будет сдать проблем, связанных с собраний агенту второго уровня.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-112">You can troubleshoot calls, but you'll hand off problems with meetings to a Tier 2 agent.</span></span> <span data-ttu-id="1ffa7-113">У вас нет доступа к остальной части Скайп по центру администрирования бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-113">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="1ffa7-114">**Служба технической поддержки агента с разрешениями уровня 2**: все данные, доступные в аналитике звонков и устранению неполадок с звонков и собрания.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-114">**Helpdesk agent with Tier 2 permissions**: You see all available data in Call Analytics and can help troubleshoot problems with both calls and meetings.</span></span> <span data-ttu-id="1ffa7-115">У вас нет доступа к остальной части Скайп по центру администрирования бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-115">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
<span data-ttu-id="1ffa7-116">Если вам требуется помощь разрешения видеть ваше Скайп для администрирования бизнес.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-116">See your Skype for Business admin if you need help with permissions.</span></span>
  
 <span data-ttu-id="1ffa7-117">**Откройте вызова Analytics агентом служба технической поддержки первого уровня или уровня 2**</span><span class="sxs-lookup"><span data-stu-id="1ffa7-117">**Open Call Analytics as a Tier 1 or Tier 2 helpdesk agent**</span></span>
  
1. <span data-ttu-id="1ffa7-118">Перейдите в центр администрирования Office 365 и вход с помощью учетной записи рабочего или школы.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-118">Go to the Office 365 admin center and sign in using your work or school account.</span></span> <span data-ttu-id="1ffa7-119">В веб-браузере перейдите к *https://adminportal.services.skypeforbusiness.com*.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-119">Then in your web browser go to *https://adminportal.services.skypeforbusiness.com*.</span></span>
    
2. <span data-ttu-id="1ffa7-120">**Поиск пользователей**в начните вводить имя или sip-адрес пользователя, звонки, следует выполнить устранение неполадок и затем выберите пользователя в списке.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-120">In **User Search**, start typing either the name or sip address of the user whose calls you want to troubleshoot and then select the user from the list.</span></span>
    
    ![Снимок экрана поля поиска пользователя аналитических звонков в Скайп по центру администрирования бизнес.](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. <span data-ttu-id="1ffa7-122">В **журнал звонков**выберите звонок или собрания, для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-122">In **Call history**, select the call or meeting that you want to troubleshoot.</span></span>
    
    ![Снимок экрана показана страница Журнал звонков для пользователя с помощью информации, например сведений о контакте пользователя, сводка качества 7 дней и действия для собраний и звонки и обзор даты и времени, получателей и качество звука](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. <span data-ttu-id="1ffa7-124">Перейдите на вкладку **Дополнительно** и затем найдите желтый и красный элементов, которые указывают на наличие проблем вызовов плохого качества или подключения.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-124">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="1ffa7-125">В сведения о сеансе для каждого вызова или собрания незначительные проблемы отображаются в желтый цвет.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-125">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="1ffa7-126">(Например, на следующем снимке экрана приведены значения параметра желтого цвета средний уровень колебаний, максимальное число дрожания и средний коэффициент потерь пакетов.) Если что-то желтый, находится вне обычного диапазона и могут вызывать проблемы, но он вряд ли будет основные причины проблемы.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-126">(For example, in the following screenshot, the values are in yellow for Average jitter, Max jitter, and Average packet loss rate.) If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="1ffa7-127">Если что-то красного, указывает на серьезную проблему, и это скорее всего главной причиной вызовов плохого качества для данного сеанса.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-127">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
    
    ![Снимке экрана показан вкладку Дополнительно журнал звонков пользователя с разделом входящие сетевые развернуть, чтобы отобразить отображение данных для средний уровень колебаний, максимальный уровень дрожания и средний коэффициент потерь пакетов в желтый цвет, что означает, что они являются незначительные проблемы.](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
<span data-ttu-id="1ffa7-129">В редких случаях качество взаимодействия данных не будет получено для звуковых сеансов.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-129">In rare cases, quality of experience data isn't received for audio sessions.</span></span> <span data-ttu-id="1ffa7-130">Часто причиной Удаление вызова и подключение с завершение работы клиента.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-130">Often this is caused by the call dropping and connection with the client terminating.</span></span> <span data-ttu-id="1ffa7-131">В этом случае оценка сеанса: «недоступна».</span><span class="sxs-lookup"><span data-stu-id="1ffa7-131">When this occurs, the session rating is "unavailable".</span></span>
  
<span data-ttu-id="1ffa7-132">Для звуковых сеансов, есть ли у качества взаимодействия (QoE) данных в следующей таблице описываются основные проблемы, допускающие сеанса как «плохих».</span><span class="sxs-lookup"><span data-stu-id="1ffa7-132">For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as "poor."</span></span>
  
|<span data-ttu-id="1ffa7-133">**Ошибка**</span><span class="sxs-lookup"><span data-stu-id="1ffa7-133">**Issue**</span></span>|<span data-ttu-id="1ffa7-134">**Область**</span><span class="sxs-lookup"><span data-stu-id="1ffa7-134">**Area**</span></span>|<span data-ttu-id="1ffa7-135">**Описание**</span><span class="sxs-lookup"><span data-stu-id="1ffa7-135">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1ffa7-136">Вызов программы установки</span><span class="sxs-lookup"><span data-stu-id="1ffa7-136">Call setup</span></span>  <br/> |<span data-ttu-id="1ffa7-137">Сеанс</span><span class="sxs-lookup"><span data-stu-id="1ffa7-137">Session</span></span>  <br/> |<span data-ttu-id="1ffa7-138">Код ошибки Ms-diag 20-29 указывает не удалось звонок.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-138">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="1ffa7-139">Пользователь не может присоединиться к звонка или собрания.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-139">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="1ffa7-140">Сети звука классификации процента звонков низкого качества</span><span class="sxs-lookup"><span data-stu-id="1ffa7-140">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="1ffa7-141">Сеанс</span><span class="sxs-lookup"><span data-stu-id="1ffa7-141">Session</span></span>  <br/> |<span data-ttu-id="1ffa7-142">Проблемы качества сети были обнаружены в областях потери пакетов, дрожание, Замедление nmos, время приема-Передачи, или скрытого отношение.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-142">Network quality issues were encountered in areas such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio.</span></span> <span data-ttu-id="1ffa7-143">Дополнительные сведения об условиях, используемый для классификации неполадки вызовов в этом [блоге Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133)см.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-143">For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).</span></span>  <br/> |
|<span data-ttu-id="1ffa7-144">Устройство не работает</span><span class="sxs-lookup"><span data-stu-id="1ffa7-144">Device not functioning</span></span>  <br/> |<span data-ttu-id="1ffa7-145">Устройства</span><span class="sxs-lookup"><span data-stu-id="1ffa7-145">Device</span></span>  <br/> | <span data-ttu-id="1ffa7-146">Устройство не работает правильно.</span><span class="sxs-lookup"><span data-stu-id="1ffa7-146">A device isn't functioning correctly.</span></span> <span data-ttu-id="1ffa7-147">Устройство, не работает соотношения являются:</span><span class="sxs-lookup"><span data-stu-id="1ffa7-147">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="1ffa7-148">DeviceRenderNotFunctioningEventRatio > = 0,005</span><span class="sxs-lookup"><span data-stu-id="1ffa7-148">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="1ffa7-149">DeviceCaptureNotFunctioningEventRatio > = 0,005</span><span class="sxs-lookup"><span data-stu-id="1ffa7-149">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="1ffa7-150">See also</span><span class="sxs-lookup"><span data-stu-id="1ffa7-150">Related topics</span></span>
[<span data-ttu-id="1ffa7-151">Настройка средства аналитики звонков в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="1ffa7-151">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="1ffa7-152">В чем разница между средством аналитики звонков и панелью мониторинга качества звонков?</span><span class="sxs-lookup"><span data-stu-id="1ffa7-152">What's the difference between Call Analytics and Call Quality Dashboard?</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 