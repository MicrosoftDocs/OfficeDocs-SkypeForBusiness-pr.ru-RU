---
title: Общие звонки и ответ на групповые звонки в Microsoft Teams
ms.author: lolaj
author: lolaj
manager: serdars
ms.date: 01/16/19
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service:
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Вызовите общего доступа и раскладки звонок группы Пользователи могут совместно использовать входящие звонки с коллегами, чтобы звонки можно отслеживались при недоступности пользователя.
ms.openlocfilehash: 31df45d0420457528fd517c851b845a09cab32e0
ms.sourcegitcommit: 0fcca2d8303da82cc00a504f4183bee50ab23eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2019
ms.locfileid: "28328319"
---
# <a name="call-sharing-and-group-call-pickup-in-microsoft-teams"></a><span data-ttu-id="6af1f-103">Общие звонки и ответ на групповые звонки в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6af1f-103">Call sharing and group call pickup in Microsoft Teams</span></span>

<span data-ttu-id="6af1f-104">Общий доступ к звонков и группу раскладки функции общего ресурса позволяет пользователям группами Майкрософт, их входящих звонков с коллегами, чтобы коллеги могут отвечать на звонки, возникающих при пользователя недоступен звонков.</span><span class="sxs-lookup"><span data-stu-id="6af1f-104">The call sharing and group call pickup features of Microsoft Teams let users share their incoming calls with colleagues so that the colleagues can answer calls that occur while the user is unavailable.</span></span>

<span data-ttu-id="6af1f-105">Групповой звонок раскладки менее аварийные получателям, чем другие формы вызов общего доступа (например, переадресации звонков или одновременных звонков), так как пользователи могут настраивать способ уведомления об общих входящий звонок (через звуковые и визуальные уведомления, только visual или заголовок в приложении группы), и они могут принять решение на него ответить.</span><span class="sxs-lookup"><span data-stu-id="6af1f-105">Group call pickup is less disruptive to recipients than other forms of call sharing (such as call forwarding or simultaneous ringing) because users can configure how they want to be notified of an incoming shared call (via audio and visual notification, visual only, or banner in the Teams app), and they can decide whether to answer it.</span></span>

<span data-ttu-id="6af1f-106">Для совместного использования вызовов с другими пользователями, пользователь создает группу звонка и добавляет пользователей, их нужно совместно использовать их в приложении.</span><span class="sxs-lookup"><span data-stu-id="6af1f-106">To share calls with others, a user creates a call group and adds the users they want to share their calls with.</span></span> <span data-ttu-id="6af1f-107">Затем они выбрать Одновременный звонок или переадресовывать параметр.</span><span class="sxs-lookup"><span data-stu-id="6af1f-107">Then they choose a simultaneous ring or forward setting.</span></span> <span data-ttu-id="6af1f-108">Для получения дополнительных сведений в разделе [вызова переадресации и одновременно звонить в группах](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) .</span><span class="sxs-lookup"><span data-stu-id="6af1f-108">See [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e) for details.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6af1f-109">Пользователи, владелец группы вызова и участники группы вызова должен быть в режиме только группы развертывания.</span><span class="sxs-lookup"><span data-stu-id="6af1f-109">Users, the call group owner, and members of the call group must be in Teams Only deployment mode.</span></span> <span data-ttu-id="6af1f-110">Для получения дополнительных сведений о режимах развертывания групп видеть [понять группами Майкрософт и Скайп для бизнеса сосуществования и взаимодействия](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="6af1f-110">For more details on Teams deployment modes, see [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md)</span></span>

## <a name="license-required"></a><span data-ttu-id="6af1f-111">Требуется лицензия</span><span class="sxs-lookup"><span data-stu-id="6af1f-111">License required</span></span>

<span data-ttu-id="6af1f-112">Пользователи должны быть включены для установки и использование общего доступа к вызова и групповой звонок раскладки корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="6af1f-112">Users must be Enterprise Voice enabled to set up and use call sharing and group call pickup.</span></span> <span data-ttu-id="6af1f-113">Дополнительные сведения о модели лицензирования в разделе [Лицензирование Office 365 для групп Майкрософт](office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="6af1f-113">For additional details on the licensing model, See [Office 365 licensing for Microsoft Teams](office-365-licensing.md).</span></span>

## <a name="configure-group-call-pickup"></a><span data-ttu-id="6af1f-114">Настройка группы вызова раскладки</span><span class="sxs-lookup"><span data-stu-id="6af1f-114">Configure group call pickup</span></span>

<span data-ttu-id="6af1f-115">Для настройки группы вызова раскладки, пользователь сначала настраивает группы вызова (это не то же, как группы безопасности или группу Office 365) и затем добавляет пользователей, их нужно совместно использовать их в приложении.</span><span class="sxs-lookup"><span data-stu-id="6af1f-115">To set up group call pickup, a user first configures a call group (this is not the same as a security group or an Office 365 group), and then adds the users they want to share their calls with.</span></span> <span data-ttu-id="6af1f-116">После этого они выберите Одновременный звонок или вызова прямая параметр.</span><span class="sxs-lookup"><span data-stu-id="6af1f-116">Then, they choose a simultaneous ring or call forward setting.</span></span> <span data-ttu-id="6af1f-117">Дополнительные сведения и пошаговые процедуры в разделе [вызова переадресации и одновременно звонить в группах](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span><span class="sxs-lookup"><span data-stu-id="6af1f-117">For more information and step-by-step procedures, see [Call forwarding and simultaneous ring in Teams](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e).</span></span>

<span data-ttu-id="6af1f-118">Вызова Создание группы и уведомлений о установки сохраняются на основе функций; Администраторы не нужно настроить эти функции для своих пользователей.</span><span class="sxs-lookup"><span data-stu-id="6af1f-118">Call group creation and notification preferences are user-driven features; administrators do not have to configure these features for their users.</span></span> <span data-ttu-id="6af1f-119">Звонок группы не могут создаваться из группы безопасности или группы Office 365; они должны быть созданы в группы.</span><span class="sxs-lookup"><span data-stu-id="6af1f-119">Call groups cannot be created from security groups or Office 365 groups; they must be created in Teams.</span></span>

<span data-ttu-id="6af1f-120">Администраторы не можете запретить пользователям Создание групп и изменять другая Настройка раскладки звонок.</span><span class="sxs-lookup"><span data-stu-id="6af1f-120">Admins cannot prevent users from creating groups and changing other call pickup setting.</span></span> <span data-ttu-id="6af1f-121">Функциональные возможности не блокируются.</span><span class="sxs-lookup"><span data-stu-id="6af1f-121">The functionality is not blocked.</span></span>

## <a name="limitations"></a><span data-ttu-id="6af1f-122">Ограничения</span><span class="sxs-lookup"><span data-stu-id="6af1f-122">Limitations</span></span>

<span data-ttu-id="6af1f-123">Клиент может содержать не более 32 768 звонок группы.</span><span class="sxs-lookup"><span data-stu-id="6af1f-123">A tenant can contain a maximum of 32,768 call groups.</span></span> <span data-ttu-id="6af1f-124">Может быть не более 5 пользователей в каждой группе звонок.</span><span class="sxs-lookup"><span data-stu-id="6af1f-124">There can be a maximum of 5 users in each call group.</span></span> 

## <a name="more-information"></a><span data-ttu-id="6af1f-125">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="6af1f-125">More information</span></span>

[<span data-ttu-id="6af1f-126">Переадресация звонков и одновременных звонков в группах</span><span class="sxs-lookup"><span data-stu-id="6af1f-126">Call forwarding and simultaneous ring in Teams</span></span>](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)