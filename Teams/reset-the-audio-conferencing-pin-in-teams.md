---
title: Сброс ПИН-кода аудиоконференций в Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
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
description: Узнайте, как сбросить ПИН-код аудиоконференции пользователя в Microsoft Teams и узнать важные сведения о ПИН-кодах.
ms.openlocfilehash: 6470085fed25a83c1a8dc46ab45e8c6ea57b5603
ms.sourcegitcommit: a07040d1527692b4dbde7bd2c21994377ad0a92e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2021
ms.locfileid: "53114028"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a><span data-ttu-id="9cfb0-103">Сброс ПИН-кода аудиоконференций в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9cfb0-103">Reset the Audio Conferencing PIN in Microsoft Teams</span></span>

<span data-ttu-id="9cfb0-104">ПИН-код — это код, который состоит из чисел, которые создаются для Microsoft Teams пользователей, которые могут аудиоконференцию.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-104">A PIN is a code made up of numbers that is created for each Microsoft Teams user who is enabled for audio conferencing.</span></span> <span data-ttu-id="9cfb0-105">ПИН-коды аудиоконференций используют организаторы собраний для подтверждения статуса организатора собрания и запуска собрания по телефону.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-105">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="9cfb0-106">Если собрание начинается Microsoft Teams приложением, ПИН-код не требуется.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-106">If they use the Microsoft Teams app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="9cfb0-107">Если пользователь забыл свой ПИН-код, и ему не удается найти сообщение электронной почты, отправленное ему при предоставлении возможности участия в аудиоконференциях, администратор может выполнить сброс его ПИН-кода, или же он может изменить свой ПИН-код самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-107">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="9cfb0-108">Собрания можно начать, когда пользователь, авторификация, присоединяется с помощью Microsoft Teams или когда организатор присоединяется с помощью ПИН-кода по телефону.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-108">Meetings can be started when an authenticated user joins using the Microsoft Teams app or when the organizer joins with their PIN over the phone.</span></span> <span data-ttu-id="9cfb0-109">Когда для начала собрания требуется ПИН-код, пользователи, присоединившиеся по телефону, помещаются в "в" и будут прослушивать музыку на удержании, пока организатор не допустит их.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-109">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the organizer admits them.</span></span> <span data-ttu-id="9cfb0-110">Если организатор собрания не запрашивает ПИН-код при открытии собрания по телефону, то при подключении к собранию участникам не потребуется вводить ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-110">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>

## <a name="reset-a-users-pin"></a><span data-ttu-id="9cfb0-111">Сброс ПИН-кода пользователя</span><span class="sxs-lookup"><span data-stu-id="9cfb0-111">Reset a user's PIN</span></span>

<span data-ttu-id="9cfb0-112">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="9cfb0-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="9cfb0-113">В левой области навигации щелкните **Пользователи** и выберите пользователя из списка доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-113">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="9cfb0-114">Нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-114">Click **Edit**.</span></span>

3. <span data-ttu-id="9cfb0-115">В **области Аудиоконференция** нажмите кнопку **Сброс ПИН-кода.**</span><span class="sxs-lookup"><span data-stu-id="9cfb0-115">Under **Audio Conferencing**, click **Reset PIN**.</span></span>

4. <span data-ttu-id="9cfb0-116">Нажмите **кнопку Сброс**.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-116">Click **Reset**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a><span data-ttu-id="9cfb0-117">Сброс собственного ПИН-кода пользователем</span><span class="sxs-lookup"><span data-stu-id="9cfb0-117">Have a user reset their own PIN</span></span>

