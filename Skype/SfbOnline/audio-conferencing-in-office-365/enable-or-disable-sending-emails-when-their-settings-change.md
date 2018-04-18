---
title: Включение и отключение отправки по электронной почте при изменении их параметров
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 9db213285a24ad0a67d305a84f275f21ce741013
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a><span data-ttu-id="a53b9-103">Включение и отключение отправки сообщения электронной почты при изменении параметров аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="a53b9-103">Enable or disable sending emails when Audio Conferencing settings change</span></span>

<span data-ttu-id="a53b9-104">Пользователи автоматически уведомления по электронной почте, включенный для аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="a53b9-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="a53b9-105">Возможны ситуации, тем не менее, если требуется сократить число сообщений, отправленных в Скайп для бизнеса и группами Майкрософт пользователя.</span><span class="sxs-lookup"><span data-stu-id="a53b9-105">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business and Microsoft Teams user.</span></span> <span data-ttu-id="a53b9-106">В таких случаях можно отключить отправку электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a53b9-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="a53b9-107">Если отключить отправку сообщения электронной почты, аудиоконференций по электронной почте не будут отправлены для пользователей, в том числе по электронной почте для пользователей включены или отключены для аудиоконференций, когда сбросить свой ПИН-код, а идентификатор конференции и конференц-связи по умолчанию телефонный номер изменения .</span><span class="sxs-lookup"><span data-stu-id="a53b9-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="a53b9-108">Ниже приведен пример сообщений электронной почты, которое отправляется пользователям, когда они были включены для аудиоконференции:</span><span class="sxs-lookup"><span data-stu-id="a53b9-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Звукового конференц-связи электронной почты](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="a53b9-110">Когда пользователи получают уведомления по электронной почте?</span><span class="sxs-lookup"><span data-stu-id="a53b9-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="a53b9-111">Существует несколько сообщений электронной почты, отправленных для пользователей в вашей организации после их, необходимо включить для аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="a53b9-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="a53b9-112">Если для них назначена лицензия на **Аудиоконференции** .</span><span class="sxs-lookup"><span data-stu-id="a53b9-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="a53b9-113">При сбросе вручную аудиоконференций ПИН-код пользователя.</span><span class="sxs-lookup"><span data-stu-id="a53b9-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="a53b9-114">Выполнение сброса идентификатора конференции пользователя вручную.</span><span class="sxs-lookup"><span data-stu-id="a53b9-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="a53b9-115">При лицензии **Аудиоконференции** удаляется из них.</span><span class="sxs-lookup"><span data-stu-id="a53b9-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="a53b9-116">Поставщик услуг аудиоконференций пользователя изменении корпорацией Майкрософт на другой поставщик или **Нет**.</span><span class="sxs-lookup"><span data-stu-id="a53b9-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="a53b9-117">При изменении поставщика аудиоконференций пользователя в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a53b9-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>
    
## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="a53b9-118">Включение или отключение сообщением электронной почты, отправляемые пользователями</span><span class="sxs-lookup"><span data-stu-id="a53b9-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="a53b9-119">Группами Майкрософт, Скайп по центру администрирования Business или Windows PowerShell можно использовать для включения или отключения электронной почты для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a53b9-119">You can use Microsoft Teams, the Skype for Business admin center, or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="a53b9-120">**Использование групп Майкрософт и Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="a53b9-120">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>
1. <span data-ttu-id="a53b9-121">В левой области переходов, перейдите к **собраниям** > **Мостов конференции**.</span><span class="sxs-lookup"><span data-stu-id="a53b9-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="a53b9-122">В верхней части страницы **Мостов конференции** нажмите кнопку **Параметры Bridge**.</span><span class="sxs-lookup"><span data-stu-id="a53b9-122">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="a53b9-123">В области **Параметры Bridge** Включение или отключение **автоматически отправлять сообщения электронной почты пользователям при их параметров - связи**.</span><span class="sxs-lookup"><span data-stu-id="a53b9-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="a53b9-124">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="a53b9-124">Click **Apply**.</span></span>
  
<span data-ttu-id="a53b9-125">**С помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="a53b9-125">**Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="a53b9-126">В **Скайп по центру администрирования бизнеса**, на панели навигации слева щелкните **звук конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="a53b9-126">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="a53b9-127">На странице **параметров Microsoft моста** установите или снимите **автоматически отправлять сообщения электронной почты пользователям при их параметров аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="a53b9-127">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="a53b9-128">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="a53b9-128">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="a53b9-129">Можно также отправлять электронной почты для пользователя с помощью параметров аудиоконференций, перейдя на **аудиоконференции** > **пользователей**, выделите пользователя и нажмите кнопку **Отправить сведения о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="a53b9-129">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="a53b9-130">После этого, которая содержит только идентификатор конференции и конференции номер телефона, но не ПИН-код будет отправлено сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a53b9-130">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="a53b9-131">[Отправить сообщение электронной почты для пользователя с помощью их сведения аудиоконференции](send-an-email-to-a-user-with-their-dial-in-information.md) более подробные сведения.</span><span class="sxs-lookup"><span data-stu-id="a53b9-131">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
<span data-ttu-id="a53b9-132">**С помощью Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a53b9-132">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="a53b9-133">Выполните следующие действия, чтобы отключить отправку сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a53b9-133">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="a53b9-134">Справка с помощью этого командлета [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)см.</span><span class="sxs-lookup"><span data-stu-id="a53b9-134">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="a53b9-135">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="a53b9-135">What else should you know?</span></span>

- <span data-ttu-id="a53b9-136">При отключении автоматического по электронной почте может вручную активировать отправку сообщения электронной почты с конференции идентификатор и номер телефона с помощью Скайп по центру администрирования бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a53b9-136">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="a53b9-137">Тем не менее если этого ПИН-кода, не будут включены.</span><span class="sxs-lookup"><span data-stu-id="a53b9-137">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="a53b9-138">Если требуется сбросить аудиоконференций ПИН-кода и отправка по электронной почте отключена, необходимо будет отправить его пользователю, с другой стороны.</span><span class="sxs-lookup"><span data-stu-id="a53b9-138">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="a53b9-139">Отключить отправку уведомлений по электронной почте можно в Центре администрирования Skype для бизнеса или с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a53b9-139">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="a53b9-140">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a53b9-140">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="a53b9-141">Можно использовать эти командлеты для экономии времени или автоматизировать этот процесс.</span><span class="sxs-lookup"><span data-stu-id="a53b9-141">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="a53b9-142">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="a53b9-142">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="a53b9-143">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="a53b9-143">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="a53b9-144">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="a53b9-144">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="a53b9-145">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="a53b9-145">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  <span data-ttu-id="a53b9-p104">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="a53b9-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a53b9-149">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="a53b9-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="a53b9-150">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a53b9-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="a53b9-p105">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="a53b9-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="a53b9-153">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a53b9-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="a53b9-154">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a53b9-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="a53b9-155">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a53b9-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="a53b9-p106">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="a53b9-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a53b9-158">See also</span><span class="sxs-lookup"><span data-stu-id="a53b9-158">Related topics</span></span>

[<span data-ttu-id="a53b9-159">Отправить пользователям при изменении их параметров звука конференц-связи по электронной почте</span><span class="sxs-lookup"><span data-stu-id="a53b9-159">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="a53b9-160">Отправка пользователям электронных писем с информацией о конференции с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="a53b9-160">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


