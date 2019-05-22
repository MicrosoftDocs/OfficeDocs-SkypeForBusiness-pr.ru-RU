---
title: Просмотр, изменение и сброс назначенного пользователю идентификатора конференции в Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Сведения о том, как назначить идентификатор конференции пользователю в Microsoft Teams и какими должны быть его параметры. '
ms.openlocfilehash: a41935e324a7ed167efc905bbe274f6ef7c85de5
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344318"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="af215-103">Просмотр и сброс назначенного пользователю идентификатора конференции в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="af215-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="af215-104">Идентификатор конференции автоматически назначается пользователю Microsoft Teams, когда он активируется для аудиоконференций в Office 365 и использует корпорацию Майкрософт в качестве поставщика услуг аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="af215-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="af215-105">Назначенный идентификатор конференции отправляется в приглашении на собрание при планировании собрания.</span><span class="sxs-lookup"><span data-stu-id="af215-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="af215-106">Каждому собранию, запланированному пользователем, будет назначен уникальный идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="af215-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="af215-107">Хотя идентификатор конференции создается и назначается пользователю автоматически, в некоторых случаях пользователю может потребоваться использовать в качестве идентификатора конкретный номер, кроме того, пользователи могут забыть или потерять этот идентификатор.</span><span class="sxs-lookup"><span data-stu-id="af215-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="af215-108">С помощью Центра администрирования Microsoft Teams или Windows PowerShell вы можете просмотреть, изменить и сбросить идентификатор конференции пользователя.</span><span class="sxs-lookup"><span data-stu-id="af215-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="af215-109">Идентификатор конференции и телефонные номера для проведения аудиоконференции, назначенные по умолчанию, будут отправлены пользователю по электронной почте. Если вы сбросите идентификатор конференции в настройках, по электронной почте вам придет другой идентификатор конференции, но не ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="af215-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="af215-110">Для получения дополнительных сведений о сбросе ПИН-кода инициатора конференции, [перейдите сюда](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="af215-110">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user-in-teams.md).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="af215-111">Просмотр и сброс идентификатора конференции</span><span class="sxs-lookup"><span data-stu-id="af215-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="af215-112">Просмотр идентификатора конференции</span><span class="sxs-lookup"><span data-stu-id="af215-112">To view the conference ID</span></span>

<span data-ttu-id="af215-113">![Значок с логотипом](media/teams-logo-30x30.png) Microsoft Teams, в котором **используется центр администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="af215-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="af215-114">В левой области навигации щелкните на элементе **Пользователи** и выберите пользователя в списке доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="af215-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="af215-115">В верхней части страницы щелкните на элементе **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="af215-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="af215-116">В области **Аудиоконференции** просмотрите значение **Идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="af215-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="af215-117">Всю информацию о конференц-связи, включая идентификатор конференции и телефонные номера для аудиоконференции, можно отправить пользователю по электронной почте, щелкнув ссылку **Отправить сведения о конференции по эл. почте**.</span><span class="sxs-lookup"><span data-stu-id="af215-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="af215-118">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="af215-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="af215-119">Дополнительные сведения см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="af215-119">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="af215-120">Сброс идентификатора конференции</span><span class="sxs-lookup"><span data-stu-id="af215-120">To reset the conference ID</span></span>

<span data-ttu-id="af215-121">вы можете сбросить идентификатор конференции для пользователя, например, если он забыл его.</span><span class="sxs-lookup"><span data-stu-id="af215-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="af215-122">![Значок с логотипом](media/teams-logo-30x30.png) Microsoft Teams, в котором **используется центр администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="af215-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="af215-123">В левой области навигации щелкните на элементе **Пользователи** и выберите пользователя в списке доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="af215-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="af215-124">В верхней части страницы щелкните на элементе **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="af215-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="af215-125">В области **Аудиоконференции** щелкните на элементе **Сбросить идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="af215-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="af215-126">В окне **Сбросить идентификатор конференции** нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="af215-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="af215-127">Автоматически создается идентификатор конференции, после чего пользователю отправляется сообщение электронной почты с новым идентификатором.</span><span class="sxs-lookup"><span data-stu-id="af215-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="af215-128">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="af215-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="af215-129">Дополнительные сведения см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="af215-129">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="af215-130">Что еще вам нужно знать?</span><span class="sxs-lookup"><span data-stu-id="af215-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="af215-131">После создания или сброса идентификатора конференции вызывающие абоненты не смогут использовать старый идентификатор.</span><span class="sxs-lookup"><span data-stu-id="af215-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="af215-132">Вам следует попросить пользователей перепланировать имеющиеся приглашения на собрание, чтобы добавить в них новый идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="af215-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="af215-133">Идентификатор конференции должен иметь длину в цифрах, заданную для моста аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="af215-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="af215-134">В идентификаторе конференции нельзя использовать буквы или специальные символы; можно использовать только цифры.</span><span class="sxs-lookup"><span data-stu-id="af215-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="af215-135">Идентификатор конференции для всех пользователей аудиоконференций состоит из 7 символов по умолчанию, и количество знаков не подлежит изменению.</span><span class="sxs-lookup"><span data-stu-id="af215-135">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="af215-136">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="af215-136">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="af215-p107">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="af215-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="af215-140">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="af215-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="af215-141">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="af215-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="af215-142">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="af215-142">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="af215-143">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="af215-143">Related topics</span></span>

[<span data-ttu-id="af215-144">Оцените или приобретите аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="af215-144">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

