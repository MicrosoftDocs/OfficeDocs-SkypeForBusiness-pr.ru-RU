---
title: Включение и отключение отправки сообщений электронной почты при изменении параметров аудиоконференций в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Узнайте, как включать и отключать отправку писем с помощью Skype пользователям при изменении настроек, например ПИН-кода или номера для аудиоконференций по умолчанию. '
ms.openlocfilehash: 7c9c768dfc8bb01bdcbc8e9f20bec1bd980b1e0d
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23864318"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="e2af3-103">Включение и отключение отправки сообщений электронной почты при изменении параметров аудиоконференций в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="e2af3-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="e2af3-104">Если необходимо включить или отключить отправку сообщений электронной почты в Microsoft Teams, см. статью [Включение и отключение отправки сообщений электронной почты при изменении параметров аудиоконференций в Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span><span class="sxs-lookup"><span data-stu-id="e2af3-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="e2af3-105">Пользователи автоматически получают уведомления по электронной почте, если они активированы для аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="e2af3-105">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="e2af3-106">В некоторых случаях требуется сократить количество уведомлений по электронной почте, отправляемых пользователям Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e2af3-106">There may be times though when you want to reduce the number of emails that are sent to users, and in that case you can disable this.</span></span> <span data-ttu-id="e2af3-107">В этом случае можно отключить функцию отправки сообщений по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="e2af3-107">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="e2af3-108">Если отправка уведомлений по электронной почте отключена, пользователи не будут получать сообщения электронной почты, включая сообщения о разрешении/запрете на использование аудиоконференции, а также о сбросе ПИН-кода и изменении идентификатора конференции или стандартного телефонного номера конференции.</span><span class="sxs-lookup"><span data-stu-id="e2af3-108">If you disable sending emails, all dial-in conferencing emails won't be sent to your users including emails for when users are enabled or disabled for dial-in conferencing, when their PIN is reset, when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="e2af3-109">Далее приведен пример сообщения электронной почты, отправленного пользователям, для которых разрешена аудиоконференция.</span><span class="sxs-lookup"><span data-stu-id="e2af3-109">Here is an example of the email that is sent to users that are enabled for dial-in conferencing:</span></span>
  
![Сообщение электронной почты относительно аудиоконференции](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="e2af3-111">Когда пользователи получают уведомления по электронной почте?</span><span class="sxs-lookup"><span data-stu-id="e2af3-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="e2af3-112">Когда пользователям разрешена функция аудиоконференции, для них устанавливается отправка нескольких электронных писем в указанных ниже случаях.</span><span class="sxs-lookup"><span data-stu-id="e2af3-112">There are several emails that are set to users in your organization after they are enabled for dial-in conferencing:</span></span>
    
  - <span data-ttu-id="e2af3-113">Если пользователям назначена лицензия **Аудиоконференции**.</span><span class="sxs-lookup"><span data-stu-id="e2af3-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="e2af3-114">При ручном сбросе ПИН-кода аудиоконференции пользователя.</span><span class="sxs-lookup"><span data-stu-id="e2af3-114">When you manually reset the user's dial-in conferencing PIN.</span></span>
    
  - <span data-ttu-id="e2af3-115">При ручном сбросе идентификатора конференции пользователя.</span><span class="sxs-lookup"><span data-stu-id="e2af3-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="e2af3-116">Если удаляется лицензия  **Аудиоконференции**.</span><span class="sxs-lookup"><span data-stu-id="e2af3-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="e2af3-117">При изменении поставщика услуг аудиоконференций (по умолчанию  Microsoft) или указании параметра **Нет**.</span><span class="sxs-lookup"><span data-stu-id="e2af3-117">When the dial-in conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="e2af3-118">При изменении поставщика услуг аудиоконференций обратно на Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e2af3-118">When the dial-in conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="e2af3-119">Включение или отключение отправки сообщений электронной почты пользователям</span><span class="sxs-lookup"><span data-stu-id="e2af3-119">Enable or disable email from being sent to dial-in users</span></span>

<span data-ttu-id="e2af3-120">Можно использовать центр администрирования Skype для бизнеса или Windows PowerShell для включения или отключения отправки сообщений электронной почты пользователям.</span><span class="sxs-lookup"><span data-stu-id="e2af3-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email from being sent to users.</span></span>

 
<span data-ttu-id="e2af3-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="e2af3-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="e2af3-122">В левой панели **центра администрирования Skype для бизнеса** нажмите **Аудиоконференции**.</span><span class="sxs-lookup"><span data-stu-id="e2af3-122">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**Microsoft bridge settings.</span></span>
    
2. <span data-ttu-id="e2af3-123">На странице **Параметры моста Microsoft** установите или снимите флажок **Автоматически отправлять сообщения пользователям при изменении их параметров аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="e2af3-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="e2af3-124">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="e2af3-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="e2af3-125">Можно также отправить сообщение электронной почты с параметрами аудиоконференции пользователю, выбрав **Аудиоконференции** > **Пользователи**, выбрав пользователя и нажав **Отправить сведения о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="e2af3-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="e2af3-126">В этом случае будет отправлено сообщение электронной почты, которое включает только идентификатор и номер телефона конференции. Сообщение не будет содержать ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="e2af3-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>  <span data-ttu-id="e2af3-127">Для получения дополнительной информации см. [Отправка пользователям сообщений электронной почты с информацией об их параметрах аудиоконференций](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="e2af3-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="e2af3-128">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e2af3-128">**Using Windows PowerShell to manage Lync Online**</span></span>
  
- <span data-ttu-id="e2af3-129">Для отключения отправки сообщений электронной почты выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="e2af3-129">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="e2af3-130">См. справку относительно этого командлета: [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="e2af3-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="e2af3-131">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="e2af3-131">What else should you know?</span></span>

- <span data-ttu-id="e2af3-132">Когда автоматическая отправка уведомлений по электронной почте отключена, можно запускать отправку уведомлений с идентификатором конференции и номером телефона вручную, с помощью центра администрирования Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="e2af3-132">When automatic emails are disabled, you can still can manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="e2af3-133">Однако при этом в письме будет отсутствовать ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="e2af3-133">However, if you do this the PIN won't be included.</span></span> <span data-ttu-id="e2af3-134">Если требуется сбросить ПИН-код аудиоконференции, а отправка уведомлений по электронной почте отключена, выберите другой способ отправки.</span><span class="sxs-lookup"><span data-stu-id="e2af3-134">If you want to reset the dial-in conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="e2af3-135">Отключить отправку уведомлений по электронной почте можно в центре администрирования Skype для бизнеса или с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2af3-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="e2af3-136">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2af3-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="e2af3-137">Можно использовать эти командлеты для экономии времени или автоматизировать этот процесс.</span><span class="sxs-lookup"><span data-stu-id="e2af3-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="e2af3-138">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="e2af3-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="e2af3-139">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="e2af3-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="e2af3-140">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="e2af3-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="e2af3-141">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="e2af3-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  <span data-ttu-id="e2af3-p104">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="e2af3-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e2af3-145">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="e2af3-145">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="e2af3-146">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2af3-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="e2af3-p105">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="e2af3-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="e2af3-149">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="e2af3-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="e2af3-150">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="e2af3-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="e2af3-151">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="e2af3-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="e2af3-p106">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="e2af3-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e2af3-154">См. также:</span><span class="sxs-lookup"><span data-stu-id="e2af3-154">Related topics</span></span>

[<span data-ttu-id="e2af3-155">Сообщения электронной почты, отправляемые пользователям при изменении параметров аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="e2af3-155">Emails sent to users when their settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="e2af3-156">Отправка пользователям сообщений электронной почты с информацией об их параметрах аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="e2af3-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


