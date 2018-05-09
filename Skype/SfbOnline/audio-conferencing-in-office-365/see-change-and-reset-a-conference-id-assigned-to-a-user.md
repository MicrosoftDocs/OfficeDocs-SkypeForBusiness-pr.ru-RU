---
title: Видеть, изменение и сброс идентификатор конференции, назначенных пользователю
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Узнайте, как назначить пользователю в Скайп для бизнеса идентификатор конференции и какие конференции идентификатор приложения-службы должны быть параметров. '
ms.openlocfilehash: 73c5d3cc95b7967cd9d6eaae83a14e19143e431b
ms.sourcegitcommit: b93d1a0012aacb164d700db0143683cb6f276bf4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user"></a><span data-ttu-id="b354f-103">Просмотр и сброс идентификатор конференции, назначенных пользователю</span><span class="sxs-lookup"><span data-stu-id="b354f-103">View and reset a conference ID assigned to a user</span></span>

<span data-ttu-id="b354f-104">Идентификатор конференц-связи автоматически назначается Скайп для пользователя Business или группами Майкрософт, если они зависят от выбора звукового конференц-связи в Office 365 и использовать Microsoft в качестве поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="b354f-104">A conferencing ID is automatically assigned to a Skype for Business or Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="b354f-105">Идентификатор конференции, назначенный отправляется в приглашении на собрание, при планировании собрания.</span><span class="sxs-lookup"><span data-stu-id="b354f-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="b354f-106">Каждое собрание, который пользователь планирует будет присваивает идентификатор уникальный конференции.</span><span class="sxs-lookup"><span data-stu-id="b354f-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="b354f-107">Идентификатор конференции будет автоматически создан и назначенных пользователю, однако иногда может потребоваться при пользователь не нужно использовать этот сертификат и требуется установить на определенное число или при пользователи не могут не забудьте или теряют их идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="b354f-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="b354f-108">**Скайп по центру администрирования бизнеса** и Windows PowerShell можно использовать для просмотра, изменение и сброс их идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="b354f-108">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="b354f-109">Сообщения электронной почты будут отправляться пользователю с идентификатор конференции и телефонных номеров конференции по умолчанию, или если сбросить идентификатор конференции разных электронной почты будут отправлены, что будут включать идентификатор конференции, но не ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="b354f-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="b354f-110">Дополнительные сведения о сброс ПИН-кода инициатора конференции, [Перейдите сюда](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="b354f-110">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span> 
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="b354f-111">Просмотр и сброс конференции идентификаторы</span><span class="sxs-lookup"><span data-stu-id="b354f-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="b354f-112">Чтобы просмотреть идентификатор конференции</span><span class="sxs-lookup"><span data-stu-id="b354f-112">To view the conference ID</span></span>

<span data-ttu-id="b354f-113">![команды логотип 30x30.png](../images/teams-logo-30x30.png) **с помощью групп Майкрософт и Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="b354f-113">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="b354f-114">На панели навигации слева щелкните **Пользователи**и затем выберите пользователя в списке Доступные пользователи.</span><span class="sxs-lookup"><span data-stu-id="b354f-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="b354f-115">В верхней части страницы нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="b354f-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="b354f-116">В окне **Аудио конференц-связи**найдите в разделе **Идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="b354f-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="b354f-117">Можно отправить все сведения конференц-связи для пользователя в сообщение электронной почты, включая идентификатор конференции и звуковых телефонных номеров, щелкнув ссылку **Отправить сведения о конференции по электронной почте** .</span><span class="sxs-lookup"><span data-stu-id="b354f-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="b354f-118">Windows PowerShell можно использовать для просмотра идентификатор конференции для пользователя.</span><span class="sxs-lookup"><span data-stu-id="b354f-118">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="b354f-119">Для этого выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b354f-119">To do so, run:</span></span>
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


<span data-ttu-id="b354f-120">![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="b354f-120">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="b354f-121">Можно просматривать их идентификатор конференции и отправьте его для пользователей.</span><span class="sxs-lookup"><span data-stu-id="b354f-121">You can view their conference ID and send it to users.</span></span>
  
1. <span data-ttu-id="b354f-122">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="b354f-122">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="b354f-123">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="b354f-123">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="b354f-124">В **Скайп по центру администрирования Business**> **аудиоконференции** > **пользователей**, выберите пользователя, которому требуется идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="b354f-124">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>
    
4. <span data-ttu-id="b354f-125">На странице "действия" найдите в разделе **Идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="b354f-125">In the Action page, look under **Conference ID**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="b354f-126">Можно отправить все сведения конференц-связи для пользователя в сообщение электронной почты, включая идентификатор конференции и звуковых телефонных номеров, щелкнув ссылку **Отправить сведения о конференции по электронной почте** , после выбора пользователя на странице " **Пользователи** ".</span><span class="sxs-lookup"><span data-stu-id="b354f-126">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>

<span data-ttu-id="b354f-127">Windows PowerShell можно использовать для просмотра идентификатор конференции для пользователя.</span><span class="sxs-lookup"><span data-stu-id="b354f-127">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="b354f-128">Для этого выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b354f-128">To do so, run:</span></span>
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="b354f-129">Чтобы сбросить идентификатор конференции</span><span class="sxs-lookup"><span data-stu-id="b354f-129">To reset the conference ID</span></span>

<span data-ttu-id="b354f-130">Можно восстановить идентификатор конференции для пользователя, если, например, если они забыли.</span><span class="sxs-lookup"><span data-stu-id="b354f-130">You can reset a conference ID for a user if, for example, if they forget it.</span></span>
  
<span data-ttu-id="b354f-131">![команды логотип 30x30.png](../images/teams-logo-30x30.png) **с помощью групп Майкрософт и Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="b354f-131">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="b354f-132">На панели навигации слева щелкните **Пользователи**и затем выберите пользователя в списке Доступные пользователи.</span><span class="sxs-lookup"><span data-stu-id="b354f-132">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="b354f-133">В верхней части страницы нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="b354f-133">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="b354f-134">В разделе **Audio конференц-связи**нажмите кнопку **Сброс идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="b354f-134">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="b354f-135">В окне **сбросить идентификатор конференции** нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="b354f-135">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="b354f-136">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="b354f-136">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
    
    <span data-ttu-id="b354f-137">Можно восстановить идентификатор конференции для пользователя с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b354f-137">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="b354f-138">Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="b354f-138">To do this, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

<span data-ttu-id="b354f-139">![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="b354f-139">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="b354f-140">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="b354f-140">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="b354f-141">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="b354f-141">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="b354f-142">В **Скайп по центру администрирования Business**> **аудиоконференции** > **пользователей**, в области действий в разделе **Идентификатор конференции**, нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="b354f-142">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="b354f-143">В **Сброс идентификатор конференции?** окно, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="b354f-143">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="b354f-144">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="b354f-144">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
    
    <span data-ttu-id="b354f-145">Можно восстановить идентификатор конференции для пользователя с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b354f-145">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="b354f-146">Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="b354f-146">To do this, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="b354f-147">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="b354f-147">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="b354f-148">После создания новый идентификатор или один сбрасывается, старый идентификатор конференции не может использоваться с абонентов.</span><span class="sxs-lookup"><span data-stu-id="b354f-148">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="b354f-149">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="b354f-149">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="b354f-150">Пользователи могут использовать Скайп средством переноса собрания бизнеса требуется обновить их существующих собраний.</span><span class="sxs-lookup"><span data-stu-id="b354f-150">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="b354f-151">Чтобы узнать, как загрузить, установить и запустить средство, обратитесь к разделу: [Средство обновления собрания для Скайп для бизнес-деятельности и Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Скайп для бизнеса в Интернет, средство миграции собрания (64-разрядная версия)](http://go.microsoft.com/fwlink/?LinkID=626047)и [Скайп для бизнеса в Интернет, средство миграции собрания (32-разрядная версия)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="b354f-151">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
- <span data-ttu-id="b354f-152">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b354f-152">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
    
- <span data-ttu-id="b354f-153">Идентификатор конференции должны соответствовать длина цифрами на звукового конференц-канала.</span><span class="sxs-lookup"><span data-stu-id="b354f-153">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="b354f-154">Нельзя использовать буквы или специальных символов в конференции идентификаторы; можно использовать только цифры.</span><span class="sxs-lookup"><span data-stu-id="b354f-154">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="b354f-155">Идентификатор конференции для всех пользователей аудиоконференций будет 7 символов по умолчанию, и количество знаков, нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="b354f-155">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="b354f-156">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b354f-156">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="b354f-p112">Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="b354f-p112">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b354f-160">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b354f-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="b354f-161">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="b354f-161">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="b354f-p113">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="b354f-p113">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="b354f-164">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b354f-164">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="b354f-165">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b354f-165">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="b354f-166">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b354f-166">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="b354f-167">See also</span><span class="sxs-lookup"><span data-stu-id="b354f-167">Related topics</span></span>

[<span data-ttu-id="b354f-168">Пробная и платная аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="b354f-168">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

