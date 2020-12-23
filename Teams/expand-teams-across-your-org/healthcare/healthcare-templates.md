---
title: Шаблоны для медицинских организаций
author: serdarsoysal
ms.author: serdars
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
description: Используйте шаблоны Microsoft Teams с Microsoft Graph для быстрого и простого создания команд, предоставляя предопределенный шаблон настроек, каналов и приложений.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4c2e10efbff98150b120d1c026d4d810629333f2
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790411"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a><span data-ttu-id="b1161-103">Начало работы с шаблонами Teams для медицинских организаций</span><span class="sxs-lookup"><span data-stu-id="b1161-103">Get started with Teams templates for healthcare organizations</span></span>

<span data-ttu-id="b1161-104">Шаблоны Microsoft Teams позволяют быстро и легко создавать команды, предоставляя предопределяющий шаблон настроек, каналов и предварительно установленных приложений.</span><span class="sxs-lookup"><span data-stu-id="b1161-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="b1161-105">В медицинских организациях шаблоны могут быть особенно эффективны, так как они обеспечивают структуру для пользователей, чтобы ориентироваться в том, как эффективно использовать Teams.</span><span class="sxs-lookup"><span data-stu-id="b1161-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="b1161-106">Шаблоны также позволяют администраторам развертывать согласованные группы в организации.</span><span class="sxs-lookup"><span data-stu-id="b1161-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="b1161-107">Эта статья для вас, если вы отвечаете за планирование, развертывание и управление несколькими командами в организации здравоохранения.</span><span class="sxs-lookup"><span data-stu-id="b1161-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="b1161-108">В настоящее время мы предлагаем два шаблона для здравоохранения, которые можно использовать в различных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="b1161-108">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="b1161-109">Подробнее о шаблонах команд см. в шаблонах [Teams.](../../get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="b1161-109">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span>

## <a name="ward-template"></a><span data-ttu-id="b1161-110">Шаблон шаблона "Шаблон шаблона"</span><span class="sxs-lookup"><span data-stu-id="b1161-110">Ward template</span></span>

<span data-ttu-id="b1161-111">Шаблон шаблона предназначен для общения и совместной работы в рамках одного из отделов, pod или отделов.</span><span class="sxs-lookup"><span data-stu-id="b1161-111">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="b1161-112">Шаблон можно использовать для упрощения управления пациентом, а также для оперативных потребностей человека.</span><span class="sxs-lookup"><span data-stu-id="b1161-112">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="b1161-113">Например, в канале "Извещающие" можно размещать объявления, а сменами можно управлять в области  "Персонал". </span><span class="sxs-lookup"><span data-stu-id="b1161-113">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="b1161-114">Если вы хотите упростить свою операцию, этот шаблон вам по-настоящему упорядочен.</span><span class="sxs-lookup"><span data-stu-id="b1161-114">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="b1161-115">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="b1161-115">Base Template Type</span></span> |<span data-ttu-id="b1161-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="b1161-116">baseTemplateId</span></span> |<span data-ttu-id="b1161-117">Каналы шаблонов базовых показателей</span><span class="sxs-lookup"><span data-stu-id="b1161-117">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="b1161-118">Здравоохранение — Сша</span><span class="sxs-lookup"><span data-stu-id="b1161-118">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="b1161-119">Объявления\*</span><span class="sxs-lookup"><span data-stu-id="b1161-119">Announcements\*</span></span> <br> <span data-ttu-id="b1161-120">Huddles\*</span><span class="sxs-lookup"><span data-stu-id="b1161-120">Huddles\*</span></span> <br> <span data-ttu-id="b1161-121">Округ округит\*</span><span class="sxs-lookup"><span data-stu-id="b1161-121">Rounds\*</span></span> <br> <span data-ttu-id="b1161-122">Персонал\*</span><span class="sxs-lookup"><span data-stu-id="b1161-122">Staffing\*</span></span> <br> <span data-ttu-id="b1161-123">Обучение\*</span><span class="sxs-lookup"><span data-stu-id="b1161-123">Training\*</span></span> |
|     | |         |

<span data-ttu-id="b1161-124">\* Автоматическое избранное</span><span class="sxs-lookup"><span data-stu-id="b1161-124">\* Auto-favorited</span></span>

## <a name="hospital-template"></a><span data-ttu-id="b1161-125">Шаблон для больнице</span><span class="sxs-lookup"><span data-stu-id="b1161-125">Hospital template</span></span>

<span data-ttu-id="b1161-126">Шаблон для управления больницей предназначен для общения и совместной работы между несколькими ее отделами, pods и другими отделами.</span><span class="sxs-lookup"><span data-stu-id="b1161-126">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="b1161-127">В этот шаблон входит несколько рабочих каналов, включая "Объявления", "Хранитель" и "Хранитель", но также предлагается сценарий, который расширяет шаблон с разнообразными дополнительными каналами для работы со специализированными сайтами, которые можно добавлять, удалять или редактировать по своему вкусу. </span><span class="sxs-lookup"><span data-stu-id="b1161-127">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="b1161-128">Например, если у вас есть отдел *endocrinology,* но для *Ophthalmology* не нужен канал, сценарий можно адаптировать, чтобы включить канал *endocrinology* и удалить канал *Ophthalmology.*</span><span class="sxs-lookup"><span data-stu-id="b1161-128">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="b1161-129">Мы рекомендуем не использовать эти специализированные каналы в автоматическом избранном, чтобы избежать насыщенности уведомлений.</span><span class="sxs-lookup"><span data-stu-id="b1161-129">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="b1161-130">Как правило, пользователи избранные каналы, которые им важны.</span><span class="sxs-lookup"><span data-stu-id="b1161-130">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="b1161-131">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="b1161-131">Base Template Type</span></span> |<span data-ttu-id="b1161-132">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="b1161-132">baseTemplateId</span></span> |<span data-ttu-id="b1161-133">Каналы шаблонов базовых показателей</span><span class="sxs-lookup"><span data-stu-id="b1161-133">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="b1161-134">Здравоохранение — больнице</span><span class="sxs-lookup"><span data-stu-id="b1161-134">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="b1161-135">Объявления\*</span><span class="sxs-lookup"><span data-stu-id="b1161-135">Announcements\*</span></span> <br> <span data-ttu-id="b1161-136">Соответствие требованиям\*</span><span class="sxs-lookup"><span data-stu-id="b1161-136">Compliance\*</span></span> <br> <span data-ttu-id="b1161-137">Хранитель</span><span class="sxs-lookup"><span data-stu-id="b1161-137">Custodial</span></span> <br> <span data-ttu-id="b1161-138">Человеческие ресурсы</span><span class="sxs-lookup"><span data-stu-id="b1161-138">Human Resources</span></span> <br> <span data-ttu-id="b1161-139">Веха</span><span class="sxs-lookup"><span data-stu-id="b1161-139">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="b1161-140">\* Автоматическое избранное</span><span class="sxs-lookup"><span data-stu-id="b1161-140">\* Auto-favorited</span></span> 

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="b1161-141">Использование шаблонов сторонних шаблонов</span><span class="sxs-lookup"><span data-stu-id="b1161-141">How to use first-party templates</span></span>

<span data-ttu-id="b1161-142">Чтобы использовать эти шаблоны, просто измените свойство template@odata.bind в теле запроса со стандартного на шаблон TemplateIDs выше.</span><span class="sxs-lookup"><span data-stu-id="b1161-142">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="b1161-143">Дополнительные сведения о развертывании шаблонов Teams см. в статье Microsoft Graph о том, как [создать команду.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="b1161-143">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="b1161-144">Каналы в шаблоне будут автоматически созданы на вкладке "Общие".</span><span class="sxs-lookup"><span data-stu-id="b1161-144">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="b1161-145">Пример: сценарий расширения шаблона в больнице</span><span class="sxs-lookup"><span data-stu-id="b1161-145">Example: Hospital template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="b1161-146">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b1161-146">Related topics</span></span>

[<span data-ttu-id="b1161-147">Начало работы с шаблонами Teams</span><span class="sxs-lookup"><span data-stu-id="b1161-147">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="b1161-148">Начало работы с Teams для организаций в сфере здравоохранения</span><span class="sxs-lookup"><span data-stu-id="b1161-148">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)

[<span data-ttu-id="b1161-149">Начало работы с шаблонами Teams в консоли администрирования</span><span class="sxs-lookup"><span data-stu-id="b1161-149">Get started with Teams templates in the admin console</span></span>](../../get-started-with-teams-templates-in-the-admin-console.md)
