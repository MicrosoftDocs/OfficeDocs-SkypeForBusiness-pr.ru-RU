---
title: "Видеть, изменение и сброс идентификатор конференции, назначенных пользователю"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: "Узнайте, как назначить пользователю в Скайп для бизнеса идентификатор конференции и какие конференции идентификатор приложения-службы должны быть параметров. "
ms.openlocfilehash: b542e764d0b8b1587c34e78a54612410cd72a3bd
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2018
---
# <a name="see-change-and-reset-a-conference-id-assigned-to-a-user"></a><span data-ttu-id="eee93-103">Видеть, изменение и сброс идентификатор конференции, назначенных пользователю</span><span class="sxs-lookup"><span data-stu-id="eee93-103">See, change, and reset a conference ID assigned to a user</span></span>

<span data-ttu-id="eee93-104">Идентификатор конференц-связи автоматически назначается Скайп для пользователя Business или группами Майкрософт, если они зависят от выбора звукового конференц-связи в Office 365 и использовать Microsoft в качестве поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="eee93-104">A conferencing ID is automatically assigned to a Skype for Business or Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="eee93-105">Назначенный идентификатор конференции может быть статических или динамических и отправляется в приглашении на собрание, при планировании собрания.</span><span class="sxs-lookup"><span data-stu-id="eee93-105">The conference ID assigned can be either static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span>
  
