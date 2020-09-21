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
description: Вы узнаете, как использовать шаблоны групп для создания структур групп, предназначенных для финансовых потребностей, предоставляя предварительно определенные параметры, каналы и предустановленные приложения с помощью консоли администрирования.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 270e03d58a89cf35132f254d2dd1af55d894e8d0
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2020
ms.locfileid: "48136114"
---
# <a name="use-teams-financial-templates-in-the-admin-console"></a><span data-ttu-id="86c5e-103">Использование финансовых шаблонов Teams в консоли администрирования</span><span class="sxs-lookup"><span data-stu-id="86c5e-103">Use Teams financial templates in the admin console</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="86c5e-104">Шаблоны групп позволяют быстро и легко создавать группы, предоставляя готовый шаблон параметров, каналов и предустановленных приложений.</span><span class="sxs-lookup"><span data-stu-id="86c5e-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="86c5e-105">Шаблоны групп имеют предварительно составленные определения структур групп, разработанные для финансовых потребностей.</span><span class="sxs-lookup"><span data-stu-id="86c5e-105">Teams templates have pre-built definitions of team structures designed around financial needs.</span></span> <span data-ttu-id="86c5e-106">Вы также можете расширять шаблоны групп, чтобы создавать группы, адаптированные в соответствии с конкретными потребностями Организации.</span><span class="sxs-lookup"><span data-stu-id="86c5e-106">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="86c5e-107">В этой статье мы рассмотрим каждый из шаблонов Teams и как мы рекомендуем использовать их.</span><span class="sxs-lookup"><span data-stu-id="86c5e-107">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="86c5e-108">Эта статья предназначена для вас, если вы несете ответственность за планирование, развертывание и управление несколькими группами в рамках своей финансовой организации.</span><span class="sxs-lookup"><span data-stu-id="86c5e-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your financial organization.</span></span> <span data-ttu-id="86c5e-109">Предполагается, что в вашей организации уже развернута служба Teams.</span><span class="sxs-lookup"><span data-stu-id="86c5e-109">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="86c5e-110">Если вы еще не выполнили развертывание групп, начните с ознакомления с [развертыванием Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="86c5e-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="86c5e-111">Дополнительные сведения о шаблонах групп можно найти в разделе Начало [работы с шаблонами групп](get-started-with-teams-templates-in-the-admin-console.md).</span><span class="sxs-lookup"><span data-stu-id="86c5e-111">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="global-crisis-or-event"></a><span data-ttu-id="86c5e-112">Глобальное критическое событие</span><span class="sxs-lookup"><span data-stu-id="86c5e-112">Global crisis or event</span></span>

<span data-ttu-id="86c5e-113">Централизованная совместная работа в рамках группы критической деятельности для бизнеса и помощь в создании планов бесперебойной работы, совместной работе с удаленными документами, отслеживания общения с клиентами и сохранения всех участников цикла с объявлениями и новостями.</span><span class="sxs-lookup"><span data-stu-id="86c5e-113">Centralize collaboration for your crisis team across business units and help create business continuity plans, share remote working tips, track customer communications, and keep everyone in the loop with announcements and news.</span></span>

