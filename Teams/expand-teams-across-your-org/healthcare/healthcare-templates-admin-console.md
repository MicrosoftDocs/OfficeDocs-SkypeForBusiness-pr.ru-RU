---
title: Создание команды с помощью шаблонов Teams для здравоохранения
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Используйте шаблоны Microsoft Teams в Центре администрирования или в Microsoft Graph, чтобы быстро и удобно создавать команды на основе готовых шаблонов с параметрами, каналами и приложениями.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 13b85818101e1c3d42ae6dc715274ac23453e178
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117877"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a><span data-ttu-id="41716-103">Создание команды с помощью шаблонов Teams для здравоохранения</span><span class="sxs-lookup"><span data-stu-id="41716-103">Create a team using Teams healthcare templates</span></span>

<span data-ttu-id="41716-104">С помощью шаблонов Microsoft Teams можно быстро и удобно создавать команды: готовые шаблоны содержат параметры, каналы и предустановленные приложения.</span><span class="sxs-lookup"><span data-stu-id="41716-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="41716-105">Шаблоны могут быть особенно эффективными для организаций здравоохранения, поскольку они помогают пользователям научиться эффективнее использовать Teams.</span><span class="sxs-lookup"><span data-stu-id="41716-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="41716-106">Благодаря шаблонам администраторы могут развертывать одинаково устроенные команды в своих организациях.</span><span class="sxs-lookup"><span data-stu-id="41716-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="41716-107">Эта статья предназначена для вас, если вы отвечаете за планирование, развертывание и управление несколькими командами в своей организации здравоохранения.</span><span class="sxs-lookup"><span data-stu-id="41716-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="41716-108">Выберите метод создания команд с помощью шаблонов Teams для здравоохранения:</span><span class="sxs-lookup"><span data-stu-id="41716-108">Choose a method for creating teams with the Teams healthcare templates:</span></span>

