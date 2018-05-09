---
title: Начало конференции аудио по телефону без ПИН-кода
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: 4deb415e9fd7154d72b7d598bcc5dfb8eabed6ed
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin"></a><span data-ttu-id="7ec32-103">Начало конференции аудио по телефону без ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="7ec32-103">Start an Audio Conference over the phone without a PIN</span></span>

<span data-ttu-id="7ec32-104">Это может быть неудобства для пользователей, которые телефонное подключение к собранию, в течение которого будут храниться в зал собраний, прослушивание музыки, так как Скайп для бизнеса или группами Майкрософт Организатор собрания еще не запущена собрания.</span><span class="sxs-lookup"><span data-stu-id="7ec32-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business or Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="7ec32-105">Если организатор собрания вызывает к собранию по умолчанию, ПИН-код должен начать собрание.</span><span class="sxs-lookup"><span data-stu-id="7ec32-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="7ec32-106">Можно настроить его, чтобы любой пользователь может звонить на собрание и не будут запрашиваться ПИН-код начать собрание.</span><span class="sxs-lookup"><span data-stu-id="7ec32-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="7ec32-107">Чтобы включить или отключить этот параметр для одного пользователя, используйте центр администрирования Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7ec32-107">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="7ec32-108">Если кто-то запущен собрания из Скайп для бизнеса или группами Майкрософт приложения ПИН-код не требуется для организатора собрания.</span><span class="sxs-lookup"><span data-stu-id="7ec32-108">A PIN isn't required for the meeting organizer if someone has started the meeting from a Skype for Business or Microsoft Teams app.</span></span> <span data-ttu-id="7ec32-109">ПИН-код только в том случае требуется при Организатор собрания присоединился к их собрание по телефону.</span><span class="sxs-lookup"><span data-stu-id="7ec32-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="7ec32-110">ПИН-код для собраний отправляется звука пользователя при назначаются лицензии **Аудиоконференций** и включена поддержка аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="7ec32-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="7ec32-111">В разделе [Отправить сообщение электронной почты для пользователя с помощью их аудиоконференции сведения](send-an-email-to-a-user-with-their-dial-in-information.md) и [сообщения электронной почты, которые отправляются пользователям при изменении их параметров звука конференц-связи, автоматически](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="7ec32-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="7ec32-112">Разрешение и запрет присоединения анонимных абонентов к собранию</span><span class="sxs-lookup"><span data-stu-id="7ec32-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="7ec32-113">![команды логотип 30x30.png](../images/teams-logo-30x30.png) **с помощью групп Майкрософт и Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="7ec32-113">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="7ec32-114">В левой панели навигации щелкните **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="7ec32-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="7ec32-115">Выберите пользователя в списке и нажмите кнопку **Изменить** в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="7ec32-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="7ec32-116">Щелкните меню рядом с пунктом **Мостов конференции**и нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="7ec32-116">Click the menu next to **Conference Bridges**, and then click **Edit**.</span></span>

4. <span data-ttu-id="7ec32-117">В области **конференции bridge поставщика** Включение или отключение **непроверенный Разрешить звонящим быть первого людей в ходе собрания. Если не, затем они будет ждать в зале ожидания прошедшего проверку подлинности пользователь присоединился к**.</span><span class="sxs-lookup"><span data-stu-id="7ec32-117">In the **Conference bridge provider** pane, enable or disable **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="7ec32-118">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="7ec32-118">Click **Apply**.</span></span> 

<span data-ttu-id="7ec32-119">![sfb логотип 30x30.png](../images/sfb-logo-30x30.png) **с помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="7ec32-119">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="7ec32-120">В **Скайп по центру администрирования бизнеса**, в левой области переходов, перейдите к **аудиоконференции** > **пользователей**.</span><span class="sxs-lookup"><span data-stu-id="7ec32-120">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
2. <span data-ttu-id="7ec32-121">В списке выберите пользователя и в области действий нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="7ec32-121">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="7ec32-122">На странице свойств пользователя в разделе **параметры собрания**установите или снимите **непроверенный Разрешить звонящим быть первого людей в ходе собрания. Если не, затем они будет ждать в зале ожидания прошедшего проверку подлинности пользователь присоединился к**.</span><span class="sxs-lookup"><span data-stu-id="7ec32-122">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="7ec32-123">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="7ec32-123">Click **Save**.</span></span> 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
    
 <span data-ttu-id="7ec32-124">**С помощью Windows Powershell**</span><span class="sxs-lookup"><span data-stu-id="7ec32-124">**Using Windows Powershell**</span></span>
  
- <span data-ttu-id="7ec32-125">Выполните следующее:</span><span class="sxs-lookup"><span data-stu-id="7ec32-125">Run the following:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="7ec32-126">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="7ec32-126">What else should you know?</span></span>

- <span data-ttu-id="7ec32-127">Если требуется сбросить ПИН-код, ознакомьтесь со [Сброс ПИН-кода конференц-связи звука](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="7ec32-127">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
- <span data-ttu-id="7ec32-128">Если анонимный доступ или не требует ПИН-код начать собрание:</span><span class="sxs-lookup"><span data-stu-id="7ec32-128">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="7ec32-129">Если собрание еще не запущена (нет ни один собрания еще): Звонящий будет запрос, если он является организатором; Если Рид Да, он будет запрашиваться ПИН-код и после он ввода ПИН-код, будет запущен процесс собрания и пользователь будет присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="7ec32-129">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="7ec32-130">Если собрание уже запущена (кто-либо уже собрания): нет необходимости абонента, если он является организатором, и он никогда не будет выведен запрос для ПИН-кода; собрания уже запущена, а Звонящий будет присоединиться к ней.</span><span class="sxs-lookup"><span data-stu-id="7ec32-130">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="7ec32-131">Если анонимный доступ или не требует ПИН-код начать собрание, отключен:</span><span class="sxs-lookup"><span data-stu-id="7ec32-131">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="7ec32-132">Если собрание еще не запущена (нет ни один собрания еще): нет необходимости абонента, если она является организатором, и она никогда не будет выведен запрос для ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="7ec32-132">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="7ec32-133">Так как параметр организатора — это значение отключено, будет запущен процесс собрания и анонимных абонентов будет присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="7ec32-133">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="7ec32-134">Если собрание уже запущена (кто-либо уже собрания): нет необходимости абонента, если она является организатором, и она никогда не будет выведен запрос для ПИН-кода, собрания уже запущена и Звонящий будет присоединиться к ней.</span><span class="sxs-lookup"><span data-stu-id="7ec32-134">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="7ec32-135">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ec32-135">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="7ec32-136">Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="7ec32-136">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
-  <span data-ttu-id="7ec32-p104">Что касается Windows PowerShell, то Skype для бизнеса online дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="7ec32-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7ec32-140">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="7ec32-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="7ec32-141">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ec32-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="7ec32-p105">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="7ec32-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="7ec32-144">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="7ec32-144">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="7ec32-145">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="7ec32-145">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="7ec32-146">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="7ec32-146">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="7ec32-p106">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="7ec32-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7ec32-149">See also</span><span class="sxs-lookup"><span data-stu-id="7ec32-149">Related topics</span></span>

[<span data-ttu-id="7ec32-150">Пробная и платная аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="7ec32-150">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
