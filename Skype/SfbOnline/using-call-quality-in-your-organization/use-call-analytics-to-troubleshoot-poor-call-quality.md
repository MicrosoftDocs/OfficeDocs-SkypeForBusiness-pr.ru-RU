---
title: Use Call Analytics to troubleshoot poor Skype for Business call quality
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
description: Use Call Analytics details about devices, networks, and connectivity to troubleshoot user problems with Skype for Business calls and meetings.
ms.openlocfilehash: 8f782a18dd7cb7fe7cbae73c7bd43b3e44c6928c
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality"></a><span data-ttu-id="d867c-103">Use Call Analytics to troubleshoot poor Skype for Business call quality</span><span class="sxs-lookup"><span data-stu-id="d867c-103">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>

<span data-ttu-id="d867c-104">Call Analytics helps you to troubleshoot call or connection problems with Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="d867c-104">Call Analytics helps you to troubleshoot call or connection problems with Skype for Business.</span></span> <span data-ttu-id="d867c-105">Call Analytics shows detailed information about the devices, networks, and connectivity for the calls and meetings of each user in your Skype for Business account.</span><span class="sxs-lookup"><span data-stu-id="d867c-105">Call Analytics shows detailed information about the devices, networks, and connectivity for the calls and meetings of each user in your Skype for Business account.</span></span> <span data-ttu-id="d867c-106">If building, site, and tenant information has been added to Call Analytics, it will also be shown for each call and session.</span><span class="sxs-lookup"><span data-stu-id="d867c-106">If building, site, and tenant information has been added to Call Analytics, it will also be shown for each call and session.</span></span> <span data-ttu-id="d867c-107">Information available via Call Analytics can help you figure out why a user had a poor call or meeting experience.</span><span class="sxs-lookup"><span data-stu-id="d867c-107">Information available via Call Analytics can help you figure out why a user had a poor call or meeting experience.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d867c-p102">На данный момент доступна лишь предварительная версия средства аналитики звонков. Описание и изображения в этой статье могут не соответствовать фактическому интерфейсу.</span><span class="sxs-lookup"><span data-stu-id="d867c-p102">Call Analytics is currently in preview. Text and images described here may not match your experience.</span></span>
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a><span data-ttu-id="d867c-110">Troubleshoot call quality problems using Call Analytics</span><span class="sxs-lookup"><span data-stu-id="d867c-110">Troubleshoot call quality problems using Call Analytics</span></span>

<span data-ttu-id="d867c-111">The permissions level assigned to you determines what type of information you have access to in Call Analytics:</span><span class="sxs-lookup"><span data-stu-id="d867c-111">The permissions level assigned to you determines what type of information you have access to in Call Analytics:</span></span>
  
- <span data-ttu-id="d867c-112">**Skype for Business admin**: You have access to all the information in Call Analytics and in the Skype for Business Admin center.</span><span class="sxs-lookup"><span data-stu-id="d867c-112">**Skype for Business admin**: You have access to all the information in Call Analytics and in the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="d867c-113">**Helpdesk agent with Tier 1 permissions**: You see a limited set of data in Call Analytics.</span><span class="sxs-lookup"><span data-stu-id="d867c-113">**Helpdesk agent with Tier 1 permissions**: You see a limited set of data in Call Analytics.</span></span> <span data-ttu-id="d867c-114">You can troubleshoot calls, but you'll hand off problems with meetings to a Tier 2 agent.</span><span class="sxs-lookup"><span data-stu-id="d867c-114">You can troubleshoot calls, but you'll hand off problems with meetings to a Tier 2 agent.</span></span> <span data-ttu-id="d867c-115">You don't have access to the rest of the Skype for Business Admin center.</span><span class="sxs-lookup"><span data-stu-id="d867c-115">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="d867c-116">**Helpdesk agent with Tier 2 permissions**: You see all available data in Call Analytics and can help troubleshoot problems with both calls and meetings.</span><span class="sxs-lookup"><span data-stu-id="d867c-116">**Helpdesk agent with Tier 2 permissions**: You see all available data in Call Analytics and can help troubleshoot problems with both calls and meetings.</span></span> <span data-ttu-id="d867c-117">You don't have access to the rest of the Skype for Business Admin center.</span><span class="sxs-lookup"><span data-stu-id="d867c-117">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
<span data-ttu-id="d867c-118">See your Skype for Business admin if you need help with permissions.</span><span class="sxs-lookup"><span data-stu-id="d867c-118">See your Skype for Business admin if you need help with permissions.</span></span>
  
 <span data-ttu-id="d867c-119">**Open Call Analytics as a Tier 1 or Tier 2 helpdesk agent**</span><span class="sxs-lookup"><span data-stu-id="d867c-119">**Open Call Analytics as a Tier 1 or Tier 2 helpdesk agent**</span></span>
  
1. <span data-ttu-id="d867c-120">Go to the Office 365 admin center and sign in using your work or school account.</span><span class="sxs-lookup"><span data-stu-id="d867c-120">Go to the Office 365 admin center and sign in using your work or school account.</span></span> <span data-ttu-id="d867c-121">Then in your web browser go to *https://adminportal.services.skypeforbusiness.com*.</span><span class="sxs-lookup"><span data-stu-id="d867c-121">Then in your web browser go to *https://adminportal.services.skypeforbusiness.com*.</span></span>
    