| <span data-ttu-id="86c5e-114">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="86c5e-114">Base template type</span></span>|<span data-ttu-id="86c5e-115">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="86c5e-115">baseTemplateId</span></span> | <span data-ttu-id="86c5e-116">Свойства, которые поставляются с этим базовым шаблоном</span><span class="sxs-lookup"><span data-stu-id="86c5e-116">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
| <span data-ttu-id="86c5e-117">Совместная работа в глобальной аварийной ситуации или мероприятии</span><span class="sxs-lookup"><span data-stu-id="86c5e-117">Collaborate on global crisis or event</span></span>|`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |<span data-ttu-id="86c5e-118">Дистрибутор</span><span class="sxs-lookup"><span data-stu-id="86c5e-118">Channels:</span></span> <ul><li><span data-ttu-id="86c5e-119">Общий</span><span class="sxs-lookup"><span data-stu-id="86c5e-119">General</span></span><li><span data-ttu-id="86c5e-120">Обслуживании</span><span class="sxs-lookup"><span data-stu-id="86c5e-120">Announcements</span></span></li><li><span data-ttu-id="86c5e-121">Новости мира</span><span class="sxs-lookup"><span data-stu-id="86c5e-121">World news</span></span></li><li><span data-ttu-id="86c5e-122">Бесперебойность бизнеса</span><span class="sxs-lookup"><span data-stu-id="86c5e-122">Business continuity</span></span></li><li><span data-ttu-id="86c5e-123">Удаленная работа</span><span class="sxs-lookup"><span data-stu-id="86c5e-123">Remote working</span></span></li><li><span data-ttu-id="86c5e-124">Внутренние каналы связи</span><span class="sxs-lookup"><span data-stu-id="86c5e-124">Internal comms</span></span></li><li><span data-ttu-id="86c5e-125">Внешние каналы связи</span><span class="sxs-lookup"><span data-stu-id="86c5e-125">External comms</span></span></li><li><span data-ttu-id="86c5e-126">Жалобы клиентов</span><span class="sxs-lookup"><span data-stu-id="86c5e-126">Customer complaints</span></span></li><li><span data-ttu-id="86c5e-127">Баллами</span><span class="sxs-lookup"><span data-stu-id="86c5e-127">Kudos</span></span></li><li><span data-ttu-id="86c5e-128">Руководящее обновление</span><span class="sxs-lookup"><span data-stu-id="86c5e-128">Executive update</span></span></li></ul><span data-ttu-id="86c5e-129">Приложения</span><span class="sxs-lookup"><span data-stu-id="86c5e-129">Apps:</span></span> <ul><li><span data-ttu-id="86c5e-130">Благодарность</span><span class="sxs-lookup"><span data-stu-id="86c5e-130">Praise</span></span></li><li><span data-ttu-id="86c5e-131">Узел</span><span class="sxs-lookup"><span data-stu-id="86c5e-131">Wiki</span></span></li><li><span data-ttu-id="86c5e-132">Веб-сайта</span><span class="sxs-lookup"><span data-stu-id="86c5e-132">Website</span></span></li></ul>|
||||

## <a name="collaborate-within-a-bank-branch"></a><span data-ttu-id="86c5e-133">Совместная работа в рамках банковского отделения</span><span class="sxs-lookup"><span data-stu-id="86c5e-133">Collaborate within a bank branch</span></span>

<span data-ttu-id="86c5e-134">Централизованная совместная работа сотрудников филиалов по huddles, собраниям клиентов, бизнес-процессам, таким как "Совместная работа", и сохранение всех участников цикла с помощью объявлений и баллами.</span><span class="sxs-lookup"><span data-stu-id="86c5e-134">Centralize collaboration for your bank branch employees across Huddles, Customer Meetings, Business Processes such as Mortgage Collaboration, and keep everyone in the loop with Announcements and Kudos.</span></span>

| <span data-ttu-id="86c5e-135">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="86c5e-135">Base template type</span></span> |<span data-ttu-id="86c5e-136">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="86c5e-136">baseTemplateId</span></span>| <span data-ttu-id="86c5e-137">Свойства, которые поставляются с этим базовым шаблоном</span><span class="sxs-lookup"><span data-stu-id="86c5e-137">Properties that come with this base template</span></span> |
| ------------------ |--|----------------------------------------------------- |
|<span data-ttu-id="86c5e-138">Совместная работа в рамках банковского отделения</span><span class="sxs-lookup"><span data-stu-id="86c5e-138">Collaborate within a bank branch</span></span>|`com.microsoft.teams.template.CollaborateWithinABankBranch` |<span data-ttu-id="86c5e-139">Дистрибутор</span><span class="sxs-lookup"><span data-stu-id="86c5e-139">Channels:</span></span> <ul><li><span data-ttu-id="86c5e-140">Общий</span><span class="sxs-lookup"><span data-stu-id="86c5e-140">General</span></span><li><span data-ttu-id="86c5e-141">Обслуживании</span><span class="sxs-lookup"><span data-stu-id="86c5e-141">Announcements</span></span></li><li><span data-ttu-id="86c5e-142">Huddles</span><span class="sxs-lookup"><span data-stu-id="86c5e-142">Huddles</span></span></li><li><span data-ttu-id="86c5e-143">Собрания пользователей</span><span class="sxs-lookup"><span data-stu-id="86c5e-143">Customer meetings</span></span></li><li><span data-ttu-id="86c5e-144">Тренингов</span><span class="sxs-lookup"><span data-stu-id="86c5e-144">Coaching</span></span></li><li><span data-ttu-id="86c5e-145">Разработка навыков</span><span class="sxs-lookup"><span data-stu-id="86c5e-145">Skills development</span></span></li><li><span data-ttu-id="86c5e-146">Обработка займа</span><span class="sxs-lookup"><span data-stu-id="86c5e-146">Loan processing</span></span></li><li><span data-ttu-id="86c5e-147">Жалобы клиентов</span><span class="sxs-lookup"><span data-stu-id="86c5e-147">Customer complaints</span></span></li><li><span data-ttu-id="86c5e-148">Баллами</span><span class="sxs-lookup"><span data-stu-id="86c5e-148">Kudos</span></span></li><li><span data-ttu-id="86c5e-149">Забавные вещи</span><span class="sxs-lookup"><span data-stu-id="86c5e-149">Fun stuff</span></span></li><li><span data-ttu-id="86c5e-150">Соответствие требованиям</span><span class="sxs-lookup"><span data-stu-id="86c5e-150">Compliance</span></span></li></ul>|
||||

