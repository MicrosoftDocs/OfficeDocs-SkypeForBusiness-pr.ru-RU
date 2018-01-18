---
title: "Включение и отключение отправки по электронной почте при изменении их параметров"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 4efabf42f7253d89b37282103a3046cf7b2b0d26
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2017
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a><span data-ttu-id="a234d-103">Включение и отключение отправки сообщения электронной почты при изменении параметров аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="a234d-103">Enable or disable sending emails when Audio Conferencing settings change</span></span>

<span data-ttu-id="a234d-104">Пользователи автоматически уведомления по электронной почте, включенный для аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="a234d-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="a234d-105">Возможны ситуации, тем не менее, если требуется сократить число сообщений, отправленных в Скайп для бизнеса и группами Майкрософт пользователя.</span><span class="sxs-lookup"><span data-stu-id="a234d-105">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business and Microsoft Teams user.</span></span> <span data-ttu-id="a234d-106">В таких случаях можно отключить отправку электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a234d-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="a234d-107">Если отключить отправку сообщения электронной почты, аудиоконференций по электронной почте не будут отправлены для пользователей, в том числе по электронной почте для пользователей включены или отключены для аудиоконференций, когда сбросить свой ПИН-код, а идентификатор конференции и конференц-связи по умолчанию телефонный номер изменения .</span><span class="sxs-lookup"><span data-stu-id="a234d-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="a234d-108">Ниже приведен пример сообщений электронной почты, которое отправляется пользователям, когда они были включены для аудиоконференции:</span><span class="sxs-lookup"><span data-stu-id="a234d-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Звукового конференц-связи электронной почты](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="a234d-110">Когда пользователи получают уведомления по электронной почте?</span><span class="sxs-lookup"><span data-stu-id="a234d-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="a234d-111">Существует несколько сообщений электронной почты, отправленных для пользователей в вашей организации после их, необходимо включить для аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="a234d-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="a234d-112">Если для них назначена лицензия на **Аудиоконференции** .</span><span class="sxs-lookup"><span data-stu-id="a234d-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="a234d-113">При сбросе вручную аудиоконференций ПИН-код пользователя.</span><span class="sxs-lookup"><span data-stu-id="a234d-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="a234d-114">Выполнение сброса идентификатора конференции пользователя вручную.</span><span class="sxs-lookup"><span data-stu-id="a234d-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="a234d-115">При лицензии **Аудиоконференции** удаляется из них.</span><span class="sxs-lookup"><span data-stu-id="a234d-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="a234d-116">Поставщик услуг аудиоконференций пользователя изменении корпорацией Майкрософт на другой поставщик или **Нет**.</span><span class="sxs-lookup"><span data-stu-id="a234d-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="a234d-117">При изменении поставщика аудиоконференций пользователя в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a234d-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>
    
## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="a234d-118">Включение или отключение сообщением электронной почты, отправляемые пользователями</span><span class="sxs-lookup"><span data-stu-id="a234d-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="a234d-119">Скайп по центру администрирования Business или Windows PowerShell можно использовать для включения или отключения электронной почты для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a234d-119">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>
  
 <span data-ttu-id="a234d-120">**С помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="a234d-120">**Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="a234d-121">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="a234d-121">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="a234d-122">Перейдите в **Центр администрирования Office 365** > **Скайп для бизнеса**и на панели навигации слева щелкните **звук конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="a234d-122">Go to the **Office 365 admin center** > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="a234d-123">На странице **параметров Microsoft моста** установите или снимите **автоматически отправлять сообщения электронной почты пользователям при их параметров аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="a234d-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="a234d-124">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a234d-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="a234d-125">Можно также отправлять электронной почты для пользователя с помощью параметров аудиоконференций, перейдя на **аудиоконференции** > **пользователей**, выделите пользователя и нажмите кнопку **Отправить сведения о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="a234d-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="a234d-126">После этого, которая содержит только идентификатор конференции и конференции номер телефона, но не ПИН-код будет отправлено сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a234d-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="a234d-127">[Отправить сообщение электронной почты для пользователя с помощью их сведения аудиоконференции](send-an-email-to-a-user-with-their-dial-in-information.md) более подробные сведения.</span><span class="sxs-lookup"><span data-stu-id="a234d-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
 <span data-ttu-id="a234d-128">**С помощью Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a234d-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="a234d-129">Выполните следующие действия, чтобы отключить отправку сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="a234d-129">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="a234d-130">Справка с помощью этого командлета [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)см.</span><span class="sxs-lookup"><span data-stu-id="a234d-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="a234d-131">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="a234d-131">What else should you know?</span></span>

