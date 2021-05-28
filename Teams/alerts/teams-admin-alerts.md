---
title: Microsoft Teams Мониторинг и оповещение
author: vaibhav
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: vapati
f1.keywords: ''
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-collaboration
description: Узнайте о возможностях Teams и уведомлений, доступных в центре Microsoft Teams администрирования.
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: c99cc9af08fb1353e0c94e6f8bf156df04327d49
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684613"
---
# <a name="microsoft-teams-monitoring-and-alerting"></a><span data-ttu-id="d41f1-103">Microsoft Teams мониторинга и оповещений</span><span class="sxs-lookup"><span data-stu-id="d41f1-103">Microsoft Teams monitoring and alerting</span></span>

<span data-ttu-id="d41f1-104">Новые возможности мониторинга и оповещения для Microsoft Teams доступны в центре Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="d41f1-104">New monitoring and alerting capabilities for Microsoft Teams are available in the Teams admin center.</span></span> <span data-ttu-id="d41f1-105">Используйте различные наборы правил, доступные в разделе Уведомления & оповещения в Центре администрирования Teams для отслеживания Teams и получения оповещений. </span><span class="sxs-lookup"><span data-stu-id="d41f1-105">Use different sets of rules available under the **Notifications & alerts** section in the Teams admin center to monitor Teams capabilities and receive alerts.</span></span> <span data-ttu-id="d41f1-106">Например, вы можете активно отслеживать состояние устройств Teams, таких как IP-телефоны, полосы совместной работы и другие, если они неожиданно перейдут в автономный режим.</span><span class="sxs-lookup"><span data-stu-id="d41f1-106">For example, you can actively monitor the health of Teams devices such as IP Phones, collaboration bars, and others if they unexpectedly go offline.</span></span>  

<span data-ttu-id="d41f1-107">Ваша организация может использовать Teams мониторинг и оповещение для следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="d41f1-107">Your organization can use Teams monitoring and alerting to do the following items:</span></span>

- <span data-ttu-id="d41f1-108">Автоматическое управление Teams возможностями</span><span class="sxs-lookup"><span data-stu-id="d41f1-108">Automatically manage Teams capabilities</span></span>
- <span data-ttu-id="d41f1-109">Будьте оповещены, если они показывают что-то непредвиденное.</span><span class="sxs-lookup"><span data-stu-id="d41f1-109">Be alerted if they show something unexpected.</span></span>
- <span data-ttu-id="d41f1-110">Чтобы вернуть все в нужное время, необходимо принять меры по исправлению.</span><span class="sxs-lookup"><span data-stu-id="d41f1-110">Take corrective actions to get things back on-track.</span></span>

## <a name="how-to-manage-monitoring-and-alerting"></a><span data-ttu-id="d41f1-111">Управление мониторингом и оповещениями</span><span class="sxs-lookup"><span data-stu-id="d41f1-111">How to manage monitoring and alerting</span></span>

 <span data-ttu-id="d41f1-112">Настраивать правила оповещения может только глобальный администратор Microsoft 365 или администратор Teams службы.</span><span class="sxs-lookup"><span data-stu-id="d41f1-112">You must be a global admin in Microsoft 365 or a Teams service admin to configure alerting rules.</span></span> <span data-ttu-id="d41f1-113">Дополнительные [Teams Teams](../using-admin-roles.md) роли администраторов и отчеты о них см. в Teams в этой области.</span><span class="sxs-lookup"><span data-stu-id="d41f1-113">See [Use Teams administrator roles to manage Teams](../using-admin-roles.md) to learn more about Teams admin roles and which reports each admin role can access.</span></span>

1. <span data-ttu-id="d41f1-114">Войдите в Центр администрирования Teams.</span><span class="sxs-lookup"><span data-stu-id="d41f1-114">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="d41f1-115">В области навигации слева выберите **Уведомления & оповещения**.</span><span class="sxs-lookup"><span data-stu-id="d41f1-115">From the left navigation, select **Notifications & alerts**.</span></span>
3. <span data-ttu-id="d41f1-116">Выберите правило, необходимое для настройки, в области **Правила.**</span><span class="sxs-lookup"><span data-stu-id="d41f1-116">Choose the rule you want to configure from **Rules**.</span></span>

## <a name="teams-monitoring-rules-reference"></a><span data-ttu-id="d41f1-117">Teams правила мониторинга</span><span class="sxs-lookup"><span data-stu-id="d41f1-117">Teams monitoring rules reference</span></span>

<span data-ttu-id="d41f1-118">Мы продолжаем добавлять и улучшать возможности мониторинга Teams, добавляя различные возможности мониторинга и настройки.</span><span class="sxs-lookup"><span data-stu-id="d41f1-118">We continue adding to and improving the Teams monitoring experience by adding various monitoring capabilities and configuration functionalities.</span></span> <span data-ttu-id="d41f1-119">Вот список правил Teams мониторинга, доступных в Teams администрирования.</span><span class="sxs-lookup"><span data-stu-id="d41f1-119">Here's a list of the Teams monitoring rules currently available in the Teams admin center.</span></span>


|<span data-ttu-id="d41f1-120">Правило</span><span class="sxs-lookup"><span data-stu-id="d41f1-120">Rule</span></span>  |<span data-ttu-id="d41f1-121">Возможность мониторинга</span><span class="sxs-lookup"><span data-stu-id="d41f1-121">Monitoring capability</span></span>|<span data-ttu-id="d41f1-122">Что отслеживается?</span><span class="sxs-lookup"><span data-stu-id="d41f1-122">What's monitored?</span></span> |
|---------|---------|---------|
|[<span data-ttu-id="d41f1-123">Состояние состояния устройства</span><span class="sxs-lookup"><span data-stu-id="d41f1-123">Device health status</span></span>](device-health-status.md)  |<span data-ttu-id="d41f1-124">Teams Устройств</span><span class="sxs-lookup"><span data-stu-id="d41f1-124">Teams Devices</span></span> | <span data-ttu-id="d41f1-125">Pro активно отслеживайте Teams устройствах, если они работают в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="d41f1-125">Pro-actively monitor Teams devices if they go offline.</span></span>|