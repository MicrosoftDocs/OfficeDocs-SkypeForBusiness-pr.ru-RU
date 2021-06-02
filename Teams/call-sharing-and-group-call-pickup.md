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
description: Общий доступ к звонкам и групповой звонок позволяет пользователям делиться входящие звонки с коллегами, чтобы их можно было захватывать, когда пользователь недоступен.
ms.openlocfilehash: 98094ff0b4b5d7b037915273b2c2730d42517c22
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717840"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="97dac-103">Общие звонки и ответ на групповые звонки в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="97dac-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="97dac-104">Функции общего доступа к звонкам и группового звонка Microsoft Teams позволить пользователям делиться своими входящие звонки с коллегами, чтобы они могли отвечать на звонки, которые происходят, когда пользователь недоступен.</span><span class="sxs-lookup"><span data-stu-id="97dac-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="97dac-105">Групповой звонок менее деструктивен для получателей, чем другие формы общего доступа к звонкам (например, переадрешение или одновременный звонок), так как пользователи могут настроить способ уведомления о входящих общих звонках (посредством аудио- и визуальных уведомлений, только визуальных или баннеров в приложении Teams) и решать, следует ли ответить на него.</span><span class="sxs-lookup"><span data-stu-id="97dac-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="97dac-106">Чтобы делиться звонками с другими пользователями, пользователь создает группу звонков и добавляет пользователей, с ними нужно поделиться.</span><span class="sxs-lookup"><span data-stu-id="97dac-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="97dac-107">Затем он выбирает одновременный звонок или переадваровку.</span><span class="sxs-lookup"><span data-stu-id="97dac-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="97dac-108">Подробные [сведения см.](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) в Teams переад Teams звонках.</span><span class="sxs-lookup"><span data-stu-id="97dac-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span> <span data-ttu-id="97dac-109">Обратите внимание, что мобильные устройства будут получать уведомления только в том случае, если они настроены для баннера и мелодии звонка.</span><span class="sxs-lookup"><span data-stu-id="97dac-109">Note that mobile devices will only get notified if they're set for banner and ringtone.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97dac-110">Пользователи, владелец группы зовов и участники группы должны быть в режиме Teams только для развертывания.</span><span class="sxs-lookup"><span data-stu-id="97dac-110">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="97dac-111">Дополнительные сведения о режимах Teams см. в Microsoft Teams и Skype для бизнеса сосуществования и [совместной работы.](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="97dac-111">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="97dac-112">Требуется лицензия</span><span class="sxs-lookup"><span data-stu-id="97dac-112">License required</span></span>

<span data-ttu-id="97dac-113">Чтобы настроить и использовать общий доступ к звонкам и групповой звонок, пользователям должна быть назначена Microsoft Teams телефонная система лицензия.</span><span class="sxs-lookup"><span data-stu-id="97dac-113">Users must be assigned a Microsoft Teams Phone System license to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="97dac-114">Дополнительные сведения о модели лицензирования см. в этой [телефонная система.](https://docs.microsoft.com/MicrosoftTeams/here-s-what-you-get-with-phone-system)</span><span class="sxs-lookup"><span data-stu-id="97dac-114">For additional details on the licensing model, see [Here's what you get with Phone System](https://docs.microsoft.com/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="97dac-115">Настройка группового звонка</span><span class="sxs-lookup"><span data-stu-id="97dac-115">Configure group call pickup</span></span>

<span data-ttu-id="97dac-116">Чтобы настроить групповой звонок, пользователь сначала настроит группу звонков (это не то же самое, что группа безопасности или группа Microsoft 365), а затем добавит пользователей, с ними нужно поделиться своими звонками.</span><span class="sxs-lookup"><span data-stu-id="97dac-116">To set up group call pickup, a user first configures a call group (this is not the same as a security group or a Microsoft 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="97dac-117">Затем он выбирает одновременный звонок или переадваровку.</span><span class="sxs-lookup"><span data-stu-id="97dac-117">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="97dac-118">Дополнительные сведения и пошаговые процедуры см. в этой [Teams.](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)</span><span class="sxs-lookup"><span data-stu-id="97dac-118">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="97dac-119">Параметры создания групп вызовов и уведомлений — это пользовательские функции. администраторам не нужно настраивать эти функции для своих пользователей.</span><span class="sxs-lookup"><span data-stu-id="97dac-119">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="97dac-120">Группы вызовов нельзя создавать из групп безопасности или Microsoft 365 групп; их необходимо создать в Teams.</span><span class="sxs-lookup"><span data-stu-id="97dac-120">Call groups cannot be created from security groups or Microsoft 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="97dac-121">Администраторы должны включить группы вызовов с помощью **параметра TeamsCallingPolicy AllowCallGroups** для пользователя.</span><span class="sxs-lookup"><span data-stu-id="97dac-121">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="97dac-122">Администраторы также могут включить эту возможность на Teams портале администрирования.</span><span class="sxs-lookup"><span data-stu-id="97dac-122">Admins can also enable this via Teams Admin portal.</span></span>  <span data-ttu-id="97dac-123">Кроме того, настроенный пользователь также может настраивать группы вызовов непосредственно через клиента.</span><span class="sxs-lookup"><span data-stu-id="97dac-123">In addition, the configured user can also configure their call groups via the client directly.</span></span> <span data-ttu-id="97dac-124">Администратор или конечные пользователи не могут заблокировать конфигурацию друг для друга, но Teams и Teams должны правильно показывать эту связь в обоих местах.</span><span class="sxs-lookup"><span data-stu-id="97dac-124">Admin or end users cannot block the configuration by each other, but Teams Admin portal and Teams client should show this relationship accurately in both places.</span></span> 

<span data-ttu-id="97dac-125">Важно! Когда администраторы отключили группы вызовов для пользователей (после того как они были включены и связи между ними настроены), администраторам необходимо очистить связи между группами вызовов для пользователей в Центре администрирования Teams, чтобы избежать неправильной маршрутизы звонка.</span><span class="sxs-lookup"><span data-stu-id="97dac-125">Important: When admins turn off call groups for users (after it has been turned on and the call group relationships are configured), the admins have to clean up the call group relationships for users in the Teams admin center to avoid incorrect call routing.</span></span> 

## <a name="limitations"></a><span data-ttu-id="97dac-126">Ограничения</span><span class="sxs-lookup"><span data-stu-id="97dac-126">Limitations</span></span>

<span data-ttu-id="97dac-127">Каждая настроенная группа звонка может иметь не более 25 пользователей или 32 768 символов.</span><span class="sxs-lookup"><span data-stu-id="97dac-127">Each configured call group can have a maximum of 25 users or 32,768 characters.</span></span> 

## <a name="more-information"></a><span data-ttu-id="97dac-128">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="97dac-128">More information</span></span>

[<span data-ttu-id="97dac-129">Переад вызовы и одновременные Teams</span><span class="sxs-lookup"><span data-stu-id="97dac-129">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)
