---
title: Изменение настроек для моста аудиоконференций
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: Изменение параметров моста аудиоконференций, включая уведомления о входе и выходе, воспроизведения имен и номеров телефонов, тонов и запрос на запись имени.
ms.openlocfilehash: 7609ac7639012eb29d6d6cab4b482c1502d27c51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102646"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="d901a-103">Изменение настроек для моста аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="d901a-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="d901a-104">При настройке аудиоконференций в Microsoft 365 или Office 365 вы будете получать телефонные номера пользователей от так называемого моста аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="d901a-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="d901a-105">Мост конференц-связи может содержать один или несколько телефонных номеров.</span><span class="sxs-lookup"><span data-stu-id="d901a-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="d901a-106">Эти номера телефонов используются, когда звонят на собрание по телефону.</span><span class="sxs-lookup"><span data-stu-id="d901a-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="d901a-107">Номер телефона будет включен в нижнюю часть Skype для бизнеса или Microsoft Teams приглашения на собрание.</span><span class="sxs-lookup"><span data-stu-id="d901a-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="d901a-108">Мост для проведения собраний отвечает на звонок и выводит вызывающего звоняющего голосовые подсказки с помощью автозавершена, а затем в зависимости от параметров может получать уведомления, просить звонив записать свое имя и управлять настройками ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="d901a-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="d901a-109">ПИН-ны даются организаторам собраний, чтобы они могли начинать собрания, если они не используют Skype для бизнеса или Microsoft Teams приложение.</span><span class="sxs-lookup"><span data-stu-id="d901a-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="d901a-110">ПИН-код необходим только организатору собрания, Skype для бизнеса или Microsoft Teams еще не начал собрание.</span><span class="sxs-lookup"><span data-stu-id="d901a-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="d901a-111">Если кто-то звонит на собрание, организатору собрания требуется ПИН-код, чтобы начать собрание.</span><span class="sxs-lookup"><span data-stu-id="d901a-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) <span data-ttu-id="d901a-113">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d901a-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="d901a-114">На левой навигации перейдите к **мосту Конференц-связь**  >  **собраний**.</span><span class="sxs-lookup"><span data-stu-id="d901a-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="d901a-115">В верхней части страницы **Мост конференции** щелкните **Параметры моста**.</span><span class="sxs-lookup"><span data-stu-id="d901a-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="d901a-116">В области **Параметры моста** выберите:</span><span class="sxs-lookup"><span data-stu-id="d901a-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="d901a-117">**Уведомления о входе и выходе из собрания** Если отключить эту возможность, пользователи, которые уже присоединились к собранию, не будут уведомлены о том, что кто-то входит в собрание или покидает его.</span><span class="sxs-lookup"><span data-stu-id="d901a-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="d901a-118">Включив уведомления о **входе и выходе из** собрания, вы можете выбрать указанные здесь параметры.</span><span class="sxs-lookup"><span data-stu-id="d901a-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="d901a-119">**Имена или номера телефонов** Когда пользователь присоединяется к собранию по телефону, его номер телефона будет разыт.</span><span class="sxs-lookup"><span data-stu-id="d901a-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="d901a-120">**Тоны** Когда пользователи присоединяются к собранию по телефонной сети, при их подзвучит звуковой сигнал.</span><span class="sxs-lookup"><span data-stu-id="d901a-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="d901a-121">**Попросите звоняющих записать свое имя перед присоединением к собранию** Если отключить эту возможность, перед тем как присоединяться к собранию, вызывателям не будет предложено записать свое имя.</span><span class="sxs-lookup"><span data-stu-id="d901a-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="d901a-122">Чтобы установить длину ПИН-кода для собраний, в списке Длина  ПИН-кода выберите нужное число цифр.</span><span class="sxs-lookup"><span data-stu-id="d901a-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="d901a-123">Чтобы указать, отправлять ли пользователям электронную почту, включите или отключите функцию Автоматическое отправка сообщений пользователям в случае изменения конфигурации **аудиоконференции.**</span><span class="sxs-lookup"><span data-stu-id="d901a-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="d901a-124">Дополнительные сведения см. в сообщениях электронной почты, которые автоматически отправляются пользователям при изменении их параметров аудиоконференции в Microsoft Teams или Сообщения электронной почты, отправленные пользователям при изменении их параметров в [Skype для бизнеса Online.](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) [](emails-sent-to-users-when-their-settings-change-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="d901a-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="d901a-125">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="d901a-125">Click **Save**.</span></span> 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="d901a-126">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d901a-126">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="d901a-127">Чтобы сэкономить время или автоматизировать этот процесс, можно использовать [cmdlet Set-CsDialinConferencingBridge.](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge)</span><span class="sxs-lookup"><span data-stu-id="d901a-127">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) cmdlet.</span></span>
    
- <span data-ttu-id="d901a-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="d901a-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="d901a-129">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365 с помощью единого администрирования, который упростит выполнение повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="d901a-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="d901a-130">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="d901a-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d901a-131">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="d901a-131">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="d901a-132">[Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="d901a-132">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="d901a-133">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="d901a-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="d901a-134">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="d901a-134">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="d901a-135">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="d901a-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="d901a-136">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="d901a-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="d901a-137">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="d901a-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > <span data-ttu-id="d901a-p107">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="d901a-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d901a-140">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d901a-140">Related topics</span></span>

[<span data-ttu-id="d901a-141">Настройка аудиоконференций для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d901a-141">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="d901a-142">Настройка аудиоконференций для Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="d901a-142">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)