<span data-ttu-id="eee93-106">Статические идентификаторы используются в том случае, когда пользователи в вашей организации не требуется запомнить случайное число; их можно выбрать определенное число или использовать один, который легко запомнить.</span><span class="sxs-lookup"><span data-stu-id="eee93-106">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="eee93-107">При использовании идентификаторы динамических конференции каждого собрания, расписания пользователя будет присваивает идентификатор уникальный конференции.</span><span class="sxs-lookup"><span data-stu-id="eee93-107">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="eee93-108">Если вы хотите назначить динамических вместо статических конференции идентификаторы, [Перейдите сюда](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="eee93-108">If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="eee93-109">Идентификатор статического конференции будет автоматически создан и назначенных пользователю, однако иногда может потребоваться при пользователь не нужно использовать этот сертификат и требуется установить на определенное число или при пользователи не могут не забудьте или теряют их идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="eee93-109">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="eee93-110">**Скайп по центру администрирования бизнеса** и Windows PowerShell можно использовать для просмотра, изменение и сброс их идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="eee93-110">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="eee93-111">Сообщения электронной почты будут отправляться пользователю с идентификатор конференции и телефонных номеров конференции по умолчанию, или если сбросить идентификатор конференции разных электронной почты будут отправлены, что будут включать идентификатор конференции, но не ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="eee93-111">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span>
  
## <a name="view-and-change-conference-ids"></a><span data-ttu-id="eee93-112">Просмотр и изменение конференции идентификаторы</span><span class="sxs-lookup"><span data-stu-id="eee93-112">View and change conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="eee93-113">Чтобы просмотреть идентификатор конференции</span><span class="sxs-lookup"><span data-stu-id="eee93-113">To view the conference ID</span></span>

<span data-ttu-id="eee93-114">Можно просматривать их идентификатор конференции и отправьте его для пользователей.</span><span class="sxs-lookup"><span data-stu-id="eee93-114">You can view their conference ID and send it to users.</span></span>
  
1. <span data-ttu-id="eee93-115">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="eee93-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="eee93-116">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="eee93-116">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="eee93-117">В **Скайп по центру администрирования Business**> **аудиоконференции** > **пользователей**, выберите пользователя, которому требуется идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="eee93-117">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>
    
4. <span data-ttu-id="eee93-118">На странице "действия" найдите в разделе **Идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="eee93-118">In the Action page, look under **Conference ID**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="eee93-119">Можно отправить все сведения конференц-связи для пользователя в сообщение электронной почты, включая идентификатор конференции и звуковых телефонных номеров, щелкнув ссылку **Отправить сведения о конференции по электронной почте** , после выбора пользователя на странице " **Пользователи** ".</span><span class="sxs-lookup"><span data-stu-id="eee93-119">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>
  
    <span data-ttu-id="eee93-120">Windows PowerShell можно использовать для просмотра идентификатор конференции для пользователя.</span><span class="sxs-lookup"><span data-stu-id="eee93-120">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="eee93-121">Для этого выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="eee93-121">To do so, run:</span></span>
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    <span data-ttu-id="eee93-122">В разделе [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) , чтобы узнать больше о командлета.</span><span class="sxs-lookup"><span data-stu-id="eee93-122">See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.</span></span>
    
### <a name="to-assign-or-change-the-conference-id"></a><span data-ttu-id="eee93-123">Чтобы назначить или изменить идентификатор конференции</span><span class="sxs-lookup"><span data-stu-id="eee93-123">To assign or change the conference ID</span></span>

<span data-ttu-id="eee93-124">Можно назначить или изменить идентификатор конференции для пользователя, если, например, кто-то хочет идентификатор конференции, который легко запомнить.</span><span class="sxs-lookup"><span data-stu-id="eee93-124">You can assign or change a conference ID for a user if, for example, someone wants a conference ID that's easy to remember.</span></span>

  > [!NOTE]
  > <span data-ttu-id="eee93-125">Скайп по центру администрирования бизнес не может использоваться для изменения идентификатора конференции, который автоматически создается, но можно использовать Windows PowerShell для изменения или измените идентификатор конференции, задания.</span><span class="sxs-lookup"><span data-stu-id="eee93-125">The Skype for Business admin center can't be used to edit a conference ID that has been automatically created, but you can use Windows PowerShell to edit or change a conference ID that you have set.</span></span> 
     
<span data-ttu-id="eee93-126">Чтобы изменить или идентификатор конференции для пользователя, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="eee93-126">To edit or change the conference ID for a user, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

  > [!TIP]
  > <span data-ttu-id="eee93-127">Идентификатор конференции должен содержать 7 символов, и его нельзя изменить в Скайп для бизнеса центра администрирования или с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eee93-127">A conference ID must contain 7 digits, and you can't change it in the Skype for Business admin center or by using Windows PowerShell.</span></span> 
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="eee93-128">Чтобы сбросить идентификатор конференции</span><span class="sxs-lookup"><span data-stu-id="eee93-128">To reset the conference ID</span></span>

<span data-ttu-id="eee93-129">Можно восстановить идентификатор конференции для пользователя, если, например, если они забыли.</span><span class="sxs-lookup"><span data-stu-id="eee93-129">You can reset a conference ID for a user if, for example, if they forget it.</span></span>
  
1. <span data-ttu-id="eee93-130">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="eee93-130">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="eee93-131">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="eee93-131">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="eee93-132">В **Скайп по центру администрирования Business**> **аудиоконференции** > **пользователей**, в области действий в разделе **Идентификатор конференции**, нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="eee93-132">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="eee93-133">В **Сброс идентификатор конференции?** окно, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="eee93-133">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="eee93-134">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="eee93-134">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
    
    <span data-ttu-id="eee93-135">Можно восстановить идентификатор конференции для пользователя с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eee93-135">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="eee93-136">Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="eee93-136">To do this, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetLeaderPIN 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="eee93-137">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="eee93-137">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="eee93-138">После создания новый идентификатор или один сбрасывается, старый идентификатор конференции не может использоваться с абонентов.</span><span class="sxs-lookup"><span data-stu-id="eee93-138">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="eee93-139">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="eee93-139">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="eee93-140">Пользователи могут использовать Скайп средством переноса собрания бизнеса требуется обновить их существующих собраний.</span><span class="sxs-lookup"><span data-stu-id="eee93-140">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="eee93-141">Чтобы узнать, как загрузить, установить и запустить средство, обратитесь к разделу: [Средство обновления собрания для Скайп для бизнес-деятельности и Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Скайп для бизнеса в Интернет, средство миграции собрания (64-разрядная версия)](http://go.microsoft.com/fwlink/?LinkID=626047)и [Скайп для бизнеса в Интернет, средство миграции собрания (32-разрядная версия)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="eee93-141">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
- <span data-ttu-id="eee93-142">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span><span class="sxs-lookup"><span data-stu-id="eee93-142">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
    
- <span data-ttu-id="eee93-143">Идентификатор конференции должны соответствовать длина цифрами на звукового конференц-канала.</span><span class="sxs-lookup"><span data-stu-id="eee93-143">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="eee93-144">Нельзя использовать буквы или специальных символов в конференции идентификаторы; можно использовать только цифры.</span><span class="sxs-lookup"><span data-stu-id="eee93-144">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="eee93-145">Идентификатор конференции для всех пользователей аудиоконференций будет 7 символов по умолчанию, и количество знаков, нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="eee93-145">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
- <span data-ttu-id="eee93-146">Если пользователь перемещается от корпорации Майкрософт в качестве поставщика аудиоконференций поставщика аудиоконференций сторонних производителей или поставщик услуг аудиоконференций имеет значение **None**, идентификатор конференции больше не будут работать.</span><span class="sxs-lookup"><span data-stu-id="eee93-146">If the user is moved from Microsoft as the audio conferencing provider to a third-party audio conferencing provider or the audio conferencing provider is set to **None**, the conference ID will no longer work.</span></span> <span data-ttu-id="eee93-147">В разделе [Назначение независимых производителей в качестве поставщика аудиоконференций](assign-a-third-party-as-the-audio-conferencing-provider.md) или [перемещения поставщика аудиоконференций пользователя в корпорацию Майкрософт](moving-a-user-s-audio-conferencing-provider-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="eee93-147">See [Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md) or [Moving a user's audio conferencing provider to Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md).</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="eee93-148">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eee93-148">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="eee93-p110">Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="eee93-p110">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="eee93-152">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="eee93-152">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="eee93-153">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="eee93-153">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="eee93-p111">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="eee93-p111">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="eee93-156">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eee93-156">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="eee93-157">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="eee93-157">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="eee93-158">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="eee93-158">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="eee93-159">See also</span><span class="sxs-lookup"><span data-stu-id="eee93-159">Related topics</span></span>

[<span data-ttu-id="eee93-160">Конференц-связь с телефонным подключением в Office 365</span><span class="sxs-lookup"><span data-stu-id="eee93-160">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

