---
title: Развертывание групп Майкрософт облачная служба голосовой связи
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 05/16/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Загрузите страница Playbook Включение сайта Планирование групп развертывания и ускорить и оптимизации круга пользователей, качество и удовлетворенность с точки зрения.
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45d74a26b65f788e914587b521a5bb14ea606567
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "25012307"
---
# <a name="deploy-my-service"></a><span data-ttu-id="a9673-103">Развернуть службу</span><span class="sxs-lookup"><span data-stu-id="a9673-103">Deploy my service</span></span>

<span data-ttu-id="a9673-104">В этой статье дается обзор требований для правильного развертывания облачные службы голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="a9673-104">This article gives an overview of the requirements for properly deploying cloud voice services.</span></span> <span data-ttu-id="a9673-105">Выполнив инструкции по развертыванию облачные службы голосовой связи, можно убедиться в том успешно учетную запись для все требования и возможности повторяемого результатов.</span><span class="sxs-lookup"><span data-stu-id="a9673-105">By following prescriptive guidance for deploying cloud voice services, you can make sure you successfully account for all requirements and deliver repeatable results.</span></span>

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="a9673-106">Страница playbook Включение сайта для рабочих нагрузок группами Майкрософт голосовой связи</span><span class="sxs-lookup"><span data-stu-id="a9673-106">Site enablement playbook for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="a9673-107">Используйте этот страница playbook для вашей организации успешно планирование и выполнение развертывания функций голосовой связи группами Майкрософт на основе узла.</span><span class="sxs-lookup"><span data-stu-id="a9673-107">Use this playbook to help your organization successfully plan and execute the rollout of Microsoft Teams voice features on a site-by-site basis.</span></span>

<span data-ttu-id="a9673-108">Включая все необходимые действия, рекомендуется временных шкал, а также ссылки на соответствующие рекомендации для каждого действия эта страница playbook охватывает начала до конца рекомендации для обеспечения успешного развертывания групп голосовой связи для данного сайта, посвященных факторы, которые важны для пользователя.</span><span class="sxs-lookup"><span data-stu-id="a9673-108">Including all required activities, recommended timelines, and links to corresponding guidance for each activity, this playbook covers end-to-end guidance to help ensure a successful Teams voice deployment for a given site, focusing on factors that are important to the user.</span></span>

<span data-ttu-id="a9673-109">Выполнив действия в этом вкладка playbook вашей организации выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a9673-109">By completing the activities in this playbook, your organization can:</span></span>

-   <span data-ttu-id="a9673-110">Эффективное планирование и планирование процесса развертывания групп.</span><span class="sxs-lookup"><span data-stu-id="a9673-110">Effectively plan and schedule your Teams rollout.</span></span>

-   <span data-ttu-id="a9673-111">Ускорение и оптимизация внедрения пользователя.</span><span class="sxs-lookup"><span data-stu-id="a9673-111">Accelerate and optimize user adoption.</span></span>

-   <span data-ttu-id="a9673-112">Уменьшение потребности в поддержке и выше.</span><span class="sxs-lookup"><span data-stu-id="a9673-112">Reduce support needs and increase user satisfaction.</span></span>

