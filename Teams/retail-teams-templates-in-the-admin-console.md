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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 8b72fe7b1f101278d206d49f06203fe9841ba25f
ms.sourcegitcommit: af9f96010460f9323db84912fe143aa0750ac798
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171083"
---
# <a name="use-teams-retail-templates-in-the-admin-console"></a><span data-ttu-id="d71cd-103">Использование розничных шаблонов Teams в консоли администрирования</span><span class="sxs-lookup"><span data-stu-id="d71cd-103">Use Teams retail templates in the admin console</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="d71cd-104">Шаблоны групп позволяют быстро и легко создавать группы, предоставляя готовый шаблон параметров, каналов и предустановленных приложений.</span><span class="sxs-lookup"><span data-stu-id="d71cd-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="d71cd-105">Шаблоны групп имеют предварительно составленные определения структур групп, разработанных в отношении потребностей розничной торговли.</span><span class="sxs-lookup"><span data-stu-id="d71cd-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="d71cd-106">Шаблоны Teams можно использовать для быстрого создания типов рабочих групп, которые подходят для розничных продавцов, и их развертывания в Организации.</span><span class="sxs-lookup"><span data-stu-id="d71cd-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="d71cd-107">Вы также можете расширять шаблоны групп, чтобы создавать группы, адаптированные в соответствии с конкретными потребностями Организации.</span><span class="sxs-lookup"><span data-stu-id="d71cd-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="d71cd-108">В этой статье мы рассмотрим каждый из шаблонов Teams и как мы рекомендуем использовать их.</span><span class="sxs-lookup"><span data-stu-id="d71cd-108">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="d71cd-109">Эта статья предназначена для вас, если вы несете ответственность за планирование, развертывание и управление несколькими группами в рамках своей организации розничной торговли.</span><span class="sxs-lookup"><span data-stu-id="d71cd-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="d71cd-110">Предполагается, что в вашей организации уже развернута служба Teams.</span><span class="sxs-lookup"><span data-stu-id="d71cd-110">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="d71cd-111">Если вы еще не выполнили развертывание групп, начните с ознакомления с [развертыванием Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="d71cd-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="d71cd-112">Дополнительные сведения о шаблонах групп можно найти в разделе Начало [работы с шаблонами групп](get-started-with-teams-templates-in-the-admin-console.md).</span><span class="sxs-lookup"><span data-stu-id="d71cd-112">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="organize-a-store"></a><span data-ttu-id="d71cd-113">Упорядочение магазина</span><span class="sxs-lookup"><span data-stu-id="d71cd-113">Organize a store</span></span>

<span data-ttu-id="d71cd-114">Централизованное управление задачами, общий доступ к документам и устранение проблем с клиентами.</span><span class="sxs-lookup"><span data-stu-id="d71cd-114">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="d71cd-115">Интегрируйте дополнительные приложения, чтобы ускорить смену начала & конечные процессы.</span><span class="sxs-lookup"><span data-stu-id="d71cd-115">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="d71cd-116">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="d71cd-116">Base template type</span></span> |<span data-ttu-id="d71cd-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="d71cd-117">baseTemplateId</span></span> | <span data-ttu-id="d71cd-118">Свойства, которые поставляются с этим базовым шаблоном</span><span class="sxs-lookup"><span data-stu-id="d71cd-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="d71cd-119">Упорядочение магазина</span><span class="sxs-lookup"><span data-stu-id="d71cd-119">Organize a store</span></span>| `retailStore`|<span data-ttu-id="d71cd-120">Дистрибутор</span><span class="sxs-lookup"><span data-stu-id="d71cd-120">Channels:</span></span> <ul><li><span data-ttu-id="d71cd-121">Общий</span><span class="sxs-lookup"><span data-stu-id="d71cd-121">General</span></span><li><span data-ttu-id="d71cd-122">Переносится смена</span><span class="sxs-lookup"><span data-stu-id="d71cd-122">Shift handoff</span></span></li><li><span data-ttu-id="d71cd-123">Образователь</span><span class="sxs-lookup"><span data-stu-id="d71cd-123">Learning</span></span></li></ul> <span data-ttu-id="d71cd-124">Приложения</span><span class="sxs-lookup"><span data-stu-id="d71cd-124">Apps:</span></span> <ul><li><span data-ttu-id="d71cd-125">Узел</span><span class="sxs-lookup"><span data-stu-id="d71cd-125">Wiki</span></span></li></ul>|
||||

## <a name="manager-collaboration"></a><span data-ttu-id="d71cd-126">Совместная работа руководителя</span><span class="sxs-lookup"><span data-stu-id="d71cd-126">Manager Collaboration</span></span>

<span data-ttu-id="d71cd-127">Шаблон совместной работы руководителя идеально подходит для создания группы для совместной работы над магазинами и областями и т. д. Например, если в вашей организации есть регионы, вы можете создать группу совместной работы с руководителем для региона Калифорнии и включить в нее всех руководителей магазина, а также региональных менеджеров для этого региона.</span><span class="sxs-lookup"><span data-stu-id="d71cd-127">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="d71cd-128">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="d71cd-128">Base template type</span></span>| <span data-ttu-id="d71cd-129">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="d71cd-129">baseTemplateId</span></span> | <span data-ttu-id="d71cd-130">Свойства, которые поставляются с этим базовым шаблоном</span><span class="sxs-lookup"><span data-stu-id="d71cd-130">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="d71cd-131">Совместная работа в Retail Manager</span><span class="sxs-lookup"><span data-stu-id="d71cd-131">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="d71cd-132">Дистрибутор</span><span class="sxs-lookup"><span data-stu-id="d71cd-132">Channels:</span></span> <ul><li><span data-ttu-id="d71cd-133">Общий</span><span class="sxs-lookup"><span data-stu-id="d71cd-133">General</span></span><li><span data-ttu-id="d71cd-134">Операции</span><span class="sxs-lookup"><span data-stu-id="d71cd-134">Operations</span></span></li><li><span data-ttu-id="d71cd-135">Образователь</span><span class="sxs-lookup"><span data-stu-id="d71cd-135">Learning</span></span></li></ul> <span data-ttu-id="d71cd-136">Приложения</span><span class="sxs-lookup"><span data-stu-id="d71cd-136">Apps:</span></span> <ul><li><span data-ttu-id="d71cd-137">Узел</span><span class="sxs-lookup"><span data-stu-id="d71cd-137">Wiki</span></span></li></ul>|
||||
