---
title: Включение и отключение входе и выходе участников собраний
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Узнайте, как включить запись и выхода из Включение и отключение оповещений в Скайп для бизнеса собрания с помощью Скайп по центру администрирования бизнес. '
ms.openlocfilehash: a9c3788db6b5742b4f2b41961c3843b4939c315b
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings"></a><span data-ttu-id="aa0b4-103">Включение и отключение входе и выходе участников собраний</span><span class="sxs-lookup"><span data-stu-id="aa0b4-103">Turn on or off entry and exit announcements for meetings</span></span>

<span data-ttu-id="aa0b4-104">При установке аудиоконференций в Office 365, вы получите звукового конференц-канала.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-104">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="aa0b4-105">Конференц-канал может содержать один или несколько телефонных номеров, которые пользователи будут использовать вызывает Скайп для бизнеса или группами Майкрософт собрания.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Skype for Business or Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="aa0b4-106">Мост конференц-связи ответы звонка для пользователя, который, к собрания с помощью телефона.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="aa0b4-107">Мост конференц-связи ответы вызывающего абонента с голосовые приглашения участников автосекретарь конференц-связи и затем, в зависимости от параметров, можно воспроизводить уведомления, попросите звонящих записать их имя и настройка безопасности ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="aa0b4-108">ПИН-код предоставляется Скайп для бизнеса или группами Майкрософт Организатор собрания и позволяет им начало собрания, если они не может начать собрание, с помощью Скайп для бизнеса или группами Майкрософт приложения.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-108">A PIN is given to a Skype for Business or Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using a Skype for Business or Microsoft Teams app.</span></span> <span data-ttu-id="aa0b4-109">Тем не менее, устанавливать, чтобы ПИН-код не требуется для запуска собрания.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="aa0b4-110">Настройка параметров присоединения к собранию</span><span class="sxs-lookup"><span data-stu-id="aa0b4-110">Setting meeting join options</span></span>

<span data-ttu-id="aa0b4-111">**Использование групп Майкрософт и Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="aa0b4-111">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="aa0b4-112">В левой области переходов, перейдите к **собраниям** > **Мостов конференции**.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="aa0b4-113">В верхней части страницы **Мостов конференции** нажмите кнопку **Параметры Bridge**.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-113">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="aa0b4-114">В области **Параметры Bridge** включить или отключить **Включить запись собрание и выйти из уведомления, чтобы быть включенным**.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-114">In the **Bridge settings** pane, enable or disable **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="aa0b4-115">Этот флажок установлен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-115">This is selected by default.</span></span> <span data-ttu-id="aa0b4-116">Если снять, пользователей, которые уже присоединились к собранию не уведомления, когда кто-то или выходе из собрания.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-116">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
4. <span data-ttu-id="aa0b4-117">В разделе **объявлений типа входа и выхода**выберите **имена или номера телефонов** или **тона**.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-117">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
5. <span data-ttu-id="aa0b4-118">Включение или отключение **абонентов Ask записать их имя перед присоединением к собранию**.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-118">Enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
6. <span data-ttu-id="aa0b4-119">После внесения изменений нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-119">After you make your changes, click **Apply**.</span></span>

<span data-ttu-id="aa0b4-120">**С помощью Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="aa0b4-120">**Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="aa0b4-121">В окне **Центр администрирования Skype для бизнеса** на панели навигации слева выберите **Конференц-связь с телефонным подключением** > **Параметры моста Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-121">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="aa0b4-122">В разделе **при присоединении к собраниям**установите или снимите флажок **Включить запись собрание и выйти из уведомления, чтобы быть включенным**.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-122">Under **Meeting join experience**, select or clear **Enable meeting entry and exit notifications to be turned on**.</span></span> <span data-ttu-id="aa0b4-123">Этот флажок установлен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-123">This is selected by default.</span></span> <span data-ttu-id="aa0b4-124">Если снять, пользователей, которые уже присоединились к собранию не уведомления, когда кто-то или выходе из собрания.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-124">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
3. <span data-ttu-id="aa0b4-125">В разделе **объявлений типа входа и выхода**выберите **имена или номера телефонов** или **тона**.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-125">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
4. <span data-ttu-id="aa0b4-126">Установите или снимите флажок **задать абонентов записать их имя перед присоединением к собранию**.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-126">Check or uncheck **Ask callers to record their name before joining the meeting**.</span></span>
    
5. <span data-ttu-id="aa0b4-127">После внесения изменений нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-127">After you make your changes, click **Save**.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="aa0b4-128">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa0b4-128">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="aa0b4-129">Для экономии времени или автоматизировать этот процесс, можно использовать командлет [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .</span><span class="sxs-lookup"><span data-stu-id="aa0b4-129">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
-  <span data-ttu-id="aa0b4-p105">Что касается Windows PowerShell, то Skype для бизнеса online дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-p105">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="aa0b4-133">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="aa0b4-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="aa0b4-134">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa0b4-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="aa0b4-135">Windows PowerShell имеет много преимуществ в скорости, простоты и повышения производительности по сравнению только с помощью центра администрирования Office 365, например, когда выполняются изменения параметров для нескольких пользователей за один раз.</span><span class="sxs-lookup"><span data-stu-id="aa0b4-135">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="aa0b4-136">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="aa0b4-136">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="aa0b4-137">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="aa0b4-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="aa0b4-138">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="aa0b4-138">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="aa0b4-139">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="aa0b4-139">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="aa0b4-p107">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="aa0b4-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="aa0b4-142">See also</span><span class="sxs-lookup"><span data-stu-id="aa0b4-142">Related topics</span></span>

[<span data-ttu-id="aa0b4-143">Общие вопросы по аудиоконференциям</span><span class="sxs-lookup"><span data-stu-id="aa0b4-143">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
