---
title: Что не рекомендуется использовать в Skype для бизнеса Server 2019
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Сводка: эти функции удалены из Skype для бизнеса Server 2019.'
ms.openlocfilehash: 9fd6ddc28a3b75b8d4c411aa7909516d4b5c0ab8
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418363"
---
# <a name="whats-deprecated-from-skype-for-business-server-2019"></a><span data-ttu-id="b1e6b-103">Что не рекомендуется использовать в Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="b1e6b-103">What's deprecated from Skype for Business Server 2019</span></span>

<span data-ttu-id="b1e6b-104">Узнайте о функциях и функциях, которые не рекомендуются в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b1e6b-104">Learn about the features and functionality that are deprecated in Skype for Business Server 2019.</span></span> <span data-ttu-id="b1e6b-105">Сведения о новых возможностях Skype для бизнеса Server 2019 можно найти [в разделе что это такое в Skype для бизнеса server 2019](whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="b1e6b-105">For information about new features in Skype for Business Server 2019, see [What's in Skype for Business Server 2019](whats-new.md).</span></span>

<span data-ttu-id="b1e6b-106">Некоторые из выкрывающихся функций включены в Skype для бизнеса Server 2019 для обеспечения совместимости с предыдущими версиями продукта.</span><span class="sxs-lookup"><span data-stu-id="b1e6b-106">Some de-emphasized features are included in Skype for Business Server 2019 for compatibility with previous product versions.</span></span>

## <a name="features-deprecated-in-skype-for-business-server-2019"></a><span data-ttu-id="b1e6b-107">Возможности, устаревшие в Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="b1e6b-107">Features deprecated in Skype for Business Server 2019</span></span> 

    The following features and functionality have been deprecated in Skype for Business Server 2019.

### <a name="xmpp-gateways-for-skype-for-business-server"></a><span data-ttu-id="b1e6b-108">Шлюзы КСМПП для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b1e6b-108">XMPP Gateways for Skype for Business Server</span></span>

<span data-ttu-id="b1e6b-109">Skype для бизнеса Server 2015 и его предшественники могут настроить на пограничном сервере прокси-сервер с расширенными сообщениями и протоколом доступности КСМПП и шлюз КСМПП на сервере переднего плана или пуле внешних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="b1e6b-109">Skype for Business Server 2015 and its predecessors allowed you to configure an Extensible Messaging and Presence Protocol (XMPP) proxy on the Edge Server and an XMPP Gateway on the Front End Server or Front End pool.</span></span> <span data-ttu-id="b1e6b-110">Эта функция больше не доступна в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b1e6b-110">This functionality is no longer available in Skype for Business Server 2019.</span></span>

### <a name="persistent-chat-for-skype-for-business-server"></a><span data-ttu-id="b1e6b-111">Сохраняемый чат для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b1e6b-111">Persistent Chat for Skype for Business Server</span></span>

<span data-ttu-id="b1e6b-112">Сервер сохраняемого чата — это необязательная роль, которая позволяет нескольким пользователям в Организации принимать участие в беседах в чате, которые сохраняются с течением времени.</span><span class="sxs-lookup"><span data-stu-id="b1e6b-112">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="b1e6b-113">В Skype для бизнеса Server 2019 нельзя разворачивать сохраняемый чат.</span><span class="sxs-lookup"><span data-stu-id="b1e6b-113">Persistent chat can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="b1e6b-114">Эта роль сервера удаляется из построителя топологии и из кода.</span><span class="sxs-lookup"><span data-stu-id="b1e6b-114">This server role is removed from Topology Builder, as well as from the code.</span></span> 