| <span data-ttu-id="41716-109">Кто</span><span class="sxs-lookup"><span data-stu-id="41716-109">Who</span></span> | <span data-ttu-id="41716-110">Используемый метод:</span><span class="sxs-lookup"><span data-stu-id="41716-110">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="41716-111">Администраторы и ИТ-специалисты</span><span class="sxs-lookup"><span data-stu-id="41716-111">Admins and IT Professionals</span></span> | <span data-ttu-id="41716-112">[Используйте Центр администрирования Teams](#use-the-teams-templates-in-the-teams-admin-center) для создания команд на основе шаблонов Teams для здравоохранения.</span><span class="sxs-lookup"><span data-stu-id="41716-112">[Use the Teams admin center](#use-the-teams-templates-in-the-teams-admin-center) to create teams based on the healthcare Teams templates.</span></span>|
| <span data-ttu-id="41716-113">Разработчики и системные интеграторы</span><span class="sxs-lookup"><span data-stu-id="41716-113">Developers and systems integrators</span></span> | <span data-ttu-id="41716-114">[Используйте Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) для создания команд на основе шаблонов Teams для здравоохранения.</span><span class="sxs-lookup"><span data-stu-id="41716-114">[Use the Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) to create teams based on the healthcare Teams templates.</span></span> |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a><span data-ttu-id="41716-115">Использование шаблонов Teams в Центре администрирования Teams</span><span class="sxs-lookup"><span data-stu-id="41716-115">Use the Teams templates in the Teams admin center</span></span>

<span data-ttu-id="41716-116">Администраторы Microsoft Teams могут использовать Центр администрирования Teams для создания команд с помощью шаблонов Teams.</span><span class="sxs-lookup"><span data-stu-id="41716-116">Microsoft Teams admins can use the Teams admin center to create teams with the Teams templates.</span></span> <span data-ttu-id="41716-117">В настоящее время мы предлагаем два разработанных нами шаблона для здравоохранения, которые можно использовать в различных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="41716-117">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="41716-118">Дополнительные сведения о шаблонах команд см. в статье [Начало работы с шаблонами Teams в Центре администрирования](../../get-started-with-teams-templates-in-the-admin-console.md).</span><span class="sxs-lookup"><span data-stu-id="41716-118">To learn more about team templates in general, see [Get started with Teams templates in the admin center](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

### <a name="collaborate-on-patient-care"></a><span data-ttu-id="41716-119">Совместная работа по уходу за пациентами</span><span class="sxs-lookup"><span data-stu-id="41716-119">Collaborate on patient care</span></span>

 <span data-ttu-id="41716-120">Упорядочение обмена медицинской информацией и сотрудничества в отделениях, отделах и палатах больниц.</span><span class="sxs-lookup"><span data-stu-id="41716-120">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="41716-121">Этот шаблон можно использовать для управления пациентами и для выполнения повседневных задач в отделениях больниц.</span><span class="sxs-lookup"><span data-stu-id="41716-121">The template can be used to facilitate patient management and operational needs of a ward.</span></span>

| <span data-ttu-id="41716-122">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="41716-122">Base template type</span></span> |<span data-ttu-id="41716-123">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="41716-123">baseTemplateId</span></span>| <span data-ttu-id="41716-124">Свойства базового шаблона</span><span class="sxs-lookup"><span data-stu-id="41716-124">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="41716-125">Совместная работа по уходу за пациентами</span><span class="sxs-lookup"><span data-stu-id="41716-125">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="41716-126">Каналы:</span><span class="sxs-lookup"><span data-stu-id="41716-126">Channels:</span></span><ul><li><span data-ttu-id="41716-127">Общие</span><span class="sxs-lookup"><span data-stu-id="41716-127">General</span></span></li><li><span data-ttu-id="41716-128">Объявления</span><span class="sxs-lookup"><span data-stu-id="41716-128">Announcements</span></span></li><li><span data-ttu-id="41716-129">Совещания</span><span class="sxs-lookup"><span data-stu-id="41716-129">Huddles</span></span></li><li><span data-ttu-id="41716-130">Обходы</span><span class="sxs-lookup"><span data-stu-id="41716-130">Rounds</span></span></li><li><span data-ttu-id="41716-131">Персонал</span><span class="sxs-lookup"><span data-stu-id="41716-131">Staffing</span></span></li><li><span data-ttu-id="41716-132">Обучение</span><span class="sxs-lookup"><span data-stu-id="41716-132">Training</span></span></li></ul> <span data-ttu-id="41716-133">Приложения:</span><span class="sxs-lookup"><span data-stu-id="41716-133">Apps:</span></span> <ul><li><span data-ttu-id="41716-134">Вики</span><span class="sxs-lookup"><span data-stu-id="41716-134">Wiki</span></span></li><li><span data-ttu-id="41716-135">Списки</span><span class="sxs-lookup"><span data-stu-id="41716-135">Lists</span></span></li></ul>|
||||

### <a name="hospital"></a><span data-ttu-id="41716-136">Больница</span><span class="sxs-lookup"><span data-stu-id="41716-136">Hospital</span></span>

<span data-ttu-id="41716-137">Упорядочение обмена информацией и сотрудничества между несколькими отделениями, отделами и палатами в пределах одной больницы.</span><span class="sxs-lookup"><span data-stu-id="41716-137">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="41716-138">Этот шаблон включает набор базовых каналов для работы больниц. Шаблон можно произвольно расширять для добавления специализаций.</span><span class="sxs-lookup"><span data-stu-id="41716-138">This template includes a set of base channels for hospital operations, and can be self-extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="41716-139">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="41716-139">Base template type</span></span> |<span data-ttu-id="41716-140">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="41716-140">baseTemplateId</span></span> | <span data-ttu-id="41716-141">Свойства базового шаблона</span><span class="sxs-lookup"><span data-stu-id="41716-141">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="41716-142">Больница</span><span class="sxs-lookup"><span data-stu-id="41716-142">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="41716-143">Каналы:</span><span class="sxs-lookup"><span data-stu-id="41716-143">Channels:</span></span> <ul><li><span data-ttu-id="41716-144">Общие</span><span class="sxs-lookup"><span data-stu-id="41716-144">General</span></span></li><li><span data-ttu-id="41716-145">Объявления</span><span class="sxs-lookup"><span data-stu-id="41716-145">Announcements</span></span></li><li><span data-ttu-id="41716-146">Соответствие требованиям</span><span class="sxs-lookup"><span data-stu-id="41716-146">Compliance</span></span></li><li><span data-ttu-id="41716-147">Госпитализация</span><span class="sxs-lookup"><span data-stu-id="41716-147">Custodial</span></span></li><li><span data-ttu-id="41716-148">Кадры</span><span class="sxs-lookup"><span data-stu-id="41716-148">Human resources</span></span></li><li><span data-ttu-id="41716-149">Аптека</span><span class="sxs-lookup"><span data-stu-id="41716-149">Pharmacy</span></span></li></ul> <span data-ttu-id="41716-150">Приложения:</span><span class="sxs-lookup"><span data-stu-id="41716-150">Apps:</span></span> <ul><li><span data-ttu-id="41716-151">Вики</span><span class="sxs-lookup"><span data-stu-id="41716-151">Wiki</span></span></li><li><span data-ttu-id="41716-152">Списки</span><span class="sxs-lookup"><span data-stu-id="41716-152">Lists</span></span> </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a><span data-ttu-id="41716-153">Использование шаблонов Teams с Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="41716-153">Use the Teams templates with the Microsoft Graph</span></span>

<span data-ttu-id="41716-154">Разработчики могут использовать Microsoft Graph для создания команд с помощью шаблонов Teams.</span><span class="sxs-lookup"><span data-stu-id="41716-154">Developers can use the Microsoft Graph to create teams with the Teams templates.</span></span> <span data-ttu-id="41716-155">В настоящее время мы предлагаем два разработанных нами шаблона для здравоохранения, которые можно использовать в различных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="41716-155">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="41716-156">Дополнительные сведения о шаблонах команд см. в статье [Начало работы с шаблонами Teams](../../get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="41716-156">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span> <span data-ttu-id="41716-157">Сведения о шаблонах Teams и Microsoft Graph, см. в статьях [Обзор API Microsoft Teams API](/graph/teams-concept-overview?view=graph-rest-1.0) и [Тип ресурса teamsTemplate](/graph/api/resources/teamstemplate?view=graph-rest-1.0).</span><span class="sxs-lookup"><span data-stu-id="41716-157">And for information about Teams templates and the Microsoft Graph, see [Microsoft Teams API overview](/graph/teams-concept-overview?view=graph-rest-1.0) and [teamsTemplate resource type](/graph/api/resources/teamstemplate?view=graph-rest-1.0).</span></span>

### <a name="ward-template"></a><span data-ttu-id="41716-158">Шаблон для отделений больницы</span><span class="sxs-lookup"><span data-stu-id="41716-158">Ward template</span></span>

<span data-ttu-id="41716-159">Шаблон для отделений предназначен для обмена информацией и сотрудничества в отделениях, отделах и палатах больниц.</span><span class="sxs-lookup"><span data-stu-id="41716-159">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="41716-160">Этот шаблон можно использовать для управления пациентами и для выполнения повседневных задач в отделениях больниц.</span><span class="sxs-lookup"><span data-stu-id="41716-160">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="41716-161">Например, объявления в отделении больницы можно публиковать в канале *Объявления*, а для управления рабочими сменами можно использовать канал *Персонал*.</span><span class="sxs-lookup"><span data-stu-id="41716-161">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="41716-162">Этот шаблон пригодится вам, если нужно упорядочить работу отделения больницы.</span><span class="sxs-lookup"><span data-stu-id="41716-162">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="41716-163">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="41716-163">Base Template Type</span></span> |<span data-ttu-id="41716-164">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="41716-164">baseTemplateId</span></span> |<span data-ttu-id="41716-165">Каналы базового шаблона</span><span class="sxs-lookup"><span data-stu-id="41716-165">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="41716-166">Здравоохранение — отделение</span><span class="sxs-lookup"><span data-stu-id="41716-166">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="41716-167">Объявления\*</span><span class="sxs-lookup"><span data-stu-id="41716-167">Announcements\*</span></span> <br> <span data-ttu-id="41716-168">Совещания\*</span><span class="sxs-lookup"><span data-stu-id="41716-168">Huddles\*</span></span> <br> <span data-ttu-id="41716-169">Обходы\*</span><span class="sxs-lookup"><span data-stu-id="41716-169">Rounds\*</span></span> <br> <span data-ttu-id="41716-170">Персонал\*</span><span class="sxs-lookup"><span data-stu-id="41716-170">Staffing\*</span></span> <br> <span data-ttu-id="41716-171">Обучение\*</span><span class="sxs-lookup"><span data-stu-id="41716-171">Training\*</span></span> |
|     | |         |

<span data-ttu-id="41716-172">Автоматическое избранное: \*</span><span class="sxs-lookup"><span data-stu-id="41716-172">\* Auto-favorited</span></span>

### <a name="hospital-template"></a><span data-ttu-id="41716-173">Шаблон для больниц</span><span class="sxs-lookup"><span data-stu-id="41716-173">Hospital template</span></span>

<span data-ttu-id="41716-174">Шаблон для больниц предназначен для обмена информацией и сотрудничества между несколькими отделениями, отделами и палатами в пределах одной больницы.</span><span class="sxs-lookup"><span data-stu-id="41716-174">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="41716-175">Этот шаблон включает несколько рабочих каналов, в том числе *Объявления*, *Госпитализация* и *Аптека*. Кроме того, мы предоставляем указанный ниже сценарий, дающий возможность расширить шаблон, добавив в него ряд дополнительных каналов для определенных отделений или специализаций. Вы сможете добавлять такие каналы, удалять и редактировать их по вашему усмотрению.</span><span class="sxs-lookup"><span data-stu-id="41716-175">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="41716-176">Например, если в больнице есть отделение *эндокринологии*, но не нужен канал для *офтальмологии*, можно настроить сценарий, включив в него канал *Эндокринология* и удалив канал *Офтальмология*.</span><span class="sxs-lookup"><span data-stu-id="41716-176">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="41716-177">Рекомендуем отключить автоматическое добавление в избранное таких каналов, созданных для определенных отделений и специализаций, чтобы избежать получения чрезмерного количества уведомлений.</span><span class="sxs-lookup"><span data-stu-id="41716-177">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="41716-178">Пользователи обычно заносят в избранное все каналы, которые они считают важными.</span><span class="sxs-lookup"><span data-stu-id="41716-178">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="41716-179">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="41716-179">Base Template Type</span></span> |<span data-ttu-id="41716-180">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="41716-180">baseTemplateId</span></span> |<span data-ttu-id="41716-181">Каналы базового шаблона</span><span class="sxs-lookup"><span data-stu-id="41716-181">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="41716-182">Здравоохранение — больница</span><span class="sxs-lookup"><span data-stu-id="41716-182">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="41716-183">Объявления\*</span><span class="sxs-lookup"><span data-stu-id="41716-183">Announcements\*</span></span> <br> <span data-ttu-id="41716-184">Соответствие требованиям\*</span><span class="sxs-lookup"><span data-stu-id="41716-184">Compliance\*</span></span> <br> <span data-ttu-id="41716-185">Госпитализация</span><span class="sxs-lookup"><span data-stu-id="41716-185">Custodial</span></span> <br> <span data-ttu-id="41716-186">Кадры</span><span class="sxs-lookup"><span data-stu-id="41716-186">Human Resources</span></span> <br> <span data-ttu-id="41716-187">Аптека</span><span class="sxs-lookup"><span data-stu-id="41716-187">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="41716-188">Автоматическое избранное: \*</span><span class="sxs-lookup"><span data-stu-id="41716-188">\* Auto-favorited</span></span> 

### <a name="how-to-use-first-party-templates"></a><span data-ttu-id="41716-189">Использование собственных шаблонов</span><span class="sxs-lookup"><span data-stu-id="41716-189">How to use first-party templates</span></span>

<span data-ttu-id="41716-190">Чтобы использовать эти шаблоны, измените значение свойства "template@odata.bind" в тексте запроса со "standard" на указанные выше идентификаторы TemplateID.</span><span class="sxs-lookup"><span data-stu-id="41716-190">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="41716-191">Дополнительные сведения о развертывании шаблонов Teams см. в статье Microsoft Graph о [создании команд](/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="41716-191">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="41716-192">Каналы в шаблоне будут автоматически создаваться на вкладке "Общие".</span><span class="sxs-lookup"><span data-stu-id="41716-192">The channels in the template will automatically be created under the General Tab.</span></span>

#### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="41716-193">Пример: сценарий для расширения шаблона для больниц</span><span class="sxs-lookup"><span data-stu-id="41716-193">Example: Hospital template extension script</span></span>

``` Powershell
{ 
          "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')",
          "DisplayName": "Contoso Hospital",
          "Description": "Team for all staff in Contoso Hospital",
          "Channels": [
            {
              "displayName": "Ambulatory",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Anesthesiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Cardiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "CCU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ear, Nose, and Throat",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Emergency Care",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Family Medicine",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Gynecology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "ICU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Mother-Baby",
              "IsFavoriteByDefault": false
            }, 
            {
              "displayName": "Neonatal",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Neurology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Oncology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ophthalmology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "PACU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Psychiatric",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Radiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Rehabilitation",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Surgical",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Urology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Women's Health",
              "IsFavoriteByDefault": false
            }
          ],
          "Apps": [
            {
              "Id": "1542629c-01b3-4a6d-8f76-1938b779e48d"
            }
          ]
          }

```

### <a name="related-topics"></a><span data-ttu-id="41716-194">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="41716-194">Related topics</span></span>

[<span data-ttu-id="41716-195">Начало работы с шаблонами Teams</span><span class="sxs-lookup"><span data-stu-id="41716-195">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="41716-196">Начало работы с Teams для организаций в сфере здравоохранения</span><span class="sxs-lookup"><span data-stu-id="41716-196">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)