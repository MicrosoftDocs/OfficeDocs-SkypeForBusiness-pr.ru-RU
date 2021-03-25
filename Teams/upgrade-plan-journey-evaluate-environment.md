---
title: Оценка среды перед обновлением до Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Узнайте о требованиях для правильной оценки текущей среды для перехода на Teams.
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
ms.openlocfilehash: 119a80f5a25b4a2d8599df3df6a573a1f5554c1a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119108"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a><span data-ttu-id="f9695-103">Оценка среды перед обновлением до Teams</span><span class="sxs-lookup"><span data-stu-id="f9695-103">Evaluate your environment before upgrading to Teams</span></span>

<span data-ttu-id="f9695-104">![Схема пути обновления с акцентом на этапе технической готовности](media/upgrade-banner-tech-readiness.png "Этапы пути обновления с акцентом на этапе технической готовности")</span><span class="sxs-lookup"><span data-stu-id="f9695-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="f9695-105">Эта статья является частью этапа технической готовности, которое вы завершаете параллельно с этапом подготовки пользователя.</span><span class="sxs-lookup"><span data-stu-id="f9695-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="f9695-106">Прежде чем при этом подтверждать, что вы выполнили эти действия на предыдущих этапах:</span><span class="sxs-lookup"><span data-stu-id="f9695-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="f9695-107">Привлечение заинтересованных лиц проекта</span><span class="sxs-lookup"><span data-stu-id="f9695-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="f9695-108">Определение области проекта</span><span class="sxs-lookup"><span data-stu-id="f9695-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="f9695-109">Понимание сосуществования и совместной работы Skype для бизнеса и Teams</span><span class="sxs-lookup"><span data-stu-id="f9695-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="f9695-110">Выбранный путь обновления</span><span class="sxs-lookup"><span data-stu-id="f9695-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="f9695-111">В этой статье приводится обзор требований для правильной оценки текущей среды для работы Teams.</span><span class="sxs-lookup"><span data-stu-id="f9695-111">This article gives an overview of the requirements for properly evaluating your current environment for operating Teams.</span></span> <span data-ttu-id="f9695-112">Оценив свою среду, вы определите риски и требования, которые влияют на общее развертывание.</span><span class="sxs-lookup"><span data-stu-id="f9695-112">By evaluating your environment, you identify risks and requirements that will influence your overall deployment.</span></span> <span data-ttu-id="f9695-113">Предварительно определяя эти элементы, вы можете скорректировать свое планирование, чтобы добиться успеха.</span><span class="sxs-lookup"><span data-stu-id="f9695-113">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-the-discovery-questionnaire"></a><span data-ttu-id="f9695-114">Введение в анкету обнаружения</span><span class="sxs-lookup"><span data-stu-id="f9695-114">Introduction to the Discovery Questionnaire</span></span>

<span data-ttu-id="f9695-115">Для достижения своих ключевых результатов (OKRs) ранее были приняты ключевые решения о обслуживании.</span><span class="sxs-lookup"><span data-stu-id="f9695-115">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="f9695-116">Далее необходимо выполнить обнаружение среды, чтобы оценить все аспекты ИТ-инфраструктуры, сети и операций, чтобы подтвердить готовность организации к внедрению решения.</span><span class="sxs-lookup"><span data-stu-id="f9695-116">The next step is to perform environmental discovery to evaluate all aspects relating to your IT infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span> <span data-ttu-id="f9695-117">Обнаружение — одна из важнейших этапов, которые необходимо предпринять при планировании пути к Teams.</span><span class="sxs-lookup"><span data-stu-id="f9695-117">Discovery is one of the very first, key steps that you take when planning for your journey to Teams.</span></span> <span data-ttu-id="f9695-118">Обнаружение среды должно включать оценку готовности сети, чтобы убедиться, что ваша сеть может поддерживать обновление до Teams.</span><span class="sxs-lookup"><span data-stu-id="f9695-118">Environmental discovery must include a network readiness assessment to ensure your network can support upgrading to Teams.</span></span> <span data-ttu-id="f9695-119">Вы выполняете подробное обнаружение вашей среды, чтобы лучше понять ее текущее состояние и выявить сложности или, что еще важнее, заблокировать выполнение развернутого решения Teams.</span><span class="sxs-lookup"><span data-stu-id="f9695-119">You perform a detailed discovery of your environment to better understand its current state and to reveal any difficulties or—even more important—possible blockers to the execution of your Teams rollout.</span></span>

<span data-ttu-id="f9695-120">В ходе оценки готовности к внедрению и оценке готовности к внедрению вы определяете технические риски, а также разрабатываете план снижения для каждого обнаруженного риска.</span><span class="sxs-lookup"><span data-stu-id="f9695-120">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="f9695-121">Эти сведения следует включить в реестр рисков.</span><span class="sxs-lookup"><span data-stu-id="f9695-121">You should incorporate this information in the risk register.</span></span>

