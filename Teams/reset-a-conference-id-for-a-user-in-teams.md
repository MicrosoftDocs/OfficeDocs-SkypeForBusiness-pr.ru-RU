---
title: Сброс идентификатора конференции для пользователя в Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
- seo-marvel-mar2020
description: Узнайте, как сбросить ИД конференции пользователя в Microsoft Teams и получить ссылки на средства обновления собраний и миграции.
ms.openlocfilehash: edccab5da883c1707ade75519e96615ed3524bf3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117647"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="7323b-103">Сброс идентификатора конференции для пользователя в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7323b-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="7323b-104">Динамический ИД конференции содержится в нижней части приглашений на собрание, а также номера телефонов для телефонного звонка, которые могут использоваться звонителями для звонков на собрание.</span><span class="sxs-lookup"><span data-stu-id="7323b-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="7323b-105">Когда пользователь наберет номер телефона, автозаводщик собрания попросит вызывающего пользователя ввести этот номер конференции, чтобы он принял участие в собрании.</span><span class="sxs-lookup"><span data-stu-id="7323b-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7323b-106">Коды конференций создаются автоматически, от 7 до 9 цифр и задаются при включке аудиоконференции для пользователя.</span><span class="sxs-lookup"><span data-stu-id="7323b-106">Conference IDs are generated automatically, will be between 7-9 digits, and are set when you enable Audio Conferencing for a user.</span></span> <span data-ttu-id="7323b-107">**Статические ИД конференции не поддерживаются.**</span><span class="sxs-lookup"><span data-stu-id="7323b-107">**Static conference IDs aren't supported.**</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="7323b-108">Сброс ИД конференции для пользователя</span><span class="sxs-lookup"><span data-stu-id="7323b-108">Resetting the conference ID for a user</span></span>

<span data-ttu-id="7323b-109">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="7323b-109">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="7323b-110">В области навигации слева **щелкните**"Пользователи" и выберите пользователя в списке доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="7323b-110">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="7323b-111">Нажмите **кнопку "Изменить".**</span><span class="sxs-lookup"><span data-stu-id="7323b-111">Click **Edit**.</span></span>

3. <span data-ttu-id="7323b-112">В **области аудиоконференции нажмите** кнопку **"Сбросить ИД конференции".**</span><span class="sxs-lookup"><span data-stu-id="7323b-112">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="7323b-113">В **окне "Сброс ИД конференции"** нажмите кнопку **"Сброс".**</span><span class="sxs-lookup"><span data-stu-id="7323b-113">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="7323b-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="7323b-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="7323b-115">По умолчанию электронные письма отправляются пользователям, но это можно отключить.</span><span class="sxs-lookup"><span data-stu-id="7323b-115">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="7323b-116">После сброса идентификатора конференции на электронную почту пользователя отправляется сообщение с новым идентификатором конференции.</span><span class="sxs-lookup"><span data-stu-id="7323b-116">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="7323b-117">Во многих случаях это сообщение электронной почты отправляется на основной адрес электронной почты их почтового ящика Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="7323b-117">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="7323b-118">Сообщение электронной почты содержит новый ИД конференции, номера телефонов для телефонного звонка по умолчанию и инструкции по обновлению существующих собраний.</span><span class="sxs-lookup"><span data-stu-id="7323b-118">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="7323b-119">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="7323b-119">What else should I know?</span></span>

- <span data-ttu-id="7323b-120">Вы можете отправить пользователю по электронной почте все сведения о конференции, включая ее ИД и  номера телефонов для телефонного  звонка, нажав кнопку "Отправить сведения о конференции" по электронной почте для пользователя в разделе "Аудиоконференции".</span><span class="sxs-lookup"><span data-stu-id="7323b-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="7323b-121">ПИН-код не отправляется.</span><span class="sxs-lookup"><span data-stu-id="7323b-121">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="7323b-122">Код конференции из 7–9 цифр создается службой Teams.</span><span class="sxs-lookup"><span data-stu-id="7323b-122">A 7- 9 digit conference ID is created by the Teams service.</span></span> <span data-ttu-id="7323b-123">Его длину изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="7323b-123">You can't change its length.</span></span>
    
- <span data-ttu-id="7323b-124">После сброса новый идентификатор конференции будет отображаться в поле **Идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="7323b-124">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="7323b-125">После создания нового идентификатора конференции старый идентификатор не может использоваться для выполнения вызовов.</span><span class="sxs-lookup"><span data-stu-id="7323b-125">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="7323b-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="7323b-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="7323b-127">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="7323b-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="7323b-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="7323b-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="7323b-129">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="7323b-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="7323b-130">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="7323b-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7323b-131">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="7323b-131">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="7323b-132">[Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="7323b-132">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="7323b-133">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="7323b-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="7323b-134">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="7323b-134">Related topics</span></span>

[<span data-ttu-id="7323b-135">Сброс ПИН-кода для аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="7323b-135">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)