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
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams на примере голосовой почты для многоязычной корпорации
appliesto:
- Microsoft Teams
ms.openlocfilehash: b0da56bc0da083654a0cd694bd5983f2fe4fe515
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093729"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="718ad-103">Пример: планирование обновления Teams Contoso</span><span class="sxs-lookup"><span data-stu-id="718ad-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="718ad-104">При переходе с Skype для бизнеса на Teams компания Contoso хочет обеспечить простой переход для конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="718ad-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="718ad-105">Вместо того чтобы одновременно Teams все пользователи, они решили настроить гибридное подключение и использовать перекрывающиеся возможности для перемещения пользователей в Teams.</span><span class="sxs-lookup"><span data-stu-id="718ad-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="718ad-106">Это позволило пользователям в Teams и Skype для бизнеса локально делиться информацией о присутствии и общаться.</span><span class="sxs-lookup"><span data-stu-id="718ad-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="718ad-107">Когда пользователи ввели пилотный проект для телефонная система, они были перемещены в режим Teams только для пользователей.</span><span class="sxs-lookup"><span data-stu-id="718ad-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="718ad-108">Чтобы понять основные понятия обновления, методов и режимов, Contoso прочитает следующие статьи:</span><span class="sxs-lookup"><span data-stu-id="718ad-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="718ad-109">Начало перехода на Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="718ad-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="718ad-110">Стратегии обновления для ИТ-администраторов</span><span class="sxs-lookup"><span data-stu-id="718ad-110">Upgrade strategies for IT administrators</span></span>](upgrade-to-teams-on-prem-implement.md) 
- [<span data-ttu-id="718ad-111">Руководство по миграции и взаимосвязи</span><span class="sxs-lookup"><span data-stu-id="718ad-111">Migration and interoperability guidance</span></span>](migration-interop-guidance-for-teams-with-skype.md)
 
<span data-ttu-id="718ad-112">Компания Contoso также участвовала в сеансе Ignite 2019, в котором был проектирование пути от Skype для бизнеса [до Teams.](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="718ad-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="718ad-113">Contoso узнал о:</span><span class="sxs-lookup"><span data-stu-id="718ad-113">Contoso learned about:</span></span>

- <span data-ttu-id="718ad-114">Основные понятия, такие как interoperability, federation и upgrade behavior</span><span class="sxs-lookup"><span data-stu-id="718ad-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="718ad-115">Режимы сосуществования и управление на основе TeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="718ad-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="718ad-116">Пользовательский интерфейс для:</span><span class="sxs-lookup"><span data-stu-id="718ad-116">End user experience for:</span></span> 

  - <span data-ttu-id="718ad-117">Чат и вызовы</span><span class="sxs-lookup"><span data-stu-id="718ad-117">Chat and Calling</span></span> 

  - <span data-ttu-id="718ad-118">Планирование собраний</span><span class="sxs-lookup"><span data-stu-id="718ad-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="718ad-119">Доступность функций совместной работы в Teams клиентах</span><span class="sxs-lookup"><span data-stu-id="718ad-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="718ad-120">Чтобы спланировать и настроить гибридное подключение, первым шагом в перемещении локальной [](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) среды в [](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) облако contoso является планирование гибридного подключения и Настройка гибридного подключения, чтобы понять, как:</span><span class="sxs-lookup"><span data-stu-id="718ad-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="718ad-121">Настройте службу локальной среды для федерации с помощью Office 365.</span><span class="sxs-lookup"><span data-stu-id="718ad-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="718ad-122">Настройте в своей локальной среде доверительные Office 365 и встройте общее адресное пространство SIP с помощью Office 365</span><span class="sxs-lookup"><span data-stu-id="718ad-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="718ad-123">Включить общее адресное пространство SIP в Office 365 клиента.</span><span class="sxs-lookup"><span data-stu-id="718ad-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="718ad-124">Используйте режим "Острова" во время технического пилотного проекта.</span><span class="sxs-lookup"><span data-stu-id="718ad-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="718ad-125">Переключение пользователей в режим TeamsOnly после включения телефонная система.</span><span class="sxs-lookup"><span data-stu-id="718ad-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="718ad-126">Режим TeamsOnly требуется для планирования звонков и прямой маршрутации.</span><span class="sxs-lookup"><span data-stu-id="718ad-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span>