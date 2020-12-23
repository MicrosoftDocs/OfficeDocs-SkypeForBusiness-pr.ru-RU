---
title: Пример дела с голосовой командой Contoso
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
description: Пример голосовой работы Teams для многоязычной корпорации
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a964075dfae514759309a81a7d7140cddd10220
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701227"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a><span data-ttu-id="787ae-103">Пример: обзор голосовой миграции Teams</span><span class="sxs-lookup"><span data-stu-id="787ae-103">Contoso case study: Teams voice migration overview</span></span>

<span data-ttu-id="787ae-104">В этой статье на примере вымышленной международной корпорации Contoso реализовано голосовое решение Teams для своей организации.</span><span class="sxs-lookup"><span data-stu-id="787ae-104">This article introduces a case study for how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span>

<span data-ttu-id="787ae-105">Компания Contoso развернула Microsoft 365 корпоративный и рассмотрела основные решения по проектированию и внедрению для следующих проектов: сеть, удостоверения, Windows 10 корпоративный, Office 365 профессиональныйplus, управление мобильными устройствами, защита информации, безопасность, обновление Skype для бизнеса до Teams, телефонной системы и аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="787ae-105">Contoso has deployed Microsoft 365 Enterprise and addressed major design decisions and implementation details for the following: networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, security, upgrade from Skype for Business to Teams, Phone System, and Audio Conferencing.</span></span>  