<span data-ttu-id="b1e6b-115">Эта функция доступна в Teams.</span><span class="sxs-lookup"><span data-stu-id="b1e6b-115">The same functionality is available in Teams.</span></span> <span data-ttu-id="b1e6b-116">Дополнительные сведения можно найти в разделе [Начало работы с обновлением Microsoft Teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="b1e6b-116">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span>

### <a name="sql-mirroring-for-skype-for-business-server"></a><span data-ttu-id="b1e6b-117">Зеркальное отображение SQL для сервера Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b1e6b-117">SQL Mirroring for Skype for Business Server</span></span>

<span data-ttu-id="b1e6b-118">Зеркальное отображение SQL не может быть развернуто в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b1e6b-118">SQL Mirroring can't be deployed with Skype for Business Server 2019.</span></span> <span data-ttu-id="b1e6b-119">Другие варианты обеспечения высокой доступности и аварийного восстановления по-прежнему поддерживаются, и вы можете выбрать один из них.</span><span class="sxs-lookup"><span data-stu-id="b1e6b-119">Other options for providing High Availability and Disaster Recovery are still supported and you should choose from among them.</span></span> <span data-ttu-id="b1e6b-120">Ознакомьтесь со сведениями о том, как [в Skype для бизнеса Server вы можете ознакомиться с высокой надежностью и восстановлением после аварии](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) .</span><span class="sxs-lookup"><span data-stu-id="b1e6b-120">See [Plan for high availability and disaster recovery in Skype for Business Server](../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) to review the options.</span></span>

### <a name="in-place-upgrades"></a><span data-ttu-id="b1e6b-121">Обновления на месте</span><span class="sxs-lookup"><span data-stu-id="b1e6b-121">In-place upgrades</span></span> 

<span data-ttu-id="b1e6b-122">Обновления на месте были выпущены в Skype для бизнеса Server 2015, но больше не поддерживаются в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b1e6b-122">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="b1e6b-123">Для получения дополнительных сведений обратитесь к разделу [Переход в Skype для бизнеса Server 2019, который](migration/migration-to-skype-for-business-server-2019.md) поддерживается параллельным обновлением.</span><span class="sxs-lookup"><span data-stu-id="b1e6b-123">Side by side upgrade and coexistance is supported, see [Migration to Skype for Business Server 2019](migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>

### <a name="mobility-service-mcx"></a><span data-ttu-id="b1e6b-124">Служба Mobility Service (МККС)</span><span class="sxs-lookup"><span data-stu-id="b1e6b-124">Mobility Service (Mcx)</span></span>

<span data-ttu-id="b1e6b-125">Поддержка службы Mobility Service, используемая существующими мобильными клиентами, больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b1e6b-125">Mobility Service support used by legacy mobile clients is no longer available in Skype for Business Server 2019.</span></span> <span data-ttu-id="b1e6b-126">Ранее это было объявлено в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b1e6b-126">This was previously announced in Skype for Business Server 2015.</span></span>

<span data-ttu-id="b1e6b-127">На всех текущих мобильных клиентах Skype для бизнеса уже используется веб-API единой системы обмена сообщениями (УКВА) для поддержки мгновенных сообщений, присутствия и контактов.</span><span class="sxs-lookup"><span data-stu-id="b1e6b-127">All current Skype for Business mobile clients already use Unified Communications Web API (UCWA) to support instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="b1e6b-128">Пользователи с устаревшими клиентами, использующими МККС, должны обновиться до текущего клиента.</span><span class="sxs-lookup"><span data-stu-id="b1e6b-128">Users with legacy clients using Mcx will need to upgrade to a current client.</span></span>

<span data-ttu-id="b1e6b-129">Дополнительные сведения можно найти в разделе [планирование мобильных устройств в Skype для бизнеса Server](../SfbServer/plan-your-deployment/mobility.md) и [мобильных клиентах для Skype для бизнеса](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span><span class="sxs-lookup"><span data-stu-id="b1e6b-129">For more details, see [Plan for Mobility for Skype for Business Server](../SfbServer/plan-your-deployment/mobility.md) and [Mobile client feature comparison for Skype for Business](../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md).</span></span>

## <a name="tools"></a><span data-ttu-id="b1e6b-130">Инструменты</span><span class="sxs-lookup"><span data-stu-id="b1e6b-130">Tools</span></span>

<span data-ttu-id="b1e6b-131">Перечисленные ниже инструменты не будут доступны для использования в первоначальном выпуске Skype для бизнеса Server 2019:</span><span class="sxs-lookup"><span data-stu-id="b1e6b-131">The following tools will not be available for use at the initial release of Skype for Business Server 2019:</span></span>

- <span data-ttu-id="b1e6b-132">Калькулятор планирования мощности Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b1e6b-132">Skype for Business Server Capacity Planning Calculator</span></span>
- <span data-ttu-id="b1e6b-133">Средства отладки в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b1e6b-133">Skype for Business Server Debugging Tools</span></span>
- <span data-ttu-id="b1e6b-134">Средства пакета ресурсов в Skype для бизнеса Server (некоторые инструменты будут удалены)</span><span class="sxs-lookup"><span data-stu-id="b1e6b-134">Skype for Business Server Resource Kit Tools (some tools will be removed)</span></span>
    - <span data-ttu-id="b1e6b-135">Счетчик парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="b1e6b-135">Call Parkometer</span></span>
    - <span data-ttu-id="b1e6b-136">Пользовательская консоль поиска</span><span class="sxs-lookup"><span data-stu-id="b1e6b-136">Lookup user console</span></span>
    - <span data-ttu-id="b1e6b-137">Миграция неназначенного числа объявлений</span><span class="sxs-lookup"><span data-stu-id="b1e6b-137">Unassigned number Announcement Migration</span></span>

<span data-ttu-id="b1e6b-138">Следующие средства не поддерживаются в Skype для бизнеса Server 2019:</span><span class="sxs-lookup"><span data-stu-id="b1e6b-138">The following tools are not supported with Skype for Business Server 2019:</span></span>

- <span data-ttu-id="b1e6b-139">Методология качества связи (но не для панели мониторинга качества звонков)</span><span class="sxs-lookup"><span data-stu-id="b1e6b-139">Call Quality Methodology (but not Call Quality Dashboard)</span></span>
- <span data-ttu-id="b1e6b-140">Система показателей качества звонков (Майкрософт), версия 1.5</span><span class="sxs-lookup"><span data-stu-id="b1e6b-140">Microsoft Call Quality Methodology Scorecard, v1.5</span></span>
- <span data-ttu-id="b1e6b-141">Средство планирования Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="b1e6b-141">Skype for Business Server 2015 Planning Tool</span></span>
- <span data-ttu-id="b1e6b-142">Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="b1e6b-142">Skype for Business Server 2015 Stress and Performance Tool</span></span>

### <a name="see-also"></a><span data-ttu-id="b1e6b-143">См. также</span><span class="sxs-lookup"><span data-stu-id="b1e6b-143">See also</span></span>

[<span data-ttu-id="b1e6b-144">Новые возможности Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="b1e6b-144">What's new in Skype for Business Server 2019</span></span>](whats-new.md)

[<span data-ttu-id="b1e6b-145">Перенос федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="b1e6b-145">Migrating XMPP federation</span></span>](migration/migrating-xmpp-federation.md)
