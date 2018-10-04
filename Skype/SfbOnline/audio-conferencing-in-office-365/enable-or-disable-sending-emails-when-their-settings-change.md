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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Узнайте, как включать и отключать отправку писем с помощью Skype пользователям при изменении настроек, например ПИН-кода или номера для аудиоконференций по умолчанию. '
ms.openlocfilehash: a9100de01fc835916af54d08b84dbd03a06ec1d6
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370876"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="a3c6f-103">Включение и отключение отправки сообщений электронной почты при изменении параметров аудиоконференций в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a3c6f-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="a3c6f-104">Если необходимо включить или отключить отправку сообщений электронной почты в Microsoft Teams, см. статью [Включение и отключение отправки сообщений электронной почты при изменении параметров аудиоконференций в Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span><span class="sxs-lookup"><span data-stu-id="a3c6f-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="a3c6f-p101">Users are automatically notified by email when they are enabled for Audio Conferencing. There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users. In such cases, you can disable sending email.</span><span class="sxs-lookup"><span data-stu-id="a3c6f-p101">Users are automatically notified by email when they are enabled for Audio Conferencing. There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users. In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="a3c6f-108">Если отключить отправку сообщения электронной почты, аудиоконференций по электронной почте не будут отправлены для пользователей, в том числе по электронной почте для пользователей включены или отключены для аудиоконференций, когда сбросить свой ПИН-код, а идентификатор конференции и конференц-связи по умолчанию телефонный номер изменения .</span><span class="sxs-lookup"><span data-stu-id="a3c6f-108">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="a3c6f-109">Ниже приведен пример сообщений электронной почты, которое отправляется пользователям, когда они были включены для аудиоконференции:</span><span class="sxs-lookup"><span data-stu-id="a3c6f-109">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Сообщение электронной почты относительно аудиоконференции](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="a3c6f-111">Когда пользователи получают уведомления по электронной почте?</span><span class="sxs-lookup"><span data-stu-id="a3c6f-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="a3c6f-112">Существует несколько сообщений электронной почты, отправленных для пользователей в вашей организации после их, необходимо включить для аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="a3c6f-112">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="a3c6f-113">Если пользователям назначена лицензия **Аудиоконференции**.</span><span class="sxs-lookup"><span data-stu-id="a3c6f-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="a3c6f-114">При сбросе вручную аудиоконференций ПИН-код пользователя.</span><span class="sxs-lookup"><span data-stu-id="a3c6f-114">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="a3c6f-115">Выполнение сброса идентификатора конференции пользователя вручную.</span><span class="sxs-lookup"><span data-stu-id="a3c6f-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="a3c6f-116">Если удаляется лицензия  **Аудиоконференции**.</span><span class="sxs-lookup"><span data-stu-id="a3c6f-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="a3c6f-117">Поставщик услуг аудиоконференций пользователя изменении корпорацией Майкрософт на другой поставщик или **Нет**.</span><span class="sxs-lookup"><span data-stu-id="a3c6f-117">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="a3c6f-118">При изменении поставщика аудиоконференций пользователя в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a3c6f-118">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="a3c6f-119">Включение или отключение сообщением электронной почты, отправляемые пользователями</span><span class="sxs-lookup"><span data-stu-id="a3c6f-119">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="a3c6f-120">Скайп по центру администрирования Business или Windows PowerShell можно использовать для включения или отключения электронной почты для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a3c6f-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

 
<span data-ttu-id="a3c6f-121">![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="a3c6f-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="a3c6f-122">В **Скайп по центру администрирования бизнеса**, на панели навигации слева щелкните **звук конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="a3c6f-122">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="a3c6f-123">На странице **Параметры моста Microsoft** поставьте или снимите флажок **Автоматически отправлять сообщения пользователям при изменении их параметров аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="a3c6f-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="a3c6f-124">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a3c6f-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="a3c6f-p102">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.  If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.  See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span><span class="sxs-lookup"><span data-stu-id="a3c6f-p102">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.  If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.  See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="a3c6f-128">**С помощью Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a3c6f-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="a3c6f-129">Для отключения отправки сообщений электронной почты выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a3c6f-129">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="a3c6f-130">См. справку относительно этого командлета: [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="a3c6f-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="a3c6f-131">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="a3c6f-131">What else should you know?</span></span>

- <span data-ttu-id="a3c6f-p103">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center. However, if you do this, the PIN won't be included. If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span><span class="sxs-lookup"><span data-stu-id="a3c6f-p103">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center. However, if you do this, the PIN won't be included. If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="a3c6f-135">Отключить отправку уведомлений по электронной почте можно в Центре администрирования Skype для бизнеса или с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a3c6f-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="a3c6f-136">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3c6f-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="a3c6f-137">Можно использовать эти командлеты для экономии времени или автоматизировать этот процесс.</span><span class="sxs-lookup"><span data-stu-id="a3c6f-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="a3c6f-138">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="a3c6f-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="a3c6f-139">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="a3c6f-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="a3c6f-140">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="a3c6f-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="a3c6f-141">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="a3c6f-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- <span data-ttu-id="a3c6f-p104">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="a3c6f-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a3c6f-145">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="a3c6f-145">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="a3c6f-146">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3c6f-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="a3c6f-p105">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="a3c6f-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="a3c6f-149">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a3c6f-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="a3c6f-150">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a3c6f-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="a3c6f-151">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="a3c6f-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="a3c6f-p106">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="a3c6f-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a3c6f-154">See also</span><span class="sxs-lookup"><span data-stu-id="a3c6f-154">Related topics</span></span>

[<span data-ttu-id="a3c6f-155">Отправить пользователям при изменении их параметров звука конференц-связи по электронной почте</span><span class="sxs-lookup"><span data-stu-id="a3c6f-155">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="a3c6f-156">Отправка пользователям электронных писем с информацией о конференции с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="a3c6f-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


