---
title: Использование шаблонов Teams для розничной торговли в Центре администрирования
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
description: Узнайте, как использовать шаблоны Teams, чтобы создавать структуры команд для розничной торговли путем предоставления готовых параметров, каналов и предварительно установленных приложений с помощью Центра администрирования.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b40da8fd1cc8182d0e5ad80c30f5a459f17d26f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662644"
---
# <a name="use-teams-retail-templates-in-the-admin-center"></a><span data-ttu-id="b2942-103">Использование шаблонов Teams для розничной торговли в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="b2942-103">Use Teams retail templates in the admin center</span></span>

<span data-ttu-id="b2942-104">Шаблоны Teams позволяют быстро и легко создавать команды, предоставляя готовый шаблон параметров, каналов и предварительно установленных приложений.</span><span class="sxs-lookup"><span data-stu-id="b2942-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="b2942-105">Шаблоны Teams содержат предварительно созданные определения структур команд, предназначенные для розничной торговли.</span><span class="sxs-lookup"><span data-stu-id="b2942-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="b2942-106">Вы можете использовать шаблоны Teams, чтобы быстро создавать команды, подходящие для розничной торговли, и развертывать их в организации.</span><span class="sxs-lookup"><span data-stu-id="b2942-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="b2942-107">Вы также можете расширить шаблоны Teams, чтобы создавать команды, адаптированные под конкретные потребности вашей организации.</span><span class="sxs-lookup"><span data-stu-id="b2942-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="b2942-108">В этой статье вы познакомитесь с каждым шаблоном Teams и рекомендуемыми способами их использования.</span><span class="sxs-lookup"><span data-stu-id="b2942-108">In this article, we'll introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="b2942-109">Эта статья предназначена для вас, если вы отвечаете за планирование, развертывание и управление несколькими командами в своей организации розничной торговли.</span><span class="sxs-lookup"><span data-stu-id="b2942-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="b2942-110">Предполагается, что вы уже развернули службу Teams в своей организации.</span><span class="sxs-lookup"><span data-stu-id="b2942-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="b2942-111">Если вы еще не развернули Teams, см. статью [Как развернуть Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b2942-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="b2942-112">Другие общие сведения о шаблонах команд см. в статье [Начало работы с шаблонами Teams](get-started-with-teams-templates-in-the-admin-console.md).</span><span class="sxs-lookup"><span data-stu-id="b2942-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="organize-a-store"></a><span data-ttu-id="b2942-113">Организация магазина</span><span class="sxs-lookup"><span data-stu-id="b2942-113">Organize a store</span></span>

<span data-ttu-id="b2942-114">Объедините своих сотрудников розничной торговли в едином интерфейсе для управления задачами, обмена документами и решения проблем клиентов.</span><span class="sxs-lookup"><span data-stu-id="b2942-114">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="b2942-115">Интегрируйте дополнительные приложения для упрощения начала и завершения смен.</span><span class="sxs-lookup"><span data-stu-id="b2942-115">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="b2942-116">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="b2942-116">Base template type</span></span> |<span data-ttu-id="b2942-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="b2942-117">baseTemplateId</span></span> | <span data-ttu-id="b2942-118">Свойства базового шаблона</span><span class="sxs-lookup"><span data-stu-id="b2942-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="b2942-119">Организация магазина</span><span class="sxs-lookup"><span data-stu-id="b2942-119">Organize a store</span></span>|`retailStore`|<span data-ttu-id="b2942-120">Каналы:</span><span class="sxs-lookup"><span data-stu-id="b2942-120">Channels:</span></span> <ul><li><span data-ttu-id="b2942-121">Общий</span><span class="sxs-lookup"><span data-stu-id="b2942-121">General</span></span><li><span data-ttu-id="b2942-122">Передача смены</span><span class="sxs-lookup"><span data-stu-id="b2942-122">Shift handoff</span></span></li><li><span data-ttu-id="b2942-123">Обучение</span><span class="sxs-lookup"><span data-stu-id="b2942-123">Learning</span></span></li></ul> <span data-ttu-id="b2942-124">Приложения:</span><span class="sxs-lookup"><span data-stu-id="b2942-124">Apps:</span></span> <ul><li><span data-ttu-id="b2942-125">Вики</span><span class="sxs-lookup"><span data-stu-id="b2942-125">Wiki</span></span></li></ul>|
||||

## <a name="manager-collaboration"></a><span data-ttu-id="b2942-126">Взаимодействие руководителей</span><span class="sxs-lookup"><span data-stu-id="b2942-126">Manager Collaboration</span></span>

<span data-ttu-id="b2942-127">Шаблон взаимодействия руководителей идеально подходит, чтобы создать команду для группы руководителей с целью совместной работы в магазинах, регионах и т. д. Например, если в вашей организации есть регионы, вы можете создать команду взаимодействия руководителей для Московской области и включить в нее всех руководителей магазинов в этом регионе, а также регионального руководителя.</span><span class="sxs-lookup"><span data-stu-id="b2942-127">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="b2942-128">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="b2942-128">Base template type</span></span>| <span data-ttu-id="b2942-129">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="b2942-129">baseTemplateId</span></span> | <span data-ttu-id="b2942-130">Свойства базового шаблона</span><span class="sxs-lookup"><span data-stu-id="b2942-130">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="b2942-131">Розничная торговля — взаимодействие руководителей</span><span class="sxs-lookup"><span data-stu-id="b2942-131">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="b2942-132">Каналы:</span><span class="sxs-lookup"><span data-stu-id="b2942-132">Channels:</span></span> <ul><li><span data-ttu-id="b2942-133">Общий</span><span class="sxs-lookup"><span data-stu-id="b2942-133">General</span></span><li><span data-ttu-id="b2942-134">Операции</span><span class="sxs-lookup"><span data-stu-id="b2942-134">Operations</span></span></li><li><span data-ttu-id="b2942-135">Обучение</span><span class="sxs-lookup"><span data-stu-id="b2942-135">Learning</span></span></li></ul> <span data-ttu-id="b2942-136">Приложения:</span><span class="sxs-lookup"><span data-stu-id="b2942-136">Apps:</span></span> <ul><li><span data-ttu-id="b2942-137">Вики</span><span class="sxs-lookup"><span data-stu-id="b2942-137">Wiki</span></span></li></ul>|
||||
