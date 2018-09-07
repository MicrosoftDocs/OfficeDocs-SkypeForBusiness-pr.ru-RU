---
title: Начало конференции аудио по телефону без ПИН-кода в группах Майкрософт
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Узнайте, как для включения или отключения анонимных абонентов из присоединение к собранию из центра администрирования группы. '
ms.openlocfilehash: f85cd3e2ae0c1f87810f5b5312ba8bc9dc9d34c9
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861045"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="4e3e2-103">Начало конференции аудио по телефону без ПИН-кода в группах Майкрософт</span><span class="sxs-lookup"><span data-stu-id="4e3e2-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="4e3e2-104">Это может быть неудобства для пользователей, которые телефонное подключение к собранию, в течение которого будут храниться в зал собраний, прослушивание музыки, так как организатор собрания групп Майкрософт не запущена собрания.</span><span class="sxs-lookup"><span data-stu-id="4e3e2-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="4e3e2-105">Если организатор собрания вызывает к собранию по умолчанию, ПИН-код должен начать собрание.</span><span class="sxs-lookup"><span data-stu-id="4e3e2-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="4e3e2-106">Можно настроить его, чтобы любой пользователь может звонить на собрание и не будут запрашиваться ПИН-код начать собрание.</span><span class="sxs-lookup"><span data-stu-id="4e3e2-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="4e3e2-107">Центр администрирования можно использовать для включения или отключения этот параметр для одного пользователя.</span><span class="sxs-lookup"><span data-stu-id="4e3e2-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="4e3e2-108">Если кто-то запущен собрания из приложения группами Майкрософт, ПИН-код не требуется для организатора собрания.</span><span class="sxs-lookup"><span data-stu-id="4e3e2-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="4e3e2-109">ПИН-код только в том случае требуется при Организатор собрания присоединился к их собрание по телефону.</span><span class="sxs-lookup"><span data-stu-id="4e3e2-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="4e3e2-110">ПИН-код для собраний отправляется звука пользователя при назначаются лицензии **Аудиоконференций** и включена поддержка аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="4e3e2-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="4e3e2-111">В разделе [Отправить сообщение электронной почты для пользователя с помощью их аудиоконференции сведения](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) и [сообщения электронной почты, которые отправляются пользователям при изменении их параметров звука конференц-связи, автоматически](emails-sent-to-users-when-their-settings-change-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4e3e2-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="4e3e2-112">Разрешение и запрет присоединения анонимных абонентов к собранию</span><span class="sxs-lookup"><span data-stu-id="4e3e2-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="4e3e2-113">![команды логотип 30x30.png](media/teams-logo-30x30.png) **с помощью групп Майкрософт и Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="4e3e2-113">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="4e3e2-114">В левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="4e3e2-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="4e3e2-115">Выберите пользователя в списке и нажмите кнопку **Изменить** в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="4e3e2-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="4e3e2-116">Рядом с пунктом **Звук конференц-связи**нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="4e3e2-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="4e3e2-117">На левой панели **Звук конференц-связи** включить или отключить, **не прошедшим проверку подлинности абонентов может быть первый, кто участие в собрании**.</span><span class="sxs-lookup"><span data-stu-id="4e3e2-117">In the **Audio Conferencing** pane, enable or disable **Unauthenticated callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="4e3e2-118">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="4e3e2-118">Click **Save**.</span></span> 

<span data-ttu-id="4e3e2-119">**С помощью Windows Powershell**</span><span class="sxs-lookup"><span data-stu-id="4e3e2-119">**Using Windows Powershell**</span></span>
  
<span data-ttu-id="4e3e2-120">В разделе [Справочник по Microsoft команды PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="4e3e2-120">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="4e3e2-121">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="4e3e2-121">What else should you know?</span></span>

- <span data-ttu-id="4e3e2-122">Если требуется сбросить ПИН-код, ознакомьтесь со [Сброс ПИН-кода конференц-связи звука](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4e3e2-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="4e3e2-123">Если анонимный доступ или не требует ПИН-код начать собрание:</span><span class="sxs-lookup"><span data-stu-id="4e3e2-123">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="4e3e2-124">Если собрание еще не запущена (нет ни один собрания еще): Звонящий будет запрос, если он является организатором; Если Рид Да, он будет запрашиваться ПИН-код и после он ввода ПИН-код, будет запущен процесс собрания и пользователь будет присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="4e3e2-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="4e3e2-125">Если собрание уже запущена (кто-либо уже собрания): нет необходимости абонента, если он является организатором, и он никогда не будет выведен запрос для ПИН-кода; собрания уже запущена, а Звонящий будет присоединиться к ней.</span><span class="sxs-lookup"><span data-stu-id="4e3e2-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="4e3e2-126">Если анонимный доступ или не требует ПИН-код начать собрание, отключен:</span><span class="sxs-lookup"><span data-stu-id="4e3e2-126">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="4e3e2-127">Если собрание еще не запущена (нет ни один собрания еще): нет необходимости абонента, если она является организатором, и она никогда не будет выведен запрос для ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="4e3e2-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="4e3e2-128">Так как параметр организатора — это значение отключено, будет запущен процесс собрания и анонимных абонентов будет присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="4e3e2-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="4e3e2-129">Если собрание уже запущена (кто-либо уже собрания): нет необходимости абонента, если она является организатором, и она никогда не будет выведен запрос для ПИН-кода, собрания уже запущена и Звонящий будет присоединиться к ней.</span><span class="sxs-lookup"><span data-stu-id="4e3e2-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4e3e2-130">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="4e3e2-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="4e3e2-p104">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="4e3e2-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4e3e2-134">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="4e3e2-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="4e3e2-135">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e3e2-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="4e3e2-136">Дополнительные сведения о Windows PowerShell, [Справочник по Microsoft команды PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="4e3e2-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4e3e2-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="4e3e2-137">Related topics</span></span>

[<span data-ttu-id="4e3e2-138">Пробная и платная аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="4e3e2-138">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
