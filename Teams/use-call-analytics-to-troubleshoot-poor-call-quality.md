---
title: Устранение неполадок с качеством звонков с помощью средства аналитики звонков
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
ms.openlocfilehash: db1f0ed4ce79936a5355fe087220fe2802f61ce6
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2018
ms.locfileid: "23783152"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a><span data-ttu-id="1db61-103">Устранение неполадок с качеством звонков с помощью средства аналитики звонков</span><span class="sxs-lookup"><span data-stu-id="1db61-103">Use Call Analytics to troubleshoot poor call quality</span></span>

<span data-ttu-id="1db61-104">Вызов Analytics помогает неполадок соединение или звонок с группами Майкрософт и Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1db61-104">Call Analytics helps you to troubleshoot call or connection problems with Microsoft Teams and Skype for Business.</span></span> <span data-ttu-id="1db61-105">Аналитика вызова отображаются подробные сведения о устройств, сетей и связи для звонков и собраний с каждого пользователя в учетную запись Office 365.</span><span class="sxs-lookup"><span data-stu-id="1db61-105">Call Analytics shows detailed information about the devices, networks, and connectivity for the calls and meetings of each user in your Office 365 account.</span></span> <span data-ttu-id="1db61-106">Если сборка, веб-сайтов и клиентов добавлена информация для вызова аналитика, он также будет отображаться для каждого вызова и сеанса.</span><span class="sxs-lookup"><span data-stu-id="1db61-106">If building, site, and tenant information has been added to Call Analytics, it will also be shown for each call and session.</span></span> <span data-ttu-id="1db61-107">Сведения, недоступные с помощью вызова аналитики, которые помогут понять, почему пользователь имеет плохой или приглашения качества.</span><span class="sxs-lookup"><span data-stu-id="1db61-107">Information available via Call Analytics can help you figure out why a user had a poor call or meeting experience.</span></span> 
  
<span data-ttu-id="1db61-108">**Вызов Analytics теперь доступен в группами Майкрософт и Скайп по центру администрирования бизнес.**</span><span class="sxs-lookup"><span data-stu-id="1db61-108">**Call Analytics is now available in the Microsoft Teams and Skype for Business Admin Center.**</span></span> <span data-ttu-id="1db61-109">Чтобы просмотреть все сведения о вызовах и данные для пользователя, используйте вкладку **Журнал звонков** . Это можно сделать, нужна на странице профиля пользователя выполнить поиск по словам для пользователей из панели мониторинга или поиск пользователя от **пользователей** в левой панели навигации.</span><span class="sxs-lookup"><span data-stu-id="1db61-109">To see all of the call information and data for a user, use the **Call History** tab. You can do this by looking on the user's profile page by either searching for the user from the dashboard or finding the user from **Users** in the left navigation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1db61-110">Служба технической поддержки агента разрешения и отправка топологии сети будут доступны в новый портал администрирования в течение нескольких месяцев.</span><span class="sxs-lookup"><span data-stu-id="1db61-110">Helpdesk agent permissions and network topology upload will be available in the new admin portal in the coming months.</span></span> <span data-ttu-id="1db61-111">В это время, могут продолжить использовать https://adminportal.services.skypeforbusiness.com для уровня 1 и 2 уровня доступа служба технической поддержки.</span><span class="sxs-lookup"><span data-stu-id="1db61-111">In the meantime, you can continue to use  https://adminportal.services.skypeforbusiness.com for Tier 1 and Tier 2 helpdesk access.</span></span>
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a><span data-ttu-id="1db61-112">Устранение проблемы с качеством звонок с помощью вызова аналитики</span><span class="sxs-lookup"><span data-stu-id="1db61-112">Troubleshoot call quality problems using Call Analytics</span></span>

<span data-ttu-id="1db61-113">Уровень разрешений, назначенных пользователю определяет, какой тип данных у вас есть доступ к в аналитике звонков:</span><span class="sxs-lookup"><span data-stu-id="1db61-113">The permissions level assigned to you determines what type of information you have access to in Call Analytics:</span></span>
  
