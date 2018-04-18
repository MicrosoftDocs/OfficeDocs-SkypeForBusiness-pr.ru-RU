---
title: Admins Configure Skype for Business settings for individual users
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.custom:
- Setup
- LIL_Placement
description: 'Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. '
ms.openlocfilehash: 930960117a46639e86ed2d24c286a5270b21acb9
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="cf2e1-103">Admins: Configure Skype for Business settings for individual users</span><span class="sxs-lookup"><span data-stu-id="cf2e1-103">Admins: Configure Skype for Business settings for individual users</span></span>

<span data-ttu-id="cf2e1-104">This article explains how admins configure Skype for Business for a small number of users.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-104">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="cf2e1-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="cf2e1-106">To allow (or block) everyone in your business to communicate with external people, see:</span><span class="sxs-lookup"><span data-stu-id="cf2e1-106">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="cf2e1-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="cf2e1-108">The article also explains how to block communication with specific domains.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-108">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="cf2e1-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="cf2e1-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="cf2e1-110">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-110">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="cf2e1-111">Configure general settings for one user</span><span class="sxs-lookup"><span data-stu-id="cf2e1-111">Configure general settings for one user</span></span>
<span data-ttu-id="cf2e1-112"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="cf2e1-112"></span></span>

<span data-ttu-id="cf2e1-113">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-113">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>
  
1. <span data-ttu-id="cf2e1-114">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-114">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="cf2e1-115">Выберите **Центры администрирования** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="cf2e1-116">Выберите **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-116">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="cf2e1-118">Choose which users you want to edit.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-118">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="cf2e1-119">В области справа выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-119">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="cf2e1-121">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-121">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="cf2e1-122">**Option**</span><span class="sxs-lookup"><span data-stu-id="cf2e1-122">**Option**</span></span>|<span data-ttu-id="cf2e1-123">**Сведения**</span><span class="sxs-lookup"><span data-stu-id="cf2e1-123">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cf2e1-124">Audio and HD video</span><span class="sxs-lookup"><span data-stu-id="cf2e1-124">Audio and HD video</span></span>  <br/> |<span data-ttu-id="cf2e1-125">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meeetings (none).</span><span class="sxs-lookup"><span data-stu-id="cf2e1-125">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meeetings (none).</span></span>  <br/> |
|<span data-ttu-id="cf2e1-126">Record conversations and meetings</span><span class="sxs-lookup"><span data-stu-id="cf2e1-126">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="cf2e1-127">Choose what this person is allowed to record.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-127">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="cf2e1-128">This option is not available with Skype for Business Basic.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-128">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="cf2e1-129">For compliance, turn off non-archived features</span><span class="sxs-lookup"><span data-stu-id="cf2e1-129">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="cf2e1-130">Choose this option if you're legally required to preserve electronically stored information.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-130">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="cf2e1-131">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in in the Exchange admin center.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-131">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in in the Exchange admin center.</span></span> <span data-ttu-id="cf2e1-132">It turns off the following features:</span><span class="sxs-lookup"><span data-stu-id="cf2e1-132">It turns off the following features:</span></span> <br/>  <span data-ttu-id="cf2e1-133">Передача файлов через службу мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="cf2e1-133">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="cf2e1-134">Общие страницы OneNote</span><span class="sxs-lookup"><span data-stu-id="cf2e1-134">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="cf2e1-135">Примечания PowerPoint</span><span class="sxs-lookup"><span data-stu-id="cf2e1-135">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="cf2e1-136">To configure these settings in bulk, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-136">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="cf2e1-137">See [Managing policies in Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="cf2e1-137">See [Managing policies in Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="cf2e1-138">Block external communications</span><span class="sxs-lookup"><span data-stu-id="cf2e1-138">Block external communications</span></span>
<span data-ttu-id="cf2e1-139"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="cf2e1-139"></span></span>

<span data-ttu-id="cf2e1-140">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-140">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="cf2e1-141">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="cf2e1-141">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="cf2e1-142">Choose **External communications**, and then clear the options as appropriate:</span><span class="sxs-lookup"><span data-stu-id="cf2e1-142">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
  - <span data-ttu-id="cf2e1-143">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-143">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
  - <span data-ttu-id="cf2e1-144">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-144">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="cf2e1-145">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-145">Click **Save**.</span></span>
    
<span data-ttu-id="cf2e1-146">To configure these settings in bulk, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-146">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="cf2e1-147">See [Managing communications in Skype for Business Online with outside users and organizations](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="cf2e1-147">See [Managing communications in Skype for Business Online with outside users and organizations](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="cf2e1-148">Edit audio conferencing settings for one user</span><span class="sxs-lookup"><span data-stu-id="cf2e1-148">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="cf2e1-149"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="cf2e1-149"></span></span>

1. <span data-ttu-id="cf2e1-150">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="cf2e1-150">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="cf2e1-151">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-151">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="cf2e1-152">**Настройка аудиоконференции**</span><span class="sxs-lookup"><span data-stu-id="cf2e1-152">**Audio conferencing setting**</span></span>|<span data-ttu-id="cf2e1-153">**Описание**</span><span class="sxs-lookup"><span data-stu-id="cf2e1-153">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cf2e1-154">**Provider name**</span><span class="sxs-lookup"><span data-stu-id="cf2e1-154">**Provider name**</span></span> <br/> |<span data-ttu-id="cf2e1-155">Choose your provider from the list.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-155">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="cf2e1-156">**Платный номер** (обязательно)</span><span class="sxs-lookup"><span data-stu-id="cf2e1-156">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="cf2e1-157">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-157">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="cf2e1-158">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-158">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="cf2e1-159">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-159">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="cf2e1-160">**Бесплатный номер**</span><span class="sxs-lookup"><span data-stu-id="cf2e1-160">**Toll-free number**</span></span> <br/> |<span data-ttu-id="cf2e1-161">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-161">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="cf2e1-162">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-162">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="cf2e1-163">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-163">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="cf2e1-164">**Conference ID and PIN** (required)</span><span class="sxs-lookup"><span data-stu-id="cf2e1-164">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="cf2e1-165">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-165">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="cf2e1-166">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-166">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="cf2e1-167">To configure these settings in bulk, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cf2e1-167">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="cf2e1-168">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="cf2e1-168">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="cf2e1-169">See also</span><span class="sxs-lookup"><span data-stu-id="cf2e1-169">Related topics</span></span> 

[<span data-ttu-id="cf2e1-170">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="cf2e1-170">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="cf2e1-171">Лицензирование надстроек Skype для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cf2e1-171">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 