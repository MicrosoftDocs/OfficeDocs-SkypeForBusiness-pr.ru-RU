---
title: Обновление Microsoft Teams | Оценка среды, вопросы обнаружения
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Воспользуйтесь этим руководством, чтобы узнать о требованиях для правильной оценки текущей среды для перехода на Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 799d348f05c8fece6684d01768934faedcb7603f
ms.sourcegitcommit: f7f86744c6dbf0db87e1408fd1f4b770fda07ff9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158747"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a><span data-ttu-id="120d3-103">Оценка среды перед обновлением в Teams</span><span class="sxs-lookup"><span data-stu-id="120d3-103">Evaluate your environment before upgrading to Teams</span></span>

<span data-ttu-id="120d3-104">![Обновление схемы поездки с акцентом на этапе технической подготовки](media/upgrade-banner-tech-readiness.png "Этапы путешествия по обновлению с акцентом на этапе технической подготовки")</span><span class="sxs-lookup"><span data-stu-id="120d3-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="120d3-105">Эта статья относится к техническому этапу подготовки к обновлению, действиям, завершенным параллельно с этапом готовности пользователей.</span><span class="sxs-lookup"><span data-stu-id="120d3-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="120d3-106">Прежде чем продолжить, подтвердите, что вы выполнили следующие действия из предыдущих стадий.</span><span class="sxs-lookup"><span data-stu-id="120d3-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="120d3-107">Вовлеченные заинтересованные лица в проект</span><span class="sxs-lookup"><span data-stu-id="120d3-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="120d3-108">Определение области охвата проекта</span><span class="sxs-lookup"><span data-stu-id="120d3-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="120d3-109">Сосуществование и взаимодействие Skype для бизнеса и рабочих групп</span><span class="sxs-lookup"><span data-stu-id="120d3-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="120d3-110">Выбрано путешествие с обновлением</span><span class="sxs-lookup"><span data-stu-id="120d3-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="120d3-111">В этой статье приводятся общие сведения о требованиях для правильной оценки текущей среды для операционных групп.</span><span class="sxs-lookup"><span data-stu-id="120d3-111">This article gives an overview of the requirements for properly evaluating your current environment for operating Teams.</span></span> <span data-ttu-id="120d3-112">Оценивая вашу среду, вы определяете риски и требования, которые повлияют на общее развертывание.</span><span class="sxs-lookup"><span data-stu-id="120d3-112">By evaluating your environment, you identify risks and requirements that will influence your overall deployment.</span></span> <span data-ttu-id="120d3-113">Определив эти элементы заранее, вы можете настроить планирование на успех.</span><span class="sxs-lookup"><span data-stu-id="120d3-113">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-the-discovery-questionnaire"></a><span data-ttu-id="120d3-114">Общие сведения о анкете обнаружения</span><span class="sxs-lookup"><span data-stu-id="120d3-114">Introduction to the Discovery Questionnaire</span></span>

<span data-ttu-id="120d3-115">Для получения ключевых результатов (OKRs) вы раньше внесли ключевые решения для обслуживания.</span><span class="sxs-lookup"><span data-stu-id="120d3-115">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="120d3-116">Следующий этап — это возможность оценить все аспекты, связанные с инфраструктурой ИТ, сетью и операциями, чтобы убедиться в том, что ваша организация готова к реализации решения.</span><span class="sxs-lookup"><span data-stu-id="120d3-116">The next step is to perform environmental discovery to evaluate all aspects relating to your IT infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span> <span data-ttu-id="120d3-117">Обнаружение — это один из самых первых, ключевых шагов, которые вы собираетесь планировать в Teams.</span><span class="sxs-lookup"><span data-stu-id="120d3-117">Discovery is one of the very first, key steps that you take when planning for your journey to Teams.</span></span> <span data-ttu-id="120d3-118">Обнаружение среды должно включать оценку готовности к использованию сети, чтобы убедиться в том, что сеть сможет поддерживать обновление до Teams.</span><span class="sxs-lookup"><span data-stu-id="120d3-118">Environmental discovery must include a network readiness assessment to ensure your network can support upgrading to Teams.</span></span> <span data-ttu-id="120d3-119">Вы выполняете подробное обнаружение среды, чтобы лучше понять ее текущее состояние и выявить все проблемы или (еще более важные), которые могут быть заблокированы для выполнения выпуска команды.</span><span class="sxs-lookup"><span data-stu-id="120d3-119">You perform a detailed discovery of your environment to better understand its current state and to reveal any difficulties or—even more important—possible blockers to the execution of your Teams rollout.</span></span>

<span data-ttu-id="120d3-120">Вы определяете технические риски в рамках оценки среды и оценки готовности к внедрению, а также Разработайте план снижения риска для каждого определенного риска.</span><span class="sxs-lookup"><span data-stu-id="120d3-120">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="120d3-121">Эти сведения следует включить в реестр рисков.</span><span class="sxs-lookup"><span data-stu-id="120d3-121">You should incorporate this information in the risk register.</span></span>

