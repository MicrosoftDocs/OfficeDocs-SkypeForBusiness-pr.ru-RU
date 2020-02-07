---
title: Развертывание облачной голосовой службы Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
audience: admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Скачайте сайт Плайбук, чтобы спланировать выгрузку и ускорить и оптимизировать работу пользователей, восприятие качества и удовлетворенность вашими группами.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65a9c79dd29656b7bdc8563f0444d90133399f2b
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825177"
---
# <a name="deploy-my-service"></a><span data-ttu-id="4561c-103">Развертывание службы</span><span class="sxs-lookup"><span data-stu-id="4561c-103">Deploy my service</span></span>

<span data-ttu-id="4561c-104">В этой статье приводятся общие сведения о требованиях для правильного развертывания облачных служб голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="4561c-104">This article gives an overview of the requirements for properly deploying cloud voice services.</span></span> <span data-ttu-id="4561c-105">Следуя рекомендациям по развертыванию облачных служб, вы можете убедиться в том, что вы успешно выполнили учет всех требований и сделали повторяемые результаты.</span><span class="sxs-lookup"><span data-stu-id="4561c-105">By following prescriptive guidance for deploying cloud voice services, you can make sure you successfully account for all requirements and deliver repeatable results.</span></span>

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="4561c-106">Плайбук включения сайта для голосовой нагрузки Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4561c-106">Site enablement playbook for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="4561c-107">Используйте этот плайбук, чтобы помочь вашей организации успешно спланировать и выполнить развертывание функций голосовой связи Microsoft Teams на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="4561c-107">Use this playbook to help your organization successfully plan and execute the rollout of Microsoft Teams voice features on a site-by-site basis.</span></span>

<span data-ttu-id="4561c-108">В этом плайбук описаны все необходимые действия, Рекомендуемые временные шкалы и ссылки на соответствующие инструкции для каждого действия, а также инструкции по обеспечению соответствия требованиям для обеспечения успешности развертывания голосовых команд для определенного сайта в соответствии с важными факторами. для пользователя.</span><span class="sxs-lookup"><span data-stu-id="4561c-108">Including all required activities, recommended timelines, and links to corresponding guidance for each activity, this playbook covers end-to-end guidance to help ensure a successful Teams voice deployment for a given site, focusing on factors that are important to the user.</span></span>

<span data-ttu-id="4561c-109">Выполнив действия, описанные в этом плайбук, ваша организация может:</span><span class="sxs-lookup"><span data-stu-id="4561c-109">By completing the activities in this playbook, your organization can:</span></span>

-   <span data-ttu-id="4561c-110">Эффективная планирование и планирование выпуска групп.</span><span class="sxs-lookup"><span data-stu-id="4561c-110">Effectively plan and schedule your Teams rollout.</span></span>

-   <span data-ttu-id="4561c-111">Ускорьте и оптимизируйте внедрение пользователей.</span><span class="sxs-lookup"><span data-stu-id="4561c-111">Accelerate and optimize user adoption.</span></span>

-   <span data-ttu-id="4561c-112">Снижение потребностей в поддержке и повышение степени удовлетворенности пользователей.</span><span class="sxs-lookup"><span data-stu-id="4561c-112">Reduce support needs and increase user satisfaction.</span></span>

