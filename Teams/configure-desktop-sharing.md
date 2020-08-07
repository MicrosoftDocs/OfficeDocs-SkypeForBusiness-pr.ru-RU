---
title: Настройка общего доступа к рабочему столу в Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
description: Сведения о том, как настроить политику собраний, чтобы позволить пользователям делиться рабочими столами в чате и собраниях Teams.
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 857c9c4d830cb3264a83a41b555d26ee004751de
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581750"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="7405d-103">Настройка общего доступа к рабочему столу в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7405d-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="7405d-104">Общий доступ к рабочему столу позволяет пользователям отображать экран или приложение во время встречи или чата.</span><span class="sxs-lookup"><span data-stu-id="7405d-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="7405d-105">Администраторы могут настроить общий доступ к экрану в Microsoft Teams, чтобы пользователи могли совместно использовать весь экран, приложение или файл.</span><span class="sxs-lookup"><span data-stu-id="7405d-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="7405d-106">Вы можете разрешить пользователям предоставлять или запрашивать контроль, разрешать общий доступ к PowerPoint, добавлять доску и разрешать общие заметки.</span><span class="sxs-lookup"><span data-stu-id="7405d-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="7405d-107">Вы также можете настроить, могут ли анонимные или внешние пользователи запрашивать управление общим экраном.</span><span class="sxs-lookup"><span data-stu-id="7405d-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="7405d-108">Чтобы настроить общий экран, вы создаете новую политику собраний, а затем назначаете ее пользователям, которыми хотите управлять.</span><span class="sxs-lookup"><span data-stu-id="7405d-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="7405d-109">**В [центре администрирования Microsoft Teams ](https://admin.teams.microsoft.com/)**</span><span class="sxs-lookup"><span data-stu-id="7405d-109">**In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/)**</span></span>

1. <span data-ttu-id="7405d-110">Выберите **Собрания** > \*\*политики собраний \*\*.</span><span class="sxs-lookup"><span data-stu-id="7405d-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![Снимок экрана, показывающий выбранные политики собрания](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="7405d-112">На странице **Политики собраний** выберите **Новая политика**.</span><span class="sxs-lookup"><span data-stu-id="7405d-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![Снимок экрана с сообщением о политике собрания](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="7405d-114">Дайте вашей политике уникальный заголовок и введите краткое описание.</span><span class="sxs-lookup"><span data-stu-id="7405d-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="7405d-115">В разделе **Общий доступ к контенту** выберите **режим совместного использования экрана** из раскрывающегося списка:</span><span class="sxs-lookup"><span data-stu-id="7405d-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="7405d-116">**Весь экран** - позволяет пользователям совместно использовать весь рабочий стол.</span><span class="sxs-lookup"><span data-stu-id="7405d-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="7405d-117">**Одно приложение** - позволяет пользователям ограничить общий доступ к экрану одним активным приложением.</span><span class="sxs-lookup"><span data-stu-id="7405d-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="7405d-118">**Отключено** - отключение общего доступа к экрану.</span><span class="sxs-lookup"><span data-stu-id="7405d-118">**Disabled** – Turns off screen sharing.</span></span>

    ![Снимок экрана, показывающий параметры режима обмена](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="7405d-120">Включите или выключите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="7405d-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="7405d-121">**Разрешать участнику предоставлять или запрашивать контроль** – позволяет членам команды предоставлять или запрашивать контроль над классической версией или приложением выступающего.</span><span class="sxs-lookup"><span data-stu-id="7405d-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter's desktop or application.</span></span>
    - <span data-ttu-id="7405d-122">**Разрешить внешнему участнику предоставлять или запрашивать контроль** — это политика для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="7405d-122">**Allow an external participant to give or request control** – This is a per-user policy.</span></span> <span data-ttu-id="7405d-123">Есть ли в Организации этот набор для пользователя, не зависит от того, какие данные могут выполнять внешние участники, независимо от того, какой у вас организатор собрания.</span><span class="sxs-lookup"><span data-stu-id="7405d-123">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="7405d-124">Этот параметр определяет, могут ли внешние участники получать контроль или запрашивать контроль над экраном общего доступа, в зависимости от того, какой общий доступ настроен в политиках собрания Организации.</span><span class="sxs-lookup"><span data-stu-id="7405d-124">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span>
    - <span data-ttu-id="7405d-125">**Предоставление общего доступа к PowerPoint** — позволяет пользователям создавать собрания, позволяющие отправлять и предоставлять доступ к презентациям PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="7405d-125">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="7405d-126">**Разрешить на доске** — позволяет пользователям делиться досками.</span><span class="sxs-lookup"><span data-stu-id="7405d-126">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="7405d-127">**Разрешить общие заметки** - позволяет пользователям делать общие заметки.</span><span class="sxs-lookup"><span data-stu-id="7405d-127">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="7405d-128">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7405d-128">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="7405d-129">Используйте PowerShell для настройки общего рабочего стола</span><span class="sxs-lookup"><span data-stu-id="7405d-129">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="7405d-130">Вы также можете использовать командлет [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) для управления общим доступом к рабочему столу.</span><span class="sxs-lookup"><span data-stu-id="7405d-130">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="7405d-131">Установите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="7405d-131">Set the following parameters:</span></span>

- <span data-ttu-id="7405d-132">Описание</span><span class="sxs-lookup"><span data-stu-id="7405d-132">Description</span></span>
- <span data-ttu-id="7405d-133">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="7405d-133">ScreenSharingMode</span></span>
- <span data-ttu-id="7405d-134">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="7405d-134">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="7405d-135">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="7405d-135">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="7405d-136">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="7405d-136">AllowPowerPointSharing</span></span>
- <span data-ttu-id="7405d-137">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="7405d-137">AllowWhiteboard</span></span>
- <span data-ttu-id="7405d-138">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="7405d-138">AllowSharedNotes</span></span>

<span data-ttu-id="7405d-139">[Подробнее об использовании командлета csTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="7405d-139">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

