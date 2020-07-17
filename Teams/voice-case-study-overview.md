---
title: Исследование успеха в голосовых сообщениях в Teams contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Исследование вариантов голосовой связи в среде Teams для международной Организации
appliesto:
- Microsoft Teams
ms.openlocfilehash: 100889bacffdb9de722bd2e1e7295905876dab2e
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786087"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a><span data-ttu-id="0f440-103">Исследование успеха Contoso: Общие сведения о переносе голосовых команд</span><span class="sxs-lookup"><span data-stu-id="0f440-103">Contoso case study: Teams voice migration overview</span></span>

<span data-ttu-id="0f440-104">В этой статье рассказывается о том, как вымышленная многонациональная корпорация компании Contoso реализовала для своей организации решение для голосовой связи по группам.</span><span class="sxs-lookup"><span data-stu-id="0f440-104">This article introduces a case study for how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span>

<span data-ttu-id="0f440-105">Компания Contoso развернула Microsoft 365 Enterprise и разрешила основные рекомендации по проектированию и сведениям о реализации: сеть, идентификация, Windows 10 корпоративный, Office 365 профессиональный плюс, управление мобильными устройствами, защита информации, безопасность, переход с Skype для бизнеса на Teams, телефонную систему и голосовую конференцию.</span><span class="sxs-lookup"><span data-stu-id="0f440-105">Contoso has deployed Microsoft 365 Enterprise and addressed major design decisions and implementation details for the following: networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, security, upgrade from Skype for Business to Teams, Phone System, and Audio Conferencing.</span></span>  

