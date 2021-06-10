---
title: Просмотр, изменение и сброс ИД конференции пользователя
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
- seo-marvel-apr2020
description: Узнайте, как назначить ИД конференции пользователю в Microsoft Teams и какие параметры должны быть для этих параметров.
ms.openlocfilehash: b57a419266ceca09a73fc4bf75bb12153e41ea91
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117212"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a><span data-ttu-id="a89b4-103">Просмотр и сброс назначенного пользователю ИД конференции в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a89b4-103">View and reset a conference ID assigned to a user in Microsoft Teams</span></span>

<span data-ttu-id="a89b4-104">Когда пользователь Microsoft Teams аудиоконференцию в Microsoft 365 или Office 365 и использует Майкрософт в качестве поставщика услуг аудиоконференций, пользователю автоматически.</span><span class="sxs-lookup"><span data-stu-id="a89b4-104">A conferencing ID is automatically assigned to a Microsoft Teams user when they are set up for Audio Conferencing in Microsoft 365 or Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="a89b4-105">Присвоенный ему ИД конференции отправляется в приглашении на собрание при его запланированном собрании.</span><span class="sxs-lookup"><span data-stu-id="a89b4-105">The conference ID assigned is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="a89b4-106">Каждому собранию, запланированному пользователем, будет назначен уникальный идентификатор конференции.</span><span class="sxs-lookup"><span data-stu-id="a89b4-106">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> 
  
<span data-ttu-id="a89b4-107">Хотя ИД конференции будет автоматически создан и назначен пользователю, иногда пользователь не хочет использовать этот номер и хочет установить определенное число, или пользователи не могут вспомнить или потеряли свой ИД конференции.</span><span class="sxs-lookup"><span data-stu-id="a89b4-107">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="a89b4-108">Вы можете использовать Microsoft Teams или Windows PowerShell для просмотра, изменения и сброса их ИД конференции.</span><span class="sxs-lookup"><span data-stu-id="a89b4-108">You can use Microsoft Teams admin center or Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="a89b4-109">Идентификатор конференции и телефонные номера для проведения аудиоконференции, назначенные по умолчанию, будут отправлены пользователю по электронной почте. Если вы сбросите идентификатор конференции в настройках, по электронной почте вам придет другой идентификатор конференции, но не ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="a89b4-109">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span> <span data-ttu-id="a89b4-110">Дополнительные сведения о том, как сбросить ПИН-код организатора [конференции Microsoft Teams](reset-a-conference-id-for-a-user-in-teams.md) см. в этой Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a89b4-110">See [Reset a conference ID for a user in Microsoft Teams](reset-a-conference-id-for-a-user-in-teams.md) for more information about how to reset a conference organizer's PIN.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a><span data-ttu-id="a89b4-111">Просмотр и сброс идентификатора конференции</span><span class="sxs-lookup"><span data-stu-id="a89b4-111">View and reset conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="a89b4-112">Просмотр ИД конференции</span><span class="sxs-lookup"><span data-stu-id="a89b4-112">To view the conference ID</span></span>

<span data-ttu-id="a89b4-113">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="a89b4-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="a89b4-114">В левой области навигации щелкните **Пользователи** и выберите пользователя из списка доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="a89b4-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="a89b4-115">В верхней части страницы нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="a89b4-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="a89b4-116">В **области Аудиоконференции** посмотрите на **ИД конференции**.</span><span class="sxs-lookup"><span data-stu-id="a89b4-116">Under **Audio Conferencing**, look under **Conference ID**.</span></span>

    > [!TIP]
    > <span data-ttu-id="a89b4-117">Вы можете отправить пользователю по электронной почте все сведения о конференции, включая ее ИД и номера телефонов для аудиосвязи, щелкнув ссылку Отправить сведения о конференции по **электронной** почте.</span><span class="sxs-lookup"><span data-stu-id="a89b4-117">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info in email** link.</span></span>
  
<span data-ttu-id="a89b4-118">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a89b4-118">**Using Windows PowerShell**</span></span>

<span data-ttu-id="a89b4-119">Дополнительные сведения см. в Microsoft Teams [PowerShell.](/powershell/module/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="a89b4-119">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="a89b4-120">Сброс ИД конференции</span><span class="sxs-lookup"><span data-stu-id="a89b4-120">To reset the conference ID</span></span>

<span data-ttu-id="a89b4-121">Если, например, пользователь забыл идентификатор конференции, его можно сбросить.</span><span class="sxs-lookup"><span data-stu-id="a89b4-121">You can reset a conference ID for a user if, for example, they forget it.</span></span>
  
<span data-ttu-id="a89b4-122">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="a89b4-122">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="a89b4-123">В левой области навигации щелкните **Пользователи** и выберите пользователя из списка доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="a89b4-123">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="a89b4-124">В верхней части страницы нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="a89b4-124">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="a89b4-125">В **области Аудиоконференции** щелкните **Сбросить ИД конференции**.</span><span class="sxs-lookup"><span data-stu-id="a89b4-125">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>

4. <span data-ttu-id="a89b4-126">В **окне Сброс ИД конференции** нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="a89b4-126">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="a89b4-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="a89b4-127">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
  
<span data-ttu-id="a89b4-128">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a89b4-128">**Using Windows PowerShell**</span></span>

<span data-ttu-id="a89b4-129">Дополнительные сведения см. в Microsoft Teams [PowerShell.](/powershell/module/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="a89b4-129">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="what-else-should-you-know"></a><span data-ttu-id="a89b4-130">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="a89b4-130">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="a89b4-131">После создания нового ИД конференции или сброса его старый ИД конференции нельзя использовать для вызывающих вызовов.</span><span class="sxs-lookup"><span data-stu-id="a89b4-131">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="a89b4-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="a89b4-132">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 
  
    
- <span data-ttu-id="a89b4-133">Количество цифр идентификатора конференции должно соответствовать номеру Аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="a89b4-133">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="a89b4-134">В идентификаторе конференции нельзя использовать буквы или специальные символы; можно использовать только цифры.</span><span class="sxs-lookup"><span data-stu-id="a89b4-134">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
   
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="a89b4-135">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="a89b4-135">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="a89b4-136">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="a89b4-136">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="a89b4-137">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единого администрирования, который упростит выполнение повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="a89b4-137">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="a89b4-138">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="a89b4-138">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a89b4-139">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="a89b4-139">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="a89b4-140">[Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="a89b4-140">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="a89b4-141">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="a89b4-141">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="a89b4-142">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="a89b4-142">Related topics</span></span>

[<span data-ttu-id="a89b4-143">Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="a89b4-143">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)