2. <span data-ttu-id="d867c-122">In **User Search**, start typing either the name or sip address of the user whose calls you want to troubleshoot and then select the user from the list.</span><span class="sxs-lookup"><span data-stu-id="d867c-122">In **User Search**, start typing either the name or sip address of the user whose calls you want to troubleshoot and then select the user from the list.</span></span>
    
    ![Screenshot of the User Search box of Call Analytics in the Skype for Business Admin Center.](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. <span data-ttu-id="d867c-124">In **Call history**, select the call or meeting that you want to troubleshoot.</span><span class="sxs-lookup"><span data-stu-id="d867c-124">In **Call history**, select the call or meeting that you want to troubleshoot.</span></span>
    
    ![Screenshot shows the call history page for a user with information such as the user's contact details, a summary of the 7-day quality and activity for meetings and calls, and an overview of dates and times, recipients, and audio quality,](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. <span data-ttu-id="d867c-126">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span><span class="sxs-lookup"><span data-stu-id="d867c-126">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="d867c-127">In the session details for each call or meeting, minor issues appear in yellow.</span><span class="sxs-lookup"><span data-stu-id="d867c-127">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="d867c-128">(For example, in the following screenshot, the values are in yellow for Average jitter, Max jitter, and Average packet loss rate.) If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span><span class="sxs-lookup"><span data-stu-id="d867c-128">(For example, in the following screenshot, the values are in yellow for Average jitter, Max jitter, and Average packet loss rate.) If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="d867c-129">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span><span class="sxs-lookup"><span data-stu-id="d867c-129">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
    
    ![Screenshot shows the Advanced tab of a user's Call history with the Inbound network section expanded to reveal that the data for average jitter, max jitter, and average packet loss rate are shown in a yellow color, meaning they are minor issues.](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
<span data-ttu-id="d867c-131">In rare cases, quality of experience data isn't received for audio sessions.</span><span class="sxs-lookup"><span data-stu-id="d867c-131">In rare cases, quality of experience data isn't received for audio sessions.</span></span> <span data-ttu-id="d867c-132">Often this is caused by the call dropping and connection with the client terminating.</span><span class="sxs-lookup"><span data-stu-id="d867c-132">Often this is caused by the call dropping and connection with the client terminating.</span></span> <span data-ttu-id="d867c-133">When this occurs, the session rating is "unavailable".</span><span class="sxs-lookup"><span data-stu-id="d867c-133">When this occurs, the session rating is "unavailable".</span></span>
  
<span data-ttu-id="d867c-134">For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as "poor."</span><span class="sxs-lookup"><span data-stu-id="d867c-134">For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as "poor."</span></span>
  
|<span data-ttu-id="d867c-135">**Ошибка**</span><span class="sxs-lookup"><span data-stu-id="d867c-135">**Issue**</span></span>|<span data-ttu-id="d867c-136">**Area**</span><span class="sxs-lookup"><span data-stu-id="d867c-136">**Area**</span></span>|<span data-ttu-id="d867c-137">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d867c-137">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d867c-138">Call setup</span><span class="sxs-lookup"><span data-stu-id="d867c-138">Call setup</span></span>  <br/> |<span data-ttu-id="d867c-139">Session</span><span class="sxs-lookup"><span data-stu-id="d867c-139">Session</span></span>  <br/> |<span data-ttu-id="d867c-140">The error code Ms-diag 20-29 indicates the call setup failed.</span><span class="sxs-lookup"><span data-stu-id="d867c-140">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="d867c-141">The user couldn't join the call or meeting.</span><span class="sxs-lookup"><span data-stu-id="d867c-141">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="d867c-142">Audio network classified poor call</span><span class="sxs-lookup"><span data-stu-id="d867c-142">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="d867c-143">Session</span><span class="sxs-lookup"><span data-stu-id="d867c-143">Session</span></span>  <br/> |<span data-ttu-id="d867c-144">Network quality issues were encountered in areas such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio.</span><span class="sxs-lookup"><span data-stu-id="d867c-144">Network quality issues were encountered in areas such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio.</span></span> <span data-ttu-id="d867c-145">For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).</span><span class="sxs-lookup"><span data-stu-id="d867c-145">For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).</span></span>  <br/> |
|<span data-ttu-id="d867c-146">Device not functioning</span><span class="sxs-lookup"><span data-stu-id="d867c-146">Device not functioning</span></span>  <br/> |<span data-ttu-id="d867c-147">Device</span><span class="sxs-lookup"><span data-stu-id="d867c-147">Device</span></span>  <br/> | <span data-ttu-id="d867c-148">A device isn't functioning correctly.</span><span class="sxs-lookup"><span data-stu-id="d867c-148">A device isn't functioning correctly.</span></span> <span data-ttu-id="d867c-149">Device not functioning ratios are :</span><span class="sxs-lookup"><span data-stu-id="d867c-149">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="d867c-150">DeviceRenderNotFunctioningEventRatio >= 0.005</span><span class="sxs-lookup"><span data-stu-id="d867c-150">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="d867c-151">DeviceCaptureNotFunctioningEventRatio >= 0.005</span><span class="sxs-lookup"><span data-stu-id="d867c-151">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="d867c-152">See also</span><span class="sxs-lookup"><span data-stu-id="d867c-152">Related topics</span></span>
[<span data-ttu-id="d867c-153">Настройка средства аналитики звонков в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="d867c-153">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="d867c-154">В чем разница между средством аналитики звонков и панелью мониторинга качества звонков?</span><span class="sxs-lookup"><span data-stu-id="d867c-154">What's the difference between Call Analytics and Call Quality Dashboard?</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 