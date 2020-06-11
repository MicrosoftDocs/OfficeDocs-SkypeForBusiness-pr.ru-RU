---
title: Предоставление пользователям возможности записать свое имя для собрания
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: Сведения о том, как разрешить или запретить пользователям записывать свои имена при присоединении к собранию в Microsoft Teams.
ms.openlocfilehash: d7cab4fca4ad3e7732704da9837522d51314061d
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691585"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a><span data-ttu-id="9bee9-103">Предоставление пользователям возможности записи собственного имени при присоединении к собранию в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9bee9-103">Enable users to record their name when they join a meeting in Microsoft Teams</span></span>

<span data-ttu-id="9bee9-p101">При настройке голосовой конференции в Microsoft 365 или Office 365 вы будете получать номера телефонов и что называется мостом для голосовой связи. Мост конференц-связи может содержать один или несколько номеров телефонов, которые могут быть назначенными или общим номером телефона.</span><span class="sxs-lookup"><span data-stu-id="9bee9-p101">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers and what is called an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="9bee9-p102">Мост конференц-связи обеспечивает ответ на вызов пользователя, который присоединяется к собранию с телефона. Мост конференц-связи отвечает вызывающей стороне голосовыми подсказками с помощью автосекретаря, а затем, в зависимости от настроек, может воспроизвести уведомления, попросить вызывающую сторону записать свое имя и настроить ПИН-код безопасности для организаторов собрания. ПИН-коды предоставляются организаторам собраний. Организаторы могут начать собрание, введя ПИН-код. Однако собрание можно настроить таким образом, чтобы ПИН-код не требовался.</span><span class="sxs-lookup"><span data-stu-id="9bee9-p102">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers. PINs are given to meeting organizers to allow them to start a meeting. However, you can set it up so a PIN isn't required to start a meeting.</span></span>

  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="9bee9-110">Выбор необходимости записи имени вызывающего абонента</span><span class="sxs-lookup"><span data-stu-id="9bee9-110">Set whether callers should record their name</span></span>

<span data-ttu-id="9bee9-111">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="9bee9-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="9bee9-112">На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="9bee9-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="9bee9-113">В верхней части страницы **мосты** выберите пункт **Параметры моста**.</span><span class="sxs-lookup"><span data-stu-id="9bee9-113">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="9bee9-114">Включение и отключение **уведомлений о вводе и завершении собрания**.</span><span class="sxs-lookup"><span data-stu-id="9bee9-114">Enable or disable **Meeting entry and exit notifications**.</span></span>

4. <span data-ttu-id="9bee9-115">Если вы хотите включить уведомления, выберите **имена или номера телефонов** в разделе **тип извещения вход/выход**, а затем снова включите команду **Ask, чтобы записать свое имя, прежде чем присоединиться к собранию.**</span><span class="sxs-lookup"><span data-stu-id="9bee9-115">If enabling notifications, choose **Names or phone numbers** under **Entry/exit announcement type**, and then turn on **Ask callers to record their name before joining a meeting.**</span></span>

6. <span data-ttu-id="9bee9-116">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="9bee9-116">Click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="9bee9-117">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="9bee9-117">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="9bee9-118">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="9bee9-118">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9bee9-119">С помощью Windows PowerShell можно управлять Microsoft 365 или Office 365, используя единую точку администрирования, которая позволяет упростить повседневную работу, если у вас есть несколько задач.</span><span class="sxs-lookup"><span data-stu-id="9bee9-119">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="9bee9-120">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="9bee9-120">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9bee9-121">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="9bee9-121">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="9bee9-122">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9bee9-122">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="9bee9-123">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="9bee9-123">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9bee9-124">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="9bee9-124">Related topics</span></span>

[<span data-ttu-id="9bee9-125">Попробуйте или купите голосовую конференцию</span><span class="sxs-lookup"><span data-stu-id="9bee9-125">Try or purchase Audio Conferencing</span></span>](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
