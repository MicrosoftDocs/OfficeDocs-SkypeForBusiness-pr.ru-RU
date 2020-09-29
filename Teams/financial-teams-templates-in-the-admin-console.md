---
title: Начало работы с финансовыми шаблонами Teams с помощью консоли администрирования
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
description: Сведения о том, как использовать. Шаблоны групп для создания структур групп, предназначенных для финансовых потребностей, предоставляя предварительно определенные параметры, каналы и предустановленные приложения с помощью консоли администрирования.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8273e63213b6a0c3d99d6ef66cb778a2541c0327
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294415"
---
# <a name="use-teams-financial-templates-in-the-admin-console"></a><span data-ttu-id="b563a-104">Использование финансовых шаблонов Teams в консоли администрирования</span><span class="sxs-lookup"><span data-stu-id="b563a-104">Use Teams financial templates in the admin console</span></span>

<span data-ttu-id="b563a-105">Шаблоны групп позволяют быстро и легко создавать группы, предоставляя готовый шаблон параметров, каналов и предустановленных приложений.</span><span class="sxs-lookup"><span data-stu-id="b563a-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="b563a-106">Шаблоны групп имеют предварительно составленные определения структур групп, разработанные для финансовых потребностей.</span><span class="sxs-lookup"><span data-stu-id="b563a-106">Teams templates have pre-built definitions of team structures designed around financial needs.</span></span> <span data-ttu-id="b563a-107">Вы также можете расширять шаблоны групп, чтобы создавать группы, адаптированные в соответствии с конкретными потребностями Организации.</span><span class="sxs-lookup"><span data-stu-id="b563a-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="b563a-108">В этой статье мы рассмотрим каждый из шаблонов Teams и рекомендуем использовать их.</span><span class="sxs-lookup"><span data-stu-id="b563a-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="b563a-109">Эта статья предназначена для вас, если вы несете ответственность за планирование, развертывание и управление несколькими группами в рамках своей финансовой организации.</span><span class="sxs-lookup"><span data-stu-id="b563a-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your financial organization.</span></span> <span data-ttu-id="b563a-110">Вы уже развернули службу Teams в своей организации.</span><span class="sxs-lookup"><span data-stu-id="b563a-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="b563a-111">Если вы еще не выполнили развертывание групп, начните с ознакомления с [развертыванием Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b563a-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="b563a-112">Дополнительные сведения о шаблонах групп можно найти в разделе [Приступая к работе с шаблонами групп](get-started-with-teams-templates-in-the-admin-console.md).</span><span class="sxs-lookup"><span data-stu-id="b563a-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="global-crisis-or-event"></a><span data-ttu-id="b563a-113">Глобальное критическое событие</span><span class="sxs-lookup"><span data-stu-id="b563a-113">Global crisis or event</span></span>

<span data-ttu-id="b563a-114">Централизованная совместная работа в рамках группы критической деятельности для бизнеса и помощь в создании планов бесперебойной работы, совместной работе с удаленными документами, отслеживания общения с клиентами и сохранения всех участников цикла с объявлениями и новостями.</span><span class="sxs-lookup"><span data-stu-id="b563a-114">Centralize collaboration for your crisis team across business units and help create business continuity plans, share remote working tips, track customer communications, and keep everyone in the loop with announcements and news.</span></span>

