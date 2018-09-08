---
title: Просмотреть, изменение и сброс идентификатор конференции, назначенных пользователю в Скайп для бизнеса в Интернет
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Узнайте, как присвоить пользователю идентификатор конференции для Skype для бизнеса Online и какими должны быть параметры для установки идентификатора конференции. '
ms.openlocfilehash: 7996cc91bd9461f733f82da3eb01eeac7109604a
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883418"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="3341c-103">Просмотр и сброс идентификатора конференции, присвоенного пользователю в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3341c-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="3341c-104">Для получения информации об идентификаторе конференции в Microsoft Teams перейдите в [Просмотр и сброс идентификатора конференции, присвоенного пользователю в Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="3341c-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teasms](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="3341c-105">Идентификатор конференции автоматически присваевается пользователю Skype для бизнеса, когда он подключает Аудиоконференции в Office 365 и использует Microsoft в качестве поставщика Аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="3341c-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="3341c-106">Идентификатор конференции, назначенный отправляется в приглашении на собрание, при планировании собрания.</span><span class="sxs-lookup"><span data-stu-id="3341c-106">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="3341c-107">Каждому собранию, запланированному пользователем, будет назначен уникальный идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="3341c-107">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="3341c-108">Идентификатор конференции будет автоматически создан и назначенных пользователю, однако иногда может потребоваться при пользователь не нужно использовать этот сертификат и требуется установить на определенное число или при пользователи не могут не забудьте или теряют их идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="3341c-108">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="3341c-109"> *\*Войдите в административную панель Skype для бизнеса** и Windows PowerShell для просмотра, изменения и сброса идентификатора конференции.</span><span class="sxs-lookup"><span data-stu-id="3341c-109">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="3341c-110">Идентификатор конференции и телефонные номера для проведения аудиоконференции, назначенные по умолчанию, будут отправлены пользователю по электронной почте. Если вы сбросите идентификатор конференции в настройках, по электронной почте вам придет другой идентификатор конференции, но не ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="3341c-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="3341c-111">Для получения дополнительных сведений о сбросе ПИН-кода инициатора конференции, [перейдите сюда](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="3341c-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="3341c-112">Просмотр и сброс идентификатора конференции</span><span class="sxs-lookup"><span data-stu-id="3341c-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="3341c-113">Чтобы просмотреть идентификатор конференции</span><span class="sxs-lookup"><span data-stu-id="3341c-113">To view the conference ID</span></span>

<span data-ttu-id="3341c-114">![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="3341c-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="3341c-115">Вы можете посмотреть их идентификатор конференции и отправить его пользователям.</span><span class="sxs-lookup"><span data-stu-id="3341c-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="3341c-116">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="3341c-116">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="3341c-117">Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="3341c-117">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="3341c-118">В **Центре администрирования Skype для бизнеса**> **Аудиоконференции** > **Пользователи**, выберите пользователя, которому необходим идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="3341c-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="3341c-119">На странице "Действия" найдите раздел **Идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="3341c-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="3341c-120">Можно отправить все сведения конференц-связи для пользователя в сообщение электронной почты, включая идентификатор конференции и звуковых телефонных номеров, щелкнув ссылку **Отправить сведения о конференции по электронной почте** , после выбора пользователя на странице " **Пользователи** ".</span><span class="sxs-lookup"><span data-stu-id="3341c-120">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="3341c-121">**С помощью Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="3341c-121">**Using Windows PowerShell**</span></span>

<span data-ttu-id="3341c-122">Windows PowerShell может быть использован для просмотра пользовательского идентификатора конференции.</span><span class="sxs-lookup"><span data-stu-id="3341c-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="3341c-123">Для этого выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="3341c-123">To do so, run:</span></span>

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="3341c-124">Чтобы сбросить идентификатор конференции</span><span class="sxs-lookup"><span data-stu-id="3341c-124">To reset the conference ID</span></span>

<span data-ttu-id="3341c-125">Если, например, пользователь забыл идентификатор конференции, его можно сбросить.</span><span class="sxs-lookup"><span data-stu-id="3341c-125">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="3341c-126">![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="3341c-126">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="3341c-127">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="3341c-127">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="3341c-128">Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="3341c-128">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="3341c-129">В **Скайп по центру администрирования Business**> **аудиоконференции** > **пользователей**, в области действий в разделе **Идентификатор конференции**, нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="3341c-129">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="3341c-130">В **Сброс идентификатор конференции?** окно, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="3341c-130">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="3341c-131">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="3341c-131">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="3341c-132">**С помощью Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="3341c-132">**Using Windows PowerShell**</span></span>

<span data-ttu-id="3341c-133">Вы можете сбросить пользовательский идентификатор конференции с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3341c-133">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="3341c-134">Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="3341c-134">To do this, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="3341c-135">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="3341c-135">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="3341c-136">После создания новый идентификатор или один сбрасывается, старый идентификатор конференции не может использоваться с абонентов.</span><span class="sxs-lookup"><span data-stu-id="3341c-136">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="3341c-137">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="3341c-137">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="3341c-138">Пользователи могут использовать Скайп средством переноса собрания бизнеса требуется обновить их существующих собраний.</span><span class="sxs-lookup"><span data-stu-id="3341c-138">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="3341c-139">Чтобы узнать, как загрузить, установить и запустить средство, обратитесь к разделу: [Средство обновления собрания для Скайп для бизнес-деятельности и Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Скайп для бизнеса в Интернет, средство миграции собрания (64-разрядная версия)](https://go.microsoft.com/fwlink/?LinkID=626047)и [Скайп для бизнеса в Интернет, средство миграции собрания (32-разрядная версия)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="3341c-139">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>

- <span data-ttu-id="3341c-140">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3341c-140">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="3341c-141">Количество цифр идентификатора конференции должно соответствовать номеру Аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="3341c-141">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="3341c-142">В идентификаторе конференции нельзя использовать буквы или специальные символы; можно использовать только цифры.</span><span class="sxs-lookup"><span data-stu-id="3341c-142">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="3341c-143">Идентификатор конференции для всех пользователей аудиоконференций состоит из 7 символов по умолчанию, и количество знаков не подлежит изменению.</span><span class="sxs-lookup"><span data-stu-id="3341c-143">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="3341c-144">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3341c-144">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="3341c-p109">Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="3341c-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="3341c-148">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3341c-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="3341c-149">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="3341c-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="3341c-p110">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="3341c-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="3341c-152">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3341c-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="3341c-153">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3341c-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="3341c-154">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="3341c-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="3341c-155">See also</span><span class="sxs-lookup"><span data-stu-id="3341c-155">Related topics</span></span>

[<span data-ttu-id="3341c-156">Пробная и платная аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="3341c-156">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

