---
title: Просмотр, изменение и сброс назначенного пользователю конференц-зала в Skype для бизнеса Online
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
ms.openlocfilehash: 79c83999fdf9a9736dfe1ee425337edf938d3375
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110015"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="67506-103">Просмотр и сброс идентификатора конференции, присвоенного пользователю в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="67506-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="67506-104">Сведения об пользовательских ИД конференц-связи в Microsoft Teams см. в документе "Просмотр и сброс ИД конференции, назначенного пользователю [в Microsoft Teams".](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)</span><span class="sxs-lookup"><span data-stu-id="67506-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="67506-105">Когда пользователь настроил аудиоконференцию в Microsoft 365 или Office 365 и в качестве поставщика услуг аудиоконференции, пользователю Skype для бизнеса автоматически будет назначен соответствующий номер.</span><span class="sxs-lookup"><span data-stu-id="67506-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="67506-106">Присвоенный ему ИД конференции отправляется в приглашении на собрание при его запланированном собрании.</span><span class="sxs-lookup"><span data-stu-id="67506-106">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="67506-107">Каждому собранию, запланированному пользователем, будет назначен уникальный идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="67506-107">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="67506-108">Хотя пользовательский ИД конференции будет автоматически создан и назначен пользователю, иногда пользователь не хочет использовать этот номер и хочет установить для него определенный номер, а также когда пользователи не могут вспомнить или потеряли свой ИД конференции.</span><span class="sxs-lookup"><span data-stu-id="67506-108">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="67506-109"> **Войдите в административную панель Skype для бизнеса** и Windows PowerShell для просмотра, изменения и сброса идентификатора конференции.</span><span class="sxs-lookup"><span data-stu-id="67506-109">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="67506-110">Идентификатор конференции и телефонные номера для проведения аудиоконференции, назначенные по умолчанию, будут отправлены пользователю по электронной почте. Если вы сбросите идентификатор конференции в настройках, по электронной почте вам придет другой идентификатор конференции, но не ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="67506-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="67506-111">Для получения дополнительных сведений о сбросе ПИН-кода инициатора конференции, [перейдите сюда](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="67506-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="67506-112">Просмотр и сброс идентификатора конференции</span><span class="sxs-lookup"><span data-stu-id="67506-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="67506-113">Просмотр ИД конференции</span><span class="sxs-lookup"><span data-stu-id="67506-113">To view the conference ID</span></span>

