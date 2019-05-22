---
title: Начало аудиоконференции по телефону без ПИН-кода в Microsoft Teams
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
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Сведения о том, как включить или отключить анонимным вызывающим абонентам возможность присоединяться к собранию из Центра администрирования Teams. '
ms.openlocfilehash: 246eda17bd9e373a0dcecb4a75aa4f51efc8ae22
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344188"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="6ef83-103">Начало аудиоконференции по телефону без ПИН-кода в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6ef83-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="6ef83-104">Пока организатор не начал собрание, пользователи, подключившиеся к собранию по телефону, находятся в зале ожидания, прослушивая музыку.</span><span class="sxs-lookup"><span data-stu-id="6ef83-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="6ef83-105">При подключении организатора к собранию по телефону по умолчанию запрашивается ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="6ef83-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="6ef83-106">Можно настроить параметры таким образом, чтобы ПИН-код не запрашивался, и к собранию мог свободно подключиться любой пользователь.</span><span class="sxs-lookup"><span data-stu-id="6ef83-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="6ef83-107">Чтобы включить или отключить эту настройку для одного пользователя, используйте Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="6ef83-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="6ef83-108">ПИН-код не требуется организатору собрания, если кто-либо начал данное собрание из приложения Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6ef83-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="6ef83-109">ПИН-код нужен только при присоединении организатора к своему собранию по телефону.</span><span class="sxs-lookup"><span data-stu-id="6ef83-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="6ef83-110">ПИН-код для собраний отправляется пользователю при назначении ему лицензии **Аудиоконференций** и при активации его для аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="6ef83-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="6ef83-111">См. статьи [Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) и [Сообщения электронной почты, отправляемые пользователям при изменении их настроек аудиоконференций](emails-sent-to-users-when-their-settings-change-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="6ef83-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="6ef83-112">Разрешение и запрет присоединения анонимных вызывающих абонентов к собранию</span><span class="sxs-lookup"><span data-stu-id="6ef83-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="6ef83-113">![Значок с логотипом](media/teams-logo-30x30.png) Microsoft Teams, в котором **используется центр администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="6ef83-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="6ef83-114">На панели навигации слева щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="6ef83-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="6ef83-115">Выберите пользователя в списке и щелкните **Изменить** в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="6ef83-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="6ef83-116">Щелкните **Изменить** рядом с элементом **Аудиоконференции**.</span><span class="sxs-lookup"><span data-stu-id="6ef83-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="6ef83-117">В области **Аудиоконференции** включите или отключите настройку **Разрешить непроверенным абонентам стать первыми участниками собрания**.</span><span class="sxs-lookup"><span data-stu-id="6ef83-117">In the **Audio Conferencing** pane, enable or disable **Unauthenticated callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="6ef83-118">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="6ef83-118">Click **Save**.</span></span> 

<span data-ttu-id="6ef83-119">\*\* Использование Windows PowerShell\*\*</span><span class="sxs-lookup"><span data-stu-id="6ef83-119">**Using Windows Powershell**</span></span>
  
<span data-ttu-id="6ef83-120">Дополнительные сведения см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="6ef83-120">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="6ef83-121">Что еще вам нужно знать?</span><span class="sxs-lookup"><span data-stu-id="6ef83-121">What else should you know?</span></span>

- <span data-ttu-id="6ef83-122">Если вы хотите сбросить ПИН-код, см. в статье [Сброс ПИН-кода для аудиоконференции](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="6ef83-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="6ef83-123">Если включен анонимный доступ или параметр, при котором для начала собрания не требуется ПИН-код:</span><span class="sxs-lookup"><span data-stu-id="6ef83-123">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="6ef83-124">Если собрание еще не началось (в нем нет участников): вызывающий абонент получает сообщение с вопросом, является ли он организатором. Если он подтверждает, он получает запрос на ввод ПИН-кода. После ввода ПИН-кода начинается собрание, и пользователь присоединяется к нему.</span><span class="sxs-lookup"><span data-stu-id="6ef83-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="6ef83-125">Если собрание уже началось (кто-либо присоединился): абонент не получит сообщения с вопросом, является ли он организатором. Кроме того, PIN-код запрашиваться не будет. Собрание уже началось, и пользователь присоединится к нему.</span><span class="sxs-lookup"><span data-stu-id="6ef83-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="6ef83-126">Если отключен анонимный доступ или параметр, при котором для начала собрания не требуется ПИН-код:</span><span class="sxs-lookup"><span data-stu-id="6ef83-126">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="6ef83-127">Если собрание еще не началось (никто не присоединился): абонент не получит сообщения с вопросом, является ли он организатором. Кроме того, PIN-код запрашиваться не будет.</span><span class="sxs-lookup"><span data-stu-id="6ef83-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="6ef83-128">Так как настройка организатора отключена, собрание начинается, и анонимные вызывающие абоненты присоединятся к нему.</span><span class="sxs-lookup"><span data-stu-id="6ef83-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="6ef83-129">Если собрание уже началось (кто-либо присоединился): абонент не получит сообщения с вопросом, является ли он организатором. Кроме того, PIN-код запрашиваться не будет. Собрание уже началось, и абонент присоединится к нему.</span><span class="sxs-lookup"><span data-stu-id="6ef83-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="6ef83-130">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="6ef83-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="6ef83-p104">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="6ef83-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6ef83-134">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="6ef83-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="6ef83-135">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ef83-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="6ef83-136">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="6ef83-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="6ef83-137">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="6ef83-137">Related topics</span></span>

[<span data-ttu-id="6ef83-138">Оцените или приобретите аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="6ef83-138">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
