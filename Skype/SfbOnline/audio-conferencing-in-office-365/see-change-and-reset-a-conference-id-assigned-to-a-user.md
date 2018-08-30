---
title: Просмотр, изменение и сброс идентификатора конференции, присвоенного пользователю в Skype для бизнеса Online
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Узнайте, как присвоить пользователю идентификатор конференции для Skype для бизнеса Online и какими должны быть параметры для установки идентификатора конференции. '
ms.openlocfilehash: 472f3b007a584979e029aade593c7b6c93ea1565
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252311"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a><span data-ttu-id="6e5a2-103">Просмотр и сброс идентификатора конференции, присвоенного пользователю в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="6e5a2-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="6e5a2-104">Для получения информации об идентификаторе конференции в Microsoft Teams перейдите в [Просмотр и сброс идентификатора конференции, присвоенного пользователю в Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span><span class="sxs-lookup"><span data-stu-id="6e5a2-104">For information about user conference IDs in Microsoft Teams, see [View and reset a conference ID assigned to a user in Microsoft Teasms](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).</span></span>

<span data-ttu-id="6e5a2-105">Идентификатор конференции автоматически присваевается пользователю Skype для бизнеса, когда он подключает Аудиоконференции в Office 365 и использует Microsoft в качестве поставщика Аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-105">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="6e5a2-106">Присвоенный идентификатор конференции отправляется в приглашении на собрание после того, как оно будет запланировано.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-106">The conference ID assigned can be either a static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="6e5a2-107">Каждому собранию, запланированному пользователем, будет назначен уникальный идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-107">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>

<span data-ttu-id="6e5a2-108">Идентификатор конференции будет создан и назначен пользователю автоматически. Однако, иногда пользователь по каким-либо причинам не сможет им воспользоваться или же вы захотите использовать определенное число. Так же пользователь может забыть или потерять идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-108">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number or if your users can't remember or have lost their conference ID, you can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span> <span data-ttu-id="6e5a2-109"> **Войдите в административную панель Skype для бизнеса** и Windows PowerShell для просмотра, изменения и сброса идентификатора конференции.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-109">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="6e5a2-110">Идентификатор конференции и телефонные номера для проведения аудиоконференции, назначенные по умолчанию, будут отправлены пользователю по электронной почте. Если вы сбросите идентификатор конференции в настройках, по электронной почте вам придет другой идентификатор конференции, но не ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-110">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="6e5a2-111">Для получения дополнительных сведений о сбросе ПИН-кода инициатора конференции, [перейдите сюда](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="6e5a2-111">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="6e5a2-112">Просмотр и сброс идентификатора конференции</span><span class="sxs-lookup"><span data-stu-id="6e5a2-112">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="6e5a2-113">Для просмотра идентификатора конференции</span><span class="sxs-lookup"><span data-stu-id="6e5a2-113">To reset the meeting conference ID</span></span>

<span data-ttu-id="6e5a2-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Использование Центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="6e5a2-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

<span data-ttu-id="6e5a2-115">Вы можете посмотреть их идентификатор конференции и отправить его пользователям.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-115">You can view their conference ID and send it to users.</span></span>

1. <span data-ttu-id="6e5a2-116">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-116">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="6e5a2-117">Перейдите в **Центр администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-117">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="6e5a2-118">В **Центре администрирования Skype для бизнеса**> **Аудиоконференции** > **Пользователи**, выберите пользователя, которому необходим идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-118">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>

4. <span data-ttu-id="6e5a2-119">На странице "Действия" найдите раздел **Идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-119">In the Action page, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="6e5a2-120">Всю информацию о конференц-связи, включая идентификатор конференции и номера телефонов для телефонного подключения, можно отправить пользователю по электронной почте, нажав **Отправить информацию о конференции по электронной почте**после выбора пользователя на странице " **Пользователи** ".</span><span class="sxs-lookup"><span data-stu-id="6e5a2-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking the **Send conference info via email**. It doesn't send the PIN.</span></span>

<span data-ttu-id="6e5a2-121">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="6e5a2-121">**Using Windows PowerShell to manage Lync Online**</span></span>

<span data-ttu-id="6e5a2-122">Windows PowerShell может быть использован для просмотра пользовательского идентификатора конференции.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-122">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="6e5a2-123">Для этого запустите:</span><span class="sxs-lookup"><span data-stu-id="6e5a2-123">To do so:</span></span>

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a><span data-ttu-id="6e5a2-124">Чтобы сбросить идентификатор конференции</span><span class="sxs-lookup"><span data-stu-id="6e5a2-124">To reset the meeting conference ID</span></span>

<span data-ttu-id="6e5a2-125">Если, например, пользователь забыл идентификатор конференции, его можно сбросить.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-125">You can reset a conference ID for a user if, for example, they forget it.</span></span>

<span data-ttu-id="6e5a2-126">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Использование Центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="6e5a2-126">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="6e5a2-127">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-127">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="6e5a2-128">Перейдите в **Центр администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-128">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="6e5a2-129">В **Центре администрирования Skype для бизнеса**> **Аудиоконференции** > **Пользователи**, в панели "Действия" **Идентификатором конференции**, нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-129">In the **Skype for Business admin center**> **Dial-in conferencing**, in the Action page under **Conference ID** click **Reset**.</span></span>

4. <span data-ttu-id="6e5a2-130">В появившемся окне**Сбросить идентификатор конференции?**, нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-130">In the ** Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="6e5a2-131">Идентификатор конференции будет создан автоматически, и новый идентификатор будет отправлен пользователю по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-131">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>

<span data-ttu-id="6e5a2-132">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="6e5a2-132">**Using Windows PowerShell to manage Lync Online**</span></span>

<span data-ttu-id="6e5a2-133">Вы можете сбросить пользовательский идентификатор конференции с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-133">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="6e5a2-134">Для этого выполните команду:</span><span class="sxs-lookup"><span data-stu-id="6e5a2-134">To do this, run:</span></span>

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="6e5a2-135">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="6e5a2-135">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="6e5a2-136">После создания нового идентификатора конференции или его сброса, абоненты не смогут воспользоваться старым идентификатором конференции.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-136">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="6e5a2-137">Вам необходимо сообщить пользователям об изменении расписания действующих собраний, чтобы убедиться, что их новые идентификаторы конференции добавлены в приглашения.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-137">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="6e5a2-138">Пользователи могут воспользоваться инструментом для переноса собраний Skype для бизнеса для обновления их существующих собраний.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-138">The users can use Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="6e5a2-139">Чтобы узнать, как загрузить, установить и запустить инструмент, обратитесь к разделу: [Инструмент для обновления собраний для Skype для бизнеса и Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype для бизнеса Online, инструмент для переноса собраний (64-разрядная версия)](https://go.microsoft.com/fwlink/?LinkID=626047)и [Skype для бизнеса Online, инструмент для переноса собраний (32-разрядная версия)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="6e5a2-139">To see how to download, install and run the Lync Meeting Update Tool, see:> Meeting Update Tool for Skype for Business and Lync  Skype for Business Online, Meeting Migration Tool (64-bit)  Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>

- <span data-ttu-id="6e5a2-140">В разделе [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ), узнайте больше об этой команде.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-140">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>

- <span data-ttu-id="6e5a2-141">Количество цифр идентификатора конференции должно соответствовать номеру Аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-141">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="6e5a2-142">В идентификаторе конференции нельзя использовать буквы или специальные символы; можно использовать только цифры.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-142">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>

- <span data-ttu-id="6e5a2-143">Идентификатор конференции для всех пользователей аудиоконференций состоит из 7 символов по умолчанию, и количество знаков не подлежит изменению.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-143">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="6e5a2-144">Хотите знать, как управлять с помощью Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="6e5a2-144">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="6e5a2-p109">Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="6e5a2-p109">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="6e5a2-148">Общие сведения о Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="6e5a2-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="6e5a2-149">Почему вам нужно использовать Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e5a2-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- <span data-ttu-id="6e5a2-p110">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="6e5a2-p110">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="6e5a2-152">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e5a2-152">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [<span data-ttu-id="6e5a2-153">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="6e5a2-153">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="6e5a2-154">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="6e5a2-154">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a><span data-ttu-id="6e5a2-155">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="6e5a2-155">Related topics</span></span>

[<span data-ttu-id="6e5a2-156">Пробная или платная Аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="6e5a2-156">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