> [!NOTE]
> <span data-ttu-id="4561c-113">Эта статья и связанные плайбук не предназначены для описания шагов технического конфигурирования, необходимых для включения обслуживания, а также для обеспечения гудка в линии для определенного сайта.</span><span class="sxs-lookup"><span data-stu-id="4561c-113">This article and the associated playbook aren’t intended to describe every technical configuration step required for service enablement or providing dial tone to a specific site.</span></span> <span data-ttu-id="4561c-114">Вместо этого они сосредоточены на действиях и задачах, рекомендованных для интегрированных пользователей, и они могут использовать голосовые нагрузки групп с помощью быстрого и плавных переходов с высоким тарифом на использование и свести к минимуму требования поддержки.</span><span class="sxs-lookup"><span data-stu-id="4561c-114">Instead, they focus on activities and tasks recommended to onboard users easily and have them start consuming Teams voice workloads through a fast and smooth transition with a high adoption rate, while minimizing support requirements.</span></span> <span data-ttu-id="4561c-115">Технические рекомендации по настройке среды для голосовой связи в Teams можно найти в статье контрольные списки для [настройки голосовых нагрузок](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)в Teams, [настройки прямой маршрутизации в Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [основных возможностей Teams](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [сети для Teams](onboarding-checklist-configure-networking.md)и [включения Office 365](onboarding-checklist-enable-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="4561c-115">For technical guidance on how to best configure your environment for Teams voice, see the onboarding checklists for [configuring Teams voice workloads](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), [configuring Direct Routing in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [Teams core capabilities](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [networking for Teams](onboarding-checklist-configure-networking.md), and [enabling Office 365](onboarding-checklist-enable-office-365.md).</span></span>

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a><span data-ttu-id="4561c-116">Плайбук области фокуса</span><span class="sxs-lookup"><span data-stu-id="4561c-116">Playbook focus areas</span></span>

<span data-ttu-id="4561c-117">Основное внимание в плайбук заключается в том, чтобы решить, какие факторы влияют на восприятие голоса при развертывании Teams.</span><span class="sxs-lookup"><span data-stu-id="4561c-117">The focus of the playbook is to address the factors that influence the user’s perception of a Teams voice deployment.</span></span> <span data-ttu-id="4561c-118">Действия и задачи группируются в следующие области фокуса:</span><span class="sxs-lookup"><span data-stu-id="4561c-118">Activities and tasks are grouped into the following focus areas:</span></span>

-   <span data-ttu-id="4561c-119">Проверка готовности службы</span><span class="sxs-lookup"><span data-stu-id="4561c-119">Validation of service readiness</span></span>
    - <span data-ttu-id="4561c-120">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="4561c-120">Audio Conferencing</span></span>
    - <span data-ttu-id="4561c-121">Планы звонков</span><span class="sxs-lookup"><span data-stu-id="4561c-121">Calling Plans</span></span>
    - <span data-ttu-id="4561c-122">Прямая маршрутизация</span><span class="sxs-lookup"><span data-stu-id="4561c-122">Direct Routing</span></span>

-   <span data-ttu-id="4561c-123">Включение пользователей</span><span class="sxs-lookup"><span data-stu-id="4561c-123">User enablement</span></span>

-   <span data-ttu-id="4561c-124">Конечные точки</span><span class="sxs-lookup"><span data-stu-id="4561c-124">Endpoints</span></span>

-   <span data-ttu-id="4561c-125">Использование и качество</span><span class="sxs-lookup"><span data-stu-id="4561c-125">Usage and quality</span></span>

-   <span data-ttu-id="4561c-126">Освоение</span><span class="sxs-lookup"><span data-stu-id="4561c-126">Adoption</span></span>

<span data-ttu-id="4561c-127">[Плайбук включения сайта для голосовой связи (плайбук)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) — это книга Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="4561c-127">The [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) is a Microsoft Excel workbook.</span></span> <span data-ttu-id="4561c-128">Каждая из этих пяти областей фокуса является отдельным листом в книге, а каждая задача развертывания и действия группируются на один из этих листов.</span><span class="sxs-lookup"><span data-stu-id="4561c-128">Each of these five focus areas is a separate sheet in the workbook, and each deployment task and activity is grouped onto one of these sheets.</span></span>

<span data-ttu-id="4561c-129">![Снимок экрана: плайбук включения сайта](media/deploy-my-service-image1.png "Снимок экрана: плайбук")</span><span class="sxs-lookup"><span data-stu-id="4561c-129">![Screenshot of the site enablement playbook](media/deploy-my-service-image1.png "Screenshot of the playbook")</span></span>

> [!NOTE]
> <span data-ttu-id="4561c-130">Вы создадите отдельный экземпляр плайбук для каждого сайта в области для выпуска Teams.</span><span class="sxs-lookup"><span data-stu-id="4561c-130">You’ll create a separate instance of the playbook for each site in scope for your Teams rollout.</span></span>

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a><span data-ttu-id="4561c-131">Использование плайбук</span><span class="sxs-lookup"><span data-stu-id="4561c-131">How to use the playbook</span></span>

<span data-ttu-id="4561c-132">Независимо от размера и сложности местоположения, для каждого сайта требуется планировать задачи и действия в достаточном объеме, а также выполнять их в оптимальном порядке — до, во время и после фактического выпуска службы.</span><span class="sxs-lookup"><span data-stu-id="4561c-132">Regardless of the size and complexity of the location, enabling each site requires that you plan your tasks and activities early enough—and execute them in optimal order—before, during, and after the actual service rollout.</span></span> <span data-ttu-id="4561c-133">Мы рекомендуем выполнить эти действия, как вы планируете и выполняете свое путешествие в Microsoft Team Voice.</span><span class="sxs-lookup"><span data-stu-id="4561c-133">We recommend that you follow these steps as you plan and execute your own journey to Microsoft Teams voice.</span></span>

1. <span data-ttu-id="4561c-134">Скачайте [Плайбук включения сайта для голосовой связи (плайбук)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) для голосовой связи Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4561c-134">Download the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) for Microsoft Teams Voice.</span></span>

2. <span data-ttu-id="4561c-135">Создайте отдельную копию плайбук для каждого сайта.</span><span class="sxs-lookup"><span data-stu-id="4561c-135">Create a separate copy of the playbook for each site.</span></span>

3. <span data-ttu-id="4561c-136">На вкладке листа с именем **плайбук для {sitename-Code}**, замените **{SiteName-Code}** соответствующими именем сайта и кодом сайта.</span><span class="sxs-lookup"><span data-stu-id="4561c-136">On the tab for the sheet named **Playbook for {SiteName-Code}**, replace **{SiteName-Code}** with the relevant site name and/or site code.</span></span>

4. <span data-ttu-id="4561c-137">Введите **имя сайта, код сайта**и **дату планового запуска**, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="4561c-137">Enter the **Site name, Site code**, and **Planned launch date**, as illustrated below.</span></span> <span data-ttu-id="4561c-138">Это важный шаг, так как он корректирует рекомендованные крайние сроки для каждого действия в плайбук.</span><span class="sxs-lookup"><span data-stu-id="4561c-138">This is a critical step, because it adjusts the recommended deadlines for every activity in the playbook.</span></span>

   <span data-ttu-id="4561c-139">![Пример с именем сайта, кодом сайта и запланированной датой запуска](media/deploy-my-service-image2.png "Пример с именем сайта в Нью-Йорке, кодом сайта NY01 и запланированной датой запуска 20-Мар-18")</span><span class="sxs-lookup"><span data-stu-id="4561c-139">![Example with site name, site code, and planned launch date](media/deploy-my-service-image2.png "Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18")</span></span>

5. <span data-ttu-id="4561c-140">Просмотрите все действия, выполните необходимые действия и обновите состояние по мере пошаговой проверки на временной шкале.</span><span class="sxs-lookup"><span data-stu-id="4561c-140">Review each activity, take necessary actions, and update the status as you walk through the timeline.</span></span> <span data-ttu-id="4561c-141">Графическое представление состояния, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="4561c-141">Status is represented graphically, as described below:</span></span>
  
   - <span data-ttu-id="4561c-142">![Зеленая](media/deploy-my-service-image3.png) галочка **Да или нет (зеленый):** действие завершено или неприменимо для этого сайта, и никаких дополнительных действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="4561c-142">![Illustration of a green check mark](media/deploy-my-service-image3.png) **Yes, or not applicable (green):** The activity has been completed, or it’s not applicable for this site, and no further action is needed.</span></span></li>
   - <span data-ttu-id="4561c-143">![Изображение желтого восклицательного знака](media/deploy-my-service-image4.png) <strong>действие еще не завершено (желтое):</strong> действие еще не завершено, и его необходимо изменить на "Да" или "нет" в расписании.</span><span class="sxs-lookup"><span data-stu-id="4561c-143">![Illustration of a yellow exclamation point](media/deploy-my-service-image4.png) <strong>The activity isn’t completed yet (yellow):</strong> The activity hasn’t been completed yet, and must be updated to Yes or No on its schedule.</span></span></li>
   - <span data-ttu-id="4561c-144">![Красный крестик, обозначающий нет](media/deploy-my-service-image5.png) <strong>(красный):</strong> действие не может быть выполнено из-за проблемы и должно быть перенесено на собрание по состоянию проекта.</span><span class="sxs-lookup"><span data-stu-id="4561c-144">![Illustration of a red X indicating no](media/deploy-my-service-image5.png) <strong>No (red):</strong> The activity can’t be completed because of an issue and must be carried to the project status meeting.</span></span></li></ul>

6. <span data-ttu-id="4561c-145">Состояние сведено в каждом разделе, а заголовок раздела форматируется с помощью одного из этих индикаторов состояния.</span><span class="sxs-lookup"><span data-stu-id="4561c-145">The status is rolled up within each section, and the section heading is formatted with one of these status indicators.</span></span> <span data-ttu-id="4561c-146">**Еженедельное состояние** также обновляется автоматически.</span><span class="sxs-lookup"><span data-stu-id="4561c-146">**Weekly status** is also updated automatically.</span></span>

<span data-ttu-id="4561c-147">![Снимок экрана: еженедельное развертывание состояния в плайбук](media/deploy-my-service-image6.png "Снимок экрана: еженедельное развертывание состояния в плайбук")</span><span class="sxs-lookup"><span data-stu-id="4561c-147">![Screenshot of the weekly status roll-ups in the playbook](media/deploy-my-service-image6.png "Screenshot of the weekly status roll-ups in the playbook")</span></span>

> [!TIP]
> <span data-ttu-id="4561c-148">Повторите описанные выше действия для всех нужных местоположений.</span><span class="sxs-lookup"><span data-stu-id="4561c-148">Repeat the steps above for all the locations you have.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4561c-149">Некоторые действия могут быть неприменимы ко всем расположениям и сайтам.</span><span class="sxs-lookup"><span data-stu-id="4561c-149">Some steps might not be applicable to all locations and sites.</span></span> <span data-ttu-id="4561c-150">Если определенные действия не относятся к сайту, необходимо выбрать вариант **не применимо** для этого действия.</span><span class="sxs-lookup"><span data-stu-id="4561c-150">If a specific activity isn’t relevant to a site, you must select **Not applicable** for this activity.</span></span> <span data-ttu-id="4561c-151">Не **удаляйте** строки в плайбук; в противном случае формулы выгрузки состояния не будут работать.</span><span class="sxs-lookup"><span data-stu-id="4561c-151">**DO NOT DELETE** any rows in the playbook; if you do, the status roll-up formulas won’t work.</span></span><br/><br/>
<span data-ttu-id="4561c-152">Обратите внимание на действия, которые могут занять больше времени, чем запланировано, например на перенос номеров и действия по закупкам.</span><span class="sxs-lookup"><span data-stu-id="4561c-152">Pay attention to activities that might take more time than you planned for, such as number porting and procurement activities.</span></span> <span data-ttu-id="4561c-153">Эти действия могут негативно повлиять на временную шкалу развертывания сайта.</span><span class="sxs-lookup"><span data-stu-id="4561c-153">These activities can negatively affect the site deployment timeline.</span></span> <span data-ttu-id="4561c-154">Убедитесь, что вы просматриваете и обновляете список мероприятий и связанную временную шкалу еженедельно и появятся их на [собрании комитетов](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) , чтобы убедиться в том, что заинтересованные лица знают о состоянии каждого сайта и возможных отклонениях от расписания развертывания.</span><span class="sxs-lookup"><span data-stu-id="4561c-154">Be sure to review and update the activity list and the associated timeline weekly, and present them at [steering committee meetings](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) to ensure that stakeholders are aware of the status of each site and any possible deviations from the deployment schedule.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="4561c-155">Точки принятия решений</span><span class="sxs-lookup"><span data-stu-id="4561c-155">Decision points</span></span></td><td><ul><li><span data-ttu-id="4561c-156">Решите, требуется ли для развертывания Плайбук включения сайта.</span><span class="sxs-lookup"><span data-stu-id="4561c-156">Decide if the Site Enablement Playbook is required for your deployment.</span></span></li><li><span data-ttu-id="4561c-157">Определите, кто будет отвечать за настройку включения сайта в Плайбук для Microsoft Teams для каждого сайта, который вы хотите развернуть.</span><span class="sxs-lookup"><span data-stu-id="4561c-157">Decide who will be responsible for customizing the Site Enablement Playbook for Microsoft Teams for every site you’ll deploy.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="4561c-158">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="4561c-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="4561c-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Скачайте Плайбук включения сайта</a>.</span><span class="sxs-lookup"><span data-stu-id="4561c-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Download the Site Enablement Playbook</a>.</span></span></li><li><span data-ttu-id="4561c-160">Настройка Плайбук включения сайта для первого сайта.</span><span class="sxs-lookup"><span data-stu-id="4561c-160">Customize the Site Enablement Playbook for your first site.</span></span></li><li><span data-ttu-id="4561c-161">При необходимости повторите эти действия для дополнительных сайтов.</span><span class="sxs-lookup"><span data-stu-id="4561c-161">Repeat as needed for additional sites.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->