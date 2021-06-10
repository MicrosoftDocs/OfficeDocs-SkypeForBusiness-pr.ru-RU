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
description: Узнайте, как настроить политику собраний, чтобы позволить пользователям делиться рабочими столами Teams чатах или собраниях.
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 35db312d7a4530f05db3cbad59d1b2b29a4e3847
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856468"
---
# <a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="da51f-103">Настройка общего доступа к рабочему столу в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="da51f-103">Configure desktop sharing in Microsoft Teams</span></span>

<span data-ttu-id="da51f-104">Общий доступ к рабочему столу позволяет пользователям отображать экран или приложение во время встречи или чата.</span><span class="sxs-lookup"><span data-stu-id="da51f-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="da51f-105">Администраторы могут настроить общий доступ к экрану в Microsoft Teams, чтобы пользователи могли совместно использовать весь экран, приложение или файл.</span><span class="sxs-lookup"><span data-stu-id="da51f-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="da51f-106">Вы можете разрешить пользователям предоставлять или запрашивать контроль, разрешать общий доступ к PowerPoint, добавлять доску и разрешать общие заметки.</span><span class="sxs-lookup"><span data-stu-id="da51f-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="da51f-107">Вы также можете настроить, могут ли анонимные или внешние пользователи запрашивать управление общим экраном.</span><span class="sxs-lookup"><span data-stu-id="da51f-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span> <span data-ttu-id="da51f-108">Внешних участников собраний Teams можно классифицировать следующим образом.</span><span class="sxs-lookup"><span data-stu-id="da51f-108">External participants in Teams meetings can be categorized as follows:</span></span>

- <span data-ttu-id="da51f-109">Анонимный пользователь</span><span class="sxs-lookup"><span data-stu-id="da51f-109">Anonymous user</span></span>
- <span data-ttu-id="da51f-110">Гостевые пользователи</span><span class="sxs-lookup"><span data-stu-id="da51f-110">Guest users</span></span>
- <span data-ttu-id="da51f-111">Пользователь B2B</span><span class="sxs-lookup"><span data-stu-id="da51f-111">B2B user</span></span>
- <span data-ttu-id="da51f-112">Федеративный пользователь</span><span class="sxs-lookup"><span data-stu-id="da51f-112">Federated user</span></span>

