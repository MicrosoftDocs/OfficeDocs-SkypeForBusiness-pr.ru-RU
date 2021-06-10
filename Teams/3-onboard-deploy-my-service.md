---
title: Развертывание облачной голосовой службы Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
audience:
- ITPro
- admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Скачайте приложение Site Enablement Playbook, чтобы спланировать процесс Teams, ускорить и оптимизировать процесс принятия пользователями, повысить качество и удовлетворенность.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c3f0105a04484efcabd5ab6c55d1269c3627895
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112635"
---
# <a name="deploy-my-service"></a><span data-ttu-id="7ebd1-103">Развертывание службы</span><span class="sxs-lookup"><span data-stu-id="7ebd1-103">Deploy my service</span></span>

<span data-ttu-id="7ebd1-104">В этой статье дается обзор требований для правильного развертывания облачных голосовых служб.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-104">This article gives an overview of the requirements for properly deploying cloud voice services.</span></span> <span data-ttu-id="7ebd1-105">Следуя рекомендациям по развертыванию облачных голосовых служб, вы можете успешно выполнить учет всех требований и обеспечить повторяемые результаты.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-105">By following prescriptive guidance for deploying cloud voice services, you can make sure you successfully account for all requirements and deliver repeatable results.</span></span>

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="7ebd1-106">Playbook enablement site for Microsoft Teams voice workloads</span><span class="sxs-lookup"><span data-stu-id="7ebd1-106">Site enablement playbook for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="7ebd1-107">Эта книга поможет вашей организации успешно спланировать и выполнить Microsoft Teams голосовых функций по сайтам.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-107">Use this playbook to help your organization successfully plan and execute the rollout of Microsoft Teams voice features on a site-by-site basis.</span></span>

<span data-ttu-id="7ebd1-108">В этом справочнике, включая все необходимые действия, рекомендуемые временные шкалы и ссылки на соответствующие рекомендации по каждому действию, даются готовые инструкции по обеспечению успешного Teams голосового развертывания на данном сайте с учетом факторов, важных для пользователя.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-108">Including all required activities, recommended timelines, and links to corresponding guidance for each activity, this playbook covers end-to-end guidance to help ensure a successful Teams voice deployment for a given site, focusing on factors that are important to the user.</span></span>

<span data-ttu-id="7ebd1-109">Выполив действия в этом playbook, ваша организация может:</span><span class="sxs-lookup"><span data-stu-id="7ebd1-109">By completing the activities in this playbook, your organization can:</span></span>

-   <span data-ttu-id="7ebd1-110">Эффективно планируйте и планируйте Teams.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-110">Effectively plan and schedule your Teams rollout.</span></span>

-   <span data-ttu-id="7ebd1-111">Ускорение и оптимизация принятия пользователей.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-111">Accelerate and optimize user adoption.</span></span>

-   <span data-ttu-id="7ebd1-112">Снизить потребности в поддержке и повысить удовлетворенность пользователей.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-112">Reduce support needs and increase user satisfaction.</span></span>

