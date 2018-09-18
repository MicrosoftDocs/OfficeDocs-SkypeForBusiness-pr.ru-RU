---
title: Просмотр, изменение и сброс назначенного пользователю идентификатора конференции в Microsoft Teams
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Сведения о том, как назначить идентификатор конференции пользователю в Microsoft Teams и какими должны быть его параметры. '
ms.openlocfilehash: d0ee177fbbe286cc68c45e1c41f391b52c44291e
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892035"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="29422-103">Просмотр и сброс назначенного пользователю идентификатора конференции в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="29422-103">View and reset a conference ID assigned to a user in Skype for Business Online</span></span>

<span data-ttu-id="29422-104">Идентификатор конференции автоматически назначается пользователю Microsoft Teams, когда он активируется для аудиоконференций в Office 365 и использует корпорацию Майкрософт в качестве поставщика услуг аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="29422-104">A conferencing ID is automatically assigned to a Skype for Business user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="29422-105">Назначенный идентификатор конференции отправляется в приглашении на собрание при планировании собрания.</span><span class="sxs-lookup"><span data-stu-id="29422-105">The conference ID assigned can be either a static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="29422-106">Каждому собранию, запланированному пользователем, будет назначен уникальный идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="29422-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="29422-107">Хотя идентификатор конференции создается и назначается пользователю автоматически, в некоторых случаях пользователю может потребоваться использовать в качестве идентификатора конкретный номер, кроме того, пользователи могут забыть или потерять этот идентификатор.</span><span class="sxs-lookup"><span data-stu-id="29422-107">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number or if your users can't remember or have lost their conference ID, you can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span> <span data-ttu-id="29422-108">С помощью Центра администрирования Microsoft Teams или Windows PowerShell вы можете просмотреть, изменить и сбросить идентификатор конференции пользователя.</span><span class="sxs-lookup"><span data-stu-id="29422-108">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="29422-109">Идентификатор конференции и телефонные номера для проведения аудиоконференции, назначенные по умолчанию, будут отправлены пользователю по электронной почте. Если вы сбросите идентификатор конференции в настройках, по электронной почте вам придет другой идентификатор конференции, но не ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="29422-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="29422-110">Для получения дополнительных сведений о сбросе ПИН-кода инициатора конференции, [перейдите сюда](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="29422-110">For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user-in-teams.md).</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="29422-111">Просмотр и сброс идентификатора конференции</span><span class="sxs-lookup"><span data-stu-id="29422-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="29422-112">Просмотр идентификатора конференции</span><span class="sxs-lookup"><span data-stu-id="29422-112">To reset the meeting conference ID</span></span>

<span data-ttu-id="29422-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **С помощью Microsoft Teams и Центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="29422-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

1. <span data-ttu-id="29422-114">В левой области навигации щелкните на элементе **Пользователи** и выберите пользователя в списке доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="29422-114">In the **Skype for Business admin center**, in the left navigation go to Audio conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="29422-115">В верхней части страницы щелкните на элементе **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="29422-115">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="29422-116">В области **Аудиоконференции** просмотрите значение **Идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="29422-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="29422-117">Всю информацию о конференц-связи, включая идентификатор конференции и телефонные номера для аудиоконференции, можно отправить пользователю по электронной почте, щелкнув ссылку **Отправить сведения о конференции по эл. почте**.</span><span class="sxs-lookup"><span data-stu-id="29422-117">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking the **Send conference info via email**.</span></span>
  
<span data-ttu-id="29422-118">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="29422-118">**Using Windows Powershell**</span></span>

<span data-ttu-id="29422-119">Дополнительные сведения см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="29422-119">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="29422-120">Сброс идентификатора конференции</span><span class="sxs-lookup"><span data-stu-id="29422-120">To reset the meeting conference ID</span></span>

<span data-ttu-id="29422-121">вы можете сбросить идентификатор конференции для пользователя, например, если он забыл его.</span><span class="sxs-lookup"><span data-stu-id="29422-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="29422-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **С помощью Microsoft Teams и Центра администрирования Skype для бизнеса**</span><span class="sxs-lookup"><span data-stu-id="29422-122">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center:**</span></span>

1. <span data-ttu-id="29422-123">В левой области навигации щелкните на элементе **Пользователи** и выберите пользователя в списке доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="29422-123">In the **Skype for Business admin center**, in the left navigation go to Audio conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="29422-124">В верхней части страницы щелкните на элементе **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="29422-124">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="29422-125">В области **Аудиоконференции** щелкните на элементе **Сбросить идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="29422-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="29422-126">В окне **Сбросить идентификатор конференции** нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="29422-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="29422-127">Автоматически создается идентификатор конференции, после чего пользователю отправляется сообщение электронной почты с новым идентификатором.</span><span class="sxs-lookup"><span data-stu-id="29422-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="29422-128">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="29422-128">**Using Windows Powershell**</span></span>

<span data-ttu-id="29422-129">Дополнительные сведения см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="29422-129">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="29422-130">Что еще вам нужно знать?</span><span class="sxs-lookup"><span data-stu-id="29422-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="29422-131">После создания или сброса идентификатора конференции вызывающие абоненты не смогут использовать старый идентификатор.</span><span class="sxs-lookup"><span data-stu-id="29422-131">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="29422-132">Вам следует попросить пользователей перепланировать имеющиеся приглашения на собрание, чтобы добавить в них новый идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="29422-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="29422-133">Идентификатор конференции должен иметь длину в цифрах, заданную для моста аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="29422-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="29422-134">В идентификаторе конференции нельзя использовать буквы или специальные символы; можно использовать только цифры.</span><span class="sxs-lookup"><span data-stu-id="29422-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="29422-135">Идентификатор конференции для всех пользователей аудиоконференций состоит из 7 символов по умолчанию, и количество знаков не подлежит изменению.</span><span class="sxs-lookup"><span data-stu-id="29422-135">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="29422-136">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="29422-136">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="29422-p107">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="29422-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="29422-140">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="29422-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="29422-141">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="29422-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="29422-142">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="29422-142">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="29422-143">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="29422-143">Related topics</span></span>

[<span data-ttu-id="29422-144">Оцените или приобретите аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="29422-144">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