- <span data-ttu-id="1db61-114">**Скайп для администрирования бизнес**: у вас есть доступ к информации в аналитике звонков и в Скайп по центру администрирования бизнес.</span><span class="sxs-lookup"><span data-stu-id="1db61-114">**Skype for Business admin**: You have access to all the information in Call Analytics and in the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="1db61-115">**Служба технической поддержки агента с разрешениями уровня 1**: просматривать ограниченный набор данных в аналитике вызова.</span><span class="sxs-lookup"><span data-stu-id="1db61-115">**Helpdesk agent with Tier 1 permissions**: You see a limited set of data in Call Analytics.</span></span> <span data-ttu-id="1db61-116">Вы можете устранить неполадки вызовов, но будет сдать проблем, связанных с собраний агенту второго уровня.</span><span class="sxs-lookup"><span data-stu-id="1db61-116">You can troubleshoot calls, but you'll hand off problems with meetings to a Tier 2 agent.</span></span> <span data-ttu-id="1db61-117">У вас нет доступа к остальной части Скайп по центру администрирования бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1db61-117">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="1db61-118">**Служба технической поддержки агента с разрешениями уровня 2**: все данные, доступные в аналитике звонков и устранению неполадок с звонков и собрания.</span><span class="sxs-lookup"><span data-stu-id="1db61-118">**Helpdesk agent with Tier 2 permissions**: You see all available data in Call Analytics and can help troubleshoot problems with both calls and meetings.</span></span> <span data-ttu-id="1db61-119">У вас нет доступа к остальной части Скайп по центру администрирования бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1db61-119">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
<span data-ttu-id="1db61-120">Если вам требуется помощь разрешения видеть ваше Скайп для администрирования бизнес.</span><span class="sxs-lookup"><span data-stu-id="1db61-120">See your Skype for Business admin if you need help with permissions.</span></span>
  
 <span data-ttu-id="1db61-121">**Откройте вызова Analytics агентом служба технической поддержки первого уровня или уровня 2**</span><span class="sxs-lookup"><span data-stu-id="1db61-121">**Open Call Analytics as a Tier 1 or Tier 2 helpdesk agent**</span></span>
  
1. <span data-ttu-id="1db61-122">Перейдите в центр администрирования Office 365 и вход с помощью учетной записи рабочего или школы.</span><span class="sxs-lookup"><span data-stu-id="1db61-122">Go to the Office 365 admin center and sign in using your work or school account.</span></span> <span data-ttu-id="1db61-123">В веб-браузере перейдите к *https://adminportal.services.skypeforbusiness.com*.</span><span class="sxs-lookup"><span data-stu-id="1db61-123">Then in your web browser go to *https://adminportal.services.skypeforbusiness.com*.</span></span>
    
