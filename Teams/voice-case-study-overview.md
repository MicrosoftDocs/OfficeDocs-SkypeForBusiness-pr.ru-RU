---
title: 'Teams голосом: пример: Contoso'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365solution-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams на примере голосовой почты для многоязычной корпорации
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19200ec5ab1556b0f2b4fda2f389e60bc236015b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097495"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a><span data-ttu-id="9217e-103">Пример: обзор переноса голосовой Teams Contoso</span><span class="sxs-lookup"><span data-stu-id="9217e-103">Contoso case study: Teams voice migration overview</span></span>

<span data-ttu-id="9217e-104">В этой статье на примере вымышленной многоязычной корпорации Contoso реализовано Teams голосового решения для своей организации.</span><span class="sxs-lookup"><span data-stu-id="9217e-104">This article introduces a case study for how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span>

<span data-ttu-id="9217e-105">Компания Contoso развернула Microsoft 365 корпоративный решения по проектированию и внедрению для следующих проектов: сеть, удостоверения, Windows 10 Корпоративная, Office 365 профессиональный плюс, управление мобильными устройствами, защита информации, безопасность, обновление с Skype для бизнеса до Teams, телефонная система и аудиоконференцию.</span><span class="sxs-lookup"><span data-stu-id="9217e-105">Contoso has deployed Microsoft 365 Enterprise and addressed major design decisions and implementation details for the following: networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, security, upgrade from Skype for Business to Teams, Phone System, and Audio Conferencing.</span></span>  

