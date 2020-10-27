---
title: Шаблоны для организаций здравоохранения
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Используйте шаблоны Microsoft Teams с Microsoft Graph, чтобы быстро и легко создавать группы, предоставляя готовый шаблон параметров, каналов и приложений.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 63376c68d8267aaa49b4bdf4033d5ebfaa0a446f
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766702"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a><span data-ttu-id="f4d45-103">Начало работы с шаблонами групп для организаций здравоохранения</span><span class="sxs-lookup"><span data-stu-id="f4d45-103">Get started with Teams templates for healthcare organizations</span></span>

<span data-ttu-id="f4d45-104">Шаблоны Microsoft Teams позволяют быстро и легко создавать группы, предоставляя готовый шаблон параметров, каналов и предустановленных приложений.</span><span class="sxs-lookup"><span data-stu-id="f4d45-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="f4d45-105">Для организаций здравоохранения шаблоны могут быть особенно мощными, так как они предоставляют структуру для пользователей, направленную на эффективное использование Teams.</span><span class="sxs-lookup"><span data-stu-id="f4d45-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="f4d45-106">Шаблоны также позволяют администраторам развертывать единообразные команды для разных организаций.</span><span class="sxs-lookup"><span data-stu-id="f4d45-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="f4d45-107">Эта статья предназначена для вас, если вы несете ответственность за планирование, развертывание и управление несколькими группами в организации здравоохранения.</span><span class="sxs-lookup"><span data-stu-id="f4d45-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="f4d45-108">В настоящее время предлагаются два основного шаблона здравоохранения, которые можно использовать в различных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="f4d45-108">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="f4d45-109">Дополнительные сведения о шаблонах групп можно найти в разделе [Начало работы с шаблонами групп](../../get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="f4d45-109">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span>

## <a name="ward-template"></a><span data-ttu-id="f4d45-110">Шаблон "на"</span><span class="sxs-lookup"><span data-stu-id="f4d45-110">Ward template</span></span>

<span data-ttu-id="f4d45-111">Шаблон "один" предназначен для общения и совместной работы в любом приложении, Pod или отделе.</span><span class="sxs-lookup"><span data-stu-id="f4d45-111">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="f4d45-112">Шаблон можно использовать для упрощения управления пациентами, а также для выполнения производственных задач.</span><span class="sxs-lookup"><span data-stu-id="f4d45-112">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="f4d45-113">Например, в каналах *извещений* и сменах могут быть опубликованы дополнительные *объявления.*</span><span class="sxs-lookup"><span data-stu-id="f4d45-113">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing* .</span></span> <span data-ttu-id="f4d45-114">Если вы хотите упростить выполнение операций, выберите этот шаблон.</span><span class="sxs-lookup"><span data-stu-id="f4d45-114">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="f4d45-115">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="f4d45-115">Base Template Type</span></span> |<span data-ttu-id="f4d45-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="f4d45-116">baseTemplateId</span></span> |<span data-ttu-id="f4d45-117">Каналы базового шаблона</span><span class="sxs-lookup"><span data-stu-id="f4d45-117">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="f4d45-118">Здравоохранение – до</span><span class="sxs-lookup"><span data-stu-id="f4d45-118">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="f4d45-119">Обслуживании\*</span><span class="sxs-lookup"><span data-stu-id="f4d45-119">Announcements\*</span></span> <br> <span data-ttu-id="f4d45-120">Huddles\*</span><span class="sxs-lookup"><span data-stu-id="f4d45-120">Huddles\*</span></span> <br> <span data-ttu-id="f4d45-121">До\*</span><span class="sxs-lookup"><span data-stu-id="f4d45-121">Rounds\*</span></span> <br> <span data-ttu-id="f4d45-122">Штата\*</span><span class="sxs-lookup"><span data-stu-id="f4d45-122">Staffing\*</span></span> <br> <span data-ttu-id="f4d45-123">Обучение\*</span><span class="sxs-lookup"><span data-stu-id="f4d45-123">Training\*</span></span> |
|     | |         |

<span data-ttu-id="f4d45-124">\* Автоматическое добавление в избранное</span><span class="sxs-lookup"><span data-stu-id="f4d45-124">\* Auto-favorited</span></span>

## <a name="hospital-template"></a><span data-ttu-id="f4d45-125">Шаблон больницы</span><span class="sxs-lookup"><span data-stu-id="f4d45-125">Hospital template</span></span>

<span data-ttu-id="f4d45-126">Шаблон больницы предназначен для общения и совместной работы между несколькими приложениями, многими из них и подразделениями в рамках больницы.</span><span class="sxs-lookup"><span data-stu-id="f4d45-126">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="f4d45-127">В этот шаблон включены несколько рабочих каналов, включая *извещения* , *custodial* и *Pharmacy* , но мы также предоставляем ниже сценарий, который расширяет шаблон с учетом разнообразных дополнительных подразделений и специальных каналов, которые можно добавлять, удалять и изменять.</span><span class="sxs-lookup"><span data-stu-id="f4d45-127">Included in this template are several operational channels including *Announcements* , *Custodial* , and *Pharmacy* , but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="f4d45-128">Например, если у вас есть отдел *Endocrinology* , но не нужен канал для *ophthalmology* , сценарий можно адаптировать для включения канала *Endocrinology* и удаления канала *ophthalmology* .</span><span class="sxs-lookup"><span data-stu-id="f4d45-128">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology* , then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="f4d45-129">Рекомендуется, чтобы эти специальные или Многомодельные каналы не были автоматически избраны для предотвращения насыщенности уведомлений.</span><span class="sxs-lookup"><span data-stu-id="f4d45-129">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="f4d45-130">Пользователи обычно используют любые каналы, которые им нужны.</span><span class="sxs-lookup"><span data-stu-id="f4d45-130">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="f4d45-131">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="f4d45-131">Base Template Type</span></span> |<span data-ttu-id="f4d45-132">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="f4d45-132">baseTemplateId</span></span> |<span data-ttu-id="f4d45-133">Каналы базового шаблона</span><span class="sxs-lookup"><span data-stu-id="f4d45-133">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="f4d45-134">Здравоохранение – больницы</span><span class="sxs-lookup"><span data-stu-id="f4d45-134">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="f4d45-135">Обслуживании\*</span><span class="sxs-lookup"><span data-stu-id="f4d45-135">Announcements\*</span></span> <br> <span data-ttu-id="f4d45-136">Соответствие требованиям\*</span><span class="sxs-lookup"><span data-stu-id="f4d45-136">Compliance\*</span></span> <br> <span data-ttu-id="f4d45-137">Custodial</span><span class="sxs-lookup"><span data-stu-id="f4d45-137">Custodial</span></span> <br> <span data-ttu-id="f4d45-138">Человеческие ресурсы</span><span class="sxs-lookup"><span data-stu-id="f4d45-138">Human Resources</span></span> <br> <span data-ttu-id="f4d45-139">Pharmacy</span><span class="sxs-lookup"><span data-stu-id="f4d45-139">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="f4d45-140">\* Автоматическое добавление в избранное</span><span class="sxs-lookup"><span data-stu-id="f4d45-140">\* Auto-favorited</span></span> 

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="f4d45-141">Использование шаблонов первого производителя</span><span class="sxs-lookup"><span data-stu-id="f4d45-141">How to use first-party templates</span></span>

<span data-ttu-id="f4d45-142">Чтобы использовать эти шаблоны, просто измените свойство "template@odata. Bind" в теле запроса с "Standard" на TemplateIDs выше.</span><span class="sxs-lookup"><span data-stu-id="f4d45-142">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="f4d45-143">Дополнительные сведения о развертывании шаблонов групп можно найти в статье Microsoft Graph о том, как [создавать группы](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="f4d45-143">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="f4d45-144">Каналы в шаблоне будут автоматически созданы на вкладке "Общие".</span><span class="sxs-lookup"><span data-stu-id="f4d45-144">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="f4d45-145">Пример: сценарий расширения шаблонов для больницы</span><span class="sxs-lookup"><span data-stu-id="f4d45-145">Example: Hospital template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="f4d45-146">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f4d45-146">Related topics</span></span>

[<span data-ttu-id="f4d45-147">Начало работы с шаблонами Teams</span><span class="sxs-lookup"><span data-stu-id="f4d45-147">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="f4d45-148">Начало работы с Teams для организаций в сфере здравоохранения</span><span class="sxs-lookup"><span data-stu-id="f4d45-148">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)

[<span data-ttu-id="f4d45-149">Начало работы с шаблонами групп на консоли администрирования</span><span class="sxs-lookup"><span data-stu-id="f4d45-149">Get started with Teams templates in the admin console</span></span>](../../get-started-with-teams-templates-in-the-admin-console.md)
