---
title: What's deprecated from Skype for Business Server 2019
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Сводка. Эти функции удалены из Skype для бизнеса Server 2019.
ms.openlocfilehash: 5c5914493d7e2f4da4fd72d6acf7ff2b979d8e88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808729"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="d81aa-103">What's deprecated from Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="d81aa-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="d81aa-104">Узнайте о функциях и функциях, неподготовленных в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d81aa-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="d81aa-105">Сведения о новых функциях в Skype для бизнеса Server 2019 см. в сведениях о skype для бизнеса [Server 2019.](whats-new.md)</span><span class="sxs-lookup"><span data-stu-id="d81aa-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="d81aa-106">Некоторые функции, для совместимости с предыдущими версиями продукта, включены в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d81aa-106">Some de-emphasized features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="d81aa-107">Функции, неподготовленные в Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="d81aa-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="d81aa-108">Шлюзы XMPP для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d81aa-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="d81aa-109">Skype для бизнеса Server 2015 и его предшественники позволяли настраивать прокси-сервер XMPP на сервере и шлюз XMPP на сервере переднего или переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="d81aa-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="d81aa-110">Эта функция больше недоступна в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d81aa-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="d81aa-111">Сохраняемая беседа для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d81aa-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="d81aa-112">Сервер сохраняемой беседы — это необязательная роль, которая позволяет нескольким пользователям в организации участвовать в беседах комнат чата, которые сохраняются с течением времени.</span><span class="sxs-lookup"><span data-stu-id="d81aa-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="d81aa-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d81aa-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="d81aa-114">Эта роль сервера удаляется из построитель топологий, а также из кода.</span><span class="sxs-lookup"><span data-stu-id="d81aa-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="d81aa-115">Такие же функции доступны в Teams.</span><span class="sxs-lookup"><span data-stu-id="d81aa-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="d81aa-116">Дополнительные сведения [см. в сведениях о том,](/microsoftteams/upgrade-start-here)как начать обновление Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d81aa-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="d81aa-117">SQL Зеркальное отражение для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d81aa-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="d81aa-118">SQL зеркальное отражение не может быть развернуто в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d81aa-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="d81aa-119">Другие варианты обеспечения высокой доступности и аварийного восстановления по-прежнему поддерживаются, и вам следует выбрать один из них.</span><span class="sxs-lookup"><span data-stu-id="d81aa-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="d81aa-120">Чтобы [просмотреть варианты, см.](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) "Планирование высокой доступности и аварийного восстановления в Skype для бизнеса Server".</span><span class="sxs-lookup"><span data-stu-id="d81aa-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="d81aa-121">Обновление на месте</span><span class="sxs-lookup"><span data-stu-id="d81aa-121">In-place upgrades</span></span> 

<span data-ttu-id="d81aa-122">Обновления на месте были доступны в Skype для бизнеса Server 2015, но больше не поддерживаются в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d81aa-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="d81aa-123">Поддержка обновления и сосуществования поддерживается в переходе на Skype для бизнеса [Server 2019](migration/migration-to-skype-for-business-server-2019.md) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="d81aa-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="d81aa-124">Mobility Service (Mcx)</span><span class="sxs-lookup"><span data-stu-id="d81aa-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="d81aa-125">Поддержка mobility Service, используемая устаревшими мобильными клиентами, больше недоступна в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d81aa-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="d81aa-126">Это было ранее объявлено в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d81aa-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="d81aa-127">Все текущие мобильные клиенты Skype для бизнеса уже используют веб-API объединенных коммуникаций (UCWA) для поддержки обмена мгновенными сообщениями, присутствия и контактов.</span><span class="sxs-lookup"><span data-stu-id="d81aa-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="d81aa-128">Пользователям с устаревшими клиентами, использующими Mcx, потребуется обновиться до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="d81aa-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="d81aa-129">Дополнительные сведения см. в сравнении функций ["Планирование](../SfbServer/plan-your-deployment/mobility.md) мобильности для Skype для бизнеса Server и [мобильных клиентов" в Skype для бизнеса.](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md)</span><span class="sxs-lookup"><span data-stu-id="d81aa-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="d81aa-130">Инструменты</span><span class="sxs-lookup"><span data-stu-id="d81aa-130">Tools</span></span>

<span data-ttu-id="d81aa-131">Следующие средства будут недоступны для использования в первоначальном выпуске Skype для бизнеса Server 2019:</span><span class="sxs-lookup"><span data-stu-id="d81aa-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="d81aa-132">Калькулятор планирования мощности Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d81aa-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="d81aa-133">Средства отладки Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d81aa-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="d81aa-134">Средства skype для бизнеса Server Resource Kit (некоторые средства будут удалены)</span><span class="sxs-lookup"><span data-stu-id="d81aa-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="d81aa-135">Call Parkometer</span><span class="sxs-lookup"><span data-stu-id="d81aa-135">Call Parkometer</span></span>
    - <span data-ttu-id="d81aa-136">Консоль пользователя подыском</span><span class="sxs-lookup"><span data-stu-id="d81aa-136">Lookup user console</span></span>
    - <span data-ttu-id="d81aa-137">Миграция объявлений с ненаписаным номером</span><span class="sxs-lookup"><span data-stu-id="d81aa-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="d81aa-138">В Skype для бизнеса Server 2019 не поддерживаются следующие средства:</span><span class="sxs-lookup"><span data-stu-id="d81aa-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="d81aa-139">Методология качества вызовов (но не панель мониторинга качества звонка)</span><span class="sxs-lookup"><span data-stu-id="d81aa-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="d81aa-140">Система показателей методологии качества вызовов Майкрософт, 1.5</span><span class="sxs-lookup"><span data-stu-id="d81aa-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="d81aa-141">Средство планирования Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="d81aa-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="d81aa-142">Skype для бизнеса Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="d81aa-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="d81aa-143">См. также</span><span class="sxs-lookup"><span data-stu-id="d81aa-143">See also</span></span>

[<span data-ttu-id="d81aa-144">Новые возможности Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="d81aa-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="d81aa-145">Перенос федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="d81aa-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)
