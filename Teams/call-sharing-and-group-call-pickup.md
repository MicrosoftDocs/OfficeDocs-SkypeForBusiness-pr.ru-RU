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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Вызовите общего доступа и раскладки звонок группы Пользователи могут совместно использовать входящие звонки с коллегами, чтобы звонки можно отслеживались при недоступности пользователя.
ms.openlocfilehash: e822d06e48f3d7df548f0fd0d04645e7e9328598
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211825"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="6d729-103">Общие звонки и ответ на групповые звонки в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6d729-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="6d729-104">Общий доступ к звонков и группу раскладки функции общего ресурса позволяет пользователям группами Майкрософт, их входящих звонков с коллегами, чтобы коллеги могут отвечать на звонки, возникающих при пользователя недоступен звонков.</span><span class="sxs-lookup"><span data-stu-id="6d729-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="6d729-105">Групповой звонок раскладки менее аварийные получателям, чем другие формы вызов общего доступа (например, переадресации звонков или одновременных звонков), так как пользователи могут настраивать способ уведомления об общих входящий звонок (через звуковые и визуальные уведомления, только visual или заголовок в приложении группы), и они могут принять решение на него ответить.</span><span class="sxs-lookup"><span data-stu-id="6d729-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="6d729-106">Для совместного использования вызовов с другими пользователями, пользователь создает группу звонка и добавляет пользователей, их нужно совместно использовать их в приложении.</span><span class="sxs-lookup"><span data-stu-id="6d729-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="6d729-107">Затем они выбрать Одновременный звонок или переадресовывать параметр.</span><span class="sxs-lookup"><span data-stu-id="6d729-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="6d729-108">Для получения дополнительных сведений в разделе [вызова переадресации и одновременно звонить в группах](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) .</span><span class="sxs-lookup"><span data-stu-id="6d729-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6d729-109">Пользователи, владелец группы вызова и участники группы вызова должен быть в режиме только группы развертывания.</span><span class="sxs-lookup"><span data-stu-id="6d729-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="6d729-110">Для получения дополнительных сведений о режимах развертывания групп видеть [понять группами Майкрософт и Скайп для бизнеса сосуществования и взаимодействия](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="6d729-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="6d729-111">Требуется лицензия</span><span class="sxs-lookup"><span data-stu-id="6d729-111">License required</span></span>

<span data-ttu-id="6d729-112">Пользователи должны быть включены для установки и использование общего доступа к вызова и групповой звонок раскладки корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="6d729-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="6d729-113">Дополнительные сведения о модели лицензирования в разделе [Лицензирование Office 365 для групп Майкрософт](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="6d729-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="6d729-114">Настройка группы вызова раскладки</span><span class="sxs-lookup"><span data-stu-id="6d729-114">Configure group call pickup</span></span>

<span data-ttu-id="6d729-115">Для настройки группы вызова раскладки, пользователь сначала настраивает группы вызова (это не то же, как группы безопасности или группу Office 365) и затем добавляет пользователей, их нужно совместно использовать их в приложении.</span><span class="sxs-lookup"><span data-stu-id="6d729-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or an Office 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="6d729-116">После этого они выберите Одновременный звонок или вызова прямая параметр.</span><span class="sxs-lookup"><span data-stu-id="6d729-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="6d729-117">Дополнительные сведения и пошаговые процедуры в разделе [вызова переадресации и одновременно звонить в группах](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span><span class="sxs-lookup"><span data-stu-id="6d729-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="6d729-118">Вызова Создание группы и уведомлений о установки сохраняются на основе функций; Администраторы не нужно настроить эти функции для своих пользователей.</span><span class="sxs-lookup"><span data-stu-id="6d729-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="6d729-119">Звонок группы не могут создаваться из группы безопасности или группы Office 365; они должны быть созданы в группы.</span><span class="sxs-lookup"><span data-stu-id="6d729-119">Call groups cannot be created from security groups or Office 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="6d729-120">«Администраторы» следует включать групп звонок с помощью параметра **TeamsCallingPolicy AllowCallGroups** для пользователя.</span><span class="sxs-lookup"><span data-stu-id="6d729-120">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="6d729-121">Администраторы могут только управлять ли этот пользователь может настроить группы вызова.</span><span class="sxs-lookup"><span data-stu-id="6d729-121">Admins can only control whether this user can configure call groups.</span></span> <span data-ttu-id="6d729-122">После бит имеет значение true, администраторы не могут запретить пользователям настройки и добавление пользователей групповой звонок по своему выбору.</span><span class="sxs-lookup"><span data-stu-id="6d729-122">Once the bit is set to true, admins cannot prevent the user from configuring and adding the call group users of their choice.</span></span>

## <a name="limitations"></a><span data-ttu-id="6d729-123">Ограничения</span><span class="sxs-lookup"><span data-stu-id="6d729-123">Limitations</span></span>

<span data-ttu-id="6d729-124">Клиент может содержать не более 32 768 звонок группы.</span><span class="sxs-lookup"><span data-stu-id="6d729-124">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="6d729-125">Может быть не более 5 пользователей в каждой группе звонок.</span><span class="sxs-lookup"><span data-stu-id="6d729-125">There can be a maximum of 5 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="6d729-126">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="6d729-126">More information</span></span>

[<span data-ttu-id="6d729-127">Переадресация звонков и одновременных звонков в группах</span><span class="sxs-lookup"><span data-stu-id="6d729-127">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)