<span data-ttu-id="da51f-113">Чтобы настроить общий экран, вы создаете новую политику собраний, а затем назначаете ее пользователям, которыми хотите управлять.</span><span class="sxs-lookup"><span data-stu-id="da51f-113">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="da51f-114">**В [центре администрирования Microsoft Teams](https://admin.teams.microsoft.com/)**</span><span class="sxs-lookup"><span data-stu-id="da51f-114">**In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/)**</span></span>

1. <span data-ttu-id="da51f-115">Выберите **Собрания** > **политики собраний**.</span><span class="sxs-lookup"><span data-stu-id="da51f-115">Select **Meetings** > **Meeting policies**.</span></span>

    ![Выбранные политики собраний](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="da51f-117">На странице **Политики собраний** выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="da51f-117">On the **Meeting policies** page, select **Add**.</span></span>

    ![Сообщение политик собрания](media/addMeeting.png)

3. <span data-ttu-id="da51f-119">Дайте вашей политике уникальный заголовок и введите краткое описание.</span><span class="sxs-lookup"><span data-stu-id="da51f-119">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="da51f-120">В разделе **Общий доступ к контенту** выберите **режим совместного использования экрана** из раскрывающегося списка:</span><span class="sxs-lookup"><span data-stu-id="da51f-120">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="da51f-121">**Весь экран** - позволяет пользователям совместно использовать весь рабочий стол.</span><span class="sxs-lookup"><span data-stu-id="da51f-121">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="da51f-122">**Одно приложение** - позволяет пользователям ограничить общий доступ к экрану одним активным приложением.</span><span class="sxs-lookup"><span data-stu-id="da51f-122">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="da51f-123">**Отключено** - отключение общего доступа к экрану.</span><span class="sxs-lookup"><span data-stu-id="da51f-123">**Disabled** – Turns off screen sharing.</span></span>

    ![Параметры режима общего доступа](media/configure-desktop-sharing-image3.png)

  > [!Note]
  > <span data-ttu-id="da51f-125">Вам не нужно включить политику звонков, чтобы пользователи могли использовать доступ к экрану из чата.</span><span class="sxs-lookup"><span data-stu-id="da51f-125">You don't have to enable the calling policy in order for users to use screen share from chat.</span></span> <span data-ttu-id="da51f-126">Однако звук отключается, пока он не включит свой звук.</span><span class="sxs-lookup"><span data-stu-id="da51f-126">However, their audio is turned off until they unmute themselves.</span></span> <span data-ttu-id="da51f-127">Кроме того, пользователь, который делится экраном, может нажать кнопку **Добавить звук,** чтобы включить звук.</span><span class="sxs-lookup"><span data-stu-id="da51f-127">In addition, the user sharing the screen can click **Add Audio** to enable audio.</span></span> <span data-ttu-id="da51f-128">Если политика звонков отключена, пользователи не смогут добавлять звук к экранной ленте из сеанса чата.</span><span class="sxs-lookup"><span data-stu-id="da51f-128">If the calling policy is disabled, users won't be able to add audio to the screen share from a chat session.</span></span>

5. <span data-ttu-id="da51f-129">Включите или выключите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="da51f-129">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="da51f-130">**Разрешить участнику предоставить или** запросить управление — позволяет участникам группы предоставить или запросить контроль над рабочим столом или приложением.</span><span class="sxs-lookup"><span data-stu-id="da51f-130">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter's desktop or application.</span></span>
    - <span data-ttu-id="da51f-131">**Разрешить внешнему участнику предоставить или запросить управление** — это политика "на пользователя".</span><span class="sxs-lookup"><span data-stu-id="da51f-131">**Allow an external participant to give or request control** – This is a per-user policy.</span></span> <span data-ttu-id="da51f-132">Настройка этого параметра организацией для пользователя не управляет возможностями внешних участников, независимо от того, что установил организатор собрания.</span><span class="sxs-lookup"><span data-stu-id="da51f-132">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="da51f-133">Этот параметр определяет, могут ли внешние участники предоставлять или запрашивать управление экраном пользователя, предоставившего общий доступ, в зависимости от того, что этот пользователь настроил в политиках собраний своей организации.</span><span class="sxs-lookup"><span data-stu-id="da51f-133">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span>
    - <span data-ttu-id="da51f-134">**Предоставление общего доступа к PowerPoint** — позволяет пользователям создавать собрания, позволяющие отправлять и предоставлять доступ к презентациям PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="da51f-134">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="da51f-135">**Разрешить на доске** — позволяет пользователям делиться досками.</span><span class="sxs-lookup"><span data-stu-id="da51f-135">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="da51f-136">**Разрешить общие заметки** - позволяет пользователям делать общие заметки.</span><span class="sxs-lookup"><span data-stu-id="da51f-136">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="da51f-137">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="da51f-137">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="da51f-138">Используйте PowerShell для настройки общего рабочего стола</span><span class="sxs-lookup"><span data-stu-id="da51f-138">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="da51f-139">Вы также можете использовать командлет [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) для управления общим доступом к рабочему столу.</span><span class="sxs-lookup"><span data-stu-id="da51f-139">You can also use the [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="da51f-140">Установите следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="da51f-140">Set the following parameters:</span></span>

- <span data-ttu-id="da51f-141">Описание</span><span class="sxs-lookup"><span data-stu-id="da51f-141">Description</span></span>
- <span data-ttu-id="da51f-142">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="da51f-142">ScreenSharingMode</span></span>
- <span data-ttu-id="da51f-143">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="da51f-143">AllowPrivateCalling</span></span>
- <span data-ttu-id="da51f-144">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="da51f-144">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="da51f-145">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="da51f-145">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="da51f-146">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="da51f-146">AllowPowerPointSharing</span></span>
- <span data-ttu-id="da51f-147">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="da51f-147">AllowWhiteboard</span></span>
- <span data-ttu-id="da51f-148">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="da51f-148">AllowSharedNotes</span></span>

<span data-ttu-id="da51f-149">[Подробнее об использовании командлета csTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="da51f-149">[Learn more about using the csTeamsMeetingPolicy cmdlet](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>