> [!NOTE]
> <span data-ttu-id="7ebd1-113">В этой статье и связанной с ней книге не описываются все этапы технической конфигурации, необходимые для реализации службы или предоставления набора номера определенному сайту.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-113">This article and the associated playbook aren’t intended to describe every technical configuration step required for service enablement or providing dial tone to a specific site.</span></span> <span data-ttu-id="7ebd1-114">Вместо этого они уделяют основное внимание действиям и задачам, рекомендуемым пользователям, и могут начать использовать Teams голосовой нагрузки благодаря быстрому и плавному переходу с высокой скоростью принятия, свести к минимуму требования к поддержке.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-114">Instead, they focus on activities and tasks recommended to onboard users easily and have them start consuming Teams voice workloads through a fast and smooth transition with a high adoption rate, while minimizing support requirements.</span></span> <span data-ttu-id="7ebd1-115">Технические рекомендации по настройке среды для голосовой связи Teams см. в контрольных списках для настройки рабочих нагрузок голосовой связи [Teams,](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)настройки прямой маршрутики в [Teams,](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md) [Teams](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)основных возможностей, сети для [Teams](prepare-network.md)и включения [Microsoft 365 или Office 365.](onboarding-checklist-enable-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="7ebd1-115">For technical guidance on how to best configure your environment for Teams voice, see the onboarding checklists for [configuring Teams voice workloads](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), [configuring Direct Routing in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [Teams core capabilities](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [networking for Teams](prepare-network.md), and [enabling Microsoft 365 or Office 365](onboarding-checklist-enable-office-365.md).</span></span>

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a><span data-ttu-id="7ebd1-116">Области фокуса в книге воспроизведения</span><span class="sxs-lookup"><span data-stu-id="7ebd1-116">Playbook focus areas</span></span>

<span data-ttu-id="7ebd1-117">Основное внимание в книге уделяется устранению факторов, влияющих на развертывание голосовой Teams пользователя.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-117">The focus of the playbook is to address the factors that influence the user’s perception of a Teams voice deployment.</span></span> <span data-ttu-id="7ebd1-118">Действия и задачи сгруппировать по следующим областям:</span><span class="sxs-lookup"><span data-stu-id="7ebd1-118">Activities and tasks are grouped into the following focus areas:</span></span>

-   <span data-ttu-id="7ebd1-119">Проверка готовности службы</span><span class="sxs-lookup"><span data-stu-id="7ebd1-119">Validation of service readiness</span></span>
    - <span data-ttu-id="7ebd1-120">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="7ebd1-120">Audio Conferencing</span></span>
    - <span data-ttu-id="7ebd1-121">Планы звонков</span><span class="sxs-lookup"><span data-stu-id="7ebd1-121">Calling Plans</span></span>
    - <span data-ttu-id="7ebd1-122">Прямая маршрутия</span><span class="sxs-lookup"><span data-stu-id="7ebd1-122">Direct Routing</span></span>

-   <span data-ttu-id="7ebd1-123">Пользовательский ветвление</span><span class="sxs-lookup"><span data-stu-id="7ebd1-123">User enablement</span></span>

-   <span data-ttu-id="7ebd1-124">Конечные точки</span><span class="sxs-lookup"><span data-stu-id="7ebd1-124">Endpoints</span></span>

-   <span data-ttu-id="7ebd1-125">Использование и качество</span><span class="sxs-lookup"><span data-stu-id="7ebd1-125">Usage and quality</span></span>

-   <span data-ttu-id="7ebd1-126">Внедрение</span><span class="sxs-lookup"><span data-stu-id="7ebd1-126">Adoption</span></span>

<span data-ttu-id="7ebd1-127">Книга [site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) является Microsoft Excel книгой.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-127">The [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) is a Microsoft Excel workbook.</span></span> <span data-ttu-id="7ebd1-128">Каждая из этих пяти областей является отдельным листом в книге, а каждая задача развертывания и действия группируется на один из этих листов.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-128">Each of these five focus areas is a separate sheet in the workbook, and each deployment task and activity is grouped onto one of these sheets.</span></span>

<span data-ttu-id="7ebd1-129">![Снимок экрана: playbook enablement сайта](media/deploy-my-service-image1.png "Снимок экрана: книга воспроизведения")</span><span class="sxs-lookup"><span data-stu-id="7ebd1-129">![Screenshot of the site enablement playbook](media/deploy-my-service-image1.png "Screenshot of the playbook")</span></span>

> [!NOTE]
> <span data-ttu-id="7ebd1-130">Вы создадим отдельный экземпляр книги для каждого сайта, в области Teams развернутого.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-130">You’ll create a separate instance of the playbook for each site in scope for your Teams rollout.</span></span>

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a><span data-ttu-id="7ebd1-131">Использование книги</span><span class="sxs-lookup"><span data-stu-id="7ebd1-131">How to use the playbook</span></span>

<span data-ttu-id="7ebd1-132">Независимо от размера и сложности расположения для каждого сайта необходимо заранее спланировать задачи и действия и выполнить их в оптимальном порядке — до, во время и после фактического внедрения службы.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-132">Regardless of the size and complexity of the location, enabling each site requires that you plan your tasks and activities early enough—and execute them in optimal order—before, during, and after the actual service rollout.</span></span> <span data-ttu-id="7ebd1-133">Мы рекомендуем вам выполнить эти действия по мере планирования и выполнения собственного пути, чтобы Microsoft Teams голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-133">We recommend that you follow these steps as you plan and execute your own journey to Microsoft Teams voice.</span></span>

1. <span data-ttu-id="7ebd1-134">Скачайте [playbook site Enablement playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) для Microsoft Teams Voice.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-134">Download the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) for Microsoft Teams Voice.</span></span>

2. <span data-ttu-id="7ebd1-135">Создайте отдельную копию книги для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-135">Create a separate copy of the playbook for each site.</span></span>

3. <span data-ttu-id="7ebd1-136">На вкладке листа с именем **Playbook для {SiteName-Code}** замените **{SiteName-Code}** соответствующим именем сайта и/или кодом сайта.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-136">On the tab for the sheet named **Playbook for {SiteName-Code}**, replace **{SiteName-Code}** with the relevant site name and/or site code.</span></span>

4. <span data-ttu-id="7ebd1-137">Введите **имя сайта, код сайта** и запланированную дату **запуска,** как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-137">Enter the **Site name, Site code**, and **Planned launch date**, as illustrated below.</span></span> <span data-ttu-id="7ebd1-138">Это крайне важное действие, так как оно корректирует рекомендуемые крайние сроки для всех действий в книге.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-138">This is a critical step, because it adjusts the recommended deadlines for every activity in the playbook.</span></span>

   <span data-ttu-id="7ebd1-139">![Пример с названием сайта, кодом сайта и запланированной датой запуска](media/deploy-my-service-image2.png "Пример с названием сайта в Москве, кодом сайта NY01 и запланированной датой запуска 20 марта 2018 г.")</span><span class="sxs-lookup"><span data-stu-id="7ebd1-139">![Example with site name, site code, and planned launch date](media/deploy-my-service-image2.png "Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18")</span></span>

5. <span data-ttu-id="7ebd1-140">Просматривайте каждое действие, принимайте необходимые действия и обновляйте состояние по мере просмотра временной шкалы.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-140">Review each activity, take necessary actions, and update the status as you walk through the timeline.</span></span> <span data-ttu-id="7ebd1-141">Состояние представлено графически, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-141">Status is represented graphically, as described below:</span></span>
  
   - <span data-ttu-id="7ebd1-142">![Изображение зеленой метки с изображением да или не применимо ](media/deploy-my-service-image3.png) **(зеленый):** действие завершено или не применимо к этому сайту, и никаких дополнительных действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-142">![Illustration of a green check mark](media/deploy-my-service-image3.png) **Yes, or not applicable (green):** The activity has been completed, or it’s not applicable for this site, and no further action is needed.</span></span></li>
   - <span data-ttu-id="7ebd1-143">![Изображение желтого восклицательного пункта Действие еще не завершено (желтое): действие еще не выполнено и в календарном плане его необходимо обновить до "Да" или ](media/deploy-my-service-image4.png) <strong></strong> "Нет".</span><span class="sxs-lookup"><span data-stu-id="7ebd1-143">![Illustration of a yellow exclamation point](media/deploy-my-service-image4.png) <strong>The activity isn’t completed yet (yellow):</strong> The activity hasn’t been completed yet, and must be updated to Yes or No on its schedule.</span></span></li>
   - <span data-ttu-id="7ebd1-144">![Красный крестик, указывающий на отсутствие "Нет" ](media/deploy-my-service-image5.png) <strong>(красный):</strong> действие не может быть выполнено из-за проблемы и должно быть выполнено в собрании по состоянии проекта.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-144">![Illustration of a red X indicating no](media/deploy-my-service-image5.png) <strong>No (red):</strong> The activity can’t be completed because of an issue and must be carried to the project status meeting.</span></span></li></ul>

6. <span data-ttu-id="7ebd1-145&quot;>Состояние скатится в каждом разделе, а заголовок раздела будет отформатирован с помощью одного из этих индикаторов состояния.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;7ebd1-145&quot;>The status is rolled up within each section, and the section heading is formatted with one of these status indicators.</span></span> <span data-ttu-id=&quot;7ebd1-146&quot;>**Еженедельное состояние** также обновляется автоматически.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;7ebd1-146&quot;>**Weekly status** is also updated automatically.</span></span>

<span data-ttu-id=&quot;7ebd1-147&quot;>![Снимок экрана: еженедельные скайп-альбомы состояния в книге](media/deploy-my-service-image6.png &quot;Снимок экрана: еженедельные скайп-альбомы состояния в книге")</span><span class="sxs-lookup"><span data-stu-id="7ebd1-147">![Screenshot of the weekly status roll-ups in the playbook](media/deploy-my-service-image6.png "Screenshot of the weekly status roll-ups in the playbook")</span></span>

> [!TIP]
> <span data-ttu-id="7ebd1-148">Повторите эти действия для всех мест, которые у вас есть.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-148">Repeat the steps above for all the locations you have.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7ebd1-149">Некоторые действия могут быть применимы не для всех местоположений и сайтов.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-149">Some steps might not be applicable to all locations and sites.</span></span> <span data-ttu-id="7ebd1-150">Если определенное действие не относится к сайту, необходимо выбрать значение Не **относится** к этому действию.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-150">If a specific activity isn’t relevant to a site, you must select **Not applicable** for this activity.</span></span> <span data-ttu-id="7ebd1-151">**НЕ УДАЛЯЙТЕ** строки в книге; В этом случае скаймерсы состояния не будут работать.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-151">**DO NOT DELETE** any rows in the playbook; if you do, the status roll-up formulas won’t work.</span></span><br/><br/>
<span data-ttu-id="7ebd1-152">Обратите внимание на действия, которые могут занять больше времени, чем вы планировали, например перенос номеров и мероприятия по закупкам.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-152">Pay attention to activities that might take more time than you planned for, such as number porting and procurement activities.</span></span> <span data-ttu-id="7ebd1-153">Эти действия могут отрицательно сказаться на временной шкале развертывания сайта.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-153">These activities can negatively affect the site deployment timeline.</span></span> <span data-ttu-id="7ebd1-154">Обязательно просматривайте и обновляйте список действий и связанную с [](./envision-steering-committee-complete-guide.md) ней временную шкалу еженедельно, а затем представить их на собраниях комитета по управлению, чтобы заинтересованные лица знали о состоянии каждого сайта и возможных отклонениях от расписания развертывания.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-154">Be sure to review and update the activity list and the associated timeline weekly, and present them at [steering committee meetings](./envision-steering-committee-complete-guide.md) to ensure that stakeholders are aware of the status of each site and any possible deviations from the deployment schedule.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="7ebd1-155">Точки принятия решений</span><span class="sxs-lookup"><span data-stu-id="7ebd1-155">Decision points</span></span></td><td><ul><li><span data-ttu-id="7ebd1-156">Решите, требуется ли для развертывания playbook site Enablement.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-156">Decide if the Site Enablement Playbook is required for your deployment.</span></span></li><li><span data-ttu-id="7ebd1-157">Определите, кто будет отвечать за настройку воспроизведения Microsoft Teams для каждого сайта, который вы будете развертывать.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-157">Decide who will be responsible for customizing the Site Enablement Playbook for Microsoft Teams for every site you’ll deploy.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="7ebd1-158">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="7ebd1-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="7ebd1-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Скачайте книгу site Enablement Playbook</a>.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Download the Site Enablement Playbook</a>.</span></span></li><li><span data-ttu-id="7ebd1-160">Настройте книгу воспроизведения enablement сайта для первого сайта.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-160">Customize the Site Enablement Playbook for your first site.</span></span></li><li><span data-ttu-id="7ebd1-161">При необходимости повторите эти процедуры для дополнительных сайтов.</span><span class="sxs-lookup"><span data-stu-id="7ebd1-161">Repeat as needed for additional sites.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->