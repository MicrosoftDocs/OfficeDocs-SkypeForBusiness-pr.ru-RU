---
title: Просмотр, изменение и сброс идентификатора конференц-связи, назначенного пользователю в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: 'Узнайте, как присвоить пользователю идентификатор конференции для Skype для бизнеса Online и какими должны быть параметры для установки идентификатора конференции. '
ms.openlocfilehash: b5ed8bb8ec32277e0bebca43338ae233aa6d38f6
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776844"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="2ccf7-103">Просмотр и сброс идентификатора конференции, присвоенного пользователю в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="2ccf7-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="2ccf7-104">Сведения об идентификаторах конференций пользователей в Microsoft Teams можно найти в разделе [Просмотр и сброс идентификатора конференц-связи, назначенного пользователю в Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="2ccf7-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="2ccf7-p101">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider. The conference ID assigned is sent in the meeting invite when the meeting is scheduled. Each meeting that a user schedules will get assigned a unique conference ID.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-p101">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider. The conference ID assigned is sent in the meeting invite when the meeting is scheduled. Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="2ccf7-p102">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-p102">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="2ccf7-p103">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="2ccf7-p103">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="2ccf7-112">Просмотр и сброс идентификатора конференции</span><span class="sxs-lookup"><span data-stu-id="2ccf7-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="2ccf7-113">Просмотр идентификатора конференции</span><span class="sxs-lookup"><span data-stu-id="2ccf7-113">To view the conference ID</span></span>

<span data-ttu-id="2ccf7-114">![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="2ccf7-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="2ccf7-115">Вы можете посмотреть их идентификатор конференции и отправить его пользователям.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="2ccf7-116">Войдите в свою рабочую или учебную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-116">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="2ccf7-117">Перейдите в центр администрирования > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-117">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="2ccf7-118">В **Центре администрирования Skype для бизнеса**> **Аудиоконференции** > **Пользователи**, выберите пользователя, которому необходим идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="2ccf7-119">На странице "Действия" найдите раздел **Идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="2ccf7-120">Вы можете отправить всем сведения о конференциях в сообщение электронной почты, которое содержит идентификатор конференции и звуковые номера, нажав кнопку **отправить сведения о конференции по электронной почте** , после того как вы выберете пользователя на странице **Пользователи** .</span><span class="sxs-lookup"><span data-stu-id="2ccf7-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="2ccf7-121">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="2ccf7-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="2ccf7-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span><span class="sxs-lookup"><span data-stu-id="2ccf7-p104">You can use Windows PowerShell to view the conference ID for a user. To do so, run:</span></span>

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

<span data-ttu-id="2ccf7-124">Чтобы узнать больше о командлете, ознакомьтесь со [статьей Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) .</span><span class="sxs-lookup"><span data-stu-id="2ccf7-124">See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.</span></span>


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="2ccf7-125">Сброс идентификатора конференции</span><span class="sxs-lookup"><span data-stu-id="2ccf7-125">To reset the conference ID</span></span>

<span data-ttu-id="2ccf7-126">Если, например, пользователь забыл идентификатор конференции, его можно сбросить.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-126">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="2ccf7-127">![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="2ccf7-127">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="2ccf7-128">Войдите в свою рабочую или учебную учетную запись.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-128">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="2ccf7-129">Перейдите в центр администрирования > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-129">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="2ccf7-130">В> **Audio conferencing**центре >  **администрирования Skype для бизнеса**, в разделе " **идентификатор конференции\*\*\*\*", в**области "действия" нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-130">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="2ccf7-131">В окне **Сброс ИД конференции?** нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-131">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="2ccf7-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="2ccf7-133">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="2ccf7-133">**Using Windows PowerShell**</span></span>

<span data-ttu-id="2ccf7-134">Вы можете сбросить пользовательский идентификатор конференции с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-134">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="2ccf7-135">Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="2ccf7-135">To do this, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="2ccf7-136">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="2ccf7-136">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="2ccf7-137">После создания нового идентификатора конференции или сброса номера старый идентификатор конференции нельзя использовать для вызывающих сторон.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-137">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="2ccf7-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="2ccf7-139">Пользователи могут использовать средство миграции собраний Skype для бизнеса для обновления существующих собраний.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-139">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="2ccf7-140">Сведения о том, как скачать, установить и запустить средство, можно найти в [статье: средство обновления собраний для Skype для бизнеса и Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype для бизнеса Online, инструмент переноса собраний (64-разрядная версия)](https://go.microsoft.com/fwlink/?LinkID=626047)и [Skype для бизнеса Online, средство миграции собраний (32-разр.)](https://www.microsoft.com/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="2ccf7-140">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="2ccf7-141">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-141">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="2ccf7-142">Количество цифр идентификатора конференции должно соответствовать номеру Аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-142">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="2ccf7-143">В идентификаторе конференции нельзя использовать буквы или специальные символы; можно использовать только цифры.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-143">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="2ccf7-144">Идентификатор конференции для всех пользователей аудиоконференций состоит из 7 символов по умолчанию, и количество знаков не подлежит изменению.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-144">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="2ccf7-145">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ccf7-145">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="2ccf7-p109">Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="2ccf7-149">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="2ccf7-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="2ccf7-150">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="2ccf7-150">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="2ccf7-151">Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности с помощью центра администрирования Microsoft 365, например при одновременном изменении параметров для нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="2ccf7-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="2ccf7-152">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="2ccf7-152">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="2ccf7-153">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2ccf7-153">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="2ccf7-154">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="2ccf7-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="2ccf7-155">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="2ccf7-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="2ccf7-156">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="2ccf7-156">Related topics</span></span>

[<span data-ttu-id="2ccf7-157">Пробная и платная аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="2ccf7-157">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

