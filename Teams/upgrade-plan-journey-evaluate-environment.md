---
title: Оценка среды перед обновлением до Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Узнайте о требованиях для правильной оценки текущей среды для обновления до Teams.
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
ms.openlocfilehash: aeb236edddea69c1c112b695c9323de19da46092
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282206"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a><span data-ttu-id="1f45f-103">Оценка среды перед обновлением до Teams</span><span class="sxs-lookup"><span data-stu-id="1f45f-103">Evaluate your environment before upgrading to Teams</span></span>

<span data-ttu-id="1f45f-104">![Схема пути обновления с акцентом на этапе технической готовности](media/upgrade-banner-tech-readiness.png "Этапы пути обновления с акцентом на этапе технической готовности")</span><span class="sxs-lookup"><span data-stu-id="1f45f-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="1f45f-105">Эта статья является частью этапа технической готовности, которое вы завершаете параллельно с этапом подготовки пользователей.</span><span class="sxs-lookup"><span data-stu-id="1f45f-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="1f45f-106">Прежде чем при этом подтверждать, что вы выполнили эти действия на предыдущих этапах:</span><span class="sxs-lookup"><span data-stu-id="1f45f-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="1f45f-107">Привлечение заинтересованных лиц по проекту</span><span class="sxs-lookup"><span data-stu-id="1f45f-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="1f45f-108">Определение области проекта</span><span class="sxs-lookup"><span data-stu-id="1f45f-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="1f45f-109">Понятное сосуществование и совместное Skype для бизнеса и Teams</span><span class="sxs-lookup"><span data-stu-id="1f45f-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="1f45f-110">Выбор пути обновления</span><span class="sxs-lookup"><span data-stu-id="1f45f-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="1f45f-111">В этой статье представлен обзор требований для правильной оценки текущей среды для Teams.</span><span class="sxs-lookup"><span data-stu-id="1f45f-111">This article gives an overview of the requirements for properly evaluating your current environment for operating Teams.</span></span> <span data-ttu-id="1f45f-112">Оценивая свою среду, вы определяете риски и требования, которые влияют на общее развертывание.</span><span class="sxs-lookup"><span data-stu-id="1f45f-112">By evaluating your environment, you identify risks and requirements that will influence your overall deployment.</span></span> <span data-ttu-id="1f45f-113">Заранее определяя эти элементы, вы можете скорректировать свое планирование, чтобы добиться успеха.</span><span class="sxs-lookup"><span data-stu-id="1f45f-113">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-the-discovery-questionnaire"></a><span data-ttu-id="1f45f-114">Введение в анкету обнаружения</span><span class="sxs-lookup"><span data-stu-id="1f45f-114">Introduction to the Discovery Questionnaire</span></span>

<span data-ttu-id="1f45f-115">Для достижения поставленных ключевых результатов вы ранее приняли ключевые решения о обслуживании.</span><span class="sxs-lookup"><span data-stu-id="1f45f-115">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="1f45f-116">Далее необходимо выполнить обнаружение среды, чтобы оценить все аспекты, связанные с ИТ-инфраструктурой, сетью и операциями, чтобы подтвердить готовность организации к внедрению решения.</span><span class="sxs-lookup"><span data-stu-id="1f45f-116">The next step is to perform environmental discovery to evaluate all aspects relating to your IT infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span> <span data-ttu-id="1f45f-117">Обнаружение — один из первых ключевых этапов, которые необходимо предпринять при планировании пути к Teams.</span><span class="sxs-lookup"><span data-stu-id="1f45f-117">Discovery is one of the very first, key steps that you take when planning for your journey to Teams.</span></span> <span data-ttu-id="1f45f-118">Обнаружение среды должно включать оценку готовности сети, чтобы убедиться, что ваша сеть может поддерживать обновление до Teams.</span><span class="sxs-lookup"><span data-stu-id="1f45f-118">Environmental discovery must include a network readiness assessment to ensure your network can support upgrading to Teams.</span></span> <span data-ttu-id="1f45f-119">Вы выполняете подробное обнаружение среды, чтобы лучше понять ее текущее состояние, а также выявить все сложности или, что еще важнее, заблокировать выполнение Teams.</span><span class="sxs-lookup"><span data-stu-id="1f45f-119">You perform a detailed discovery of your environment to better understand its current state and to reveal any difficulties or—even more important—possible blockers to the execution of your Teams rollout.</span></span>

<span data-ttu-id="1f45f-120">Технические риски определяются в ходе оценки среды и проверки готовности к внедрению, а также разрабатываются планы снижения для каждого обнаруженного риска.</span><span class="sxs-lookup"><span data-stu-id="1f45f-120">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="1f45f-121">Эти сведения следует включить в реестр рисков.</span><span class="sxs-lookup"><span data-stu-id="1f45f-121">You should incorporate this information in the risk register.</span></span>

