---
title: Настройка рабочему столу в группах Майкрософт
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 12/07/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Настройте политику собрания, чтобы дать возможность пользователям совместно использовать свои рабочие столы в чаты групп или собраний
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 422d5fb3a19dad2e14e0cdf54a532b0afc6eed67
ms.sourcegitcommit: ea6ee8ce28e82fcd7c07554c3428ae242d6f04da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/07/2018
ms.locfileid: "27202511"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="5547b-103">Настройка рабочему столу в группах Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5547b-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="5547b-104">Общий доступ к рабочему позволяет пользователям представления экрана или приложения во время собрания или беседы.</span><span class="sxs-lookup"><span data-stu-id="5547b-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="5547b-105">Администраторы могут настраивать экран общего доступа в группами Майкрософт, чтобы дать возможность пользователям совместно использовать весь экран, приложение или файл.</span><span class="sxs-lookup"><span data-stu-id="5547b-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="5547b-106">Можно разрешить пользователям предоставить или запросить управление, разрешить общий доступ к PowerPoint, добавить доску и разрешать общие заметки.</span><span class="sxs-lookup"><span data-stu-id="5547b-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="5547b-107">Можно также настроить ли анонимные или внешних пользователей можно запросить управление общей экрана.</span><span class="sxs-lookup"><span data-stu-id="5547b-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="5547b-108">Чтобы настроить совместное использование рабочего стола, создать новую политику собрания и назначьте его для пользователей, которым вы планируете управлять.</span><span class="sxs-lookup"><span data-stu-id="5547b-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="5547b-109">В группами Майкрософт & Скайп по центру администрирования бизнеса:</span><span class="sxs-lookup"><span data-stu-id="5547b-109">In the Microsoft Teams & Skype for Business Admin Center:</span></span>

1. <span data-ttu-id="5547b-110">Выберите **собраний** > **политик собраний**.</span><span class="sxs-lookup"><span data-stu-id="5547b-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![Выберите политик собраний](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="5547b-112">На странице **Meeting политики** выберите **новую политику**.</span><span class="sxs-lookup"><span data-stu-id="5547b-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![Выберите новую политику](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="5547b-114">Задайте уникальное название вашей политике и введите краткое описание.</span><span class="sxs-lookup"><span data-stu-id="5547b-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="5547b-115">В разделе **общий доступ к содержимому**выберите **режим совместное использование рабочего стола** в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="5547b-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="5547b-116">**Весь экран** — позволяет пользователям совместно использовать их всего рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="5547b-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="5547b-117">**Одно приложение** — позволяет пользователям ограничение совместное использование рабочего стола в одном приложении active.</span><span class="sxs-lookup"><span data-stu-id="5547b-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="5547b-118">**Отключенный** — отключает совместное использование рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="5547b-118">**Disabled** – Turns off screen sharing.</span></span>

    ![Выберите совместного использования режима экрана](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="5547b-120">Отключение следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="5547b-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="5547b-121">**Разрешить участника для предоставления или запросить управление** — позволяет участники группы предоставить или запросить управление докладчика рабочему столу или приложению.</span><span class="sxs-lookup"><span data-stu-id="5547b-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="5547b-122">**Разрешить внешних участников предоставить или запросить управление** — позволяет Гости и внешним пользователям (федеративных) предоставить или запросить управление рабочему столу или приложению выступающего пользователя.</span><span class="sxs-lookup"><span data-stu-id="5547b-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="5547b-123">**Общий доступ к PowerPoint разрешить** - пользователи могут создавать собрания, которые позволяют презентаций PowerPoint и общих.</span><span class="sxs-lookup"><span data-stu-id="5547b-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="5547b-124">**Разрешить Доска** – позволяет пользователям совместно использовать доску.</span><span class="sxs-lookup"><span data-stu-id="5547b-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="5547b-125">**Разрешить общие заметки** – позволяет пользователю принимать Общие заметки.</span><span class="sxs-lookup"><span data-stu-id="5547b-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="5547b-126">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="5547b-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="5547b-127">Использование PowerShell для настройки общего рабочего стола</span><span class="sxs-lookup"><span data-stu-id="5547b-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="5547b-128">Командлет [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) можно также использовать для управления рабочим столам.</span><span class="sxs-lookup"><span data-stu-id="5547b-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="5547b-129">Задайте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="5547b-129">Set the following parameters:</span></span>

- <span data-ttu-id="5547b-130">Описание</span><span class="sxs-lookup"><span data-stu-id="5547b-130">Description</span></span>
- <span data-ttu-id="5547b-131">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="5547b-131">ScreenSharingMode</span></span>
- <span data-ttu-id="5547b-132">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="5547b-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="5547b-133">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="5547b-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="5547b-134">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="5547b-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="5547b-135">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="5547b-135">AllowWhiteboard</span></span>
- <span data-ttu-id="5547b-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="5547b-136">AllowSharedNotes</span></span>

<span data-ttu-id="5547b-137">[Дополнительные сведения об использовании командлета csTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5547b-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

