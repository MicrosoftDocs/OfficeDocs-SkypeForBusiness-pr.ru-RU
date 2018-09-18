---
title: Сброс ПИН-кода аудиоконференций в Microsoft Teams
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
description: 'Сведения о ПИН-кодах и их сбросе в Microsoft Teams. '
ms.openlocfilehash: 9c63df504150dce7ba1d46329fc86a27c75ced8d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892956"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a><span data-ttu-id="e54d9-103">Сброс ПИН-кода аудиоконференций в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e54d9-103">For information about resetting Audio Conferencing PINs in Microsoft Teams, see Reset the Audio Conferencing PIN in Microsoft Teams.</span></span>

<span data-ttu-id="e54d9-104">Состоящий из цифр ПИН-код создается для каждого пользователя Microsoft Teams, активируемого для аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="e54d9-104">A PIN is a code made up of numbers that is created for each Skype for Business user who is enabled for audio conferencing.</span></span> <span data-ttu-id="e54d9-105">ПИН-коды аудиоконференций используют организаторы собраний для подтверждения статуса организатора собрания и запуска собрания по телефону.</span><span class="sxs-lookup"><span data-stu-id="e54d9-105">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="e54d9-106">Если для запуска собрания они используют приложение Microsoft Teams, ПИН-код не требуется.</span><span class="sxs-lookup"><span data-stu-id="e54d9-106">If they use the Skype for Business app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="e54d9-107">Если пользователь забыл свой ПИН-код, и ему не удается найти сообщение электронной почты, отправленное ему при предоставлении возможности участия в аудиоконференциях, администратор может выполнить сброс его ПИН-кода, или же он может изменить свой ПИН-код самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="e54d9-107">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="e54d9-108">Собрание начинается, когда прошедший проверку пользователь подключается с помощью приложения Microsoft Teams или когда организатор подключается с использованием собственного ПИН-кода по телефону.</span><span class="sxs-lookup"><span data-stu-id="e54d9-108">Meetings can be started when an authenticated user joins using a Skype for Business client or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="e54d9-109">Если для участия в телефонном собрании требуется ПИН-код, то все пользователи, подключившиеся к этому собранию по телефону, перенаправляются в зал ожидания и могут прослушивать музыку до начала собрания.</span><span class="sxs-lookup"><span data-stu-id="e54d9-109">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="e54d9-110">Если организатор собрания не запрашивает ПИН-код при открытии собрания по телефону, то при подключении к собранию участникам не потребуется вводить ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="e54d9-110">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>

## <a name="reset-a-users-pin"></a><span data-ttu-id="e54d9-111">Сброс ПИН-кода пользователя</span><span class="sxs-lookup"><span data-stu-id="e54d9-111">Reset a user's PIN</span></span>

1. <span data-ttu-id="e54d9-112">В левой области навигации щелкните на элементе **Пользователи** и выберите пользователя в списке доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="e54d9-112">In the **Skype for Business admin center**, in the left navigation go to Audio conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="e54d9-113">В верхней части страницы щелкните на элементе **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e54d9-113">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="e54d9-114">В области **Аудиоконференции** щелкните на элементе **Сбросить ПИН-код**.</span><span class="sxs-lookup"><span data-stu-id="e54d9-114">Under **Audio Conferencing**, click **Reset PIN**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="e54d9-115">Сброс ПИН-кода самим пользователем</span><span class="sxs-lookup"><span data-stu-id="e54d9-115">Have a user reset his or her own PIN</span></span>