<span data-ttu-id="f9695-122">Все вопросы, связанные с существующей инфраструктурой совместной работы и организацией Microsoft 365 или Office 365, сетью, конечными точками, операциями, внедрением и готовностей, включаются в анкету по обнаружению окружающей среды.</span><span class="sxs-lookup"><span data-stu-id="f9695-122">All matters related to your existing collaboration infrastructure and Microsoft 365 or Office 365 organization, networking, endpoints, operations, and adoption and readiness are included as part of the environmental discovery questionnaire.</span></span> <span data-ttu-id="f9695-123">Работайте вместе с проектной командой, чтобы предоставить запрашиваемую информацию как можно более подробно, чтобы упростить планирование.</span><span class="sxs-lookup"><span data-stu-id="f9695-123">Work with your project team to provide the requested information with as much detail as possible to facilitate your planning activities.</span></span>

<span data-ttu-id="f9695-124">[Анкета](upgrade-plan-journey-discovery-questionnaire.md) состоит из следующих разделов, чтобы подтвердить готовность организации к развертыванию Teams в нескольких основных областях:</span><span class="sxs-lookup"><span data-stu-id="f9695-124">[The questionnaire](upgrade-plan-journey-discovery-questionnaire.md) is divided into the following sections to confirm your organization's readiness for your Teams deployment in several major areas:</span></span>

- <span data-ttu-id="f9695-125">Сведения об организации в Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="f9695-125">Microsoft 365 or Office 365 organization details</span></span>
- <span data-ttu-id="f9695-126">Существующая сводка платформы совместной работы</span><span class="sxs-lookup"><span data-stu-id="f9695-126">Existing collaboration platform summary</span></span>
- <span data-ttu-id="f9695-127">Сведения о развертывании платформы для совместной работы</span><span class="sxs-lookup"><span data-stu-id="f9695-127">Collaboration platform deployment details</span></span>
- <span data-ttu-id="f9695-128">Сеть и доступ к службам Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="f9695-128">Networking and access to Microsoft 365 or Office 365 services</span></span>
- <span data-ttu-id="f9695-129">Конечные точки</span><span class="sxs-lookup"><span data-stu-id="f9695-129">Endpoints</span></span>
- <span data-ttu-id="f9695-130">Операции</span><span class="sxs-lookup"><span data-stu-id="f9695-130">Operations</span></span>
- <span data-ttu-id="f9695-131">Внедрение и готовность</span><span class="sxs-lookup"><span data-stu-id="f9695-131">Adoption and readiness</span></span>

> [!TIP]
> <span data-ttu-id="f9695-132">Для начала скопируйте анкету в документ Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="f9695-132">You can start by copying the questionnaire into a Microsoft Word document.</span></span> <span data-ttu-id="f9695-133">Постарайтесь отвечать на все вопросы и фиксировать все сведения по мере перемещения.</span><span class="sxs-lookup"><span data-stu-id="f9695-133">Try to answer all questions and capture all details as you move through.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/><span data-ttu-id="f9695-134">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="f9695-134">Decision point</span></span></td><td><ul><li><span data-ttu-id="f9695-135">Кто будет отвечать за прохождение оценки среды?</span><span class="sxs-lookup"><span data-stu-id="f9695-135">Who will be responsible for completing an environment assessment?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/><span data-ttu-id="f9695-136">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="f9695-136">Next step</span></span></td><td><ul><li><span data-ttu-id="f9695-137">Документировать результаты оценки среды.</span><span class="sxs-lookup"><span data-stu-id="f9695-137">Document the results of the environment assessment.</span></span></li></ul></td></tr>
</table>


## <a name="project-team"></a><span data-ttu-id="f9695-138">Группа проекта</span><span class="sxs-lookup"><span data-stu-id="f9695-138">Project team</span></span>

<span data-ttu-id="f9695-139">Убедитесь, что вы вовлечены в проект нужных людей.</span><span class="sxs-lookup"><span data-stu-id="f9695-139">Ensure that you've engaged the right people for your project team.</span></span> <span data-ttu-id="f9695-140">Проверьте действия, которые вы выполнили, [в привлечении заинтересованных лиц к проекту.](upgrade-enlist-stakeholders.md)</span><span class="sxs-lookup"><span data-stu-id="f9695-140">Verify the steps you completed in [Enlist your project stakeholders](upgrade-enlist-stakeholders.md).</span></span>

<span data-ttu-id="f9695-141">Оценив среду, переперейти к следующему шагу — [подготовке службы.](upgrade-prepare-environment-prepare-service.md)</span><span class="sxs-lookup"><span data-stu-id="f9695-141">After you evaluate your environment, proceed to the next step: [Prepare your service](upgrade-prepare-environment-prepare-service.md).</span></span>