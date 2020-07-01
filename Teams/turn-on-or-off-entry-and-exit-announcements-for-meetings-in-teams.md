---
title: Включение и отключение объявлений входа и выхода для собраний в Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
- seo-marvel-apr2020
description: Администратор может узнать о том, как включать и выключать объявления входа и выхода в собрании Microsoft Teams.
ms.openlocfilehash: ae2e8936b3fe0dbac0ba0d6ad7bfad3ab2e322ef
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938558"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="b0ae8-103">Включение и отключение оповещений о подключении к собраниям и выходе из них в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b0ae8-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="b0ae8-104">При настройке голосовой конференции в Microsoft 365 или Office 365 вы получаете мост для голосовой конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="b0ae8-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="b0ae8-105">Мост конференц-связи может содержать один или несколько телефонных номеров, которые люди будут использовать для подключения к собранию Microsoft Teams по телефону.</span><span class="sxs-lookup"><span data-stu-id="b0ae8-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="b0ae8-106">Мост конференц-связи отвечает на звонок для пользователя, подключающегося к собранию по телефону.</span><span class="sxs-lookup"><span data-stu-id="b0ae8-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="b0ae8-107">Конференц-канал отвечает вызывающему абоненту голосовым приглашением автосекретаря конференции, а затем, в зависимости от параметров, может воспроизводить уведомления, попросить звонящего записать его имя и настроить ПИН-код безопасности.</span><span class="sxs-lookup"><span data-stu-id="b0ae8-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="b0ae8-108">Организатору собрания Microsoft Teams выдается ПИН-код, позволяющий начать собрание, если это не удается сделать с помощью приложения Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b0ae8-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="b0ae8-109">Однако вы можете настроить систему так, чтобы ПИН-код для начала собрания не требовался.</span><span class="sxs-lookup"><span data-stu-id="b0ae8-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="b0ae8-110">Настройка способов присоединения к собранию</span><span class="sxs-lookup"><span data-stu-id="b0ae8-110">Setting meeting join options</span></span>

<span data-ttu-id="b0ae8-111">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="b0ae8-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="b0ae8-112">Вы должны быть администратором, чтобы внести эти изменения.</span><span class="sxs-lookup"><span data-stu-id="b0ae8-112">You must be an admin to make these changes.</span></span>

1. <span data-ttu-id="b0ae8-113">Войдите в центр администрирования по адресу  <a href="https://admin.teams.microsoft.com" target="_blank">https://admin.teams.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="b0ae8-113">Log in to the admin center at <a href="https://admin.teams.microsoft.com" target="_blank">https://admin.teams.microsoft.com</a>.</span></span>

2. <span data-ttu-id="b0ae8-114">На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="b0ae8-114">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

3. <span data-ttu-id="b0ae8-115">В верхней части страницы **Мосты конференц-связи** щелкните **Настройки моста**.</span><span class="sxs-lookup"><span data-stu-id="b0ae8-115">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

4. <span data-ttu-id="b0ae8-116">В области **Настройки моста** включите или отключите **уведомления о входе на собрание и выходе из него**.</span><span class="sxs-lookup"><span data-stu-id="b0ae8-116">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="b0ae8-117">Этот флажок установлен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b0ae8-117">This is selected by default.</span></span> <span data-ttu-id="b0ae8-118">Если его снять, пользователи, уже присоединившиеся к собранию, не будут получать уведомления, когда кто-либо подключается к собранию или покидает его.</span><span class="sxs-lookup"><span data-stu-id="b0ae8-118">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
5. <span data-ttu-id="b0ae8-119">В разделе **Тип уведомлений о входе и выходе** выберите **Имена или номера телефонов** или **Гудки**.</span><span class="sxs-lookup"><span data-stu-id="b0ae8-119">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b0ae8-120">По умолчанию внешние участники не могут видеть номера телефонов абонентов.</span><span class="sxs-lookup"><span data-stu-id="b0ae8-120">By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="b0ae8-121">Если необходимо соблюдать конфиденциальность этих номеров телефонов, выберите \*\*Тональные сигналы \*\* для пункта **Тип оповещения входа/выхода** (это позволяет предотвратить прочтение номеров приложением Teams).</span><span class="sxs-lookup"><span data-stu-id="b0ae8-121">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span>
    
6. <span data-ttu-id="b0ae8-122">Если вы выбрали **Имена или номера телефонов**, включите или отключите функцию **Попросить абонентов записывать свои имена перед присоединением к собранию**.</span><span class="sxs-lookup"><span data-stu-id="b0ae8-122">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
7. <span data-ttu-id="b0ae8-123">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="b0ae8-123">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="b0ae8-124">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="b0ae8-124">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="b0ae8-125">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="b0ae8-125">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="b0ae8-126">С помощью Windows PowerShell можно управлять Microsoft 365 или Office 365, используя единую точку администрирования, которая позволяет упростить повседневную работу, если у вас есть несколько задач.</span><span class="sxs-lookup"><span data-stu-id="b0ae8-126">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="b0ae8-127">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="b0ae8-127">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b0ae8-128">Зачем использовать Microsoft 365 или Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0ae8-128">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="b0ae8-129">Лучшие способы управления Microsoft 365 и Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0ae8-129">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="b0ae8-130">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="b0ae8-130">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b0ae8-131">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="b0ae8-131">Related topics</span></span>

[<span data-ttu-id="b0ae8-132">Общие вопросы об аудиоконференциях</span><span class="sxs-lookup"><span data-stu-id="b0ae8-132">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