<span data-ttu-id="67506-114">![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="67506-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="67506-115">Вы можете посмотреть их идентификатор конференции и отправить его пользователям.</span><span class="sxs-lookup"><span data-stu-id="67506-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="67506-116">Войте свою учетную запись с помощью своей учебной или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="67506-116">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="67506-117">Перейдите в Центр администрирования > **Skype для бизнеса.**</span><span class="sxs-lookup"><span data-stu-id="67506-117">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="67506-118">В **Центре администрирования Skype для бизнеса**> **Аудиоконференции** > **Пользователи**, выберите пользователя, которому необходим идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="67506-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="67506-119">На странице "Действия" найдите раздел **Идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="67506-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="67506-120">Вы можете отправить пользователю по электронной почте все сведения о конференции, включая ее ИД  и номера телефонов для аудиосвязи,  щелкнув ссылку "Отправить сведения о конференции" по электронной почте после выбора пользователя на странице "Пользователи".</span><span class="sxs-lookup"><span data-stu-id="67506-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="67506-121">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="67506-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="67506-122">Windows PowerShell может быть использован для просмотра пользовательского идентификатора конференции.</span><span class="sxs-lookup"><span data-stu-id="67506-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="67506-123">Для этого запустите 3</span><span class="sxs-lookup"><span data-stu-id="67506-123">To do so, run:</span></span>

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

<span data-ttu-id="67506-124">Дополнительные [информацию о cmdlet см. в get-CsOnlineDialInConferencingUser.](/powershell/module/skype/Get-CsOnlineDialInConferencingUser)</span><span class="sxs-lookup"><span data-stu-id="67506-124">See [Get-CsOnlineDialInConferencingUser](/powershell/module/skype/Get-CsOnlineDialInConferencingUser) to learn more about the cmdlet.</span></span>


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="67506-125">Сброс ИД конференции</span><span class="sxs-lookup"><span data-stu-id="67506-125">To reset the conference ID</span></span>

<span data-ttu-id="67506-126">Если, например, пользователь забыл идентификатор конференции, его можно сбросить.</span><span class="sxs-lookup"><span data-stu-id="67506-126">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="67506-127">![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="67506-127">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="67506-128">Войте свою учетную запись с помощью своей учебной или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="67506-128">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="67506-129">Перейдите в Центр администрирования > **Skype для бизнеса.**</span><span class="sxs-lookup"><span data-stu-id="67506-129">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="67506-130">В Центре **администрирования Skype** для бизнеса " Пользователи аудиоконференции" в области действий в области "ИД конференции" нажмите кнопку >    >    **"Сброс".**</span><span class="sxs-lookup"><span data-stu-id="67506-130">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="67506-131">В **окне "Сбросить ИД конференции?"** нажмите кнопку **"Да".**</span><span class="sxs-lookup"><span data-stu-id="67506-131">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="67506-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="67506-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="67506-133">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="67506-133">**Using Windows PowerShell**</span></span>

<span data-ttu-id="67506-134">Вы можете сбросить пользовательский идентификатор конференции с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67506-134">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="67506-135">Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="67506-135">To do this, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="67506-136">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="67506-136">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="67506-137">После создания нового или сброса нового ИД конференции звоня не смогут использовать старый.</span><span class="sxs-lookup"><span data-stu-id="67506-137">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="67506-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="67506-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="67506-139">Пользователи могут использовать средство переноса собраний Skype для бизнеса для обновления существующих собраний.</span><span class="sxs-lookup"><span data-stu-id="67506-139">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="67506-140">Чтобы узнать, как скачать, установить и запустить это средство, см. в этом видео: средство обновления собраний для Skype для бизнеса и [Lync,](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)Skype для бизнеса Online, средство переноса собраний [(64-битная версия)](https://go.microsoft.com/fwlink/?LinkID=626047)и Skype для бизнеса Online, средство переноса собраний [(32-битная версия).](https://www.microsoft.com/download/details.aspx?id=54079)</span><span class="sxs-lookup"><span data-stu-id="67506-140">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="67506-141">See [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) to learn more about the cmdlet.</span><span class="sxs-lookup"><span data-stu-id="67506-141">See [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="67506-142">Количество цифр идентификатора конференции должно соответствовать номеру Аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="67506-142">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="67506-143">В идентификаторе конференции нельзя использовать буквы или специальные символы; можно использовать только цифры.</span><span class="sxs-lookup"><span data-stu-id="67506-143">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="67506-144">По умолчанию всем пользователям аудиоконференции будет присвоено 9 цифр, а количество цифр изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="67506-144">The conference ID for all of your audio conferencing users will be 9 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="67506-145">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="67506-145">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="67506-146">Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия.</span><span class="sxs-lookup"><span data-stu-id="67506-146">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="67506-147">С Windows PowerShell вы можете управлять Microsoft 365, Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="67506-147">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="67506-148">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="67506-148">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="67506-149">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="67506-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="67506-150">Зачем нужно использовать Microsoft 365 или Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="67506-150">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="67506-151">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="67506-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="67506-152">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="67506-152">Learn about these advantages in the following topics:</span></span>

  - <span data-ttu-id="67506-153">[Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="67506-153">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

  - [<span data-ttu-id="67506-154">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="67506-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="67506-155">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="67506-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="67506-156">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="67506-156">Related topics</span></span>

[<span data-ttu-id="67506-157">Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="67506-157">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)