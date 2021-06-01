---
title: Просмотр, изменение и сброс ИД конференции, назначенного пользователю в Skype для бизнеса Online
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
ms.openlocfilehash: f12982298903485d93582fae3a4f39aaed49170c
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237055"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="6fa59-103">Просмотр и сброс идентификатора конференции, присвоенного пользователю в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="6fa59-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="6fa59-104">Сведения об ИД конференции пользователей в Microsoft Teams см. в этой [Microsoft Teams.](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)</span><span class="sxs-lookup"><span data-stu-id="6fa59-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="6fa59-105">Когда пользователь Skype для бизнеса аудиоконференцию в Microsoft 365 или Office 365 и использует Майкрософт в качестве поставщика услуг аудиоконференций, пользователю автоматически Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="6fa59-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="6fa59-106">Присвоенный ему ИД конференции отправляется в приглашении на собрание при его запланированном собрании.</span><span class="sxs-lookup"><span data-stu-id="6fa59-106">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="6fa59-107">Каждому собранию, запланированному пользователем, будет назначен уникальный идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="6fa59-107">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="6fa59-108">Хотя ИД конференции будет автоматически создан и назначен пользователю, иногда пользователь не хочет использовать этот номер и хочет установить определенное число, или пользователи не могут вспомнить или потеряли свой ИД конференции.</span><span class="sxs-lookup"><span data-stu-id="6fa59-108">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="6fa59-109"> **Войдите в административную панель Skype для бизнеса** и Windows PowerShell для просмотра, изменения и сброса идентификатора конференции.</span><span class="sxs-lookup"><span data-stu-id="6fa59-109">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="6fa59-110">Идентификатор конференции и телефонные номера для проведения аудиоконференции, назначенные по умолчанию, будут отправлены пользователю по электронной почте. Если вы сбросите идентификатор конференции в настройках, по электронной почте вам придет другой идентификатор конференции, но не ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="6fa59-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="6fa59-111">Для получения дополнительных сведений о сбросе ПИН-кода инициатора конференции, [перейдите сюда](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="6fa59-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="6fa59-112">Просмотр и сброс идентификатора конференции</span><span class="sxs-lookup"><span data-stu-id="6fa59-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="6fa59-113">Просмотр ИД конференции</span><span class="sxs-lookup"><span data-stu-id="6fa59-113">To view the conference ID</span></span>