<span data-ttu-id="787ae-106">В этой статье основное внимание уделялось переносу пользователей локальной системы в Teams для единой коммуникации, совместной работы и голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="787ae-106">This article focuses on how Contoso migrated their on-premises users to Teams for unified communication, collaboration, and voice.</span></span> <span data-ttu-id="787ae-107">Чтобы получить фоновую информацию о том, как Contoso ускорил цифровое преобразование с помощью облачных служб Майкрософт, см. все основные статьи, которые начинаются с изучения дела [Contoso.](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="787ae-107">For background information about how Contoso accelerated their digital transformation by using Microsoft's cloud services, see all the core articles starting with the [Contoso case study overview](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span></span>

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

<span data-ttu-id="787ae-108">В ключевых статьях вы найдете следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="787ae-108">In the core articles, you'll find information on the following:</span></span>  

- <span data-ttu-id="787ae-109">Потребности ИТ-инфраструктуры Contoso</span><span class="sxs-lookup"><span data-stu-id="787ae-109">Contoso's IT infrastructure needs</span></span>
- <span data-ttu-id="787ae-110">Сеть</span><span class="sxs-lookup"><span data-stu-id="787ae-110">Networking</span></span>
- <span data-ttu-id="787ae-111">Identity </span><span class="sxs-lookup"><span data-stu-id="787ae-111">Identity</span></span>
- <span data-ttu-id="787ae-112">Windows 10 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="787ae-112">Windows 10 Enterprise</span></span>
- <span data-ttu-id="787ae-113">Office 365 профессиональный плюс</span><span class="sxs-lookup"><span data-stu-id="787ae-113">Office 365 Pro Plus</span></span>
- <span data-ttu-id="787ae-114">Управление мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="787ae-114">Mobile device management</span></span>
- <span data-ttu-id="787ae-115">Защита информации</span><span class="sxs-lookup"><span data-stu-id="787ae-115">Information protection</span></span>
- <span data-ttu-id="787ae-116">Сводка по безопасности Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="787ae-116">Summary of Microsoft 365 Enterprise security</span></span>
- <span data-ttu-id="787ae-117">Команда для совершенно секретного проекта</span><span class="sxs-lookup"><span data-stu-id="787ae-117">Team for a top-secret project</span></span>
- <span data-ttu-id="787ae-118">Сайт SharePoint Online для конфиденциальных цифровых активов</span><span class="sxs-lookup"><span data-stu-id="787ae-118">SharePoint Online site for highly confidential digital assets</span></span>

<span data-ttu-id="787ae-119">Сведения о планировании обновления можно найти в начале работы с [обновлением Microsoft Teams.](upgrade-start-here.md)</span><span class="sxs-lookup"><span data-stu-id="787ae-119">For information about planning an upgrade, you'll want to start with [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md).</span></span>

## <a name="contoso-business-goals-for-teams"></a><span data-ttu-id="787ae-120">Бизнес-цели Contoso для Teams</span><span class="sxs-lookup"><span data-stu-id="787ae-120">Contoso business goals for Teams</span></span>

<span data-ttu-id="787ae-121">Чтобы перенести своих пользователей локально в Teams для единой коммуникации, совместной работы и голосовой связи, компания Contoso принимает решение о следующих бизнес-целях:</span><span class="sxs-lookup"><span data-stu-id="787ae-121">To migrate their on-premises users to Teams for unified communication, collaboration, and voice, Contoso decided on the following business goals:</span></span>

- <span data-ttu-id="787ae-122">Включить Teams</span><span class="sxs-lookup"><span data-stu-id="787ae-122">Teams enablement</span></span> 

  <span data-ttu-id="787ae-123">Единая команда contoso для связи и совместной работы включила Teams с правильными политиками управления и обеспечения безопасной внутренней и внешней совместной работы.</span><span class="sxs-lookup"><span data-stu-id="787ae-123">Contoso's unified communication and collaboration team enabled Teams with the correct policies to govern and enable secure internal and external collaboration.</span></span> 

- <span data-ttu-id="787ae-124">Переход со Skype для бизнеса на Teams</span><span class="sxs-lookup"><span data-stu-id="787ae-124">Skype for Business to Teams upgrade</span></span> 

  <span data-ttu-id="787ae-125">Приложение Skype для бизнеса было развернуто в компании Contoso.</span><span class="sxs-lookup"><span data-stu-id="787ae-125">Skype for Business was widely deployed within Contoso.</span></span> <span data-ttu-id="787ae-126">В связи с необходимостью перенести устаревшие системы компания Contoso решила обновить пользователей Skype для бизнеса до Teams.</span><span class="sxs-lookup"><span data-stu-id="787ae-126">With the need to move off legacy systems, Contoso decided to upgrade their Skype for Business users to Teams.</span></span> <span data-ttu-id="787ae-127">Дополнительные сведения см. в примере с планом обновления Teams в [Contoso.](voice-case-study-migration-plan.md)</span><span class="sxs-lookup"><span data-stu-id="787ae-127">For more information, see [Contoso case study: Teams upgrade plan](voice-case-study-migration-plan.md).</span></span>

- <span data-ttu-id="787ae-128">Телефонная система</span><span class="sxs-lookup"><span data-stu-id="787ae-128">Phone System</span></span>  

  <span data-ttu-id="787ae-129">Skype для бизнеса с корпоративной голосовой связи был широко развернут в Contoso.</span><span class="sxs-lookup"><span data-stu-id="787ae-129">Skype for Business with enterprise voice was widely deployed within Contoso.</span></span> <span data-ttu-id="787ae-130">Из-за необходимости перенести устаревшие системы, которые находились на следующем этапе для серверов-посредников, компания Contoso перенапрали пользователей корпоративной голосовой связи Skype для бизнеса на телефонную систему.</span><span class="sxs-lookup"><span data-stu-id="787ae-130">With the need to move off legacy systems that were the next hop for their mediation servers, Contoso migrated their Skype for Business enterprise voice users to Phone System.</span></span> <span data-ttu-id="787ae-131">На сайтах Contoso использовались план звонков Майкрософт, прямая маршрутия телефонной системы или сочетание обоих этих продуктов.</span><span class="sxs-lookup"><span data-stu-id="787ae-131">Contoso sites used Microsoft Calling Plan, Phone System Direct Routing, or a combination of both.</span></span> <span data-ttu-id="787ae-132">Дополнительные сведения см. в примере [работы с Contoso: телефонная система.](voice-case-study-phone-system.md)</span><span class="sxs-lookup"><span data-stu-id="787ae-132">For more information, see [Contoso case study: Phone System](voice-case-study-phone-system.md).</span></span>

- <span data-ttu-id="787ae-133">Маршрутизация на основе расположения</span><span class="sxs-lookup"><span data-stu-id="787ae-133">Location-Based Routing</span></span> 

  <span data-ttu-id="787ae-134">Так как расположения офисов в странах, регулируемых телефонией, необходимо создать в Contoso Location-Based маршруты, присутствующие в Skype для бизнеса при развертывании телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="787ae-134">With office locations in telephony-regulated countries, Contoso needed to recreate the Location-Based Routing that was present in Skype for Business in their Phone System deployment.</span></span> <span data-ttu-id="787ae-135">Дополнительные сведения см. в примере [contoso: Location-Based маршруты.](voice-case-study-location-based-routing.md)</span><span class="sxs-lookup"><span data-stu-id="787ae-135">For more information, see [Contoso case study: Location-Based Routing](voice-case-study-location-based-routing.md).</span></span>

- <span data-ttu-id="787ae-136">Экстренный вызов</span><span class="sxs-lookup"><span data-stu-id="787ae-136">Emergency Calling</span></span> 

  <span data-ttu-id="787ae-137">Если была реализована прямая маршрутия, Contoso настроил экстренные вызовы с утвержденными сторонними лицами.</span><span class="sxs-lookup"><span data-stu-id="787ae-137">Where Direct Routing was implemented, Contoso set up emergency calling with approved third parties.</span></span> <span data-ttu-id="787ae-138">Дополнительные сведения см. в примере [contoso: экстренные вызовы.](voice-case-study-emergency-calling.md)</span><span class="sxs-lookup"><span data-stu-id="787ae-138">For more information, see [Contoso case study: Emergency Calling](voice-case-study-emergency-calling.md).</span></span>

- <span data-ttu-id="787ae-139">Аудиоконференция</span><span class="sxs-lookup"><span data-stu-id="787ae-139">Audio Conferencing</span></span> 

  <span data-ttu-id="787ae-140">Contoso настроил номера служб аудиоконференций, которые были установлены на телефоне поставщика услуг SIP.</span><span class="sxs-lookup"><span data-stu-id="787ae-140">Contoso set up Audio Conferencing service numbers that were hosted on their SIP trunk to their PSTN provider.</span></span> <span data-ttu-id="787ae-141">Дополнительные сведения см. в примере [contoso: аудиоконференция.](voice-case-study-audio-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="787ae-141">For more information, see [Contoso case study: Audio Conferencing](voice-case-study-audio-conferencing.md).</span></span> 

- <span data-ttu-id="787ae-142">Local Media Optimization</span><span class="sxs-lookup"><span data-stu-id="787ae-142">Local Media Optimization</span></span> 

  <span data-ttu-id="787ae-143">Компания Contoso воспользовалась оптимизацией локальных мультимедиа в местах, где у них была одна прямая линия связи с телефонной системой Майкрософт, которая была задейна удаленными сайтами.</span><span class="sxs-lookup"><span data-stu-id="787ae-143">Contoso took advantage of Local Media Optimization in locations where they had one direct route trunk to Microsoft Phone System that was leveraged by remote sites.</span></span> <span data-ttu-id="787ae-144">Дополнительные сведения см. в планах оптимизации локальных [мультимедиа](direct-routing-media-optimization.md) и настройки оптимизации [локальных мультимедиа.](direct-routing-media-optimization-configure.md)</span><span class="sxs-lookup"><span data-stu-id="787ae-144">For more information, see [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).</span></span>

- <span data-ttu-id="787ae-145">Автоотводы и очереди вызовов</span><span class="sxs-lookup"><span data-stu-id="787ae-145">Auto Attendants and Call Queues</span></span>

  <span data-ttu-id="787ae-146">В результате covid-19 contoso хотел предоставлять поддержку в приемной, пока сотрудники работают удаленно.</span><span class="sxs-lookup"><span data-stu-id="787ae-146">As a result of Covid-19, Contoso wanted to provide receptionist support while their staff was working remotely.</span></span> <span data-ttu-id="787ae-147">Для управления входящие вызовами на номер телефона в приемной в Contoso использовались автоответы и очереди звонков.</span><span class="sxs-lookup"><span data-stu-id="787ae-147">Contoso used auto attendants and call queues to manage incoming calls to their receptionist's phone number.</span></span> <span data-ttu-id="787ae-148">Дополнительные сведения см. в примере работы [с Contoso: автоотетары и очереди вызовов.](voice-case-study-call-queues.md)</span><span class="sxs-lookup"><span data-stu-id="787ae-148">For more information, see [Contoso case study: Auto Attendants and Call Queues](voice-case-study-call-queues.md).</span></span>  