2. <span data-ttu-id="1db61-124">**Поиск пользователей**в начните вводить имя или sip-адрес пользователя, звонки, следует выполнить устранение неполадок и затем выберите пользователя в списке.</span><span class="sxs-lookup"><span data-stu-id="1db61-124">In **User Search**, start typing either the name or sip address of the user whose calls you want to troubleshoot and then select the user from the list.</span></span>
    
    ![Снимок экрана поля поиска пользователя аналитических звонков в Скайп по центру администрирования бизнес.](media/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. <span data-ttu-id="1db61-126">В **журнал звонков**выберите звонок или собрания, для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="1db61-126">In **Call history**, select the call or meeting that you want to troubleshoot.</span></span>
    
    ![Снимок экрана показана страница Журнал звонков для пользователя с помощью информации, например сведений о контакте пользователя, сводка качества 7 дней и действия для собраний и звонки и обзор даты и времени, получателей и качество звука](media/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. <span data-ttu-id="1db61-128">Перейдите на вкладку **Дополнительно** и затем найдите желтый и красный элементов, которые указывают на наличие проблем вызовов плохого качества или подключения.</span><span class="sxs-lookup"><span data-stu-id="1db61-128">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="1db61-129">В сведения о сеансе для каждого вызова или собрания незначительные проблемы отображаются в желтый цвет.</span><span class="sxs-lookup"><span data-stu-id="1db61-129">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="1db61-130">(Например, на следующем снимке экрана приведены значения параметра желтого цвета средний уровень колебаний, максимальное число дрожания и средний коэффициент потерь пакетов.) Если что-то желтый, находится вне обычного диапазона и могут вызывать проблемы, но он вряд ли будет основные причины проблемы.</span><span class="sxs-lookup"><span data-stu-id="1db61-130">(For example, in the following screenshot, the values are in yellow for Average jitter, Max jitter, and Average packet loss rate.) If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="1db61-131">Если что-то красного, указывает на серьезную проблему, и это скорее всего главной причиной вызовов плохого качества для данного сеанса.</span><span class="sxs-lookup"><span data-stu-id="1db61-131">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
    
    ![Снимке экрана показан вкладку Дополнительно журнал звонков пользователя с разделом входящие сетевые развернуть, чтобы отобразить отображение данных для средний уровень колебаний, максимальный уровень дрожания и средний коэффициент потерь пакетов в желтый цвет, что означает, что они являются незначительные проблемы.](media/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
<span data-ttu-id="1db61-133">В редких случаях качество взаимодействия данных не будет получено для звуковых сеансов.</span><span class="sxs-lookup"><span data-stu-id="1db61-133">In rare cases, quality of experience data isn't received for audio sessions.</span></span> <span data-ttu-id="1db61-134">Часто причиной Удаление вызова и подключение с завершение работы клиента.</span><span class="sxs-lookup"><span data-stu-id="1db61-134">Often this is caused by the call dropping and connection with the client terminating.</span></span> <span data-ttu-id="1db61-135">В этом случае оценка сеанса: «недоступна».</span><span class="sxs-lookup"><span data-stu-id="1db61-135">When this occurs, the session rating is "unavailable".</span></span>
  
<span data-ttu-id="1db61-136">Для звуковых сеансов, есть ли у качества взаимодействия (QoE) данных в следующей таблице описываются основные проблемы, допускающие сеанса как «плохих».</span><span class="sxs-lookup"><span data-stu-id="1db61-136">For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as "poor."</span></span>
  
|<span data-ttu-id="1db61-137">**Ошибка**</span><span class="sxs-lookup"><span data-stu-id="1db61-137">**Issue**</span></span>|<span data-ttu-id="1db61-138">**Область**</span><span class="sxs-lookup"><span data-stu-id="1db61-138">**Area**</span></span>|<span data-ttu-id="1db61-139">**Описание**</span><span class="sxs-lookup"><span data-stu-id="1db61-139">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1db61-140">Вызов программы установки</span><span class="sxs-lookup"><span data-stu-id="1db61-140">Call setup</span></span>  <br/> |<span data-ttu-id="1db61-141">Сеанс</span><span class="sxs-lookup"><span data-stu-id="1db61-141">Session</span></span>  <br/> |<span data-ttu-id="1db61-142">Код ошибки Ms-diag 20-29 указывает не удалось звонок.</span><span class="sxs-lookup"><span data-stu-id="1db61-142">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="1db61-143">Пользователь не может присоединиться к звонка или собрания.</span><span class="sxs-lookup"><span data-stu-id="1db61-143">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="1db61-144">Сети звука классификации процента звонков низкого качества</span><span class="sxs-lookup"><span data-stu-id="1db61-144">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="1db61-145">Сеанс</span><span class="sxs-lookup"><span data-stu-id="1db61-145">Session</span></span>  <br/> |<span data-ttu-id="1db61-146">Проблемы качества сети были обнаружены в областях потери пакетов, дрожание, Замедление nmos, время приема-Передачи, или скрытого отношение.</span><span class="sxs-lookup"><span data-stu-id="1db61-146">Network quality issues were encountered in areas such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio.</span></span> <span data-ttu-id="1db61-147">Дополнительные сведения об условиях, используемый для классификации неполадки вызовов в этом [блоге Microsoft](https://go.microsoft.com/fwlink/p/?linkid=852133)см.</span><span class="sxs-lookup"><span data-stu-id="1db61-147">For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).</span></span>  <br/> |
|<span data-ttu-id="1db61-148">Устройство не работает</span><span class="sxs-lookup"><span data-stu-id="1db61-148">Device not functioning</span></span>  <br/> |<span data-ttu-id="1db61-149">Устройства</span><span class="sxs-lookup"><span data-stu-id="1db61-149">Device</span></span>  <br/> | <span data-ttu-id="1db61-150">Устройство не работает правильно.</span><span class="sxs-lookup"><span data-stu-id="1db61-150">A device isn't functioning correctly.</span></span> <span data-ttu-id="1db61-151">Устройство, не работает соотношения являются:</span><span class="sxs-lookup"><span data-stu-id="1db61-151">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="1db61-152">DeviceRenderNotFunctioningEventRatio > = 0,005</span><span class="sxs-lookup"><span data-stu-id="1db61-152">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="1db61-153">DeviceCaptureNotFunctioningEventRatio > = 0,005</span><span class="sxs-lookup"><span data-stu-id="1db61-153">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="1db61-154">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="1db61-154">Related topics</span></span>
[<span data-ttu-id="1db61-155">Настройка средства аналитики звонков в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="1db61-155">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="1db61-156">Вызов аналитики и панель мониторинга качества звонка</span><span class="sxs-lookup"><span data-stu-id="1db61-156">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