<span data-ttu-id="6fa59-114">![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="6fa59-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="6fa59-115">Вы можете посмотреть их идентификатор конференции и отправить его пользователям.</span><span class="sxs-lookup"><span data-stu-id="6fa59-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="6fa59-116">Во войти с помощью своей учебной или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="6fa59-116">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="6fa59-117">Перейдите в центр администрирования > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="6fa59-117">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="6fa59-118">В **Центре администрирования Skype для бизнеса**> **Аудиоконференции** > **Пользователи**, выберите пользователя, которому необходим идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="6fa59-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="6fa59-119">На странице "Действия" найдите раздел **Идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="6fa59-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="6fa59-120">Вы можете отправить пользователю по электронной почте все сведения о конференции, включая ее ИД  и номера телефонов для аудиоконференции, щелкнув ссылку Отправить сведения о конференции по электронной почте после выбора пользователя на странице Пользователи. </span><span class="sxs-lookup"><span data-stu-id="6fa59-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="6fa59-121">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="6fa59-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="6fa59-122">Windows PowerShell может быть использован для просмотра пользовательского идентификатора конференции.</span><span class="sxs-lookup"><span data-stu-id="6fa59-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="6fa59-123">Для этого запустите:</span><span class="sxs-lookup"><span data-stu-id="6fa59-123">To do so, run:</span></span>

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

<span data-ttu-id="6fa59-124">Дополнительные информацию о нем см. в окне [Get-CsOnlineDialInConferencingUser.](/powershell/module/skype/Get-CsOnlineDialInConferencingUser)</span><span class="sxs-lookup"><span data-stu-id="6fa59-124">See [Get-CsOnlineDialInConferencingUser](/powershell/module/skype/Get-CsOnlineDialInConferencingUser) to learn more about the cmdlet.</span></span>


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="6fa59-125">Сброс ИД конференции</span><span class="sxs-lookup"><span data-stu-id="6fa59-125">To reset the conference ID</span></span>

<span data-ttu-id="6fa59-126">Если, например, пользователь забыл идентификатор конференции, его можно сбросить.</span><span class="sxs-lookup"><span data-stu-id="6fa59-126">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="6fa59-127">![Значок с логотипом Skype для бизнеса](../images/sfb-logo-30x30.png) **Использование центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="6fa59-127">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="6fa59-128">Во войти с помощью своей учебной или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="6fa59-128">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="6fa59-129">Перейдите в центр администрирования > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="6fa59-129">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="6fa59-130">В центре **Skype для бизнеса** аудиоконференции Пользователи , в области действий в области "ИД конференции" >    >  нажмите кнопку **Сброс**. </span><span class="sxs-lookup"><span data-stu-id="6fa59-130">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="6fa59-131">В **окне Сбросить ИД конференции?** нажмите кнопку **Да.**</span><span class="sxs-lookup"><span data-stu-id="6fa59-131">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="6fa59-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="6fa59-132">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="6fa59-133">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="6fa59-133">**Using Windows PowerShell**</span></span>

<span data-ttu-id="6fa59-134">Вы можете сбросить пользовательский идентификатор конференции с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6fa59-134">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="6fa59-135">Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="6fa59-135">To do this, run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="6fa59-136">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="6fa59-136">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="6fa59-137">После создания нового ИД конференции или сброса его старый ИД конференции не могут использовать вызыватели.</span><span class="sxs-lookup"><span data-stu-id="6fa59-137">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="6fa59-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="6fa59-138">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="6fa59-139">Пользователи могут использовать средство переноса Skype для бизнеса собраний для обновления существующих собраний.</span><span class="sxs-lookup"><span data-stu-id="6fa59-139">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="6fa59-140">Чтобы узнать, как скачать, установить и запустить средство, см. средства обновления собраний для Skype для бизнеса и [Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), Skype для бизнеса Online, Средство переноса собраний [(64-битная версия)](https://go.microsoft.com/fwlink/?LinkID=626047)и Skype для бизнеса Online, Средство переноса собраний [(32-битная версия).](https://www.microsoft.com/download/details.aspx?id=54079)</span><span class="sxs-lookup"><span data-stu-id="6fa59-140">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="6fa59-141">See [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) to learn more about the cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6fa59-141">See [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="6fa59-142">Количество цифр идентификатора конференции должно соответствовать номеру Аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="6fa59-142">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="6fa59-143">В идентификаторе конференции нельзя использовать буквы или специальные символы; можно использовать только цифры.</span><span class="sxs-lookup"><span data-stu-id="6fa59-143">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="6fa59-144">По умолчанию код конференции для всех пользователей аудиоконференции состоит из 9 цифр, а количество цифр изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="6fa59-144">The conference ID for all of your audio conferencing users will be 9 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="6fa59-145">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6fa59-145">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="6fa59-146">Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия.</span><span class="sxs-lookup"><span data-stu-id="6fa59-146">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="6fa59-147">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="6fa59-147">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="6fa59-148">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="6fa59-148">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="6fa59-149">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="6fa59-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="6fa59-150">Зачем нужно использовать Microsoft 365 или Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="6fa59-150">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="6fa59-151">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="6fa59-151">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="6fa59-152">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="6fa59-152">Learn about these advantages in the following topics:</span></span>

  - <span data-ttu-id="6fa59-153">[Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="6fa59-153">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

  - [<span data-ttu-id="6fa59-154">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="6fa59-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="6fa59-155">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="6fa59-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a><span data-ttu-id="6fa59-156">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="6fa59-156">Related topics</span></span>

[<span data-ttu-id="6fa59-157">Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="6fa59-157">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