<span data-ttu-id="9217e-106">В этой статье посвящено, как Contoso перенес своих пользователей на Teams для единой коммуникации, совместной работы и голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="9217e-106">This article focuses on how Contoso migrated their on-premises users to Teams for unified communication, collaboration, and voice.</span></span> <span data-ttu-id="9217e-107">Чтобы получить справочную информацию о том, как Contoso ускорил цифровое преобразование с помощью облачных служб Майкрософт, см. все основные статьи, начиная с обзорного исследования [Contoso.](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="9217e-107">For background information about how Contoso accelerated their digital transformation by using Microsoft's cloud services, see all the core articles starting with the [Contoso case study overview](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span></span>

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

<span data-ttu-id="9217e-108">В ключевых статьях вы найдете сведения о следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="9217e-108">In the core articles, you'll find information on the following:</span></span>  

- <span data-ttu-id="9217e-109">Потребности ИТ-инфраструктуры Contoso</span><span class="sxs-lookup"><span data-stu-id="9217e-109">Contoso's IT infrastructure needs</span></span>
- <span data-ttu-id="9217e-110">Сети</span><span class="sxs-lookup"><span data-stu-id="9217e-110">Networking</span></span>
- <span data-ttu-id="9217e-111">Identity </span><span class="sxs-lookup"><span data-stu-id="9217e-111">Identity</span></span>
- <span data-ttu-id="9217e-112">Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="9217e-112">Windows 10 Enterprise</span></span>
- <span data-ttu-id="9217e-113">Office 365 Pro плюс</span><span class="sxs-lookup"><span data-stu-id="9217e-113">Office 365 Pro Plus</span></span>
- <span data-ttu-id="9217e-114">Управление мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="9217e-114">Mobile device management</span></span>
- <span data-ttu-id="9217e-115">Защита информации</span><span class="sxs-lookup"><span data-stu-id="9217e-115">Information protection</span></span>
- <span data-ttu-id="9217e-116">Сводка по Microsoft 365 корпоративный безопасности</span><span class="sxs-lookup"><span data-stu-id="9217e-116">Summary of Microsoft 365 Enterprise security</span></span>
- <span data-ttu-id="9217e-117">Группа для совершенно секретного проекта</span><span class="sxs-lookup"><span data-stu-id="9217e-117">Team for a top-secret project</span></span>
- <span data-ttu-id="9217e-118">SharePoint Веб-сайт для конфиденциальных цифровых активов</span><span class="sxs-lookup"><span data-stu-id="9217e-118">SharePoint Online site for highly confidential digital assets</span></span>

<span data-ttu-id="9217e-119">Сведения о планировании обновления можно найти в начале работы с Microsoft Teams [обновления.](upgrade-start-here.md)</span><span class="sxs-lookup"><span data-stu-id="9217e-119">For information about planning an upgrade, you'll want to start with [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md).</span></span>

## <a name="contoso-business-goals-for-teams"></a><span data-ttu-id="9217e-120">Бизнес-цели Contoso для Teams</span><span class="sxs-lookup"><span data-stu-id="9217e-120">Contoso business goals for Teams</span></span>

<span data-ttu-id="9217e-121">Чтобы перенести своих пользователей из локальной сети в Teams для единой коммуникации, совместной работы и голосовой связи, Компания Contoso принимает решение о следующих бизнес-целях:</span><span class="sxs-lookup"><span data-stu-id="9217e-121">To migrate their on-premises users to Teams for unified communication, collaboration, and voice, Contoso decided on the following business goals:</span></span>

- <span data-ttu-id="9217e-122">Teams включить</span><span class="sxs-lookup"><span data-stu-id="9217e-122">Teams enablement</span></span> 

  <span data-ttu-id="9217e-123">Единая команда Contoso по связи и совместной работе включила Teams с правильными политиками для управления и обеспечения безопасной внутренней и внешней совместной работы.</span><span class="sxs-lookup"><span data-stu-id="9217e-123">Contoso's unified communication and collaboration team enabled Teams with the correct policies to govern and enable secure internal and external collaboration.</span></span> 

- <span data-ttu-id="9217e-124">Переход со Skype для бизнеса на Teams</span><span class="sxs-lookup"><span data-stu-id="9217e-124">Skype for Business to Teams upgrade</span></span> 

  <span data-ttu-id="9217e-125">Skype для бизнеса была развернута в Contoso.</span><span class="sxs-lookup"><span data-stu-id="9217e-125">Skype for Business was widely deployed within Contoso.</span></span> <span data-ttu-id="9217e-126">В связи с необходимостью отключить устаревшие системы компания Contoso решила обновить Skype для бизнеса пользователей до Teams.</span><span class="sxs-lookup"><span data-stu-id="9217e-126">With the need to move off legacy systems, Contoso decided to upgrade their Skype for Business users to Teams.</span></span> <span data-ttu-id="9217e-127">Дополнительные сведения см. в примере с планом обновления [Contoso:](voice-case-study-migration-plan.md)Teams обновления.</span><span class="sxs-lookup"><span data-stu-id="9217e-127">For more information, see [Contoso case study: Teams upgrade plan](voice-case-study-migration-plan.md).</span></span>

- <span data-ttu-id="9217e-128">Телефонная система</span><span class="sxs-lookup"><span data-stu-id="9217e-128">Phone System</span></span>  

  <span data-ttu-id="9217e-129">Skype для бизнеса корпоративной голосовой связи широко использовалась в Contoso.</span><span class="sxs-lookup"><span data-stu-id="9217e-129">Skype for Business with enterprise voice was widely deployed within Contoso.</span></span> <span data-ttu-id="9217e-130">Из-за необходимости переместить устаревшие системы, которые были следующим шагом для серверов-посредников, Contoso перенапрался на Skype для бизнеса пользователей корпоративной голосовой связи в телефонная система.</span><span class="sxs-lookup"><span data-stu-id="9217e-130">With the need to move off legacy systems that were the next hop for their mediation servers, Contoso migrated their Skype for Business enterprise voice users to Phone System.</span></span> <span data-ttu-id="9217e-131">Сайты Contoso использовали план звонков Майкрософт, телефонная система прямую маршрутику или сочетание обоих этих звонков.</span><span class="sxs-lookup"><span data-stu-id="9217e-131">Contoso sites used Microsoft Calling Plan, Phone System Direct Routing, or a combination of both.</span></span> <span data-ttu-id="9217e-132">Дополнительные сведения см. в примере [с contoso: телефонная система.](voice-case-study-phone-system.md)</span><span class="sxs-lookup"><span data-stu-id="9217e-132">For more information, see [Contoso case study: Phone System](voice-case-study-phone-system.md).</span></span>

- <span data-ttu-id="9217e-133">Маршрутизация на основе расположения</span><span class="sxs-lookup"><span data-stu-id="9217e-133">Location-Based Routing</span></span> 

  <span data-ttu-id="9217e-134">Благодаря расположениям офисов в странах, где есть телефонная телефония, contoso требовалось воссоздать Location-Based маршруты, которые были Skype для бизнеса в телефонная система развертывания.</span><span class="sxs-lookup"><span data-stu-id="9217e-134">With office locations in telephony-regulated countries, Contoso needed to recreate the Location-Based Routing that was present in Skype for Business in their Phone System deployment.</span></span> <span data-ttu-id="9217e-135">Дополнительные сведения см. в примере [с contoso: Location-Based Routing.](voice-case-study-location-based-routing.md)</span><span class="sxs-lookup"><span data-stu-id="9217e-135">For more information, see [Contoso case study: Location-Based Routing](voice-case-study-location-based-routing.md).</span></span>

- <span data-ttu-id="9217e-136">Экстренный вызов</span><span class="sxs-lookup"><span data-stu-id="9217e-136">Emergency Calling</span></span> 

  <span data-ttu-id="9217e-137">Если была реализована прямая маршрутия, Contoso настроил экстренные вызовы у утвержденных сторонних сторон.</span><span class="sxs-lookup"><span data-stu-id="9217e-137">Where Direct Routing was implemented, Contoso set up emergency calling with approved third parties.</span></span> <span data-ttu-id="9217e-138">Дополнительные сведения см. в примере [с Contoso: экстренные вызовы.](voice-case-study-emergency-calling.md)</span><span class="sxs-lookup"><span data-stu-id="9217e-138">For more information, see [Contoso case study: Emergency Calling](voice-case-study-emergency-calling.md).</span></span>

- <span data-ttu-id="9217e-139">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="9217e-139">Audio Conferencing</span></span> 

  <span data-ttu-id="9217e-140">Contoso настроил номера служб аудиоконференций, которые были установлены на их телефоне SIP, на поставщика услуг STN.</span><span class="sxs-lookup"><span data-stu-id="9217e-140">Contoso set up Audio Conferencing service numbers that were hosted on their SIP trunk to their PSTN provider.</span></span> <span data-ttu-id="9217e-141">Дополнительные сведения см. в примере [с contoso: аудиоконференция.](voice-case-study-audio-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="9217e-141">For more information, see [Contoso case study: Audio Conferencing](voice-case-study-audio-conferencing.md).</span></span> 

- <span data-ttu-id="9217e-142">Оптимизация локальных мультимедиа</span><span class="sxs-lookup"><span data-stu-id="9217e-142">Local Media Optimization</span></span> 

  <span data-ttu-id="9217e-143">Contoso воспользовался оптимизацией локальных мультимедиа в местах, где у них был один прямой маршрут линии связи с Телефон (Майкрософт), которая была задейна удаленными сайтами.</span><span class="sxs-lookup"><span data-stu-id="9217e-143">Contoso took advantage of Local Media Optimization in locations where they had one direct route trunk to Microsoft Phone System that was leveraged by remote sites.</span></span> <span data-ttu-id="9217e-144">Дополнительные сведения см. в настройках Плана оптимизации локальных [мультимедиа](direct-routing-media-optimization.md) и [Настройка оптимизации локальных мультимедиа.](direct-routing-media-optimization-configure.md)</span><span class="sxs-lookup"><span data-stu-id="9217e-144">For more information, see [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).</span></span>

- <span data-ttu-id="9217e-145">Автоспутники и очереди вызовов</span><span class="sxs-lookup"><span data-stu-id="9217e-145">Auto Attendants and Call Queues</span></span>

  <span data-ttu-id="9217e-146">В результате covid-19 Contoso хотел предоставлять поддержку в приемной во время удаленной работы сотрудников.</span><span class="sxs-lookup"><span data-stu-id="9217e-146">As a result of Covid-19, Contoso wanted to provide receptionist support while their staff was working remotely.</span></span> <span data-ttu-id="9217e-147">Contoso использовал автоответы и очереди звонков для управления входящие звонки на номер телефона своего регистратора.</span><span class="sxs-lookup"><span data-stu-id="9217e-147">Contoso used auto attendants and call queues to manage incoming calls to their receptionist's phone number.</span></span> <span data-ttu-id="9217e-148">Дополнительные сведения см. в примере работы с Contoso: автоспутники [и очереди вызовов.](voice-case-study-call-queues.md)</span><span class="sxs-lookup"><span data-stu-id="9217e-148">For more information, see [Contoso case study: Auto Attendants and Call Queues](voice-case-study-call-queues.md).</span></span>