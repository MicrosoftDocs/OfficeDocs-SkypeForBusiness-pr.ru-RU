---
title: Общие звонки и ответ на групповые звонки
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: Общий доступ к звонкам и групповой звонок позволяет пользователям обмениваться входящие звонки с коллегами, чтобы делать снимки, когда пользователь недоступен.
ms.openlocfilehash: 825e174a6b6f68adcc7b5aade212689b01309c24
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620730"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="255e8-103">Общие звонки и ответ на групповые звонки в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="255e8-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="255e8-104">Функции общего доступа к звонкам и группового звонка в Microsoft Teams позволяет пользователям делиться своими входящие звонки с коллегами, чтобы они могли отвечать на звонки, которые происходят, когда пользователь недоступен.</span><span class="sxs-lookup"><span data-stu-id="255e8-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="255e8-105">Групповой звонок менее прерывает работу с получателями, чем другие формы обмена звонками (например, переадрешение или одновременный звонок), так как пользователи могут настроить уведомления о входящих общих звонках (посредством аудио- и визуальных уведомлений, только визуальных или баннеров в приложении Teams) и отвечать на него.</span><span class="sxs-lookup"><span data-stu-id="255e8-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="255e8-106">Чтобы делиться звонками с другими пользователями, пользователь создает группу звонков и добавляет пользователей, с ними нужно поделиться.</span><span class="sxs-lookup"><span data-stu-id="255e8-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="255e8-107">Затем они выбирают одновременный звонок или переад параметры переадренки.</span><span class="sxs-lookup"><span data-stu-id="255e8-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="255e8-108">Подробные [сведения см. в переададных звонках и одновременных звонках в Teams.](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)</span><span class="sxs-lookup"><span data-stu-id="255e8-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span> <span data-ttu-id="255e8-109">Обратите внимание, что мобильные устройства будут получать уведомления только в том случае, если они настроены для баннера и мелодии звонка.</span><span class="sxs-lookup"><span data-stu-id="255e8-109">Note that mobile devices will only get notified if they're set for banner and ringtone.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="255e8-110">Пользователи, владелец группы звонка и участники группы должны быть в режиме развертывания Только в Teams.</span><span class="sxs-lookup"><span data-stu-id="255e8-110">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="255e8-111">Дополнительные сведения о режимах развертывания Teams см. в сведениях о сосуществовании и совместном работе Microsoft Teams и [Skype для бизнеса.](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="255e8-111">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="255e8-112">Требуется лицензия</span><span class="sxs-lookup"><span data-stu-id="255e8-112">License required</span></span>

<span data-ttu-id="255e8-113">У пользователей должна быть Корпоративная голосовая связь возможность настроить и использовать общий доступ к звонкам и групповой звонок.</span><span class="sxs-lookup"><span data-stu-id="255e8-113">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="255e8-114">Дополнительные сведения о модели лицензирования см. в описании [служб Microsoft Teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="255e8-114">For additional details on the licensing model, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="255e8-115">Настройка группового звонка</span><span class="sxs-lookup"><span data-stu-id="255e8-115">Configure group call pickup</span></span>

<span data-ttu-id="255e8-116">Чтобы настроить групповую группу звонка, пользователь сначала настраивает группу звонков (не ту же, что группа безопасности или Microsoft 365), а затем добавляет пользователей, с ними нужно поделиться своими звонками.</span><span class="sxs-lookup"><span data-stu-id="255e8-116">To set up group call pickup, a user first configures a call group (this is not the same as a security group or a Microsoft 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="255e8-117">Затем они выбирают параметры одновременного звонка или переадваровки параметров.</span><span class="sxs-lookup"><span data-stu-id="255e8-117">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="255e8-118">Дополнительные сведения и пошаговые процедуры см. в переададации вызовов и [одновременных звонках в Teams.](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)</span><span class="sxs-lookup"><span data-stu-id="255e8-118">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="255e8-119">Параметры создания и уведомления групп вызовов — это пользовательские функции. администраторам не нужно настраивать эти функции для своих пользователей.</span><span class="sxs-lookup"><span data-stu-id="255e8-119">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="255e8-120">Группы вызовов нельзя создавать из групп безопасности или групп Microsoft 365; их необходимо создать в Teams.</span><span class="sxs-lookup"><span data-stu-id="255e8-120">Call groups cannot be created from security groups or Microsoft 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="255e8-121">Администраторы должны включить группы вызовов с помощью параметра **TeamsCallingPolicy AllowCallGroups** для пользователя.</span><span class="sxs-lookup"><span data-stu-id="255e8-121">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="255e8-122">Администраторы также могут включить эту возможность на портале администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="255e8-122">Admins can also enable this via Teams Admin portal.</span></span>  <span data-ttu-id="255e8-123">Кроме того, настроенный пользователь также может настраивать группы вызовов непосредственно через клиент.</span><span class="sxs-lookup"><span data-stu-id="255e8-123">In addition, the configured user can also configure their call groups via the client directly.</span></span> <span data-ttu-id="255e8-124">Администратор и конечные пользователи не могут блокировать конфигурацию друг для друга, но портал администрирования Teams и клиент Teams должны правильно показывать эту связь в обоих местах.</span><span class="sxs-lookup"><span data-stu-id="255e8-124">Admin or end users cannot block the configuration by each other, but Teams Admin portal and Teams client should show this relationship accurately in both places.</span></span> 

<span data-ttu-id="255e8-125">Важно! Если администраторы отключили группы вызовов для пользователей (после того как они были включены и настроены отношения между ними), администраторам необходимо очистить связи групп вызовов для пользователей в Центре администрирования Teams, чтобы избежать неправильной маршрутизов.</span><span class="sxs-lookup"><span data-stu-id="255e8-125">Important: When admins turn off call groups for users (after it has been turned on and the call group relationships are configured), the admins have to clean up the call group relationships for users in the Teams admin center to avoid incorrect call routing.</span></span> 

## <a name="limitations"></a><span data-ttu-id="255e8-126">Ограничения</span><span class="sxs-lookup"><span data-stu-id="255e8-126">Limitations</span></span>

<span data-ttu-id="255e8-127">Клиент может содержать не более 32 768 групп вызовов.</span><span class="sxs-lookup"><span data-stu-id="255e8-127">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="255e8-128">В каждой группе звонка может быть не более 25 пользователей.</span><span class="sxs-lookup"><span data-stu-id="255e8-128">There can be a maximum of 25 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="255e8-129">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="255e8-129">More information</span></span>

[<span data-ttu-id="255e8-130">Переад вызовы и одновременные вызовы в Teams</span><span class="sxs-lookup"><span data-stu-id="255e8-130">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
