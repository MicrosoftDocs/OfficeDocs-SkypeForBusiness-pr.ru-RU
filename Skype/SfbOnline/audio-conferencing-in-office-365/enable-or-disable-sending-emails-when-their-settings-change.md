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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Узнайте, как включать и отключать отправку писем с помощью Skype пользователям при изменении настроек, например ПИН-кода или номера для аудиоконференций по умолчанию. '
ms.openlocfilehash: 6b9e67d8c87b023409b7934a944f298487f91289
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114255"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="75d39-103">Включение и отключение отправки сообщений электронной почты при изменении параметров аудиоконференций в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="75d39-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="75d39-104">Если необходимо включить или отключить отправку сообщений электронной почты в Microsoft Teams, см. статью [Включение и отключение отправки сообщений электронной почты при изменении параметров аудиоконференций в Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span><span class="sxs-lookup"><span data-stu-id="75d39-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="75d39-105">Пользователи автоматически получают уведомления по электронной почте, если они активированы для аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="75d39-105">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="75d39-106">Однако иногда вам может потребоваться уменьшить количество сообщений электронной почты, от отправленных пользователям Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="75d39-106">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users.</span></span> <span data-ttu-id="75d39-107">В этом случае можно отключить функцию отправки сообщений по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="75d39-107">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="75d39-108">Если отключить отправку сообщений электронной почты, электронные сообщения для аудиоконференции не будут отправляться пользователям, включая сообщения электронной почты о том, когда пользователи включены или отключены для аудиоконференции, когда сбрасывается ПИН-код, а также когда изменяется код конференции и номер телефона конференц-связи по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="75d39-108">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="75d39-109">Вот пример сообщения электронной почты, которое отправляется пользователям, если для них включена аудиоконференция:</span><span class="sxs-lookup"><span data-stu-id="75d39-109">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Сообщение электронной почты относительно аудиоконференции](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="75d39-111">Когда пользователи получают уведомления по электронной почте?</span><span class="sxs-lookup"><span data-stu-id="75d39-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="75d39-112">После включения аудиоконференции пользователям в организации отправляется несколько сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="75d39-112">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="75d39-113">При назначении пользователям лицензии **аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="75d39-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="75d39-114">При сбросе ПИН-кода аудиоконференции пользователя вручную.</span><span class="sxs-lookup"><span data-stu-id="75d39-114">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="75d39-115">Выполнение сброса идентификатора конференции пользователя вручную.</span><span class="sxs-lookup"><span data-stu-id="75d39-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="75d39-116">Если удаляется лицензия  **Аудиоконференции**.</span><span class="sxs-lookup"><span data-stu-id="75d39-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="75d39-117">При смене поставщика услуг аудиоконференций для пользователя с Microsoft на другого поставщика или на **"Нет".**</span><span class="sxs-lookup"><span data-stu-id="75d39-117">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="75d39-118">При смене поставщика услуг аудиоконференций пользователя на Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="75d39-118">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="75d39-119">Включить или отключить отправку электронной почты пользователям</span><span class="sxs-lookup"><span data-stu-id="75d39-119">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="75d39-120">Вы можете использовать Центр администрирования Skype для бизнеса или Windows PowerShell, чтобы включить или отключить отправку сообщений электронной почты пользователям.</span><span class="sxs-lookup"><span data-stu-id="75d39-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

 
<span data-ttu-id="75d39-121">![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="75d39-121">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="75d39-122">В Центре **администрирования Skype** для бизнеса на левой навигации щелкните **"Аудиоконференция".**</span><span class="sxs-lookup"><span data-stu-id="75d39-122">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="75d39-123">На странице **Параметры моста Microsoft** поставьте или снимите флажок **Автоматически отправлять сообщения пользователям при изменении их параметров аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="75d39-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="75d39-124">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="75d39-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="75d39-125">Можно также отправить сообщение электронной почты с параметрами аудиоконференции пользователю, выбрав **Аудиоконференции** > **Пользователи**, выбрав пользователя и нажав **Отправить сведения о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="75d39-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="75d39-126">В этом случае вам будет отправлено сообщение электронной почты, в которое будут включены только код конференции и номер телефона конференции, но не ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="75d39-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="75d39-127">Дополнительные [сведения см.](send-an-email-to-a-user-with-their-dial-in-information.md) в сообщении "Отправка пользователю сообщения электронной почты с информацией об аудиоконференции".</span><span class="sxs-lookup"><span data-stu-id="75d39-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="75d39-128">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="75d39-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="75d39-129">Для отключения отправки сообщений электронной почты выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="75d39-129">Run the following to disable sending emails:</span></span> 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="75d39-130">См. справку относительно этого командлета: [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings).</span><span class="sxs-lookup"><span data-stu-id="75d39-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="75d39-131">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="75d39-131">What else should you know?</span></span>

- <span data-ttu-id="75d39-132">Если автоматическая отправка электронной почты отключена, с помощью Центра администрирования Skype для бизнеса можно вручную отправить сообщение электронной почты с ид. конференции и номером телефона.</span><span class="sxs-lookup"><span data-stu-id="75d39-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="75d39-133">Однако при этом ПИН-код не включается.</span><span class="sxs-lookup"><span data-stu-id="75d39-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="75d39-134">Если вы хотите сбросить ПИН-код аудиоконференции и отправка сообщений электронной почты отключена, отправьте его пользователю другим способом.</span><span class="sxs-lookup"><span data-stu-id="75d39-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="75d39-135">Отключить отправку уведомлений по электронной почте можно в Центре администрирования Skype для бизнеса или с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75d39-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="75d39-136">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="75d39-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="75d39-137">Можно использовать эти командлеты для экономии времени или автоматизировать этот процесс.</span><span class="sxs-lookup"><span data-stu-id="75d39-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="75d39-138">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="75d39-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
  - [<span data-ttu-id="75d39-139">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="75d39-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](/powershell/module/skype/Remove-CsOnlineDialInConferencingTenantSettings)
    
  - [<span data-ttu-id="75d39-140">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="75d39-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](/powershell/module/skype/Get-CsOnlineDialinConferencingTenantConfiguration)
    
  - [<span data-ttu-id="75d39-141">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="75d39-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
- <span data-ttu-id="75d39-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="75d39-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="75d39-143">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="75d39-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="75d39-144">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="75d39-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="75d39-145">Зачем нужно использовать Microsoft 365 или Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="75d39-145">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="75d39-146">[Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="75d39-146">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="75d39-147">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="75d39-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="75d39-148">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="75d39-148">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="75d39-149">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="75d39-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="75d39-150">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="75d39-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="75d39-151">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="75d39-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="75d39-p106">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="75d39-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="75d39-154">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="75d39-154">Related topics</span></span>

[<span data-ttu-id="75d39-155">Сообщения электронной почты, отправленные пользователям при изменении параметров аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="75d39-155">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="75d39-156">Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="75d39-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)