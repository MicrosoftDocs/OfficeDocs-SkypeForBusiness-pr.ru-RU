---
title: Совместный доступ к рабочему столу в Microsoft Teams
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Настройка политики собраний для предоставления пользователям возможности совместного доступа к рабочему столу в чате и собраниях Teams
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 99c6e2a5adb9d0f9a4b4e3f6f17b7484bda96a74
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "37516890"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="f7ca9-103">Совместный доступ к рабочему столу в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f7ca9-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="f7ca9-104">Общий доступ к рабочему столу позволяет пользователям Показать экран или приложение во время собрания или чата.</span><span class="sxs-lookup"><span data-stu-id="f7ca9-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="f7ca9-105">Администраторы могут настроить демонстрацию экрана в Microsoft Teams, чтобы позволить пользователям демонстрировать весь экран, приложение или файл.</span><span class="sxs-lookup"><span data-stu-id="f7ca9-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="f7ca9-106">Вы можете предоставить пользователям разрешение или запрос на управление, разрешить общий доступ к PowerPoint, добавить доску и разрешить доступ к общим заметкам.</span><span class="sxs-lookup"><span data-stu-id="f7ca9-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="f7ca9-107">Вы также можете указать, могут ли анонимные или внешние пользователи запрашивать управление общим экраном.</span><span class="sxs-lookup"><span data-stu-id="f7ca9-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="f7ca9-108">Чтобы настроить демонстрацию экрана, создайте новую политику собраний и назначьте ее пользователям, которым хотите управлять.</span><span class="sxs-lookup"><span data-stu-id="f7ca9-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="f7ca9-109">**В центре администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="f7ca9-109">**In the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="f7ca9-110"> > Выберите**политики собраний** **для собраний**.</span><span class="sxs-lookup"><span data-stu-id="f7ca9-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![Снимок экрана, на котором выделены политики собраний](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="f7ca9-112">На странице **политики собрания** нажмите кнопку **создать политику**.</span><span class="sxs-lookup"><span data-stu-id="f7ca9-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![Снимок экрана с сообщением "политики собрания"](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="f7ca9-114">Задайте для политики уникальный заголовок и введите краткое описание.</span><span class="sxs-lookup"><span data-stu-id="f7ca9-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="f7ca9-115">В разделе **общий доступ к контенту**выберите **режим демонстрации экрана** из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="f7ca9-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="f7ca9-116">**Весь экран** — позволяет пользователям делиться на всем рабочем столе.</span><span class="sxs-lookup"><span data-stu-id="f7ca9-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="f7ca9-117">**Единое приложение** — позволяет пользователям ограничить демонстрацию экрана одним активным приложением.</span><span class="sxs-lookup"><span data-stu-id="f7ca9-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="f7ca9-118">**Disabled (отключено** ) — отключает демонстрацию экрана.</span><span class="sxs-lookup"><span data-stu-id="f7ca9-118">**Disabled** – Turns off screen sharing.</span></span>

    ![Снимок экрана, демонстрирующий параметры режима общего использования](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="f7ca9-120">Включать и отключать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f7ca9-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="f7ca9-121">**Разрешать участнику предоставлять или запрашивать контроль** – позволяет членам команды предоставлять или запрашивать контроль над классической версией или приложением выступающего.</span><span class="sxs-lookup"><span data-stu-id="f7ca9-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="f7ca9-122">**Разрешать внешнему участнику предоставлять или запрашивать контроль** — позволяет гостям и внешним (федеративным) пользователям предоставлять или запрашивать управление классической версией и приложением докладчика.</span><span class="sxs-lookup"><span data-stu-id="f7ca9-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="f7ca9-123">**Разрешить общий доступ к PowerPoint** — позволяет пользователям создавать собрания, позволяющие отправлять и предоставлять общий доступ к презентациям PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="f7ca9-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="f7ca9-124">**Разрешить доску** — позволяет пользователям делиться досками.</span><span class="sxs-lookup"><span data-stu-id="f7ca9-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="f7ca9-125">**Разрешить общие заметки** — позволяет пользователям использовать общие заметки.</span><span class="sxs-lookup"><span data-stu-id="f7ca9-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="f7ca9-126">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f7ca9-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="f7ca9-127">Настройка общего рабочего стола с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="f7ca9-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="f7ca9-128">Вы также можете использовать командлет [Set-кстеамсмитингполици](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) , чтобы управлять общим доступом к рабочему столу.</span><span class="sxs-lookup"><span data-stu-id="f7ca9-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="f7ca9-129">Задайте следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f7ca9-129">Set the following parameters:</span></span>

- <span data-ttu-id="f7ca9-130">Описание</span><span class="sxs-lookup"><span data-stu-id="f7ca9-130">Description</span></span>
- <span data-ttu-id="f7ca9-131">скриншарингмоде</span><span class="sxs-lookup"><span data-stu-id="f7ca9-131">ScreenSharingMode</span></span>
- <span data-ttu-id="f7ca9-132">алловпартиЦипантгиверекуестконтрол</span><span class="sxs-lookup"><span data-stu-id="f7ca9-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="f7ca9-133">алловекстерналпартиЦипантгиверекуестконтрол</span><span class="sxs-lookup"><span data-stu-id="f7ca9-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="f7ca9-134">алловповерпоинтшаринг</span><span class="sxs-lookup"><span data-stu-id="f7ca9-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="f7ca9-135">алловвхитебоард</span><span class="sxs-lookup"><span data-stu-id="f7ca9-135">AllowWhiteboard</span></span>
- <span data-ttu-id="f7ca9-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="f7ca9-136">AllowSharedNotes</span></span>

<span data-ttu-id="f7ca9-137">Дополнительные [сведения об использовании командлета кстеамсмитингполици](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f7ca9-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

