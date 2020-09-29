---
title: Использование розничных шаблонов Teams в консоли администрирования
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
description: Сведения о том, как использовать шаблоны групп для создания структур групп, разработанных для продавцов, с помощью консоли администрирования, предоставляя предварительно определенные параметры, каналы и предустановленные приложения.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c9e0a75c558888fcd1c558eb3f87718a85e22471
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294545"
---
# <a name="use-teams-retail-templates-in-the-admin-console"></a><span data-ttu-id="f463f-103">Использование розничных шаблонов Teams в консоли администрирования</span><span class="sxs-lookup"><span data-stu-id="f463f-103">Use Teams retail templates in the admin console</span></span>

<span data-ttu-id="f463f-104">Шаблоны групп позволяют быстро и легко создавать группы, предоставляя готовый шаблон параметров, каналов и предустановленных приложений.</span><span class="sxs-lookup"><span data-stu-id="f463f-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="f463f-105">Шаблоны групп имеют предварительно составленные определения структур групп, разработанных в отношении потребностей розничной торговли.</span><span class="sxs-lookup"><span data-stu-id="f463f-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="f463f-106">Шаблоны Teams можно использовать для быстрого создания типов рабочих групп, которые подходят для розничных продавцов, и их развертывания в Организации.</span><span class="sxs-lookup"><span data-stu-id="f463f-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="f463f-107">Вы также можете расширять шаблоны групп, чтобы создавать группы, адаптированные в соответствии с конкретными потребностями Организации.</span><span class="sxs-lookup"><span data-stu-id="f463f-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="f463f-108">В этой статье мы рассмотрим каждый из шаблонов Teams и как мы рекомендуем использовать их.</span><span class="sxs-lookup"><span data-stu-id="f463f-108">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="f463f-109">Эта статья предназначена для вас, если вы несете ответственность за планирование, развертывание и управление несколькими группами в рамках своей организации розничной торговли.</span><span class="sxs-lookup"><span data-stu-id="f463f-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="f463f-110">Предполагается, что в вашей организации уже развернута служба Teams.</span><span class="sxs-lookup"><span data-stu-id="f463f-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="f463f-111">Если вы еще не выполнили развертывание групп, начните с ознакомления с [развертыванием Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="f463f-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="f463f-112">Дополнительные сведения о шаблонах групп можно найти в разделе Начало [работы с шаблонами групп](get-started-with-teams-templates-in-the-admin-console.md).</span><span class="sxs-lookup"><span data-stu-id="f463f-112">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="organize-a-store"></a><span data-ttu-id="f463f-113">Упорядочение магазина</span><span class="sxs-lookup"><span data-stu-id="f463f-113">Organize a store</span></span>

<span data-ttu-id="f463f-114">Централизованное управление задачами, общий доступ к документам и устранение проблем с клиентами.</span><span class="sxs-lookup"><span data-stu-id="f463f-114">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="f463f-115">Интегрируйте дополнительные приложения, чтобы ускорить смену начала & конечные процессы.</span><span class="sxs-lookup"><span data-stu-id="f463f-115">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="f463f-116">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="f463f-116">Base template type</span></span> |<span data-ttu-id="f463f-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="f463f-117">baseTemplateId</span></span> | <span data-ttu-id="f463f-118">Свойства, которые поставляются с этим базовым шаблоном</span><span class="sxs-lookup"><span data-stu-id="f463f-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="f463f-119">Упорядочение магазина</span><span class="sxs-lookup"><span data-stu-id="f463f-119">Organize a store</span></span>| `retailStore`|<span data-ttu-id="f463f-120">Дистрибутор</span><span class="sxs-lookup"><span data-stu-id="f463f-120">Channels:</span></span> <ul><li><span data-ttu-id="f463f-121">Общий</span><span class="sxs-lookup"><span data-stu-id="f463f-121">General</span></span><li><span data-ttu-id="f463f-122">Переносится смена</span><span class="sxs-lookup"><span data-stu-id="f463f-122">Shift handoff</span></span></li><li><span data-ttu-id="f463f-123">Образователь</span><span class="sxs-lookup"><span data-stu-id="f463f-123">Learning</span></span></li></ul> <span data-ttu-id="f463f-124">Приложения</span><span class="sxs-lookup"><span data-stu-id="f463f-124">Apps:</span></span> <ul><li><span data-ttu-id="f463f-125">Узел</span><span class="sxs-lookup"><span data-stu-id="f463f-125">Wiki</span></span></li></ul>|
||||

## <a name="manager-collaboration"></a><span data-ttu-id="f463f-126">Совместная работа руководителя</span><span class="sxs-lookup"><span data-stu-id="f463f-126">Manager Collaboration</span></span>

<span data-ttu-id="f463f-127">Шаблон совместной работы руководителя идеально подходит для создания группы для совместной работы над магазинами и областями и т. д. Например, если в вашей организации есть регионы, вы можете создать группу совместной работы с руководителем для региона Калифорнии и включить в нее всех руководителей магазина, а также региональных менеджеров для этого региона.</span><span class="sxs-lookup"><span data-stu-id="f463f-127">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="f463f-128">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="f463f-128">Base template type</span></span>| <span data-ttu-id="f463f-129">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="f463f-129">baseTemplateId</span></span> | <span data-ttu-id="f463f-130">Свойства, которые поставляются с этим базовым шаблоном</span><span class="sxs-lookup"><span data-stu-id="f463f-130">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="f463f-131">Совместная работа в Retail Manager</span><span class="sxs-lookup"><span data-stu-id="f463f-131">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="f463f-132">Дистрибутор</span><span class="sxs-lookup"><span data-stu-id="f463f-132">Channels:</span></span> <ul><li><span data-ttu-id="f463f-133">Общий</span><span class="sxs-lookup"><span data-stu-id="f463f-133">General</span></span><li><span data-ttu-id="f463f-134">Операции</span><span class="sxs-lookup"><span data-stu-id="f463f-134">Operations</span></span></li><li><span data-ttu-id="f463f-135">Образователь</span><span class="sxs-lookup"><span data-stu-id="f463f-135">Learning</span></span></li></ul> <span data-ttu-id="f463f-136">Приложения</span><span class="sxs-lookup"><span data-stu-id="f463f-136">Apps:</span></span> <ul><li><span data-ttu-id="f463f-137">Узел</span><span class="sxs-lookup"><span data-stu-id="f463f-137">Wiki</span></span></li></ul>|
||||
