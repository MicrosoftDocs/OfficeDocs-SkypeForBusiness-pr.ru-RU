---
title: Параметры электронной почты при изменении параметров аудиоконференции
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
description: 'Узнайте, как включить Skype или отключить отправку электронных писем пользователям при изменениях параметров, таких как изменение пин-кода или номер для Microsoft Teams. '
ms.openlocfilehash: e1bb6df0a443f01ed3c9bc70d03eedc05f217ce4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092707"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="d94a4-103">Включение и отключение отправки сообщений электронной почты при изменении настроек аудиоконференций в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d94a4-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="d94a4-104">Пользователи автоматически получают уведомления по электронной почте, если они активированы для аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="d94a4-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="d94a4-105">Однако иногда может потребоваться уменьшить количество сообщений электронной почты, отправленных Microsoft Teams пользователям.</span><span class="sxs-lookup"><span data-stu-id="d94a4-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="d94a4-106">В этом случае можно отключить функцию отправки сообщений по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="d94a4-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="d94a4-107">Если отключить отправку сообщений электронной почты, электронные письма для аудиоконференции не будут отправляться пользователям, включая сообщения о том, когда пользователи включены или отключены для аудиоконференции, когда их ПИН-код сбрасывается, а также когда изменяется код конференции и номер телефона конференц-связи по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d94a4-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="d94a4-108">Вот пример сообщения электронной почты, которое отправляется пользователям, если для них включена аудиоконференция:</span><span class="sxs-lookup"><span data-stu-id="d94a4-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Пример сообщения электронной почты для аудиоконференции](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="d94a4-110">Когда пользователи получают уведомления по электронной почте?</span><span class="sxs-lookup"><span data-stu-id="d94a4-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="d94a4-111">После включения аудиоконференции пользователям в организации отправляется несколько сообщений электронной почты:</span><span class="sxs-lookup"><span data-stu-id="d94a4-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="d94a4-112">При назначении пользователям лицензии **аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="d94a4-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="d94a4-113">При сбросе ПИН-кода аудиоконференции пользователя вручную.</span><span class="sxs-lookup"><span data-stu-id="d94a4-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="d94a4-114">Выполнение сброса идентификатора конференции пользователя вручную.</span><span class="sxs-lookup"><span data-stu-id="d94a4-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="d94a4-115">Если удаляется лицензия  **Аудиоконференции**.</span><span class="sxs-lookup"><span data-stu-id="d94a4-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="d94a4-116">При смене поставщика услуг аудиоконференций пользователя с Майкрософт на другого поставщика или **нет**.</span><span class="sxs-lookup"><span data-stu-id="d94a4-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="d94a4-117">При смене поставщика услуг аудиоконференций пользователя на Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="d94a4-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="d94a4-118">Включить или отключить отправку электронной почты пользователям</span><span class="sxs-lookup"><span data-stu-id="d94a4-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="d94a4-119">Вы можете Microsoft Teams или Windows PowerShell, чтобы включить или отключить электронную почту, отправленную пользователям.</span><span class="sxs-lookup"><span data-stu-id="d94a4-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="d94a4-120">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="d94a4-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d94a4-121">На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="d94a4-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="d94a4-122">В верхней части страницы **Мосты** конференций щелкните **Параметры моста**.</span><span class="sxs-lookup"><span data-stu-id="d94a4-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="d94a4-123">В области **Параметры моста** включите или отключите параметр Автоматически отправлять сообщения электронной почты пользователям при изменении параметров телефонного **дозвона.**</span><span class="sxs-lookup"><span data-stu-id="d94a4-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="d94a4-124">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d94a4-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="d94a4-125">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d94a4-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="d94a4-126">Дополнительные сведения см. в Microsoft Teams [PowerShell.](/powershell/module/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="d94a4-126">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="d94a4-127">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="d94a4-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="d94a4-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="d94a4-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="d94a4-129">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единого администрирования, который упростит выполнение повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="d94a4-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="d94a4-130">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="d94a4-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d94a4-131">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="d94a4-131">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="d94a4-132">[Лучшие способы управления Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="d94a4-132">[Best ways to manage Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="d94a4-133">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="d94a4-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="d94a4-134">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="d94a4-134">Related topics</span></span>

[<span data-ttu-id="d94a4-135">Сообщения электронной почты, отправленные пользователям при изменении параметров аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="d94a4-135">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="d94a4-136">Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="d94a4-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)