<span data-ttu-id="0f440-106">В этой статье рассказывается о том, как компания Contoso перешла за миграцию локальных пользователей в Teams для единой системы обмена сообщениями, совместной работы и голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="0f440-106">This article focuses on how Contoso migrated their on-premises users to Teams for unified communication, collaboration, and voice.</span></span> <span data-ttu-id="0f440-107">Дополнительные сведения о том, как компания Contoso ускоряет цифровое преобразование с помощью облачных служб Майкрософт, можно найти в статье основные статьи, начиная с обзора успеха в рамках [contoso](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="0f440-107">For background information about how Contoso accelerated their digital transformation by using Microsoft's cloud services, see all the core articles starting with the [Contoso case study overview](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span></span>

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

<span data-ttu-id="0f440-108">В основных статьях вы найдете информацию по следующим адресам:</span><span class="sxs-lookup"><span data-stu-id="0f440-108">In the core articles, you'll find information on the following:</span></span>  

- <span data-ttu-id="0f440-109">ИТ-инфраструктура Contoso требуется</span><span class="sxs-lookup"><span data-stu-id="0f440-109">Contoso's IT infrastructure needs</span></span>
- <span data-ttu-id="0f440-110">Работе</span><span class="sxs-lookup"><span data-stu-id="0f440-110">Networking</span></span>
- <span data-ttu-id="0f440-111">Identity </span><span class="sxs-lookup"><span data-stu-id="0f440-111">Identity</span></span>
- <span data-ttu-id="0f440-112">Windows 10 корпоративный</span><span class="sxs-lookup"><span data-stu-id="0f440-112">Windows 10 Enterprise</span></span>
- <span data-ttu-id="0f440-113">Office 365 профессиональный плюс</span><span class="sxs-lookup"><span data-stu-id="0f440-113">Office 365 Pro Plus</span></span>
- <span data-ttu-id="0f440-114">Управление мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="0f440-114">Mobile device management</span></span>
- <span data-ttu-id="0f440-115">Защита информации</span><span class="sxs-lookup"><span data-stu-id="0f440-115">Information protection</span></span>
- <span data-ttu-id="0f440-116">Сводка по Microsoft 365 корпоративный Security</span><span class="sxs-lookup"><span data-stu-id="0f440-116">Summary of Microsoft 365 Enterprise security</span></span>
- <span data-ttu-id="0f440-117">Группа для верхнего секретного проекта</span><span class="sxs-lookup"><span data-stu-id="0f440-117">Team for a top-secret project</span></span>
- <span data-ttu-id="0f440-118">Сайт SharePoint Online для конфиденциальных цифровых ресурсов</span><span class="sxs-lookup"><span data-stu-id="0f440-118">SharePoint Online site for highly confidential digital assets</span></span>

<span data-ttu-id="0f440-119">Сведения о планировании обновления можно начать с начала [работы с обновлением Microsoft Teams](upgrade-start-here.md).</span><span class="sxs-lookup"><span data-stu-id="0f440-119">For information about planning an upgrade, you'll want to start with [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md).</span></span>

## <a name="contoso-business-goals-for-teams"></a><span data-ttu-id="0f440-120">Бизнес-цели Contoso для Teams</span><span class="sxs-lookup"><span data-stu-id="0f440-120">Contoso business goals for Teams</span></span>

<span data-ttu-id="0f440-121">Для миграции локальных пользователей в Teams для единой системы обмена сообщениями, совместной работы и голосовой связи компания Contoso решила следующие бизнес-цели:</span><span class="sxs-lookup"><span data-stu-id="0f440-121">To migrate their on-premises users to Teams for unified communication, collaboration, and voice, Contoso decided on the following business goals:</span></span>

- <span data-ttu-id="0f440-122">Включение в Teams</span><span class="sxs-lookup"><span data-stu-id="0f440-122">Teams enablement</span></span> 

  <span data-ttu-id="0f440-123">Группа единой системы обмена сообщениями и совместной работы в Contoso включает в себя необходимые политики для управления и обеспечения безопасной внутренней и внешней совместной работы.</span><span class="sxs-lookup"><span data-stu-id="0f440-123">Contoso's unified communication and collaboration team enabled Teams with the correct policies to govern and enable secure internal and external collaboration.</span></span> 

- <span data-ttu-id="0f440-124">Переход со Skype для бизнеса на Teams</span><span class="sxs-lookup"><span data-stu-id="0f440-124">Skype for Business to Teams upgrade</span></span> 

  <span data-ttu-id="0f440-125">Skype для бизнеса был широко развернут в компании Contoso.</span><span class="sxs-lookup"><span data-stu-id="0f440-125">Skype for Business was widely deployed within Contoso.</span></span> <span data-ttu-id="0f440-126">После того как вам нужно будет продвигать старые системы, компания Contoso решила обновить пользователей Skype для бизнеса до Teams.</span><span class="sxs-lookup"><span data-stu-id="0f440-126">With the need to move off legacy systems, Contoso decided to upgrade their Skype for Business users to Teams.</span></span> <span data-ttu-id="0f440-127">Дополнительные сведения можно найти в статье [исследование успеха Contoso: план обновления Teams](voice-case-study-migration-plan.md).</span><span class="sxs-lookup"><span data-stu-id="0f440-127">For more information, see [Contoso case study: Teams upgrade plan](voice-case-study-migration-plan.md).</span></span>

- <span data-ttu-id="0f440-128">Телефонная система</span><span class="sxs-lookup"><span data-stu-id="0f440-128">Phone System</span></span>  

  <span data-ttu-id="0f440-129">Skype для бизнеса с корпоративной голосовой связью был широко развернут в компании Contoso.</span><span class="sxs-lookup"><span data-stu-id="0f440-129">Skype for Business with enterprise voice was widely deployed within Contoso.</span></span> <span data-ttu-id="0f440-130">При необходимости отключить старые системы, которые были следующим прыжком для серверов-исправлений, компания Contoso перенеса пользователей голосовой связи Skype для бизнеса в телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="0f440-130">With the need to move off legacy systems that were the next hop for their mediation servers, Contoso migrated their Skype for Business enterprise voice users to Phone System.</span></span> <span data-ttu-id="0f440-131">Сайты Contoso использовали план звонков Microsoft, прямую маршрутизацию телефонной системы или их сочетание.</span><span class="sxs-lookup"><span data-stu-id="0f440-131">Contoso sites used Microsoft Calling Plan, Phone System Direct Routing, or a combination of both.</span></span> <span data-ttu-id="0f440-132">Дополнительные сведения можно найти в статье [исследование успеха Contoso: телефонная система](voice-case-study-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="0f440-132">For more information, see [Contoso case study: Phone System](voice-case-study-phone-system.md).</span></span>

- <span data-ttu-id="0f440-133">Маршрутизация на основе расположения</span><span class="sxs-lookup"><span data-stu-id="0f440-133">Location-Based Routing</span></span> 

  <span data-ttu-id="0f440-134">С помощью расположений Office в странах, использующих телефонную связь, компания Contoso требовала повторного создания маршрутизации на основе местоположения, которая была представлена в Skype для бизнеса в своем развертывании телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="0f440-134">With office locations in telephony-regulated countries, Contoso needed to recreate the Location-Based Routing that was present in Skype for Business in their Phone System deployment.</span></span> <span data-ttu-id="0f440-135">Дополнительные сведения можно найти в статье [исследование успеха Contoso: Маршрутизация на основе местоположения](voice-case-study-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="0f440-135">For more information, see [Contoso case study: Location-Based Routing](voice-case-study-location-based-routing.md).</span></span>

- <span data-ttu-id="0f440-136">Экстренный вызов</span><span class="sxs-lookup"><span data-stu-id="0f440-136">Emergency Calling</span></span> 

  <span data-ttu-id="0f440-137">Если вы реализовали прямую переадресацию, компания Contoso настроила вызов экстренной помощи с утвержденными третьими лицами.</span><span class="sxs-lookup"><span data-stu-id="0f440-137">Where Direct Routing was implemented, Contoso set up emergency calling with approved third parties.</span></span> <span data-ttu-id="0f440-138">Дополнительные сведения можно найти в статье [исследование успеха Contoso: вызов экстренной](voice-case-study-emergency-calling.md)помощи.</span><span class="sxs-lookup"><span data-stu-id="0f440-138">For more information, see [Contoso case study: Emergency Calling](voice-case-study-emergency-calling.md).</span></span>

- <span data-ttu-id="0f440-139">Аудиоконференция</span><span class="sxs-lookup"><span data-stu-id="0f440-139">Audio Conferencing</span></span> 

  <span data-ttu-id="0f440-140">Компания Contoso настроила номера служб голосовой связи, которые были размещены на их магистралье SIP с поставщиком PSTN.</span><span class="sxs-lookup"><span data-stu-id="0f440-140">Contoso set up Audio Conferencing service numbers that were hosted on their SIP trunk to their PSTN provider.</span></span> <span data-ttu-id="0f440-141">Дополнительные сведения можно найти в статье [исследование успеха Contoso: Голосовая конференция](voice-case-study-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="0f440-141">For more information, see [Contoso case study: Audio Conferencing](voice-case-study-audio-conferencing.md).</span></span> 

- <span data-ttu-id="0f440-142">Оптимизация локальных файлов мультимедиа</span><span class="sxs-lookup"><span data-stu-id="0f440-142">Local Media Optimization</span></span> 

  <span data-ttu-id="0f440-143">Компания Contoso проделала преимущества локальной оптимизации мультимедиа в расположениях, в которых у них есть прямая маршрутизация на телефонную систему Microsoft, которая использовалась удаленными сайтами.</span><span class="sxs-lookup"><span data-stu-id="0f440-143">Contoso took advantage of Local Media Optimization in locations where they had one direct route trunk to Microsoft Phone System that was leveraged by remote sites.</span></span> <span data-ttu-id="0f440-144">Дополнительные сведения можно найти в разделе [планирование оптимизации локальных файлов](direct-routing-media-optimization.md) и [Настройка оптимизации локальных файлов мультимедиа](direct-routing-media-optimization-configure.md).</span><span class="sxs-lookup"><span data-stu-id="0f440-144">For more information, see [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).</span></span>

- <span data-ttu-id="0f440-145">Автоматические ассистенты и очереди звонков</span><span class="sxs-lookup"><span data-stu-id="0f440-145">Auto Attendants and Call Queues</span></span>

  <span data-ttu-id="0f440-146">В результате Covid-19 компания Contoso хотела бы предоставить поддержку receptionist, когда их сотрудники работали в удаленном режиме.</span><span class="sxs-lookup"><span data-stu-id="0f440-146">As a result of Covid-19, Contoso wanted to provide receptionist support while their staff was working remotely.</span></span> <span data-ttu-id="0f440-147">Компания Contoso использовала автоматические ассистенты и очереди звонков для управления входящими звонками на номер телефона receptionist.</span><span class="sxs-lookup"><span data-stu-id="0f440-147">Contoso used auto attendants and call queues to manage incoming calls to their receptionist's phone number.</span></span> <span data-ttu-id="0f440-148">Дополнительные сведения можно найти в статье [исследование успеха Contoso: автосекретарей и очереди звонков](voice-case-study-call-queues.md).</span><span class="sxs-lookup"><span data-stu-id="0f440-148">For more information, see [Contoso case study: Auto Attendants and Call Queues](voice-case-study-call-queues.md).</span></span>  


