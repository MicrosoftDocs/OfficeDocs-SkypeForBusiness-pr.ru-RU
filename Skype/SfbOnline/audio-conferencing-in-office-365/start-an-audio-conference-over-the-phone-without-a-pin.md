---
title: Начало аудиоконференции по телефону без PIN-кода в Skype для бизнеса Online
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
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Узнайте, как разрешить или запретить анонимным абонентам присоединяться к собранию с помощью центра администрирования Skype for Business admin или путем использования сценария PowerShell. '
ms.openlocfilehash: 746e21b7b1a8d15c31dfe11e46ac09edfbb29b99
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23858708"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a><span data-ttu-id="2fddc-103">Начало аудиоконференции по телефону без PIN-кода в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="2fddc-103">Start an Audio Conference over the phone without a PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="2fddc-104">Сведения о начале аудиоконференции без PIN-кода в Microsoft Teams см. в статье [Начало аудиоконференции по телефону без PIN-кода в Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span><span class="sxs-lookup"><span data-stu-id="2fddc-104">For information about starting an Audio Conference without a PIN in Microsoft Teams, see [Start an Audio Conference over the phone without a PIN  in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span></span>

<span data-ttu-id="2fddc-105">Пользователи, присоединяющиеся к собранию, могут оказаться в неприятной ситуации, когда им придется слушать музыку в «зале ожидания» собрания, поскольку организатор собрания Skype для бизнеса еще не начал собрание.</span><span class="sxs-lookup"><span data-stu-id="2fddc-105">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because an organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="2fddc-106">Если организатор собрания вызывает пользователя с целью присоединения к собранию, то по умолчанию для начала собрания требуется ввести PIN-код.</span><span class="sxs-lookup"><span data-stu-id="2fddc-106">If a meeting organizer calls into their meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="2fddc-107">Можно настроить параметры таким образом, чтобы PIN-код не запрашивался при начале собрания, и к собранию мог свободно подключиться любой пользователь.</span><span class="sxs-lookup"><span data-stu-id="2fddc-107">You can set it up so that anyone can dial in to the meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="2fddc-108">Чтобы включить или отключить этот параметр для одного пользователя, используйте центр администрирования Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="2fddc-108">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="2fddc-p102">Если пользователь начал собрание из приложения Skype для бизнеса, ввод PIN-код организатора собрания не требуется. PIN-код требуется только в случае, если организатор собрания присоединяется к собранию по телефону. PIN-код для собраний отправляется пользователям, подключающимся по аудиосвязи, когда им назначена лицензии **аудиоконференции** или для них разрешена аудиоконференция. См. статьи [Отправка пользователям электронных писем с информацией об аудиоконференции](send-an-email-to-a-user-with-their-dial-in-information.md) и [Электронные письма, которые автоматически отправляются пользователям при смене настроек аудиоконференции](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="2fddc-p102">A PIN isn't required for the meeting organizer if someone has started the meeting from a Skype for Business client. A PIN is only required when a meeting organizer joins their meeting over a phone. The PIN for meetings is sent to the dial-in user when they are assigned the **Skype for Business PSTN Conferencing** license or are enabled for dial-in conferencing. See,[Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and[Emails that are automatically sent to users when their dial-in conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="2fddc-113">Разрешение и запрет присоединения анонимных абонентов к собранию</span><span class="sxs-lookup"><span data-stu-id="2fddc-113">Enable or disable anonymous callers from joining a meeting</span></span>
    
1. <span data-ttu-id="2fddc-114">В левой панели навигации **центра администрирования Skype для бизнеса** выберите **Аудиоконференции** > **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="2fddc-114">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span> 
    
2. <span data-ttu-id="2fddc-115">В списке выберите пользователя и на панели действий щелкните **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="2fddc-115">In the list select the user and on the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="2fddc-116">На странице свойств пользователя в разделе **Параметры собрания** установите или снимите флажок **Разрешить абонентам, не прошедшим проверку подлинности, быть первыми пользователями на собрании Если этот параметр не будет выбран, пользователям придется ждать в зале ожидания, пока пользователь, прошедший проверку подлинности, присоединится к собранию**.</span><span class="sxs-lookup"><span data-stu-id="2fddc-116">On the user's properties page, under **Meeting options**, check or uncheck **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="2fddc-117">Нажмите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="2fddc-117">Click **Save**.</span></span> 


    
 <span data-ttu-id="2fddc-118">\*\* Использование Windows PowerShell\*\*</span><span class="sxs-lookup"><span data-stu-id="2fddc-118">**Using Windows Powershell**</span></span>
  
- <span data-ttu-id="2fddc-119">Выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="2fddc-119">Run the following:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="2fddc-120">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="2fddc-120">What else should you know?</span></span>

- <span data-ttu-id="2fddc-121">Если требуется сбросить PIN-код, см. раздел [Сброс PIN-кода для аудиоконференции](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="2fddc-121">If you want to reset the PIN, see [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin.md).</span></span>
    
- <span data-ttu-id="2fddc-122">Если анонимный доступ включен (для начала собрания не требуется вводить PIN-код):</span><span class="sxs-lookup"><span data-stu-id="2fddc-122">If anonymous access or not requiring a PIN to start a meeting is enabled:</span></span>
    
  - <span data-ttu-id="2fddc-123">Если собрание еще не началось (никто не присоединился): абонент получает сообщение с вопросом, является ли он организатором. Если он отвечает утвердительно, он получает запрос на ввод своего PIN-кода. После ввода PIN-кода начинается собрание, и пользователь присоединяется к нему.</span><span class="sxs-lookup"><span data-stu-id="2fddc-123">A caller will be prompted if he's the organizer, if he says yes, he'll be prompted for his PIN after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="2fddc-124">Если собрание уже началось (кто-либо присоединился): абонент не получит сообщения с вопросом, является ли он организатором. Кроме того, PIN-код запрашиваться не будет. Собрание уже началось, и пользователь присоединится к нему.</span><span class="sxs-lookup"><span data-stu-id="2fddc-124">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="2fddc-125">Если анонимный доступ выключен (для начала собрания требуется ввести PIN-код):</span><span class="sxs-lookup"><span data-stu-id="2fddc-125">If anonymous access or not requiring a PIN to start a meeting is disabled:</span></span>
    
  - <span data-ttu-id="2fddc-126">Если собрание еще не началось (никто не присоединился): абонент не получит сообщения с вопросом, является ли он организатором. Кроме того, PIN-код запрашиваться не будет.</span><span class="sxs-lookup"><span data-stu-id="2fddc-126">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="2fddc-127">Поскольку параметр организатора выключен, собрание начинается, и анонимные абоненты присоединятся к нему.</span><span class="sxs-lookup"><span data-stu-id="2fddc-127">Because the setting of the organizer is set to off, the meeting will start and the anonymouscallers will join the meeting.</span></span>
    
  - <span data-ttu-id="2fddc-128">Если собрание уже началось (кто-либо присоединился): абонент не получит сообщения с вопросом, является ли он организатором. Кроме того, PIN-код запрашиваться не будет. Собрание уже началось, и абонент присоединится к нему.</span><span class="sxs-lookup"><span data-stu-id="2fddc-128">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="2fddc-129">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2fddc-129">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="2fddc-130">Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="2fddc-130">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
-  <span data-ttu-id="2fddc-p104">Что касается Windows PowerShell, то Skype для бизнеса online дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="2fddc-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="2fddc-134">Почему следует использовать Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="2fddc-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="2fddc-135">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2fddc-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="2fddc-p105">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="2fddc-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="2fddc-138">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="2fddc-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="2fddc-139">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="2fddc-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="2fddc-140">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="2fddc-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="2fddc-p106">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="2fddc-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="2fddc-143">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="2fddc-143">Related topics</span></span>

[<span data-ttu-id="2fddc-144">Пробная и платная версия аудиоконференций в Office 365</span><span class="sxs-lookup"><span data-stu-id="2fddc-144">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
