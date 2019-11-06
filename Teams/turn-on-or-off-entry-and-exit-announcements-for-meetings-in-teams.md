---
title: Включение и отключение оповещений о подключении к собраниям и выходе из них в Microsoft Teams
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Сведения о включении и отключении оповещений о подключении к собранию и выходе из него в Microsoft Teams. '
ms.openlocfilehash: 43141190d53cb3c32bd6645f850d2c6d9bb398b0
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2019
ms.locfileid: "37569305"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="5346e-103">Включение и отключение оповещений о подключении к собраниям и выходе из них в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5346e-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="5346e-104">При настройке функции аудиоконференций в Office 365 вы получите мост аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="5346e-104">When you are setting up Audio Conferencing in Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="5346e-105">Мост конференц-связи может содержать один или несколько телефонных номеров, которые люди будут использовать для подключения к собранию Microsoft Teams по телефону.</span><span class="sxs-lookup"><span data-stu-id="5346e-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="5346e-106">Мост конференц-связи отвечает на звонок для пользователя, подключающегося к собранию по телефону.</span><span class="sxs-lookup"><span data-stu-id="5346e-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="5346e-107">Конференц-канал отвечает вызывающему абоненту голосовым приглашением автосекретаря конференции, а затем, в зависимости от параметров, может воспроизводить уведомления, попросить звонящего записать его имя и настроить ПИН-код безопасности.</span><span class="sxs-lookup"><span data-stu-id="5346e-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="5346e-108">Организатору собрания Microsoft Teams выдается ПИН-код, позволяющий начать собрание, если это не удается сделать с помощью приложения Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5346e-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="5346e-109">Однако вы можете настроить систему так, чтобы ПИН-код для начала собрания не требовался.</span><span class="sxs-lookup"><span data-stu-id="5346e-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="5346e-110">Настройка способов присоединения к собранию</span><span class="sxs-lookup"><span data-stu-id="5346e-110">Setting meeting join options</span></span>

<span data-ttu-id="5346e-111">![Значок с логотипом](media/teams-logo-30x30.png) Microsoft Teams, в котором **используется центр администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="5346e-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="5346e-112">На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="5346e-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="5346e-113">В верхней части страницы **Мосты конференц-связи** щелкните **Настройки моста**.</span><span class="sxs-lookup"><span data-stu-id="5346e-113">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="5346e-114">В области **Настройки моста** включите или отключите **уведомления о входе на собрание и выходе из него**.</span><span class="sxs-lookup"><span data-stu-id="5346e-114">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="5346e-115">Этот флажок установлен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5346e-115">This is selected by default.</span></span> <span data-ttu-id="5346e-116">Если его снять, пользователи, уже присоединившиеся к собранию, не будут получать уведомления, когда кто-либо подключается к собранию или покидает его.</span><span class="sxs-lookup"><span data-stu-id="5346e-116">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
4. <span data-ttu-id="5346e-117">В области **Тип объявлений о входе или выходе** выберите **Имена или номера телефонов** или **Тональные сигналы**.</span><span class="sxs-lookup"><span data-stu-id="5346e-117">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>
    
5. <span data-ttu-id="5346e-118">Если вы выбрали **Имена или номера телефонов**, включите или отключите функцию **Попросить абонентов записывать свои имена перед присоединением к собранию**.</span><span class="sxs-lookup"><span data-stu-id="5346e-118">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
6. <span data-ttu-id="5346e-119">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5346e-119">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="5346e-120">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="5346e-120">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="5346e-p104">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="5346e-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5346e-124">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="5346e-124">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="5346e-125">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5346e-125">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="5346e-126">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="5346e-126">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5346e-127">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="5346e-127">Related topics</span></span>

[<span data-ttu-id="5346e-128">Общие вопросы об аудиоконференциях</span><span class="sxs-lookup"><span data-stu-id="5346e-128">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
