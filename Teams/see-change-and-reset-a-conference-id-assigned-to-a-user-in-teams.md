---
title: Просмотреть, изменение и сброс идентификатор конференции, назначенных пользователю групп Майкрософт
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
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Узнайте, как назначить идентификатор конференции для пользователя в группах Майкрософт и какие конференции идентификатор приложения-службы должны быть параметров. '
ms.openlocfilehash: aa69788e86689fb393684bfb9367152269cfa457
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850943"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="bfdff-103">Просмотр и сброс идентификатор конференции, назначенных пользователю групп Майкрософт</span><span class="sxs-lookup"><span data-stu-id="bfdff-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="bfdff-104">Идентификатор конференц-связь автоматически назначается пользователю группами Майкрософт, если они зависят от выбора звукового конференц-связи в Office 365 и использовать Microsoft в качестве поставщика аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="bfdff-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="bfdff-105">Идентификатор конференции, назначенный отправляется в приглашении на собрание, при планировании собрания.</span><span class="sxs-lookup"><span data-stu-id="bfdff-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="bfdff-106">Каждому собранию, запланированному пользователем, будет назначен уникальный идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="bfdff-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="bfdff-107">Идентификатор конференции будет автоматически создан и назначенных пользователю, однако иногда может потребоваться при пользователь не нужно использовать этот сертификат и требуется установить на определенное число или при пользователи не могут не забудьте или теряют их идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="bfdff-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="bfdff-108">Центр администрирования группами Майкрософт или Windows PowerShell можно использовать для просмотра, изменение и сброс их идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="bfdff-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="bfdff-109">Идентификатор конференции и телефонные номера для проведения аудиоконференции, назначенные по умолчанию, будут отправлены пользователю по электронной почте. Если вы сбросите идентификатор конференции в настройках, по электронной почте вам придет другой идентификатор конференции, но не ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="bfdff-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="bfdff-110">Для получения дополнительных сведений о сбросе ПИН-кода инициатора конференции, [перейдите сюда](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="bfdff-110">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user-in-teams.md).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="bfdff-111">Просмотр и сброс идентификатора конференции</span><span class="sxs-lookup"><span data-stu-id="bfdff-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="bfdff-112">Чтобы просмотреть идентификатор конференции</span><span class="sxs-lookup"><span data-stu-id="bfdff-112">To view the conference ID</span></span>

<span data-ttu-id="bfdff-113">![команды логотип 30x30.png](media/teams-logo-30x30.png) **с помощью групп Майкрософт и Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="bfdff-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="bfdff-114">На панели навигации слева щелкните **Пользователи**и затем выберите пользователя в списке Доступные пользователи.</span><span class="sxs-lookup"><span data-stu-id="bfdff-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="bfdff-115">В верхней части страницы нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="bfdff-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="bfdff-116">В окне **Аудио конференц-связи**найдите в разделе **Идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="bfdff-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="bfdff-117">Можно отправить все сведения конференц-связи для пользователя в сообщение электронной почты, включая идентификатор конференции и звуковых телефонных номеров, щелкнув ссылку **Отправить сведения о конференции по электронной почте** .</span><span class="sxs-lookup"><span data-stu-id="bfdff-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="bfdff-118">**С помощью Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="bfdff-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="bfdff-119">В разделе [Справочник по Microsoft команды PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="bfdff-119">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="bfdff-120">Чтобы сбросить идентификатор конференции</span><span class="sxs-lookup"><span data-stu-id="bfdff-120">To reset the conference ID</span></span>

<span data-ttu-id="bfdff-121">Если, например, пользователь забыл идентификатор конференции, его можно сбросить.</span><span class="sxs-lookup"><span data-stu-id="bfdff-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="bfdff-122">![команды логотип 30x30.png](media/teams-logo-30x30.png) **с помощью групп Майкрософт и Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="bfdff-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="bfdff-123">На панели навигации слева щелкните **Пользователи**и затем выберите пользователя в списке Доступные пользователи.</span><span class="sxs-lookup"><span data-stu-id="bfdff-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="bfdff-124">В верхней части страницы нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="bfdff-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="bfdff-125">В разделе **Audio конференц-связи**нажмите кнопку **Сброс идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="bfdff-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="bfdff-126">В окне **сбросить идентификатор конференции** нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="bfdff-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="bfdff-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="bfdff-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="bfdff-128">**С помощью Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="bfdff-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="bfdff-129">В разделе [Справочник по Microsoft команды PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="bfdff-129">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="bfdff-130">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="bfdff-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="bfdff-131">После создания новый идентификатор или один сбрасывается, старый идентификатор конференции не может использоваться с абонентов.</span><span class="sxs-lookup"><span data-stu-id="bfdff-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="bfdff-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="bfdff-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="bfdff-133">Количество цифр идентификатора конференции должно соответствовать номеру Аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="bfdff-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="bfdff-134">В идентификаторе конференции нельзя использовать буквы или специальные символы; можно использовать только цифры.</span><span class="sxs-lookup"><span data-stu-id="bfdff-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="bfdff-135">Идентификатор конференции для всех пользователей аудиоконференций состоит из 7 символов по умолчанию, и количество знаков не подлежит изменению.</span><span class="sxs-lookup"><span data-stu-id="bfdff-135">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="bfdff-136">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="bfdff-136">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="bfdff-p107">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="bfdff-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bfdff-140">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="bfdff-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="bfdff-141">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bfdff-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="bfdff-142">Дополнительные сведения о Windows PowerShell, [Справочник по Microsoft команды PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="bfdff-142">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="bfdff-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="bfdff-143">Related topics</span></span>

[<span data-ttu-id="bfdff-144">Пробная и платная аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="bfdff-144">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

