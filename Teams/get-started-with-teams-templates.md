---
title: Начало работы с группами шаблонов
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/10/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
localization_priority: Normal
robots: NOINDEX, NOFOLLOW
search.appverid: MET150
description: Узнайте, как использовать шаблоны группы для создания группы с предварительно определенные каналы.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ead0a3dc9e27b90c49808bcece0aab39bf01f13a
ms.sourcegitcommit: 4c5b9e8c4bdb1187d610209d365680702d4372fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "27801466"
---
# <a name="get-started-with-teams-templates"></a><span data-ttu-id="4c01d-103">Начало работы с группами шаблонов</span><span class="sxs-lookup"><span data-stu-id="4c01d-103">Get started with Teams templates</span></span> 

<span data-ttu-id="4c01d-104">Шаблоны группы — это готовые основе определения структуры группы, созданная на основе потребность или проекта.</span><span class="sxs-lookup"><span data-stu-id="4c01d-104">Teams templates are pre-built definitions of a team's structure designed around a business need or project.</span></span> <span data-ttu-id="4c01d-105">Шаблоны группы можно использовать для быстрого создания пробелы расширенными возможностями совместной работы с каналами для разных тем и Предустановка приложений для работы на критически важных контент и службы.</span><span class="sxs-lookup"><span data-stu-id="4c01d-105">You can use Teams templates to quickly create rich collaboration spaces with channels for different topics and preinstall apps to pull in mission-critical content and services.</span></span> <span data-ttu-id="4c01d-106">Шаблоны группы предоставить структуру предварительно определенные группы, которая поможет вам легко создавать согласованные группам в организации.</span><span class="sxs-lookup"><span data-stu-id="4c01d-106">Teams templates provide a predefined team structure that can help you easily create consistent teams across your organization.</span></span> 

<span data-ttu-id="4c01d-107">В этой статье мы расскажем свойства, которые могут быть определены в шаблонах, какие базового шаблона, все типы, и как можно использовать несколько примеров запросов на создание группы на основе шаблона.</span><span class="sxs-lookup"><span data-stu-id="4c01d-107">In this article, we'll explain the properties that can be defined in templates, what base template types are, and how you can use a few sample requests to create a team from a template.</span></span>
 
<span data-ttu-id="4c01d-108">Эта статья является для вас, если вы:</span><span class="sxs-lookup"><span data-stu-id="4c01d-108">This article is for you if you're:</span></span>

- <span data-ttu-id="4c01d-109">Ответственность за планирование, развертывание и управление нескольких групп в организации</span><span class="sxs-lookup"><span data-stu-id="4c01d-109">Responsible for planning, deploying, and managing multiple teams across your organization</span></span><br>
- <span data-ttu-id="4c01d-110">Разработчик, которым требуется для программного создания группы с предварительно определенные каналы и приложений</span><span class="sxs-lookup"><span data-stu-id="4c01d-110">A developer wanting to programmatically create a team with predefined channels and apps</span></span> 

## <a name="teams-template-capabilities"></a><span data-ttu-id="4c01d-111">Возможности шаблон группы</span><span class="sxs-lookup"><span data-stu-id="4c01d-111">Teams template capabilities</span></span>

<span data-ttu-id="4c01d-112">Большинство свойств в группе включены и поддерживаются в шаблонах.</span><span class="sxs-lookup"><span data-stu-id="4c01d-112">Most properties in a team are included and supported by templates.</span></span> <span data-ttu-id="4c01d-113">Однако некоторые свойства и функции, которые в настоящее время не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="4c01d-113">But there are a few properties and features that are not currently supported.</span></span> <span data-ttu-id="4c01d-114">Ниже приведены краткая сводка того, что реализовано и что не входит в группы шаблонов.</span><span class="sxs-lookup"><span data-stu-id="4c01d-114">The following table provides a quick summary of what's included and what's not included in Teams templates.</span></span>

