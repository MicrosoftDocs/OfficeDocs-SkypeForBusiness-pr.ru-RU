---
title: Запуск аудиоконференции по телефону без ПИН-кода в Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
- seo-marvel-mar2020
description: 'Узнайте, как включить или отключить присоединение анонимных звонков к собранию из Teams администрирования. '
ms.openlocfilehash: 520bf720a01a686a103748cdbbf26cb8426e94f2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116967"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="7d4aa-103">Начало аудиоконференции по телефону без ПИН-кода в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7d4aa-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="7d4aa-104">Пользователям, которые будут проходить собрание по телефонной связи, может быть сложно проводить собрание в "Microsoft Teams прослушивания музыки", так как Microsoft Teams не начал собрание.</span><span class="sxs-lookup"><span data-stu-id="7d4aa-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="7d4aa-105">Если организатор собрания звонит на собрание, по умолчанию для начала собрания требуется ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="7d4aa-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="7d4aa-106">Вы можете настроить его таким образом, чтобы любой человек мог звонить на собрание, а пин-код не выводиться для начала собрания.</span><span class="sxs-lookup"><span data-stu-id="7d4aa-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="7d4aa-107">С помощью Центра администрирования можно включить или отключить этот параметр для одного пользователя.</span><span class="sxs-lookup"><span data-stu-id="7d4aa-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="7d4aa-108">ПИН-код не требуется организатору собрания, если кто-то начал собрание из Microsoft Teams приложения.</span><span class="sxs-lookup"><span data-stu-id="7d4aa-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="7d4aa-109">ПИН-код требуется только в том случае, если организатор собрания присоединяется к собранию по телефону.</span><span class="sxs-lookup"><span data-stu-id="7d4aa-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="7d4aa-110">ПИН-код для собраний отправляется пользователю аудиоконференции, если ему назначена лицензия на аудиоконференцию и включена аудиоконференция. </span><span class="sxs-lookup"><span data-stu-id="7d4aa-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="7d4aa-111">[См.](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) статью Отправка электронной почты пользователю со сведениями об аудиоконференциях и Электронные письма, которые автоматически отправляются пользователям при изменении их параметров аудиоконференции. [](emails-sent-to-users-when-their-settings-change-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="7d4aa-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="7d4aa-112">Разрешение и запрет присоединения анонимных абонентов к собранию</span><span class="sxs-lookup"><span data-stu-id="7d4aa-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="7d4aa-113">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="7d4aa-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="7d4aa-114">В левой области навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="7d4aa-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="7d4aa-115">Выберите пользователя в списке и нажмите кнопку **Изменить** в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="7d4aa-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="7d4aa-116">Рядом с пунктом **Аудиоконференции** нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="7d4aa-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="7d4aa-117">В области **Аудиоконференция** включите или отключите вызывающих телефонную звонок может быть первым лицом на **собрании**.</span><span class="sxs-lookup"><span data-stu-id="7d4aa-117">In the **Audio Conferencing** pane, enable or disable **Dial-in callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="7d4aa-118">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="7d4aa-118">Click **Apply**.</span></span> 

<span data-ttu-id="7d4aa-119">**Использование Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="7d4aa-119">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="7d4aa-120">Дополнительные сведения см. в Microsoft Teams [PowerShell.](/powershell/module/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="7d4aa-120">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="7d4aa-121">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="7d4aa-121">What else should you know?</span></span>

- <span data-ttu-id="7d4aa-122">Если вы хотите сбросить ПИН-код, см. сброс ПИН-кода [аудиоконференции.](reset-the-audio-conferencing-pin-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="7d4aa-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="7d4aa-123">Если анонимный доступ или требование ПИН-кода для начала собрания отключено:</span><span class="sxs-lookup"><span data-stu-id="7d4aa-123">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="7d4aa-124">Если собрание еще не началось (в собрании пока нет ни одного из них), вызываемму звоня будет предложено, является ли он организатором; Если он даст ответ "Да", ему будет предложено ввести ПИН-код, а после ввода ПИН-кода начнется собрание, и пользователь присоединится к собранию.</span><span class="sxs-lookup"><span data-stu-id="7d4aa-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="7d4aa-125">Если собрание уже началось (кто-либо присоединился): абонент не получит сообщения с вопросом, является ли он организатором. Кроме того, PIN-код запрашиваться не будет. Собрание уже началось, и пользователь присоединится к нему.</span><span class="sxs-lookup"><span data-stu-id="7d4aa-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="7d4aa-126">Если включен анонимный доступ или не требуется ПИН-код для начала собрания:</span><span class="sxs-lookup"><span data-stu-id="7d4aa-126">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="7d4aa-127">Если собрание еще не началось (никто не присоединился): абонент не получит сообщения с вопросом, является ли он организатором. Кроме того, PIN-код запрашиваться не будет.</span><span class="sxs-lookup"><span data-stu-id="7d4aa-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="7d4aa-128">Так как параметр организатора отключен, собрание начнется, и анонимные звоняки присоединятся к собранию.</span><span class="sxs-lookup"><span data-stu-id="7d4aa-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="7d4aa-129">Если собрание уже началось (кто-либо присоединился): абонент не получит сообщения с вопросом, является ли он организатором. Кроме того, PIN-код запрашиваться не будет. Собрание уже началось, и абонент присоединится к нему.</span><span class="sxs-lookup"><span data-stu-id="7d4aa-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="7d4aa-130">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="7d4aa-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="7d4aa-131">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="7d4aa-131">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="7d4aa-132">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единого администрирования, который упростит выполнение повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="7d4aa-132">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="7d4aa-133">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="7d4aa-133">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7d4aa-134">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="7d4aa-134">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="7d4aa-135">[Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="7d4aa-135">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="7d4aa-136">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="7d4aa-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7d4aa-137">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="7d4aa-137">Related topics</span></span>

[<span data-ttu-id="7d4aa-138">Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="7d4aa-138">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)