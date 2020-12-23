---
title: Включите или отключите объявления о входе и выходе для собраний в Teams
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
description: Администратор может узнать, как включить или отключить объявления о входе и выходе на собрании Microsoft Teams.
ms.openlocfilehash: 145965f3ff2737b21c8fcb13c144e07e969fbeef
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372208"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="1313e-103">Включение и отключение оповещений о подключении к собраниям и выходе из них в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1313e-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="1313e-104">При настройке аудиоконференции в Microsoft 365 или Office 365 вы получите мост аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="1313e-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="1313e-105">Мост конференц-связи может содержать один или несколько телефонных номеров, которые люди будут использовать для подключения к собранию Microsoft Teams по телефону.</span><span class="sxs-lookup"><span data-stu-id="1313e-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span>
  
<span data-ttu-id="1313e-106">Мост конференц-связи отвечает на звонок для пользователя, подключающегося к собранию по телефону.</span><span class="sxs-lookup"><span data-stu-id="1313e-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="1313e-107">Конференц-канал отвечает вызывающему абоненту голосовым приглашением автосекретаря конференции, а затем, в зависимости от параметров, может воспроизводить уведомления, попросить звонящего записать его имя и настроить ПИН-код безопасности.</span><span class="sxs-lookup"><span data-stu-id="1313e-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="1313e-108">Организатору собрания Microsoft Teams выдается ПИН-код, позволяющий начать собрание, если это не удается сделать с помощью приложения Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1313e-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="1313e-109">Однако вы можете настроить систему так, чтобы ПИН-код для начала собрания не требовался.</span><span class="sxs-lookup"><span data-stu-id="1313e-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="1313e-110">Настройка способов присоединения к собранию</span><span class="sxs-lookup"><span data-stu-id="1313e-110">Setting meeting join options</span></span>

<span data-ttu-id="1313e-111">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="1313e-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="1313e-112">Вносить эти изменения может только администратор служб Teams.</span><span class="sxs-lookup"><span data-stu-id="1313e-112">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="1313e-113">См. [статью "Использование](https://docs.microsoft.com/microsoftteams/using-admin-roles) ролей администратора Teams для управления Teams", чтобы ознакомиться с получением ролей и разрешений администраторов.</span><span class="sxs-lookup"><span data-stu-id="1313e-113">See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="1313e-114">Войдите в Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="1313e-114">Log in to the admin center.</span></span>

2. <span data-ttu-id="1313e-115">На панели навигации слева перейдите в раздел **Собрания** > **Мосты конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="1313e-115">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span>

3. <span data-ttu-id="1313e-116">В верхней части страницы **Мосты конференц-связи** щелкните **Настройки моста**.</span><span class="sxs-lookup"><span data-stu-id="1313e-116">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span>

4. <span data-ttu-id="1313e-117">В области **Настройки моста** включите или отключите **уведомления о входе на собрание и выходе из него**.</span><span class="sxs-lookup"><span data-stu-id="1313e-117">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="1313e-118">Этот флажок установлен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1313e-118">This is selected by default.</span></span> <span data-ttu-id="1313e-119">Если его снять, пользователи, уже присоединившиеся к собранию, не будут получать уведомления, когда кто-либо подключается к собранию или покидает его.</span><span class="sxs-lookup"><span data-stu-id="1313e-119">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>

5. <span data-ttu-id="1313e-120">В разделе **Тип уведомлений о входе и выходе** выберите **Имена или номера телефонов** или **Гудки**.</span><span class="sxs-lookup"><span data-stu-id="1313e-120">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1313e-121">По умолчанию внешние участники не могут видеть телефонные номера участников телефонного звонка.</span><span class="sxs-lookup"><span data-stu-id="1313e-121">By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="1313e-122">Если необходимо соблюдать конфиденциальность этих номеров телефонов, выберите **Тональные сигналы** для пункта **Тип оповещения входа/выхода** (это позволяет предотвратить прочтение номеров приложением Teams).</span><span class="sxs-lookup"><span data-stu-id="1313e-122">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span>

6. <span data-ttu-id="1313e-123">Если вы выбрали **Имена или номера телефонов**, включите или отключите функцию **Попросить абонентов записывать свои имена перед присоединением к собранию**.</span><span class="sxs-lookup"><span data-stu-id="1313e-123">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>

7. <span data-ttu-id="1313e-124">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1313e-124">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="1313e-125">Хотите узнать больше о Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1313e-125">Want to know more about Windows PowerShell</span></span>

<span data-ttu-id="1313e-126">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="1313e-126">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="1313e-127">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="1313e-127">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="1313e-128">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="1313e-128">To get started with Windows PowerShell, see these topics:</span></span>

- [<span data-ttu-id="1313e-129">Зачем нужно использовать Microsoft 365 или Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="1313e-129">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- [<span data-ttu-id="1313e-130">Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1313e-130">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

<span data-ttu-id="1313e-131">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="1313e-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1313e-132">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="1313e-132">Related topics</span></span>

[<span data-ttu-id="1313e-133">Общие вопросы об аудиоконференциях</span><span class="sxs-lookup"><span data-stu-id="1313e-133">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