> [!NOTE]
> <span data-ttu-id="a9673-113">В этой статье и связанные страница playbook не предназначен для описания каждого этапа технические конфигурации, необходимые для подключения службы или предоставление гудка на определенный сайт.</span><span class="sxs-lookup"><span data-stu-id="a9673-113">This article and the associated playbook aren’t intended to describe every technical configuration step required for service enablement or providing dial tone to a specific site.</span></span> <span data-ttu-id="a9673-114">Вместо этого они сосредоточиться на действия и задачи, которые рекомендуется встроенного пользователям легко и их начать использование групп рабочих нагрузок голосовой связи через быстро и легко перехода внедрения высокая скорость, при минимизации требования для поддержки.</span><span class="sxs-lookup"><span data-stu-id="a9673-114">Instead, they focus on activities and tasks recommended to onboard users easily and have them start consuming Teams voice workloads through a fast and smooth transition with a high adoption rate, while minimizing support requirements.</span></span> <span data-ttu-id="a9673-115">Техническое руководство по оптимальным образом настроить среду для голосовой связи группами см контрольные списки адаптация новых сотрудников для [настройки рабочих нагрузок голосовые команды](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), [Настройка прямой маршрутизации в группах](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [группами основные возможности](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [сети для групп](onboarding-checklist-configure-networking.md), а также [Включение Office 365](onboarding-checklist-enable-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="a9673-115">For technical guidance on how to best configure your environment for Teams voice, see the onboarding checklists for [configuring Teams voice workloads](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), [configuring Direct Routing in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [Teams core capabilities](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [networking for Teams](onboarding-checklist-configure-networking.md), and [enabling Office 365](onboarding-checklist-enable-office-365.md).</span></span>

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a><span data-ttu-id="a9673-116">Страница playbook фокус областей</span><span class="sxs-lookup"><span data-stu-id="a9673-116">Playbook focus areas</span></span>

<span data-ttu-id="a9673-117">Страница playbook выделена устранения факторов, влияющих на пользователя с точки зрения развертывания голосовые команды.</span><span class="sxs-lookup"><span data-stu-id="a9673-117">The focus of the playbook is to address the factors that influence the user’s perception of a Teams voice deployment.</span></span> <span data-ttu-id="a9673-118">Действия и задачи сгруппированы в следующих областях фокус.</span><span class="sxs-lookup"><span data-stu-id="a9673-118">Activities and tasks are grouped into the following focus areas:</span></span>

-   <span data-ttu-id="a9673-119">Проверка готовности службы</span><span class="sxs-lookup"><span data-stu-id="a9673-119">Validation of service readiness</span></span>
    - <span data-ttu-id="a9673-120">Аудиоконференция</span><span class="sxs-lookup"><span data-stu-id="a9673-120">Audio Conferencing</span></span>
    - <span data-ttu-id="a9673-121">Планы звонков</span><span class="sxs-lookup"><span data-stu-id="a9673-121">Calling Plans</span></span>
    - <span data-ttu-id="a9673-122">Прямая отправка</span><span class="sxs-lookup"><span data-stu-id="a9673-122">Direct Routing</span></span>

-   <span data-ttu-id="a9673-123">Включение пользователя</span><span class="sxs-lookup"><span data-stu-id="a9673-123">User enablement</span></span>

-   <span data-ttu-id="a9673-124">Конечные точки</span><span class="sxs-lookup"><span data-stu-id="a9673-124">Endpoints</span></span>

-   <span data-ttu-id="a9673-125">Об использовании и качества</span><span class="sxs-lookup"><span data-stu-id="a9673-125">Usage and quality</span></span>

-   <span data-ttu-id="a9673-126">Освоение</span><span class="sxs-lookup"><span data-stu-id="a9673-126">Adoption</span></span>

<span data-ttu-id="a9673-127">[Страница Playbook Включение сайта для голосовой связи (страница Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) — это книга Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="a9673-127">The [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) is a Microsoft Excel workbook.</span></span> <span data-ttu-id="a9673-128">Каждый из пяти основное внимание уделяется представляет собой отдельный лист в книге, а каждой задачи развертывания и действия по группам на один из следующих таблиц.</span><span class="sxs-lookup"><span data-stu-id="a9673-128">Each of these five focus areas is a separate sheet in the workbook, and each deployment task and activity is grouped onto one of these sheets.</span></span>

<span data-ttu-id="a9673-129">![Снимок экрана с страница playbook] (media/deploy-my-service-image1.png "Снимок экрана с страница playbook")</span><span class="sxs-lookup"><span data-stu-id="a9673-129">![Screenshot of the playbook](media/deploy-my-service-image1.png "Screenshot of the playbook")</span></span>

> [!NOTE]
> <span data-ttu-id="a9673-130">Вы создадите отдельный экземпляр страница playbook для каждого сайта в области действия для развертывания групп.</span><span class="sxs-lookup"><span data-stu-id="a9673-130">You’ll create a separate instance of the playbook for each site in scope for your Teams rollout.</span></span>

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a><span data-ttu-id="a9673-131">Как использовать страница playbook</span><span class="sxs-lookup"><span data-stu-id="a9673-131">How to use the playbook</span></span>

<span data-ttu-id="a9673-132">Независимо от того, размер и сложность расположения, включение каждого сайта требует планировании задачи и действия достаточно первых — и выполнять их в оптимальном порядке — до, во время и после развертывания фактической службы.</span><span class="sxs-lookup"><span data-stu-id="a9673-132">Regardless of the size and complexity of the location, enabling each site requires that you plan your tasks and activities early enough—and execute them in optimal order—before, during, and after the actual service rollout.</span></span> <span data-ttu-id="a9673-133">Мы рекомендуем, выполните следующие действия, как планировать и выполнять свои собственные пути к голосовым группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a9673-133">We recommend that you follow these steps as you plan and execute your own journey to Microsoft Teams voice.</span></span>

1.  <span data-ttu-id="a9673-134">Загрузите [страница Playbook Включение сайта для голосовой связи (страница Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) для групп Майкрософт голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="a9673-134">Download the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) for Microsoft Teams Voice.</span></span>

2.  <span data-ttu-id="a9673-135">Создайте отдельный экземпляр страница playbook для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="a9673-135">Create a separate copy of the playbook for each site.</span></span>

3.  <span data-ttu-id="a9673-136">Замените на ярлычок листа с именем **страница Playbook для {SiteName кода}**, **{SiteName-код}** имя соответствующего сайта и/или код узла.</span><span class="sxs-lookup"><span data-stu-id="a9673-136">On the tab for the sheet named **Playbook for {SiteName-Code}**, replace **{SiteName-Code}** with the relevant site name and/or site code.</span></span>

4.  <span data-ttu-id="a9673-137">Введите **имя сайта, код узла**и **запланированных запуска даты**, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="a9673-137">Enter the **Site name, Site code**, and **Planned launch date**, as illustrated below.</span></span> <span data-ttu-id="a9673-138">Это важным этапом, так как регулировка рекомендуемые крайние сроки для каждой операции страница playbook.</span><span class="sxs-lookup"><span data-stu-id="a9673-138">This is a critical step, because it adjusts the recommended deadlines for every activity in the playbook.</span></span>

    <span data-ttu-id="a9673-139">![Пример с именем сайта Нью-Йорк, код узла NY01, и дату запуска запланированных 20 марта 18] (media/deploy-my-service-image2.png "Пример с именем сайта Нью-Йорк, код узла NY01, и дату запуска запланированных 20 марта 18")</span><span class="sxs-lookup"><span data-stu-id="a9673-139">![Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18](media/deploy-my-service-image2.png "Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18")</span></span>

5.  <span data-ttu-id="a9673-140">Просмотрите каждого действия, выполните необходимые действия и обновления состояния по мере изучения временной шкалы.</span><span class="sxs-lookup"><span data-stu-id="a9673-140">Review each activity, take necessary actions, and update the status as you walk through the timeline.</span></span> <span data-ttu-id="a9673-141">Состояние представлено графически, как описано ниже:</span><span class="sxs-lookup"><span data-stu-id="a9673-141">Status is represented graphically, as described below:</span></span>
    <ul>
    <li><span data-ttu-id="a9673-142">![Зеленый флажок](media/deploy-my-service-image3.png) **Да или Неприменимо (зеленый):** завершения операции или не применимо для этого сайта, а не требуется никаких действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="a9673-142">![Green check mark](media/deploy-my-service-image3.png) **Yes, or not applicable (green):** The activity has been completed, or it’s not applicable for this site, and no further action is needed.</span></span></li>
    <li><span data-ttu-id="a9673-143">![Желтый восклицательный знак](media/deploy-my-service-image4.png) **действия не будет завершено, но при этом (желтый):** действия не были выполнены и необходимо обновить до Да или нет, по расписанию.</span><span class="sxs-lookup"><span data-stu-id="a9673-143">![Yellow exclamation point](media/deploy-my-service-image4.png) **The activity isn’t completed yet (yellow):** The activity hasn’t been completed yet, and must be updated to Yes or No on its schedule.</span></span></li>
    <li><span data-ttu-id="a9673-144">![Красный X](media/deploy-my-service-image5.png) **Нет (красный):** действие не может быть завершена из-за неполадок и должен передаваться к собранию состояние проекта.</span><span class="sxs-lookup"><span data-stu-id="a9673-144">![Red X](media/deploy-my-service-image5.png) **No (red):** The activity can’t be completed because of an issue and must be carried to the project status meeting.</span></span></li></ul>

6.  <span data-ttu-id="a9673-145">В каждом разделе сводятся состояние и заголовок раздела имеет формат с одним из следующих индикаторов состояния.</span><span class="sxs-lookup"><span data-stu-id="a9673-145">The status is rolled up within each section, and the section heading is formatted with one of these status indicators.</span></span> <span data-ttu-id="a9673-146">Еженедельные также устанавливается **состояние** автоматически.</span><span class="sxs-lookup"><span data-stu-id="a9673-146">**Weekly status** is also updated automatically.</span></span>

<span data-ttu-id="a9673-147">![Снимок экрана с еженедельно состояние сведение данных в страница playbook] (media/deploy-my-service-image6.png "Снимок экрана с еженедельно состояние сведение данных в страница playbook")</span><span class="sxs-lookup"><span data-stu-id="a9673-147">![Screenshot of the weekly status roll-ups in the playbook](media/deploy-my-service-image6.png "Screenshot of the weekly status roll-ups in the playbook")</span></span>

> [!TIP]
> <span data-ttu-id="a9673-148">Повторите предыдущие шаги для всех расположений, у вас есть.</span><span class="sxs-lookup"><span data-stu-id="a9673-148">Repeat the steps above for all the locations you have.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a9673-149">Некоторые из них не применялось для всех сайтов и расположения.</span><span class="sxs-lookup"><span data-stu-id="a9673-149">Some steps might not be applicable to all locations and sites.</span></span> <span data-ttu-id="a9673-150">Если определенное действие не относится к сайту, необходимо выбрать **неприменимо** для этого действия.</span><span class="sxs-lookup"><span data-stu-id="a9673-150">If a specific activity isn’t relevant to a site, you must select **Not applicable** for this activity.</span></span> <span data-ttu-id="a9673-151">**Не удалять** какие-либо строки в страница playbook; в противном случае формулы свертки состояния не будут работать.</span><span class="sxs-lookup"><span data-stu-id="a9673-151">**DO NOT DELETE** any rows in the playbook; if you do, the status roll-up formulas won’t work.</span></span><br/><br/>
<span data-ttu-id="a9673-152">Обратите внимание на действия, которые может занимать больше времени, чем запланированных для, например номер перенос и закупок.</span><span class="sxs-lookup"><span data-stu-id="a9673-152">Pay attention to activities that might take more time than you planned for, such as number porting and procurement activities.</span></span> <span data-ttu-id="a9673-153">Эти действия может отрицательно сказаться на временная шкала развертывания сайта.</span><span class="sxs-lookup"><span data-stu-id="a9673-153">These activities can negatively affect the site deployment timeline.</span></span> <span data-ttu-id="a9673-154">Убедитесь, что для просмотра и обновить список действий и связанные временной шкалы еженедельно и представлять их на [собраниях исполнительного комитета](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) для обеспечения учитывать состояние каждого сайта и любые возможные отклонения от графика развертывания заинтересованных лиц.</span><span class="sxs-lookup"><span data-stu-id="a9673-154">Be sure to review and update the activity list and the associated timeline weekly, and present them at [steering committee meetings](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) to ensure that stakeholders are aware of the status of each site and any possible deviations from the deployment schedule.</span></span>

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="a9673-155">Точки принятия решений</span><span class="sxs-lookup"><span data-stu-id="a9673-155">Decision points</span></span></td><td><ul><li><span data-ttu-id="a9673-156">Решите, если страница Playbook Включение сайта является обязательным для развертывания.</span><span class="sxs-lookup"><span data-stu-id="a9673-156">Decide if the Site Enablement Playbook is required for your deployment.</span></span></li><li><span data-ttu-id="a9673-157">Определить, кто будет отвечать по настройке страница Playbook Включение сайта для групп Майкрософт для каждого узла, который вы развертываете.</span><span class="sxs-lookup"><span data-stu-id="a9673-157">Decide who will be responsible for customizing the Site Enablement Playbook for Microsoft Teams for every site you’ll deploy.</span></span></li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="a9673-158">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="a9673-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="a9673-159">[Загрузите страница Playbook Включение сайта](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true).</span><span class="sxs-lookup"><span data-stu-id="a9673-159">[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true).</span></span></li><li><span data-ttu-id="a9673-160">Настройка страница Playbook Включение сайта для первого сайта.</span><span class="sxs-lookup"><span data-stu-id="a9673-160">Customize the Site Enablement Playbook for your first site.</span></span></li><li><span data-ttu-id="a9673-161">Повторите для дополнительных сайтов.</span><span class="sxs-lookup"><span data-stu-id="a9673-161">Repeat as needed for additional sites.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->