| <span data-ttu-id="4c01d-115">**Свойства группы, поддерживаемые шаблоны группы**</span><span class="sxs-lookup"><span data-stu-id="4c01d-115">**Team properties supported by Teams templates**</span></span> | <span data-ttu-id="4c01d-116">**Свойства группы еще не поддерживаются шаблонами групп**</span><span class="sxs-lookup"><span data-stu-id="4c01d-116">**Team properties not yet supported by Teams templates**</span></span> |
| ------------------------------------------------ | -------------------------------------------------------- |
| <span data-ttu-id="4c01d-117">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="4c01d-117">Base template type</span></span> | <span data-ttu-id="4c01d-118">Членство в группы</span><span class="sxs-lookup"><span data-stu-id="4c01d-118">Team membership</span></span> |
| <span data-ttu-id="4c01d-119">Название команды</span><span class="sxs-lookup"><span data-stu-id="4c01d-119">Team name</span></span> | <span data-ttu-id="4c01d-120">Изображение группы</span><span class="sxs-lookup"><span data-stu-id="4c01d-120">Team picture</span></span> |
| <span data-ttu-id="4c01d-121">Описание группы</span><span class="sxs-lookup"><span data-stu-id="4c01d-121">Team description</span></span> | <span data-ttu-id="4c01d-122">Параметры канала</span><span class="sxs-lookup"><span data-stu-id="4c01d-122">Channel settings</span></span> |
| <span data-ttu-id="4c01d-123">Группа видимости (public или private)</span><span class="sxs-lookup"><span data-stu-id="4c01d-123">Team visibility (public or private)</span></span> | <span data-ttu-id="4c01d-124">Соединители</span><span class="sxs-lookup"><span data-stu-id="4c01d-124">Connectors</span></span> |
| <span data-ttu-id="4c01d-125">Параметры группы (например, элемент, гостевой @ упоминания)</span><span class="sxs-lookup"><span data-stu-id="4c01d-125">Team settings (for example, member, guest, @ mentions)</span></span> | <span data-ttu-id="4c01d-126">Файлы и контента</span><span class="sxs-lookup"><span data-stu-id="4c01d-126">Files and content</span></span> |
| <span data-ttu-id="4c01d-127">Auto избранного канала</span><span class="sxs-lookup"><span data-stu-id="4c01d-127">Auto-favorite channel</span></span> | |
| <span data-ttu-id="4c01d-128">Установленного приложения</span><span class="sxs-lookup"><span data-stu-id="4c01d-128">Installed app</span></span> | |
| <span data-ttu-id="4c01d-129">Закрепленные вкладок</span><span class="sxs-lookup"><span data-stu-id="4c01d-129">Pinned tabs</span></span> | | 

> [!NOTE]
> <span data-ttu-id="4c01d-130">Мы будем Добавление дополнительные возможности шаблона в будущих версиях Microsoft групп, поэтому советуем обновленные сведения о поддерживаемых свойств.</span><span class="sxs-lookup"><span data-stu-id="4c01d-130">We'll be adding more template capabilities in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="what-are-base-template-types"></a><span data-ttu-id="4c01d-131">Что такое типы базового шаблона?</span><span class="sxs-lookup"><span data-stu-id="4c01d-131">What are base template types?</span></span>

<span data-ttu-id="4c01d-132">Типы базового шаблона — это специальные шаблоны, которые созданы Microsoft для конкретных отраслей.</span><span class="sxs-lookup"><span data-stu-id="4c01d-132">Base template types are special templates that Microsoft created for specific industries.</span></span> <span data-ttu-id="4c01d-133">Эти шаблоны базового часто содержит собственный приложения, которые не доступны в свойства хранилища и группы, которые еще не поддерживаются по отдельности в шаблонах группами.</span><span class="sxs-lookup"><span data-stu-id="4c01d-133">These base templates often contain proprietary apps that aren't available in the store and team properties that are not yet supported individually in Teams templates.</span></span>

<span data-ttu-id="4c01d-134">После определения типа базового шаблона можно расширить или переопределить эти специальные шаблоны, с помощью дополнительных свойств, которые вы хотите указать.</span><span class="sxs-lookup"><span data-stu-id="4c01d-134">Once a base template type is defined, you can extend or override these special templates with additional properties that you'd like to specify.</span></span> <span data-ttu-id="4c01d-135">Однако некоторые типы базового шаблона содержит свойства, которые не может быть переопределен.</span><span class="sxs-lookup"><span data-stu-id="4c01d-135">But some base template types contain properties that can't be overridden.</span></span> 

<span data-ttu-id="4c01d-136">По умолчанию базового шаблона — это значение **Standard** которого не содержит все дополнительные специализированных приложений или специальные свойства.</span><span class="sxs-lookup"><span data-stu-id="4c01d-136">By default the base template is set to **Standard** which doesn't contain any additional proprietary apps or special properties.</span></span> <span data-ttu-id="4c01d-137">Ниже текущего списка шаблонов базовые типы недоступны.</span><span class="sxs-lookup"><span data-stu-id="4c01d-137">Below is the current list of base templates types available.</span></span>

