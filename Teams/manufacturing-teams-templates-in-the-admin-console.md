---
title: Начало работы с шаблонами производства Teams в центре администрирования
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
description: Сведения о том, как использовать. Шаблоны групп для создания структур групп, разработанных для производственных потребностей, предоставляя предварительно определенные параметры, каналы и предустановленные приложения с помощью центра администрирования.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9013bda2f83a63776dfbf9110a0863dcf68c0ddb
ms.sourcegitcommit: bc471f18e40e37456edc9696e11b175581847617
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "48800602"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-center"></a><span data-ttu-id="2526c-104">Использование шаблонов производства Teams в центре администрирования</span><span class="sxs-lookup"><span data-stu-id="2526c-104">Use Teams manufacturing templates in the admin center</span></span>

<span data-ttu-id="2526c-105">Шаблоны групп позволяют быстро и легко создавать группы, предоставляя готовый шаблон параметров, каналов и предустановленных приложений.</span><span class="sxs-lookup"><span data-stu-id="2526c-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="2526c-106">Шаблоны групп имеют предварительно составленные определения структур групп, разработанных вокруг производственных потребностей.</span><span class="sxs-lookup"><span data-stu-id="2526c-106">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="2526c-107">Вы также можете расширять шаблоны групп, чтобы создавать группы, адаптированные в соответствии с конкретными потребностями Организации.</span><span class="sxs-lookup"><span data-stu-id="2526c-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="2526c-108">В этой статье мы представляем каждый из шаблонов Teams и рекомендуем использовать их.</span><span class="sxs-lookup"><span data-stu-id="2526c-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="2526c-109">Эта статья предназначена для тех, кто ответственен за планирование, развертывание и управление несколькими группами в Организации.</span><span class="sxs-lookup"><span data-stu-id="2526c-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="2526c-110">Вы уже развернули службу Teams в своей организации.</span><span class="sxs-lookup"><span data-stu-id="2526c-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="2526c-111">Если вы еще не выполнили развертывание групп, начните с ознакомления с [развертыванием Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="2526c-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="2526c-112">Дополнительные сведения о шаблонах групп можно найти в разделе [Приступая к работе с шаблонами групп](get-started-with-teams-templates-in-the-admin-console.md).</span><span class="sxs-lookup"><span data-stu-id="2526c-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="2526c-113">Качество и безопасность</span><span class="sxs-lookup"><span data-stu-id="2526c-113">Quality and safety</span></span>

<span data-ttu-id="2526c-114">Централизованная связь, доступ к ресурсам и заводские операции с помощью группы фабрики производства.</span><span class="sxs-lookup"><span data-stu-id="2526c-114">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="2526c-115">Включают в себя документы о политике и процедурах, обучающие видеоматериалы, уведомления о безопасности, а также процессы смены handover.</span><span class="sxs-lookup"><span data-stu-id="2526c-115">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="2526c-116">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="2526c-116">Base template type</span></span>|<span data-ttu-id="2526c-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="2526c-117">baseTemplateId</span></span> | <span data-ttu-id="2526c-118">Свойства, которые поставляются с этим базовым шаблоном</span><span class="sxs-lookup"><span data-stu-id="2526c-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="2526c-119">Качество и безопасность</span><span class="sxs-lookup"><span data-stu-id="2526c-119">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="2526c-120">Дистрибутор</span><span class="sxs-lookup"><span data-stu-id="2526c-120">Channels:</span></span> <ul><li><span data-ttu-id="2526c-121">Общий</span><span class="sxs-lookup"><span data-stu-id="2526c-121">General</span></span><li><span data-ttu-id="2526c-122">Обслуживании</span><span class="sxs-lookup"><span data-stu-id="2526c-122">Announcements</span></span></li><li><span data-ttu-id="2526c-123">Строка 1</span><span class="sxs-lookup"><span data-stu-id="2526c-123">Line 1</span></span></li><li><span data-ttu-id="2526c-124">Строка 2</span><span class="sxs-lookup"><span data-stu-id="2526c-124">Line 2</span></span></li><li><span data-ttu-id="2526c-125">Строка 3</span><span class="sxs-lookup"><span data-stu-id="2526c-125">Line 3</span></span></li><li><span data-ttu-id="2526c-126">Безопасность</span><span class="sxs-lookup"><span data-stu-id="2526c-126">Safety</span></span></li><li><span data-ttu-id="2526c-127">Обучение</span><span class="sxs-lookup"><span data-stu-id="2526c-127">Training</span></span></li><li><span data-ttu-id="2526c-128">Настройки</span><span class="sxs-lookup"><span data-stu-id="2526c-128">Maintenance</span></span></li><li><span data-ttu-id="2526c-129">Забавные вещи</span><span class="sxs-lookup"><span data-stu-id="2526c-129">Fun stuff</span></span></li></ul> <span data-ttu-id="2526c-130">Приложения</span><span class="sxs-lookup"><span data-stu-id="2526c-130">Apps:</span></span> <ul><li><span data-ttu-id="2526c-131">Узел</span><span class="sxs-lookup"><span data-stu-id="2526c-131">Wiki</span></span></li></ul>|
||||