- <span data-ttu-id="a234d-132">При отключении автоматического по электронной почте может вручную активировать отправку сообщения электронной почты с конференции идентификатор и номер телефона с помощью Скайп по центру администрирования бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a234d-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="a234d-133">Тем не менее если этого ПИН-кода, не будут включены.</span><span class="sxs-lookup"><span data-stu-id="a234d-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="a234d-134">Если требуется сбросить аудиоконференций ПИН-кода и отправка по электронной почте отключена, необходимо будет отправить его пользователю, с другой стороны.</span><span class="sxs-lookup"><span data-stu-id="a234d-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="a234d-135">По умолчанию отправителя сообщения электронной почты будут из Office 365, но можно изменить адрес электронной почты и отображаемое имя, с помощью Windows PowerShell и также с помощью командлета [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .</span><span class="sxs-lookup"><span data-stu-id="a234d-135">By default, the sender of the emails will be from Office 365, but you can change the email address and display name using Windows PowerShell and also use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="a234d-136">Если вы хотите изменить сведения об адресе электронной почты, необходимо убедитесь в том, что политики входящей электронной почты в вашей среде разрешить сообщения электронной почты, полученные из настраиваемые указан адрес отправителя.</span><span class="sxs-lookup"><span data-stu-id="a234d-136">If you want to change the email address information, you need to make sure that the inbound email policies of your environment allow emails that come from the custom specified from address.</span></span>
  
  - <span data-ttu-id="a234d-137">Введите адрес электронной почты в параметр  _SendEmailFromAddress_.</span><span class="sxs-lookup"><span data-stu-id="a234d-137">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>
    
  - <span data-ttu-id="a234d-138">Введите отображаемое имя в параметр  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="a234d-138">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
  - <span data-ttu-id="a234d-139">Установите для параметра _SendEmailOverride_ значение _True_.</span><span class="sxs-lookup"><span data-stu-id="a234d-139">Set the  _SendEmailOverride_ parameter to _True_.</span></span>
    
  -  `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
- <span data-ttu-id="a234d-140">Отключить отправку уведомлений по электронной почте можно в Центре администрирования Skype для бизнеса или с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a234d-140">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="a234d-141">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a234d-141">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="a234d-142">Можно использовать эти командлеты для экономии времени или автоматизировать этот процесс.</span><span class="sxs-lookup"><span data-stu-id="a234d-142">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="a234d-143">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="a234d-143">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="a234d-144">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="a234d-144">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="a234d-145">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="a234d-145">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="a234d-146">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="a234d-146">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  <span data-ttu-id="a234d-147">Windows PowerShell — все сведения об управлении пользователями и какие пользователи разрешенные или запрещенные для.</span><span class="sxs-lookup"><span data-stu-id="a234d-147">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="a234d-148">С помощью Windows PowerShell можно управлять Office 365 с помощью точки администрирования, которые можно упростить повседневной работой при наличии нескольких задач для выполнения.</span><span class="sxs-lookup"><span data-stu-id="a234d-148">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="a234d-149">Для начала работы с оболочкой Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="a234d-149">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a234d-150">Почему необходимо использовать Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a234d-150">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="a234d-151">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a234d-151">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="a234d-152">Windows PowerShell имеет много преимуществ в скорости, простоты и повышения производительности по сравнению только с помощью центра администрирования Office 365, например, при внесении изменений параметров для нескольких пользователей за один раз.</span><span class="sxs-lookup"><span data-stu-id="a234d-152">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="a234d-153">Сведения об этих преимуществах в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="a234d-153">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="a234d-154">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a234d-154">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="a234d-155">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a234d-155">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="a234d-156">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a234d-156">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="a234d-p106">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="a234d-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a234d-159">См. также:</span><span class="sxs-lookup"><span data-stu-id="a234d-159">Related topics</span></span>

[<span data-ttu-id="a234d-160">Отправить пользователям при изменении их параметров звука конференц-связи по электронной почте</span><span class="sxs-lookup"><span data-stu-id="a234d-160">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="a234d-161">Отправить сообщение электронной почты для пользователя с помощью их сведения аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="a234d-161">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)

[<span data-ttu-id="a234d-162">Настройка аудиоконференций в Skype для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a234d-162">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

