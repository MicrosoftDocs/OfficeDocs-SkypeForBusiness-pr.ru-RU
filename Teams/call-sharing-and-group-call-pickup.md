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
ms.sourcegitcommit: 920a7dbdc2a0ede94d0a4bd573c01a1ccd838b7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "31993583"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="e9c6c-103">Общие звонки и ответ на групповые звонки в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e9c6c-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="e9c6c-104">Общий доступ к звонков и группу раскладки функции общего ресурса позволяет пользователям группами Майкрософт, их входящих звонков с коллегами, чтобы коллеги могут отвечать на звонки, возникающих при пользователя недоступен звонков.</span><span class="sxs-lookup"><span data-stu-id="e9c6c-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="e9c6c-105">Групповой звонок раскладки менее аварийные получателям, чем другие формы вызов общего доступа (например, переадресации звонков или одновременных звонков), так как пользователи могут настраивать способ уведомления об общих входящий звонок (через звуковые и визуальные уведомления, только visual или заголовок в приложении группы), и они могут принять решение на него ответить.</span><span class="sxs-lookup"><span data-stu-id="e9c6c-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="e9c6c-106">Для совместного использования вызовов с другими пользователями, пользователь создает группу звонка и добавляет пользователей, их нужно совместно использовать их в приложении.</span><span class="sxs-lookup"><span data-stu-id="e9c6c-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="e9c6c-107">Затем они выбрать Одновременный звонок или переадресовывать параметр.</span><span class="sxs-lookup"><span data-stu-id="e9c6c-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="e9c6c-108">Для получения дополнительных сведений в разделе [вызова переадресации и одновременно звонить в группах](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) .</span><span class="sxs-lookup"><span data-stu-id="e9c6c-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9c6c-109">Пользователи, владелец группы вызова и участники группы вызова должен быть в режиме только группы развертывания.</span><span class="sxs-lookup"><span data-stu-id="e9c6c-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="e9c6c-110">Для получения дополнительных сведений о режимах развертывания групп видеть [понять группами Майкрософт и Скайп для бизнеса сосуществования и взаимодействия](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="e9c6c-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="e9c6c-111">Требуется лицензия</span><span class="sxs-lookup"><span data-stu-id="e9c6c-111">License required</span></span>

<span data-ttu-id="e9c6c-112">Пользователи должны быть включены для установки и использование общего доступа к вызова и групповой звонок раскладки корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="e9c6c-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="e9c6c-113">Дополнительные сведения о модели лицензирования в разделе [Лицензирование Office 365 для групп Майкрософт](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="e9c6c-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="e9c6c-114">Настройка группы вызова раскладки</span><span class="sxs-lookup"><span data-stu-id="e9c6c-114">Configure group call pickup</span></span>

<span data-ttu-id="e9c6c-115">Для настройки группы вызова раскладки, пользователь сначала настраивает группы вызова (это не то же, как группы безопасности или группу Office 365) и затем добавляет пользователей, их нужно совместно использовать их в приложении.</span><span class="sxs-lookup"><span data-stu-id="e9c6c-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or an Office 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="e9c6c-116">После этого они выберите Одновременный звонок или вызова прямая параметр.</span><span class="sxs-lookup"><span data-stu-id="e9c6c-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="e9c6c-117">Дополнительные сведения и пошаговые процедуры в разделе [вызова переадресации и одновременно звонить в группах](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span><span class="sxs-lookup"><span data-stu-id="e9c6c-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="e9c6c-118">Вызова Создание группы и уведомлений о установки сохраняются на основе функций; Администраторы не нужно настроить эти функции для своих пользователей.</span><span class="sxs-lookup"><span data-stu-id="e9c6c-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="e9c6c-119">Звонок группы не могут создаваться из группы безопасности или группы Office 365; они должны быть созданы в группы.</span><span class="sxs-lookup"><span data-stu-id="e9c6c-119">Call groups cannot be created from security groups or Office 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="e9c6c-120">«Администраторы» следует включать групп звонок с помощью параметра **TeamsCallingPolicy AllowCallGroups** для пользователя.</span><span class="sxs-lookup"><span data-stu-id="e9c6c-120">Admins should enable call groups via the **TeamsCallingPolicy AllowCallGroups** setting for a user.</span></span> <span data-ttu-id="e9c6c-121">Администраторы могут только управлять ли этот пользователь может настроить группы вызова.</span><span class="sxs-lookup"><span data-stu-id="e9c6c-121">Admins can only control whether this user can configure call groups.</span></span> <span data-ttu-id="e9c6c-122">После бит имеет значение true, администраторы не могут запретить пользователям настройки и добавление пользователей групповой звонок по своему выбору.</span><span class="sxs-lookup"><span data-stu-id="e9c6c-122">Once the bit is set to true, admins cannot prevent the user from configuring and adding the call group users of their choice.</span></span>

## <a name="limitations"></a><span data-ttu-id="e9c6c-123">Ограничения</span><span class="sxs-lookup"><span data-stu-id="e9c6c-123">Limitations</span></span>

<span data-ttu-id="e9c6c-124">Клиент может содержать не более 32 768 звонок группы.</span><span class="sxs-lookup"><span data-stu-id="e9c6c-124">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="e9c6c-125">Может быть не более 5 пользователей в каждой группе звонок.</span><span class="sxs-lookup"><span data-stu-id="e9c6c-125">There can be a maximum of 5 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="e9c6c-126">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="e9c6c-126">More information</span></span>

[<span data-ttu-id="e9c6c-127">Переадресация звонков и одновременных звонков в группах</span><span class="sxs-lookup"><span data-stu-id="e9c6c-127">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)