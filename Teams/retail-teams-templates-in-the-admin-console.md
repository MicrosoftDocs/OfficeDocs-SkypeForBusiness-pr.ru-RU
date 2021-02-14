---
title: Использование шаблонов в розничной сети Teams в Центре администрирования
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Узнайте, как с помощью шаблонов Teams создавать структуры групп, разработанные для потребностей розничного продавца, предоставляя предопределять параметры, каналы и предварительно установленные приложения с помощью Центра администрирования.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b40da8fd1cc8182d0e5ad80c30f5a459f17d26f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662644"
---
# <a name="use-teams-retail-templates-in-the-admin-center"></a><span data-ttu-id="53b9b-103">Использование шаблонов в розничной сети Teams в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="53b9b-103">Use Teams retail templates in the admin center</span></span>

<span data-ttu-id="53b9b-104">Шаблоны Teams позволяют быстро и легко создавать команды, предоставляя предопределяющий шаблон настроек, каналов и предварительно установленных приложений.</span><span class="sxs-lookup"><span data-stu-id="53b9b-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="53b9b-105">Шаблоны Teams имеют встроенные определения структур групп, разработанных для потребностей розничного продавца.</span><span class="sxs-lookup"><span data-stu-id="53b9b-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="53b9b-106">Вы можете использовать шаблоны Teams для быстрого создания типов команд, которые хорошо работают для розничных продавцов, и их развертывания в организации.</span><span class="sxs-lookup"><span data-stu-id="53b9b-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="53b9b-107">Вы также можете расширить шаблоны Teams для создания команд, специально разработанных для ваших организационных потребностей.</span><span class="sxs-lookup"><span data-stu-id="53b9b-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="53b9b-108">В этой статье мы познакомим вас с каждым из шаблонов Teams и рекомендациями по их использованию.</span><span class="sxs-lookup"><span data-stu-id="53b9b-108">In this article, we'll introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="53b9b-109">Эта статья для вас, если вы отвечаете за планирование, развертывание и управление несколькими командами в розничной сети.</span><span class="sxs-lookup"><span data-stu-id="53b9b-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="53b9b-110">Мы предполагаем, что вы уже развернули службу Teams в своей организации.</span><span class="sxs-lookup"><span data-stu-id="53b9b-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="53b9b-111">Если вы еще не начали работу с Teams, начните с чтения этой [статьи.](How-to-roll-out-teams.md)</span><span class="sxs-lookup"><span data-stu-id="53b9b-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="53b9b-112">Подробнее о шаблонах команд читайте в теме "Начало [работы с шаблонами Teams".](get-started-with-teams-templates-in-the-admin-console.md)</span><span class="sxs-lookup"><span data-stu-id="53b9b-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="organize-a-store"></a><span data-ttu-id="53b9b-113">Организация магазина</span><span class="sxs-lookup"><span data-stu-id="53b9b-113">Organize a store</span></span>

<span data-ttu-id="53b9b-114">Централизованное управление задачами, совместное управление документами и решение проблем клиентов.</span><span class="sxs-lookup"><span data-stu-id="53b9b-114">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="53b9b-115">Интеграция дополнительных приложений для упорядочения процессов & смен.</span><span class="sxs-lookup"><span data-stu-id="53b9b-115">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="53b9b-116">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="53b9b-116">Base template type</span></span> |<span data-ttu-id="53b9b-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="53b9b-117">baseTemplateId</span></span> | <span data-ttu-id="53b9b-118">Свойства, которые доступны с этим базовым шаблоном</span><span class="sxs-lookup"><span data-stu-id="53b9b-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="53b9b-119">Организация магазина</span><span class="sxs-lookup"><span data-stu-id="53b9b-119">Organize a store</span></span>|`retailStore`|<span data-ttu-id="53b9b-120">Каналы:</span><span class="sxs-lookup"><span data-stu-id="53b9b-120">Channels:</span></span> <ul><li><span data-ttu-id="53b9b-121">Общий</span><span class="sxs-lookup"><span data-stu-id="53b9b-121">General</span></span><li><span data-ttu-id="53b9b-122">Смена передачи</span><span class="sxs-lookup"><span data-stu-id="53b9b-122">Shift handoff</span></span></li><li><span data-ttu-id="53b9b-123">Обучение</span><span class="sxs-lookup"><span data-stu-id="53b9b-123">Learning</span></span></li></ul> <span data-ttu-id="53b9b-124">Приложения:</span><span class="sxs-lookup"><span data-stu-id="53b9b-124">Apps:</span></span> <ul><li><span data-ttu-id="53b9b-125">Вики-сайт</span><span class="sxs-lookup"><span data-stu-id="53b9b-125">Wiki</span></span></li></ul>|
||||

## <a name="manager-collaboration"></a><span data-ttu-id="53b9b-126">Совместная работа руководителя</span><span class="sxs-lookup"><span data-stu-id="53b9b-126">Manager Collaboration</span></span>

<span data-ttu-id="53b9b-127">Шаблон совместной работы руководителя идеально подходит для создания команды для группы руководителей для совместной работы в магазинах и регионах и т. д. Например, если в вашей организации есть регионы, вы можете создать команду совместной работы руководителя для Новской области и включить в нее всех менеджеров магазинов в этом регионе, а также регионального руководителя в этом регионе.</span><span class="sxs-lookup"><span data-stu-id="53b9b-127">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="53b9b-128">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="53b9b-128">Base template type</span></span>| <span data-ttu-id="53b9b-129">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="53b9b-129">baseTemplateId</span></span> | <span data-ttu-id="53b9b-130">Свойства, которые доступны с этим базовым шаблоном</span><span class="sxs-lookup"><span data-stu-id="53b9b-130">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="53b9b-131">Розничная торговля — совместная работа руководителя</span><span class="sxs-lookup"><span data-stu-id="53b9b-131">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="53b9b-132">Каналы:</span><span class="sxs-lookup"><span data-stu-id="53b9b-132">Channels:</span></span> <ul><li><span data-ttu-id="53b9b-133">Общий</span><span class="sxs-lookup"><span data-stu-id="53b9b-133">General</span></span><li><span data-ttu-id="53b9b-134">Операции</span><span class="sxs-lookup"><span data-stu-id="53b9b-134">Operations</span></span></li><li><span data-ttu-id="53b9b-135">Обучение</span><span class="sxs-lookup"><span data-stu-id="53b9b-135">Learning</span></span></li></ul> <span data-ttu-id="53b9b-136">Приложения:</span><span class="sxs-lookup"><span data-stu-id="53b9b-136">Apps:</span></span> <ul><li><span data-ttu-id="53b9b-137">Вики-сайт</span><span class="sxs-lookup"><span data-stu-id="53b9b-137">Wiki</span></span></li></ul>|
||||