1. <span data-ttu-id="9cfb0-118">Пользователь должен перейти в [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) .</span><span class="sxs-lookup"><span data-stu-id="9cfb0-118">Have the user go to [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span></span>
2. <span data-ttu-id="9cfb0-119">Нажмите **кнопку Сброс ПИН-кода.**</span><span class="sxs-lookup"><span data-stu-id="9cfb0-119">Click **Reset PIN**.</span></span> 

> [!NOTE]
> <span data-ttu-id="9cfb0-120">В GCCH перейдите в: https://webdir2g.online.gov.skypeforbusiness.us/lscp/usp/pstnconferencing .</span><span class="sxs-lookup"><span data-stu-id="9cfb0-120">For GCCH go to: https://webdir2g.online.gov.skypeforbusiness.us/lscp/usp/pstnconferencing.</span></span>

## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="9cfb0-121">Что еще необходимо знать о ПИН-кодах?</span><span class="sxs-lookup"><span data-stu-id="9cfb0-121">What else should you know about PINs?</span></span>

- <span data-ttu-id="9cfb0-122">В целях безопасности ПИН-код отображается только один раз администратору при сбросе ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-122">For security purposes, the PIN is only shown to an administrator one time, when the PIN is reset.</span></span> <span data-ttu-id="9cfb0-123">После сброса ПИН-кода администратором ОН будет указан в списке \*\*\*\*\*\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-123">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\*.</span></span>
    
- <span data-ttu-id="9cfb0-124">По умолчанию автоматическое отправка сообщений электронной почты пользователям включено, и пользователи получают электронное письмо со своим ПИН-кодом, когда им будет включена аудиоконференция или при сбросе ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-124">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="9cfb0-125">Но если вы отключили автоматическое отправку сообщений электронной почты, пользователю не будет отправлено сообщение об сбросе ПИН-кода, и вам придется вручную отправлять сведения о ПИН-коде пользователю.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-125">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="9cfb0-126">Когда собрание начинается, организатор должен допустить всех пользователей STN в " "в"", чтобы присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-126">When a meeting starts, the organizer needs to admit all PSTN users in the lobby to join the meeting.</span></span> <span data-ttu-id="9cfb0-127">Например, если два участника ДНР попытаются присоединиться к собранию до начала, они будут помещаются в "lobby" и будут прослушивать музыку на удержании, а когда организатор собрания присоединяется с помощью ПИН-кода по телефону, начинается собрание, и организатор может использовать команду "Присоединиться к собранию" (нажмите \*21), чтобы допустить всех пользователей ДНР в "ветвь".</span><span class="sxs-lookup"><span data-stu-id="9cfb0-127">For example, if two PSTN participants try to join a meeting before it has started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using their PIN via phone, the meeting will start and the organizer can use the in-meeting command (press \*21) to admit all PSTN users in the lobby.</span></span>
    
- <span data-ttu-id="9cfb0-128">По умолчанию анонимным звонителям не разрешается начать собрание.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-128">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="9cfb0-129">Когда пользователь включает аудиоконференцию, по умолчанию ему отправляются сообщения электронной почты, включающие сведения о аудиоконференции и ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-129">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="9cfb0-130">У пользователя должен быть почтовый ящик Microsoft 365 или Office 365, так как при сбросе ПИН-кода новый ПИН-код отправляется пользователю по электронной почте на его основной SMTP-адрес (псевдоним), установленный для пользователя.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-130">The user must have a Microsoft 365 or Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="9cfb0-131">При настройке аудиоконференций вы задаете цифры, которые должны быть включены в ПИН-коды в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-131">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="9cfb0-132">ПИН-коды могут быть от 4 до 12 цифр ( значение по умолчанию — 5).</span><span class="sxs-lookup"><span data-stu-id="9cfb0-132">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="9cfb0-133">При изменении длины ПИН-кода новое значение применяется только к новым ПИН-кодам и не применяется к ПИН-кодам для существующих пользователей, которым разрешено участие в аудиоконференциях.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-133">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="9cfb0-134">См. [Настройка длины PIN-кода для собраний с аудиоконференцией](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9cfb0-134">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span></span>
    
- <span data-ttu-id="9cfb0-135">По умолчанию для сообщения электронной почты Microsoft 365 или Office 365 основным SMTP-адресом пользователя.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-135">The email by default will be set to the Microsoft 365 or Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="9cfb0-136">Вы можете отправлять сообщения электронной почты на Microsoft 365 адрес электронной почты Office 365 hotmail или MSN.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-136">You can send an email to a non-Microsoft 365 or non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="9cfb0-137">Используемый по умолчанию адрес электронной почты можно изменить с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-137">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="9cfb0-138">Это полезно, если у пользователей нет почтового ящика Exchange в Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-138">This is useful if the users don't have an Exchange mailbox in Microsoft 365 or Office 365.</span></span>

    

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9cfb0-139">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="9cfb0-139">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="9cfb0-140">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-140">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9cfb0-141">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единого администрирования, который упростит выполнение повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-141">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="9cfb0-142">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-142">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9cfb0-143">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="9cfb0-143">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="9cfb0-144">[Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="9cfb0-144">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="9cfb0-145">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="9cfb0-145">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9cfb0-146">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="9cfb0-146">Related topics</span></span>

[<span data-ttu-id="9cfb0-147">Сброс идентификатора конференции для пользователя</span><span class="sxs-lookup"><span data-stu-id="9cfb0-147">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user-in-teams.md)
