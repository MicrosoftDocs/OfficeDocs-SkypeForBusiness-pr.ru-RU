---
title: Общие звонки и ответ на групповые звонки в Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 02/19/2019
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Предоставление общего доступа к собранию и групповая связь позволяет пользователям предоставлять общий доступ к входящим звонкам с коллегами, чтобы можно было получать вызовы, когда пользователь недоступен.
ms.openlocfilehash: 02c6605f3a5ea1df3457eaadea9956727431a827
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283481"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="74421-103">Общие звонки и ответ на групповые звонки в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="74421-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="74421-104">Функции отправки и предоставления общего доступа к вызовам Microsoft Teams позволяют пользователям обмениваться входящими звонками с коллегами, чтобы они могли отвечать на звонки, происходящие, когда пользователь недоступен.</span><span class="sxs-lookup"><span data-stu-id="74421-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="74421-105">Отправка группового звонка менее неактивна получателям, чем для других форм общего доступа к вызовам (например, переадресация звонков или Одновременный звонок), так как пользователи могут настроить способ уведомления о входящем звонке (с помощью звука и визуального уведомления, визуально). или заголовков в приложении Teams), и они могут решить, нужно ли вам отвечать на них.</span><span class="sxs-lookup"><span data-stu-id="74421-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="74421-106">Чтобы поделиться звонками с другими людьми, пользователь создаст группу звонков и добавит пользователей, которым нужно предоставить доступ к своим звонкам.</span><span class="sxs-lookup"><span data-stu-id="74421-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="74421-107">Затем вы выбираете параметр Одновременный звонок или переадресация.</span><span class="sxs-lookup"><span data-stu-id="74421-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="74421-108">Подробные сведения о [переадресации звонков и одновременные звонки в Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) см.</span><span class="sxs-lookup"><span data-stu-id="74421-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74421-109">Пользователи, владелец группы звонков и члены группы звонков должны находиться в режиме развертывания только Teams.</span><span class="sxs-lookup"><span data-stu-id="74421-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="74421-110">Подробнее о режимах развертывания Teams можно узнать в разделе Общие сведения о сосуществовании [и взаимодействии Microsoft Teams и Skype для бизнеса](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="74421-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="74421-111">Требуется лицензия</span><span class="sxs-lookup"><span data-stu-id="74421-111">License required</span></span>

<span data-ttu-id="74421-112">Для настройки и использования функции совместного использования звонков и группового звонка пользователи должны быть включены в корпоративную голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="74421-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="74421-113">Дополнительные сведения о модели лицензирования можно найти в разделе [Лицензирование Office 365 для Microsoft Teams](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="74421-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="74421-114">Настройка отправки группового звонка</span><span class="sxs-lookup"><span data-stu-id="74421-114">Configure group call pickup</span></span>

<span data-ttu-id="74421-115">Для настройки отправки группового звонка пользователь сначала настраивает группу обзвона (это не то же самое, что группа безопасности или группа Office 365), а затем добавляет пользователей, которым нужно предоставить доступ к своим звонкам.</span><span class="sxs-lookup"><span data-stu-id="74421-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or an Office 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="74421-116">Затем выберите параметр Одновременный звонок или переадресация звонков.</span><span class="sxs-lookup"><span data-stu-id="74421-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="74421-117">Дополнительные сведения и пошаговые инструкции можно найти [в разделе Переадресация звонков и одновременные звонки в Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span><span class="sxs-lookup"><span data-stu-id="74421-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="74421-118">Настройки создания и уведомлений групп звонков — это функции, управляемые пользователем; администраторам не нужно настраивать эти параметры для пользователей.</span><span class="sxs-lookup"><span data-stu-id="74421-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="74421-119">Группы звонков нельзя создавать из групп безопасности или групп Office 365; они должны быть созданы в Teams.</span><span class="sxs-lookup"><span data-stu-id="74421-119">Call groups cannot be created from security groups or Office 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="74421-120">Администраторы должны включать группы звонков через параметр **Теамскаллингполици алловкаллграупс** для пользователя.</span><span class="sxs-lookup"><span data-stu-id="74421-120">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="74421-121">Администраторы могут управлять тем, может ли пользователь настраивать группы звонков.</span><span class="sxs-lookup"><span data-stu-id="74421-121">Admins can only control whether this user can configure call groups.</span></span> <span data-ttu-id="74421-122">После того как для бита установлено значение true, администраторы не смогут запретить пользователю настраивать и добавлять пользователей группы звонков.</span><span class="sxs-lookup"><span data-stu-id="74421-122">Once the bit is set to true, admins cannot prevent the user from configuring and adding the call group users of their choice.</span></span>

## <a name="limitations"></a><span data-ttu-id="74421-123">Предел</span><span class="sxs-lookup"><span data-stu-id="74421-123">Limitations</span></span>

<span data-ttu-id="74421-124">Клиент может содержать не более 32 768 групп звонков.</span><span class="sxs-lookup"><span data-stu-id="74421-124">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="74421-125">В каждой группе звонков может быть не более 5 пользователей.</span><span class="sxs-lookup"><span data-stu-id="74421-125">There can be a maximum of 5 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="74421-126">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="74421-126">More information</span></span>

[<span data-ttu-id="74421-127">Переадресация звонков и одновременные звонки в Teams</span><span class="sxs-lookup"><span data-stu-id="74421-127">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)