| <span data-ttu-id="4c01d-138">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="4c01d-138">Base template type</span></span> | <span data-ttu-id="4c01d-139">Идентификатор базового шаблона</span><span class="sxs-lookup"><span data-stu-id="4c01d-139">baseTemplateId</span></span> | <span data-ttu-id="4c01d-140">Базовый шаблон собственные приложения и специальные свойства</span><span class="sxs-lookup"><span data-stu-id="4c01d-140">Base template proprietary apps and special properties</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="4c01d-141">Standard</span><span class="sxs-lookup"><span data-stu-id="4c01d-141">Standard</span></span> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`standard` | <span data-ttu-id="4c01d-142">Нет дополнительных приложений и свойства</span><span class="sxs-lookup"><span data-stu-id="4c01d-142">No additional apps and properties</span></span> |
| <span data-ttu-id="4c01d-143">Образование-</span><span class="sxs-lookup"><span data-stu-id="4c01d-143">Education -</span></span> <br><span data-ttu-id="4c01d-144">Класс группы<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4c01d-144">Class team<sup>1</sup></span></span> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationClass` | <span data-ttu-id="4c01d-145">Приложения:</span><span class="sxs-lookup"><span data-stu-id="4c01d-145">Apps:</span></span><ul><li><span data-ttu-id="4c01d-146">Записной книжке OneNote класс (прикрепленных к вкладке « **Общие** »)</span><span class="sxs-lookup"><span data-stu-id="4c01d-146">OneNote Class Notebook (pinned to the **General** tab)</span></span> </li><li><span data-ttu-id="4c01d-147">Назначения приложения (прикрепленных к вкладке « **Общие** »)</span><span class="sxs-lookup"><span data-stu-id="4c01d-147">Assignments app (pinned to the **General** tab)</span></span></li></ul> <span data-ttu-id="4c01d-148">Свойства группы:</span><span class="sxs-lookup"><span data-stu-id="4c01d-148">Team properties:</span></span><ul><li><span data-ttu-id="4c01d-149">Группа видимости, задайте значение **HiddenMembership** (не может быть переопределен)</span><span class="sxs-lookup"><span data-stu-id="4c01d-149">Team visibility set to **HiddenMembership** (cannot be overridden)</span></span></li></ul> |
| <span data-ttu-id="4c01d-150">Образование-</span><span class="sxs-lookup"><span data-stu-id="4c01d-150">Education -</span></span><br><span data-ttu-id="4c01d-151">Персонал группы<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4c01d-151">Staff team<sup>1</sup></span></span> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationStaff` | <span data-ttu-id="4c01d-152">Приложения:</span><span class="sxs-lookup"><span data-stu-id="4c01d-152">Apps:</span></span><ul><li><span data-ttu-id="4c01d-153">Записной книжке OneNote персонала (прикрепленных к вкладке « **Общие** »)</span><span class="sxs-lookup"><span data-stu-id="4c01d-153">OneNote Staff Notebook (pinned to the **General** tab)</span></span></li></ul> |
|<span data-ttu-id="4c01d-154">Образование-</span><span class="sxs-lookup"><span data-stu-id="4c01d-154">Education -</span></span><br><span data-ttu-id="4c01d-155">Группа PLC</span><span class="sxs-lookup"><span data-stu-id="4c01d-155">PLC team</span></span> |`https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationProfessionalLearningCommunity` | <span data-ttu-id="4c01d-156">Приложения:</span><span class="sxs-lookup"><span data-stu-id="4c01d-156">Apps:</span></span><ul><li><span data-ttu-id="4c01d-157">Записной книжке OneNote PLC (прикрепленных к вкладке « **Общие** »)</span><span class="sxs-lookup"><span data-stu-id="4c01d-157">OneNote PLC Notebook (pinned to the **General** tab)</span></span></ul></li>|
|||

<span data-ttu-id="4c01d-158"><sup>1</sup> публикации в конце октября 2018 г.</span><span class="sxs-lookup"><span data-stu-id="4c01d-158"><sup>1</sup> Publication in late October, 2018</span></span>

> [!NOTE]
> <span data-ttu-id="4c01d-159">Мы будем добавлять дополнительные базового шаблона в следующих типов выпусков группами Майкрософт, чтобы проверять обратно на самые последние сведения о поддерживаемых свойств.</span><span class="sxs-lookup"><span data-stu-id="4c01d-159">We'll be adding more base template types in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="examples"></a><span data-ttu-id="4c01d-160">Примеры</span><span class="sxs-lookup"><span data-stu-id="4c01d-160">Examples</span></span> 