| <span data-ttu-id="b563a-115">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="b563a-115">Base template type</span></span>|<span data-ttu-id="b563a-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="b563a-116">baseTemplateId</span></span> | <span data-ttu-id="b563a-117">Свойства, которые поставляются с этим базовым шаблоном</span><span class="sxs-lookup"><span data-stu-id="b563a-117">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
| <span data-ttu-id="b563a-118">Совместная работа в глобальной аварийной ситуации или мероприятии</span><span class="sxs-lookup"><span data-stu-id="b563a-118">Collaborate on global crisis or event</span></span>|`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |<span data-ttu-id="b563a-119">Дистрибутор</span><span class="sxs-lookup"><span data-stu-id="b563a-119">Channels:</span></span> <ul><li><span data-ttu-id="b563a-120">Общий</span><span class="sxs-lookup"><span data-stu-id="b563a-120">General</span></span><li><span data-ttu-id="b563a-121">Обслуживании</span><span class="sxs-lookup"><span data-stu-id="b563a-121">Announcements</span></span></li><li><span data-ttu-id="b563a-122">Новости мира</span><span class="sxs-lookup"><span data-stu-id="b563a-122">World news</span></span></li><li><span data-ttu-id="b563a-123">Бесперебойность бизнеса</span><span class="sxs-lookup"><span data-stu-id="b563a-123">Business continuity</span></span></li><li><span data-ttu-id="b563a-124">Удаленная работа</span><span class="sxs-lookup"><span data-stu-id="b563a-124">Remote working</span></span></li><li><span data-ttu-id="b563a-125">Внутренние каналы связи</span><span class="sxs-lookup"><span data-stu-id="b563a-125">Internal comms</span></span></li><li><span data-ttu-id="b563a-126">Внешние каналы связи</span><span class="sxs-lookup"><span data-stu-id="b563a-126">External comms</span></span></li><li><span data-ttu-id="b563a-127">Жалобы клиентов</span><span class="sxs-lookup"><span data-stu-id="b563a-127">Customer complaints</span></span></li><li><span data-ttu-id="b563a-128">Баллами</span><span class="sxs-lookup"><span data-stu-id="b563a-128">Kudos</span></span></li><li><span data-ttu-id="b563a-129">Руководящее обновление</span><span class="sxs-lookup"><span data-stu-id="b563a-129">Executive update</span></span></li></ul><span data-ttu-id="b563a-130">Приложения</span><span class="sxs-lookup"><span data-stu-id="b563a-130">Apps:</span></span> <ul><li><span data-ttu-id="b563a-131">Благодарность</span><span class="sxs-lookup"><span data-stu-id="b563a-131">Praise</span></span></li><li><span data-ttu-id="b563a-132">Узел</span><span class="sxs-lookup"><span data-stu-id="b563a-132">Wiki</span></span></li><li><span data-ttu-id="b563a-133">Веб-сайта</span><span class="sxs-lookup"><span data-stu-id="b563a-133">Website</span></span></li></ul>|
||||

## <a name="collaborate-within-a-bank-branch"></a><span data-ttu-id="b563a-134">Совместная работа в рамках банковского отделения</span><span class="sxs-lookup"><span data-stu-id="b563a-134">Collaborate within a bank branch</span></span>

<span data-ttu-id="b563a-135">Централизованная совместная работа сотрудников филиалов по huddles, собраниям клиентов, бизнес-процессам, таким как "Совместная работа", и сохранение всех участников цикла с помощью объявлений и баллами.</span><span class="sxs-lookup"><span data-stu-id="b563a-135">Centralize collaboration for your bank branch employees across Huddles, Customer Meetings, Business Processes such as Mortgage Collaboration, and keep everyone in the loop with Announcements and Kudos.</span></span>

| <span data-ttu-id="b563a-136">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="b563a-136">Base template type</span></span> |<span data-ttu-id="b563a-137">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="b563a-137">baseTemplateId</span></span>| <span data-ttu-id="b563a-138">Свойства, которые поставляются с этим базовым шаблоном</span><span class="sxs-lookup"><span data-stu-id="b563a-138">Properties that come with this base template</span></span> |
| ------------------ |--|----------------------------------------------------- |
|<span data-ttu-id="b563a-139">Совместная работа в рамках банковского отделения</span><span class="sxs-lookup"><span data-stu-id="b563a-139">Collaborate within a bank branch</span></span>|`com.microsoft.teams.template.CollaborateWithinABankBranch` |<span data-ttu-id="b563a-140">Дистрибутор</span><span class="sxs-lookup"><span data-stu-id="b563a-140">Channels:</span></span> <ul><li><span data-ttu-id="b563a-141">Общий</span><span class="sxs-lookup"><span data-stu-id="b563a-141">General</span></span><li><span data-ttu-id="b563a-142">Обслуживании</span><span class="sxs-lookup"><span data-stu-id="b563a-142">Announcements</span></span></li><li><span data-ttu-id="b563a-143">Huddles</span><span class="sxs-lookup"><span data-stu-id="b563a-143">Huddles</span></span></li><li><span data-ttu-id="b563a-144">Собрания пользователей</span><span class="sxs-lookup"><span data-stu-id="b563a-144">Customer meetings</span></span></li><li><span data-ttu-id="b563a-145">Тренингов</span><span class="sxs-lookup"><span data-stu-id="b563a-145">Coaching</span></span></li><li><span data-ttu-id="b563a-146">Разработка навыков</span><span class="sxs-lookup"><span data-stu-id="b563a-146">Skills development</span></span></li><li><span data-ttu-id="b563a-147">Обработка займа</span><span class="sxs-lookup"><span data-stu-id="b563a-147">Loan processing</span></span></li><li><span data-ttu-id="b563a-148">Жалобы клиентов</span><span class="sxs-lookup"><span data-stu-id="b563a-148">Customer complaints</span></span></li><li><span data-ttu-id="b563a-149">Баллами</span><span class="sxs-lookup"><span data-stu-id="b563a-149">Kudos</span></span></li><li><span data-ttu-id="b563a-150">Забавные вещи</span><span class="sxs-lookup"><span data-stu-id="b563a-150">Fun stuff</span></span></li><li><span data-ttu-id="b563a-151">Соответствие требованиям</span><span class="sxs-lookup"><span data-stu-id="b563a-151">Compliance</span></span></li></ul>|
||||