1. <span data-ttu-id="e54d9-116">Попросите пользователя перейти по адресу [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span><span class="sxs-lookup"><span data-stu-id="e54d9-116">Have the user go to [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span></span>
2. <span data-ttu-id="e54d9-117">Щелкните **Сбросить ПИН-код**.</span><span class="sxs-lookup"><span data-stu-id="e54d9-117">Click **Reset PIN**.</span></span> 


## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="e54d9-118">Что еще нужно знать о ПИН-кодах?</span><span class="sxs-lookup"><span data-stu-id="e54d9-118">What else should you know about PINs?</span></span>

- <span data-ttu-id="e54d9-119">В целях безопасности ПИН-код отображается однократно и только для администратора, выполняющего сброс.</span><span class="sxs-lookup"><span data-stu-id="e54d9-119">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="e54d9-120">После сброса ПИН-кода администратором он отображается в виде символов \*\*\*\*\*\*\*\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="e54d9-120">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\* in the Skype for Business admin center and in the results when they use Get-CsCsOnlineDialInConfencingUser in the Windows PowerShell.</span></span>
    
- <span data-ttu-id="e54d9-121">Автоматическая отправка уведомлений по электронной почте включена по умолчанию. Пользователи получат сообщение электронной почты при их активации для аудиоконференций или при сбросе ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="e54d9-121">Automatically sending emails to users is enabled by default and users will receive an email with their PIN when they're enabled for dial-in conferencing or when the PIN is reset. But if you have disabled automatically sending emails, then a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span> <span data-ttu-id="e54d9-122">Однако если автоматическая отправка сообщений электронной почты отключена, пользователь не получит сообщение при сбросе ПИН-кода и эти данные придется пересылать пользователю вручную.</span><span class="sxs-lookup"><span data-stu-id="e54d9-122">But if you have disabled automatically sending emails, then a PIN reset email won't be sent to a user and you will have to manually send the PIN to the user.</span></span>
    
- <span data-ttu-id="e54d9-p105">Когда начинается собрание, к нему автоматически присоединяются все пользователи, находящиеся в зале ожидания. Пример: если два участника попытаются присоединиться к собранию, когда оно еще не началось, эти участники будут перенаправлены в зал ожидания. Когда с телефона присоединяется организатор собрания под собственным ПИН-кодом, собрание начинается, и к нему подключаются все участники, находящиеся в зале ожидания.</span><span class="sxs-lookup"><span data-stu-id="e54d9-p105">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="e54d9-125">По умолчанию анонимные вызывающие абоненты не могут начинать собрание.</span><span class="sxs-lookup"><span data-stu-id="e54d9-125">The default setting isn't to allow a meeting to be started by an anonymous callers.</span></span>
    
- <span data-ttu-id="e54d9-126">Когда пользователя активируют для аудиоконференций, он по умолчанию получает сообщение электронной почты с информацией о конференции и ПИН-кодом.</span><span class="sxs-lookup"><span data-stu-id="e54d9-126">When you enable a user for dial-in conferencing, by default they are sent emails that includes conferencing information and their PIN.</span></span> <span data-ttu-id="e54d9-127">Пользователю требуется почтовый ящик Office 365, так как при сбросе ПИН-кода новый ПИН-код отправляется на основной электронный SMTP-адрес (псевдоним), назначенный этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="e54d9-127">The user must have an Office 365 mailbox because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="e54d9-128">При настройке аудиоконференций вы задаете цифры, которые должны быть включены в ПИН-коды в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e54d9-128">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="e54d9-129">ПИН-коды могут содержать от 4 до 12 цифр, по умолчанию их число равно 5.</span><span class="sxs-lookup"><span data-stu-id="e54d9-129">The PIN can only be from 4 to 12 digits. The default is 5.</span></span> <span data-ttu-id="e54d9-130">При изменении длины ПИН-кода новое значение применяется только к новым ПИН-кодам и не применяется к ПИН-кодам для существующих пользователей, которым разрешено участие в аудиоконференциях.</span><span class="sxs-lookup"><span data-stu-id="e54d9-130">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="e54d9-131">См. [Настройка длины PIN-кода для собраний с аудиоконференцией](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="e54d9-131">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span></span>
    
- <span data-ttu-id="e54d9-132">Сообщение электронной почты по умолчанию будет отправлено на основной SMTP-адрес пользователя в Office 365.</span><span class="sxs-lookup"><span data-stu-id="e54d9-132">The email by default will be set to the Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="e54d9-133">Вы можете отправить сообщение электронной почты на адрес электронной почты, который не относится к Office 365, например, на портале Hotmail или MSN.</span><span class="sxs-lookup"><span data-stu-id="e54d9-133">You can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="e54d9-134">Используемый по умолчанию адрес электронной почты можно изменить с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e54d9-134">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="e54d9-135">Это полезно, когда у пользователей нет почтового ящика Exchange в Office 365.</span><span class="sxs-lookup"><span data-stu-id="e54d9-135">This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>

    

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="e54d9-136">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="e54d9-136">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="e54d9-p109">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="e54d9-p109">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e54d9-140">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="e54d9-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="e54d9-141">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e54d9-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="e54d9-142">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="e54d9-142">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e54d9-143">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="e54d9-143">Related topics</span></span>

[<span data-ttu-id="e54d9-144">Сброс идентификатора конференции для пользователя</span><span class="sxs-lookup"><span data-stu-id="e54d9-144">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user-in-teams.md)