<span data-ttu-id="4c01d-161">Можно начать с помощью шаблона для создания группы с помощью [Microsoft Graph API](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="4c01d-161">You can start using a template to create a team by using the [Microsoft Graph API](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

### <a name="create-a-team-from-a-template"></a><span data-ttu-id="4c01d-162">Создание группы на основе шаблона</span><span class="sxs-lookup"><span data-stu-id="4c01d-162">Create a team from a template</span></span>

#### <a name="requests"></a><span data-ttu-id="4c01d-163">Запросы</span><span class="sxs-lookup"><span data-stu-id="4c01d-163">Requests</span></span>

<span data-ttu-id="4c01d-164">**Запрос на создание группы с помощью стандартных базового шаблона**</span><span class="sxs-lookup"><span data-stu-id="4c01d-164">**Request to create a team with the standard base template**</span></span>

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/standard",
  "displayName": "Sample Team",
  "description": "Sample Team’s Description"
}

~~~

<span data-ttu-id="4c01d-165">**Запрос на создание группы с помощью дополнительных канала и запретить члены из каналы**</span><span class="sxs-lookup"><span data-stu-id="4c01d-165">**Request to create a team with an extra channel and disallow members from deleting channels**</span></span>

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/standard",
  "displayName": "My Sample Team",
  "description": "My Sample Team’s Description",
  "channels": [
    {
        "displayName": "Random",
        "isFavoriteByDefault": true
    }
              ],
    "memberSettings": {
        "allowDeleteChannels": false
    }
}

~~~

<span data-ttu-id="4c01d-166">**Запрос на создание группы Все поддерживаемые свойства**</span><span class="sxs-lookup"><span data-stu-id="4c01d-166">**Request to create a team with all supported properties**</span></span>

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
    "visibility": "Private",
    "displayName": "Sample Engineering Team",
    "description": "This is a sample engineering team, used to showcase the range of properties 
supported by this API",
    "channels": [
        {
            "displayName": "Announcements 📢",
            "isFavoriteByDefault": true,
            "description": "This is a sample announcements channel that is favorited by default. Use this 
channel to make important team, product, and service announcements."
        },
        {
            "displayName": "Training 🏋️",
            "isFavoriteByDefault": true,
            "description": "This is a sample training channel that is favorited by default and contains an 
example of pinned website and YouTube tabs.",
            "tabs": [
                {
                    "teamsApp@odata.bind":
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.web')",
                   "name": "A Pinned Website",
                    "configuration": {
                        "contentUrl": "https://docs.microsoft.com/en-us/microsoftteams/microsoft-teams"
                    }
                },
                {
                    "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.youtube')",
                    "name": "A Pinned YouTube Video",
                    "configuration": {
                        "contentUrl": "https://tabs.teams.microsoft.com/Youtube/Home/YoutubeTab?
videoId=X8krAMdGvCQ",
                        "websiteUrl": "https://www.youtube.com/watch?v=X8krAMdGvCQ"
                    }
                }
            ]
        },
        {
"displayName": "Planning 📅 ",
            "description": "This is a sample of a channel that is not favorited by default, these channels 
will appear in the more channels overflow menu.",
            "isFavoriteByDefault": false
        },
        {
            "displayName": "Issues and Feedback 🐞",
            "description": "This is a sample of a channel that is not favorited by default, these channels 
will appear in the more channels overflow menu."
        }
    ],
    "memberSettings": {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
        "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "installedApps": [
        {
            "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.vsts')"
        },
        {
            "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('1542629c-01b3-4a6d-8f76-1938b779e48d')"
        }
    ]
}
~~~

### <a name="get-status"></a><span data-ttu-id="4c01d-167">Получить сведения о состоянии</span><span class="sxs-lookup"><span data-stu-id="4c01d-167">Get status</span></span>

#### <a name="request"></a><span data-ttu-id="4c01d-168">Запрос</span><span class="sxs-lookup"><span data-stu-id="4c01d-168">Request</span></span>

~~~
GET   /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
Authorization: Bearer <TOKEN>
~~~

#### <a name="response"></a><span data-ttu-id="4c01d-169">Response (Ответ)</span><span class="sxs-lookup"><span data-stu-id="4c01d-169">Response</span></span>

~~~
HTTP/1.1 200 OK
Content-Type: application/json
{
    "status": "[InProgress|Completed|Cancelled|Failed]"
}
~~~

## <a name="related-topics"></a><span data-ttu-id="4c01d-170">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="4c01d-170">Related topics</span></span>

- <span data-ttu-id="4c01d-171">[Создание группы](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (в предварительной версии)</span><span class="sxs-lookup"><span data-stu-id="4c01d-171">[Create team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>
- [<span data-ttu-id="4c01d-172">Новые группы</span><span class="sxs-lookup"><span data-stu-id="4c01d-172">New-Team</span></span>](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [<span data-ttu-id="4c01d-173">Обучение администратора для работы с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4c01d-173">Admin training for Microsoft Teams</span></span>](itadmin-readiness.md)