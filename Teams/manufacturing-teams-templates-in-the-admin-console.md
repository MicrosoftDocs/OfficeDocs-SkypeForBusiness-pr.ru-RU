---
title: Начало работы с шаблонами производства Teams на консоли администрирования
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
description: Сведения о том, как использовать шаблоны групп для создания структур групп, разработанных для производственных потребностей, предоставляя предварительно определенные параметры, каналы и предустановленные приложения с помощью консоли администрирования.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 919bfc1bc3e13985ac90484cd203bf93201babd2
ms.sourcegitcommit: af9f96010460f9323db84912fe143aa0750ac798
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171033"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-console"></a><span data-ttu-id="a2ec0-103">Использование шаблонов производства Teams в консоли администрирования</span><span class="sxs-lookup"><span data-stu-id="a2ec0-103">Use Teams manufacturing templates in the admin console</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="a2ec0-104">Шаблоны групп позволяют быстро и легко создавать группы, предоставляя готовый шаблон параметров, каналов и предустановленных приложений.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="a2ec0-105">Шаблоны групп имеют предварительно составленные определения структур групп, разработанных вокруг производственных потребностей.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-105">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="a2ec0-106">Вы также можете расширять шаблоны групп, чтобы создавать группы, адаптированные в соответствии с конкретными потребностями Организации.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-106">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="a2ec0-107">В этой статье мы рассмотрим каждый из шаблонов Teams и как мы рекомендуем использовать их.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-107">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="a2ec0-108">Эта статья предназначена для тех, кто ответственен за планирование, развертывание и управление несколькими группами в Организации.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="a2ec0-109">Предполагается, что в вашей организации уже развернута служба Teams.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-109">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="a2ec0-110">Если вы еще не выполнили развертывание групп, начните с ознакомления с [развертыванием Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="a2ec0-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="a2ec0-111">Дополнительные сведения о шаблонах групп можно найти в разделе Начало [работы с шаблонами групп](get-started-with-teams-templates-in-the-admin-console.md).</span><span class="sxs-lookup"><span data-stu-id="a2ec0-111">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="a2ec0-112">Качество и безопасность</span><span class="sxs-lookup"><span data-stu-id="a2ec0-112">Quality and safety</span></span>

<span data-ttu-id="a2ec0-113">Централизованная связь, доступ к ресурсам и заводские операции с помощью группы фабрики производства.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-113">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="a2ec0-114">Включают в себя документы о политике и процедурах, обучающие видеоматериалы, уведомления о безопасности, а также процессы смены handover.</span><span class="sxs-lookup"><span data-stu-id="a2ec0-114">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="a2ec0-115">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="a2ec0-115">Base template type</span></span>|<span data-ttu-id="a2ec0-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="a2ec0-116">baseTemplateId</span></span> | <span data-ttu-id="a2ec0-117">Свойства, которые поставляются с этим базовым шаблоном</span><span class="sxs-lookup"><span data-stu-id="a2ec0-117">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="a2ec0-118">Качество и безопасность</span><span class="sxs-lookup"><span data-stu-id="a2ec0-118">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="a2ec0-119">Дистрибутор</span><span class="sxs-lookup"><span data-stu-id="a2ec0-119">Channels:</span></span> <ul><li><span data-ttu-id="a2ec0-120">Общий</span><span class="sxs-lookup"><span data-stu-id="a2ec0-120">General</span></span><li><span data-ttu-id="a2ec0-121">Обслуживании</span><span class="sxs-lookup"><span data-stu-id="a2ec0-121">Announcements</span></span></li><li><span data-ttu-id="a2ec0-122">Строка 1</span><span class="sxs-lookup"><span data-stu-id="a2ec0-122">Line 1</span></span></li><li><span data-ttu-id="a2ec0-123">Строка 2</span><span class="sxs-lookup"><span data-stu-id="a2ec0-123">Line 2</span></span></li><li><span data-ttu-id="a2ec0-124">Строка 3</span><span class="sxs-lookup"><span data-stu-id="a2ec0-124">Line 3</span></span></li><li><span data-ttu-id="a2ec0-125">Безопасность</span><span class="sxs-lookup"><span data-stu-id="a2ec0-125">Safety</span></span></li><li><span data-ttu-id="a2ec0-126">Обучение</span><span class="sxs-lookup"><span data-stu-id="a2ec0-126">Training</span></span></li><li><span data-ttu-id="a2ec0-127">Настройки</span><span class="sxs-lookup"><span data-stu-id="a2ec0-127">Maintenance</span></span></li><li><span data-ttu-id="a2ec0-128">Забавные вещи</span><span class="sxs-lookup"><span data-stu-id="a2ec0-128">Fun stuff</span></span></li></ul> <span data-ttu-id="a2ec0-129">Приложения</span><span class="sxs-lookup"><span data-stu-id="a2ec0-129">Apps:</span></span> <ul><li><span data-ttu-id="a2ec0-130">Узел</span><span class="sxs-lookup"><span data-stu-id="a2ec0-130">Wiki</span></span></li></ul>|
||||
