---
title: Совместный доступ к рабочему столу в Microsoft Teams
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Настройте политику собрания, чтобы дать возможность пользователям совместно использовать свои рабочие столы в чаты групп или собраний
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d0434804e7d0ec57ff4470fd8e9af23b73f8179f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198402"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="3e126-103">Совместный доступ к рабочему столу в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3e126-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="3e126-104">Общий доступ к рабочему позволяет пользователям представления экрана или приложения во время собрания или беседы.</span><span class="sxs-lookup"><span data-stu-id="3e126-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="3e126-105">Администраторы могут настраивать экран общего доступа в группами Майкрософт, чтобы дать возможность пользователям совместно использовать весь экран, приложение или файл.</span><span class="sxs-lookup"><span data-stu-id="3e126-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="3e126-106">Можно разрешить пользователям предоставить или запросить управление, разрешить общий доступ к PowerPoint, добавить доску и разрешать общие заметки.</span><span class="sxs-lookup"><span data-stu-id="3e126-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="3e126-107">Можно также настроить ли анонимные или внешних пользователей можно запросить управление общей экрана.</span><span class="sxs-lookup"><span data-stu-id="3e126-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="3e126-108">Чтобы настроить совместное использование рабочего стола, создать новую политику собрания и назначьте его для пользователей, которым вы планируете управлять.</span><span class="sxs-lookup"><span data-stu-id="3e126-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="3e126-109">**В центре администрирования группами Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="3e126-109">**In the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="3e126-110">Выберите **собраний** > **политик собраний**.</span><span class="sxs-lookup"><span data-stu-id="3e126-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![Выберите политик собраний](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="3e126-112">На странице **Meeting политики** выберите **новую политику**.</span><span class="sxs-lookup"><span data-stu-id="3e126-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![Выберите новую политику](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="3e126-114">Задайте уникальное название вашей политике и введите краткое описание.</span><span class="sxs-lookup"><span data-stu-id="3e126-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="3e126-115">В разделе **общий доступ к содержимому**выберите **режим совместное использование рабочего стола** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="3e126-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="3e126-116">**Весь экран** — позволяет пользователям совместно использовать их всего рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="3e126-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="3e126-117">**Одно приложение** — позволяет пользователям ограничение совместное использование рабочего стола в одном приложении active.</span><span class="sxs-lookup"><span data-stu-id="3e126-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="3e126-118">**Отключенный** — отключает совместное использование рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="3e126-118">**Disabled** – Turns off screen sharing.</span></span>

    ![Выберите совместного использования режима экрана](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="3e126-120">Отключение следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="3e126-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="3e126-121">**Разрешить участника для предоставления или запросить управление** — позволяет участники группы предоставить или запросить управление докладчика рабочему столу или приложению.</span><span class="sxs-lookup"><span data-stu-id="3e126-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="3e126-122">**Разрешить внешних участников предоставить или запросить управление** — позволяет Гости и внешним пользователям (федеративных) предоставить или запросить управление рабочему столу или приложению выступающего пользователя.</span><span class="sxs-lookup"><span data-stu-id="3e126-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="3e126-123">**Общий доступ к PowerPoint разрешить** - пользователи могут создавать собрания, которые позволяют презентаций PowerPoint и общих.</span><span class="sxs-lookup"><span data-stu-id="3e126-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="3e126-124">**Разрешить Доска** – позволяет пользователям совместно использовать доску.</span><span class="sxs-lookup"><span data-stu-id="3e126-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="3e126-125">**Разрешить общие заметки** – позволяет пользователю принимать Общие заметки.</span><span class="sxs-lookup"><span data-stu-id="3e126-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="3e126-126">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3e126-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="3e126-127">Использование PowerShell для настройки общего рабочего стола</span><span class="sxs-lookup"><span data-stu-id="3e126-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="3e126-128">Командлет [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) можно также использовать для управления рабочим столам.</span><span class="sxs-lookup"><span data-stu-id="3e126-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="3e126-129">Задайте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="3e126-129">Set the following parameters:</span></span>

- <span data-ttu-id="3e126-130">Описание</span><span class="sxs-lookup"><span data-stu-id="3e126-130">Description</span></span>
- <span data-ttu-id="3e126-131">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="3e126-131">ScreenSharingMode</span></span>
- <span data-ttu-id="3e126-132">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="3e126-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="3e126-133">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="3e126-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="3e126-134">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="3e126-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="3e126-135">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="3e126-135">AllowWhiteboard</span></span>
- <span data-ttu-id="3e126-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="3e126-136">AllowSharedNotes</span></span>

<span data-ttu-id="3e126-137">[Дополнительные сведения об использовании командлета csTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3e126-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

