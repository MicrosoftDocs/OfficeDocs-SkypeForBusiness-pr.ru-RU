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
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: 'Сведения о том, как назначить идентификатор конференции пользователю в Microsoft Teams и какими должны быть его параметры. '
ms.openlocfilehash: e6b1a1ace9bdbf607fa4e1ef678687f37034a052
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41838139"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="cde33-103">Просмотр и сброс назначенного пользователю идентификатора конференции в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cde33-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="cde33-104">Идентификатор конференции автоматически назначается пользователю Microsoft Teams, когда он активируется для аудиоконференций в Office 365 и использует корпорацию Майкрософт в качестве поставщика услуг аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="cde33-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="cde33-105">Назначенный идентификатор конференции отправляется в приглашении на собрание при планировании собрания.</span><span class="sxs-lookup"><span data-stu-id="cde33-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="cde33-106">Каждому собранию, запланированному пользователем, будет назначен уникальный идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="cde33-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="cde33-107">Хотя идентификатор конференции создается и назначается пользователю автоматически, в некоторых случаях пользователю может потребоваться использовать в качестве идентификатора конкретный номер, кроме того, пользователи могут забыть или потерять этот идентификатор.</span><span class="sxs-lookup"><span data-stu-id="cde33-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="cde33-108">С помощью Центра администрирования Microsoft Teams или Windows PowerShell вы можете просмотреть, изменить и сбросить идентификатор конференции пользователя.</span><span class="sxs-lookup"><span data-stu-id="cde33-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="cde33-109">Идентификатор конференции и телефонные номера для проведения аудиоконференции, назначенные по умолчанию, будут отправлены пользователю по электронной почте. Если вы сбросите идентификатор конференции в настройках, по электронной почте вам придет другой идентификатор конференции, но не ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="cde33-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="cde33-110">Для получения дополнительных сведений о сбросе ПИН-кода инициатора конференции, [перейдите сюда](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="cde33-110">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user-in-teams.md).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="cde33-111">Просмотр и сброс идентификатора конференции</span><span class="sxs-lookup"><span data-stu-id="cde33-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="cde33-112">Просмотр идентификатора конференции</span><span class="sxs-lookup"><span data-stu-id="cde33-112">To view the conference ID</span></span>

<span data-ttu-id="cde33-113">![Значок с логотипом](media/teams-logo-30x30.png) Microsoft Teams, в котором **используется центр администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="cde33-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="cde33-114">В левой области навигации щелкните на элементе **Пользователи** и выберите пользователя в списке доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="cde33-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="cde33-115">В верхней части страницы щелкните на элементе **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="cde33-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="cde33-116">В области **Аудиоконференции** просмотрите значение **Идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="cde33-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="cde33-117">Всю информацию о конференц-связи, включая идентификатор конференции и телефонные номера для аудиоконференции, можно отправить пользователю по электронной почте, щелкнув ссылку **Отправить сведения о конференции по эл. почте**.</span><span class="sxs-lookup"><span data-stu-id="cde33-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="cde33-118">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="cde33-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="cde33-119">Дополнительные сведения см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="cde33-119">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="cde33-120">Сброс идентификатора конференции</span><span class="sxs-lookup"><span data-stu-id="cde33-120">To reset the conference ID</span></span>

<span data-ttu-id="cde33-121">вы можете сбросить идентификатор конференции для пользователя, например, если он забыл его.</span><span class="sxs-lookup"><span data-stu-id="cde33-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="cde33-122">![Значок с логотипом](media/teams-logo-30x30.png) Microsoft Teams, в котором **используется центр администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="cde33-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="cde33-123">В левой области навигации щелкните на элементе **Пользователи** и выберите пользователя в списке доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="cde33-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="cde33-124">В верхней части страницы щелкните на элементе **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="cde33-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="cde33-125">В области **Аудиоконференции** щелкните на элементе **Сбросить идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="cde33-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="cde33-126">В окне **Сбросить идентификатор конференции** нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="cde33-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="cde33-127">Автоматически создается идентификатор конференции, после чего пользователю отправляется сообщение электронной почты с новым идентификатором.</span><span class="sxs-lookup"><span data-stu-id="cde33-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="cde33-128">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="cde33-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="cde33-129">Дополнительные сведения см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="cde33-129">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="cde33-130">Что еще вам нужно знать?</span><span class="sxs-lookup"><span data-stu-id="cde33-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="cde33-131">После создания или сброса идентификатора конференции вызывающие абоненты не смогут использовать старый идентификатор.</span><span class="sxs-lookup"><span data-stu-id="cde33-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="cde33-132">Вам следует попросить пользователей перепланировать имеющиеся приглашения на собрание, чтобы добавить в них новый идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="cde33-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="cde33-133">Идентификатор конференции должен иметь длину в цифрах, заданную для моста аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="cde33-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="cde33-134">В идентификаторе конференции нельзя использовать буквы или специальные символы; можно использовать только цифры.</span><span class="sxs-lookup"><span data-stu-id="cde33-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
   
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="cde33-135">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="cde33-135">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="cde33-p107">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="cde33-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="cde33-139">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="cde33-139">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="cde33-140">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cde33-140">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="cde33-141">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="cde33-141">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="cde33-142">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="cde33-142">Related topics</span></span>

[<span data-ttu-id="cde33-143">Платная или пробная версия аудиоконференций в Office 365</span><span class="sxs-lookup"><span data-stu-id="cde33-143">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