<span data-ttu-id="1f45f-122">Все вопросы, относящиеся к существующей инфраструктуре совместной работы и организации Microsoft 365 или Office 365 организации, сети, конечные точки, операции, а также внедрение и готовности, включаются в анкету по обнаружению среды.</span><span class="sxs-lookup"><span data-stu-id="1f45f-122">All matters related to your existing collaboration infrastructure and Microsoft 365 or Office 365 organization, networking, endpoints, operations, and adoption and readiness are included as part of the environmental discovery questionnaire.</span></span> <span data-ttu-id="1f45f-123">Работайте со своей проектной командой, чтобы предоставить запрашиваемую информацию как можно более подробно, чтобы упростить планирование.</span><span class="sxs-lookup"><span data-stu-id="1f45f-123">Work with your project team to provide the requested information with as much detail as possible to facilitate your planning activities.</span></span>

<span data-ttu-id="1f45f-124">[Анкета](upgrade-plan-journey-discovery-questionnaire.md) состоит из следующих разделов, чтобы подтвердить готовность организации к развертыванию Teams в нескольких основных областях.</span><span class="sxs-lookup"><span data-stu-id="1f45f-124">[The questionnaire](upgrade-plan-journey-discovery-questionnaire.md) is divided into the following sections to confirm your organization's readiness for your Teams deployment in several major areas:</span></span>

- <span data-ttu-id="1f45f-125">Microsoft 365 или Office 365 сведения об организации</span><span class="sxs-lookup"><span data-stu-id="1f45f-125">Microsoft 365 or Office 365 organization details</span></span>
- <span data-ttu-id="1f45f-126">Сводка по существующей платформе совместной работы</span><span class="sxs-lookup"><span data-stu-id="1f45f-126">Existing collaboration platform summary</span></span>
- <span data-ttu-id="1f45f-127">Сведения о развертывании платформы для совместной работы</span><span class="sxs-lookup"><span data-stu-id="1f45f-127">Collaboration platform deployment details</span></span>
- <span data-ttu-id="1f45f-128">Сеть и доступ к Microsoft 365 или Office 365 службам</span><span class="sxs-lookup"><span data-stu-id="1f45f-128">Networking and access to Microsoft 365 or Office 365 services</span></span>
- <span data-ttu-id="1f45f-129">Конечные точки</span><span class="sxs-lookup"><span data-stu-id="1f45f-129">Endpoints</span></span>
- <span data-ttu-id="1f45f-130">Операции</span><span class="sxs-lookup"><span data-stu-id="1f45f-130">Operations</span></span>
- <span data-ttu-id="1f45f-131">Внедрение и готовность</span><span class="sxs-lookup"><span data-stu-id="1f45f-131">Adoption and readiness</span></span>

> [!TIP]
> <span data-ttu-id="1f45f-132">Для начала скопируйте анкету в Microsoft Word документ.</span><span class="sxs-lookup"><span data-stu-id="1f45f-132">You can start by copying the questionnaire into a Microsoft Word document.</span></span> <span data-ttu-id="1f45f-133">Попробуйте ответить на все вопросы и зафиксировать все сведения по мере перемещения.</span><span class="sxs-lookup"><span data-stu-id="1f45f-133">Try to answer all questions and capture all details as you move through.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/><span data-ttu-id="1f45f-134">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="1f45f-134">Decision point</span></span></td><td><ul><li><span data-ttu-id="1f45f-135">Кто отвечаете за выполнение оценки среды?</span><span class="sxs-lookup"><span data-stu-id="1f45f-135">Who will be responsible for completing an environment assessment?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/><span data-ttu-id="1f45f-136">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="1f45f-136">Next step</span></span></td><td><ul><li><span data-ttu-id="1f45f-137">Документировать результаты оценки среды.</span><span class="sxs-lookup"><span data-stu-id="1f45f-137">Document the results of the environment assessment.</span></span></li></ul></td></tr>
</table>


## <a name="project-team"></a><span data-ttu-id="1f45f-138">Project группы</span><span class="sxs-lookup"><span data-stu-id="1f45f-138">Project team</span></span>

<span data-ttu-id="1f45f-139">Убедитесь, что вы вовлечены в проект нужных людей.</span><span class="sxs-lookup"><span data-stu-id="1f45f-139">Ensure that you've engaged the right people for your project team.</span></span> <span data-ttu-id="1f45f-140">Проверьте действия, которые вы выполнили, в области [Привлечение заинтересованных лиц к проекту.](upgrade-enlist-stakeholders.md)</span><span class="sxs-lookup"><span data-stu-id="1f45f-140">Verify the steps you completed in [Enlist your project stakeholders](upgrade-enlist-stakeholders.md).</span></span>

<span data-ttu-id="1f45f-141">Оценив среду, перетесь к следующему шагу: [Подготовка службы.](upgrade-prepare-environment-prepare-service.md)</span><span class="sxs-lookup"><span data-stu-id="1f45f-141">After you evaluate your environment, proceed to the next step: [Prepare your service](upgrade-prepare-environment-prepare-service.md).</span></span>