<span data-ttu-id="120d3-122">Все, что связано с существующей инфраструктурой совместной работы и Microsoft 365 или Office 365 (организация, сеть, конечные точки, операции и внедрение и готовность), входят в состав анкеты по обнаружению окружающей среды.</span><span class="sxs-lookup"><span data-stu-id="120d3-122">All matters related to your existing collaboration infrastructure and Microsoft 365 or Office 365 organization, networking, endpoints, operations, and adoption and readiness are included as part of the environmental discovery questionnaire.</span></span> <span data-ttu-id="120d3-123">Вы можете работать с вашей командой проекта, чтобы предоставить запрашиваемые сведения как можно более детально, чтобы упростить планирование.</span><span class="sxs-lookup"><span data-stu-id="120d3-123">Work with your project team to provide the requested information with as much detail as possible to facilitate your planning activities.</span></span>

<span data-ttu-id="120d3-124">[Анкета](upgrade-plan-journey-discovery-questionnaire.md) разделена на следующие разделы, чтобы подтвердить готовность Организации к развертыванию Teams в нескольких основных областях:</span><span class="sxs-lookup"><span data-stu-id="120d3-124">[The questionnaire](upgrade-plan-journey-discovery-questionnaire.md) is divided into the following sections to confirm your organization's readiness for your Teams deployment in several major areas:</span></span>

- <span data-ttu-id="120d3-125">Сведения об организации Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="120d3-125">Microsoft 365 or Office 365 organization details</span></span>
- <span data-ttu-id="120d3-126">Существующая общая платформа для совместной работы</span><span class="sxs-lookup"><span data-stu-id="120d3-126">Existing collaboration platform summary</span></span>
- <span data-ttu-id="120d3-127">Сведения о развертывании платформы совместной работы</span><span class="sxs-lookup"><span data-stu-id="120d3-127">Collaboration platform deployment details</span></span>
- <span data-ttu-id="120d3-128">Работа в сети и доступ к службам Microsoft 365 и Office 365</span><span class="sxs-lookup"><span data-stu-id="120d3-128">Networking and access to Microsoft 365 or Office 365 services</span></span>
- <span data-ttu-id="120d3-129">Конечные точки</span><span class="sxs-lookup"><span data-stu-id="120d3-129">Endpoints</span></span>
- <span data-ttu-id="120d3-130">Операции</span><span class="sxs-lookup"><span data-stu-id="120d3-130">Operations</span></span>
- <span data-ttu-id="120d3-131">Внедрение и готовность</span><span class="sxs-lookup"><span data-stu-id="120d3-131">Adoption and readiness</span></span>

> [!TIP]
> <span data-ttu-id="120d3-132">Вы можете начать с копирования анкеты в документ Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="120d3-132">You can start by copying the questionnaire into a Microsoft Word document.</span></span> <span data-ttu-id="120d3-133">Попробуйте ответить на все вопросы и захватить все детали по мере их перемещения.</span><span class="sxs-lookup"><span data-stu-id="120d3-133">Try to answer all questions and capture all details as you move through.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/><span data-ttu-id="120d3-134">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="120d3-134">Decision point</span></span></td><td><ul><li><span data-ttu-id="120d3-135">Кто будет отвечать за выполнение оценки среды?</span><span class="sxs-lookup"><span data-stu-id="120d3-135">Who will be responsible for completing an environment assessment?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/><span data-ttu-id="120d3-136">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="120d3-136">Next step</span></span></td><td><ul><li><span data-ttu-id="120d3-137">Задокументируйте результаты оценки среды.</span><span class="sxs-lookup"><span data-stu-id="120d3-137">Document the results of the environment assessment.</span></span></li></ul></td></tr>
</table>


## <a name="project-team"></a><span data-ttu-id="120d3-138">Группа проекта</span><span class="sxs-lookup"><span data-stu-id="120d3-138">Project team</span></span>

<span data-ttu-id="120d3-139">Убедитесь, что вы активировали нужных пользователей для своей группы проекта.</span><span class="sxs-lookup"><span data-stu-id="120d3-139">Ensure that you've engaged the right people for your project team.</span></span> <span data-ttu-id="120d3-140">Проверьте, какие действия были выполнены в разделе [Прикрепление заинтересованных лиц проекта](upgrade-enlist-stakeholders.md).</span><span class="sxs-lookup"><span data-stu-id="120d3-140">Verify the steps you completed in [Enlist your project stakeholders](upgrade-enlist-stakeholders.md).</span></span>

<span data-ttu-id="120d3-141">После того как вы оцените свою среду, переходите к следующему шагу: [Подготовка службы](upgrade-prepare-environment-prepare-service.md).</span><span class="sxs-lookup"><span data-stu-id="120d3-141">After you evaluate your environment, proceed to the next step: [Prepare your service](upgrade-prepare-environment-prepare-service.md).</span></span>
