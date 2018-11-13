---
title: Начало работы с группами шаблонов
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
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
ms.openlocfilehash: 7850ad245eebee96b6852e7f0cc57a35adcca9f7
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295009"
---
# <a name="get-started-with-teams-templates"></a><span data-ttu-id="fa92e-103">Начало работы с группами шаблонов</span><span class="sxs-lookup"><span data-stu-id="fa92e-103">Get started with Teams templates</span></span> 

<span data-ttu-id="fa92e-104">Шаблоны группы — это готовые основе определения структуры группы, созданная на основе потребность или проекта.</span><span class="sxs-lookup"><span data-stu-id="fa92e-104">Team templates are pre-built definitions of a team's structure designed around a business need or project.</span></span> <span data-ttu-id="fa92e-105">Шаблоны группы можно использовать для быстрого создания пробелы расширенными возможностями совместной работы с каналами для разных тем и Предустановка приложений для работы на критически важных контент и службы.</span><span class="sxs-lookup"><span data-stu-id="fa92e-105">You can use team templates to quickly create rich collaboration spaces with channels for different topics and preinstall apps to pull in mission-critical content and services.</span></span> <span data-ttu-id="fa92e-106">Шаблоны группы предоставить структуру предварительно определенные группы, которая поможет вам легко создавать согласованные группам в организации.</span><span class="sxs-lookup"><span data-stu-id="fa92e-106">Team templates provide a predefined team structure that can help you easily create consistent teams across your organization.</span></span> 

<span data-ttu-id="fa92e-107">В этой статье мы расскажем свойства, которые могут быть определены в шаблонах, какие базового шаблона, все типы, и как можно использовать несколько примеров запросов на создание группы на основе шаблона.</span><span class="sxs-lookup"><span data-stu-id="fa92e-107">In this article, we'll explain the properties that can be defined in templates, what base template types are, and how you can use a few sample requests to create a team from a template.</span></span>
 
<span data-ttu-id="fa92e-108">Эта статья является для вас, если вы:</span><span class="sxs-lookup"><span data-stu-id="fa92e-108">This article is for you if you're:</span></span>

<span data-ttu-id="fa92e-109">• Ответственность за планирования, развертывания и управления несколькими группами в рамках разработчиков • A вашей организации нужна для создания группы с предопределенное каналы и приложения программными средствами</span><span class="sxs-lookup"><span data-stu-id="fa92e-109">•   Responsible for planning, deploying, and managing multiple teams across your organization •   A developer looking to create a team with predefined channels and apps programmatically</span></span>

## <a name="team-template-capabilities"></a><span data-ttu-id="fa92e-110">Возможности шаблон группы</span><span class="sxs-lookup"><span data-stu-id="fa92e-110">Team template capabilities</span></span>

<span data-ttu-id="fa92e-111">Большинство свойств в группе включены и поддерживаются в шаблонах.</span><span class="sxs-lookup"><span data-stu-id="fa92e-111">Most properties in a team are included and supported by templates.</span></span> <span data-ttu-id="fa92e-112">Однако есть некоторые свойства и функции, которые в настоящее время не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="fa92e-112">However, there are a few properties and features that are currently not supported.</span></span> <span data-ttu-id="fa92e-113">Ниже приведены краткая сводка того, что реализовано и что не входит в группы шаблонов.</span><span class="sxs-lookup"><span data-stu-id="fa92e-113">The following table provides a quick summary of what's included and what's not included in Teams templates.</span></span>

| <span data-ttu-id="fa92e-114">**Свойства группы, поддерживаемые шаблоны группы**</span><span class="sxs-lookup"><span data-stu-id="fa92e-114">**Team properties supported by Teams templates**</span></span> | <span data-ttu-id="fa92e-115">**Свойства группы еще не поддерживаются шаблонами групп**</span><span class="sxs-lookup"><span data-stu-id="fa92e-115">**Team properties not yet supported by Teams templates**</span></span> |
| ------------------------------------------------ | -------------------------------------------------------- |
| <span data-ttu-id="fa92e-116">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="fa92e-116">Base template type</span></span> | <span data-ttu-id="fa92e-117">Членство в группы</span><span class="sxs-lookup"><span data-stu-id="fa92e-117">Team membership</span></span> |
| <span data-ttu-id="fa92e-118">Название команды</span><span class="sxs-lookup"><span data-stu-id="fa92e-118">Team name</span></span> | <span data-ttu-id="fa92e-119">Изображение группы</span><span class="sxs-lookup"><span data-stu-id="fa92e-119">Team picture</span></span> |
| <span data-ttu-id="fa92e-120">Описание группы</span><span class="sxs-lookup"><span data-stu-id="fa92e-120">Team description</span></span> | <span data-ttu-id="fa92e-121">Параметры канала (, например auto Избранное и конфиденциальность)</span><span class="sxs-lookup"><span data-stu-id="fa92e-121">Channel settings (for example, auto-favorite and privacy)</span></span> |
| <span data-ttu-id="fa92e-122">Группа видимости (public или private)</span><span class="sxs-lookup"><span data-stu-id="fa92e-122">Team visibility (public or private)</span></span> | <span data-ttu-id="fa92e-123">Соединители</span><span class="sxs-lookup"><span data-stu-id="fa92e-123">Connectors</span></span> |
| <span data-ttu-id="fa92e-124">Параметры группы (например, элемент, гостевой @ упоминания)</span><span class="sxs-lookup"><span data-stu-id="fa92e-124">Team settings (for example, member, guest, @ mentions)</span></span> | <span data-ttu-id="fa92e-125">Файлы и контента</span><span class="sxs-lookup"><span data-stu-id="fa92e-125">Files and content</span></span> |
| <span data-ttu-id="fa92e-126">Auto избранного канала</span><span class="sxs-lookup"><span data-stu-id="fa92e-126">Auto-favorite channel</span></span> | |
| <span data-ttu-id="fa92e-127">Установленного приложения</span><span class="sxs-lookup"><span data-stu-id="fa92e-127">Installed app</span></span> | |
| <span data-ttu-id="fa92e-128">Закрепленные вкладок</span><span class="sxs-lookup"><span data-stu-id="fa92e-128">Pinned tabs</span></span> | | 

> [!NOTE]
> <span data-ttu-id="fa92e-129">Мы будем Добавление дополнительные возможности шаблона в будущих версиях Microsoft групп, поэтому советуем обновленные сведения о поддерживаемых свойств.</span><span class="sxs-lookup"><span data-stu-id="fa92e-129">We'll be adding more template capabilities in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="what-are-base-template-types"></a><span data-ttu-id="fa92e-130">Что такое типы базового шаблона?</span><span class="sxs-lookup"><span data-stu-id="fa92e-130">What are base template types?</span></span>

<span data-ttu-id="fa92e-131">Типы базового шаблона — это специальные шаблоны, которые созданы Microsoft для конкретных отраслей.</span><span class="sxs-lookup"><span data-stu-id="fa92e-131">Base template types are special templates that Microsoft created for specific industries.</span></span> <span data-ttu-id="fa92e-132">Эти шаблоны базового часто содержит собственный приложения, которые не доступны в свойства хранилища и группы, еще не поддерживаются в шаблонах группами по отдельности.</span><span class="sxs-lookup"><span data-stu-id="fa92e-132">These base templates often contain proprietary apps that aren't available in the store and team properties not yet supported individually in Teams templates.</span></span>

<span data-ttu-id="fa92e-133">После определения типа базового шаблона можно расширить или переопределить эти специальные шаблоны, с помощью дополнительных свойств, которые вы хотите указать.</span><span class="sxs-lookup"><span data-stu-id="fa92e-133">Once a base template type is defined, you can extend or override these special templates with additional properties that you'd like to specify.</span></span> <span data-ttu-id="fa92e-134">Тем не менее некоторые типы базового шаблона содержит свойства, которые нельзя переопределить.</span><span class="sxs-lookup"><span data-stu-id="fa92e-134">However, some base template types contain properties that can't be overridden.</span></span> 

<span data-ttu-id="fa92e-135">По умолчанию базового шаблона — это значение **Standard** которого не содержит все дополнительные специализированных приложений или специальные свойства.</span><span class="sxs-lookup"><span data-stu-id="fa92e-135">By default the base template is set to **Standard** which doesn't contain any additional proprietary apps or special properties.</span></span> <span data-ttu-id="fa92e-136">Ниже текущего списка шаблонов базовые типы недоступны.</span><span class="sxs-lookup"><span data-stu-id="fa92e-136">Below is the current list of base templates types available.</span></span>

| <span data-ttu-id="fa92e-137">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="fa92e-137">Base template type</span></span> | <span data-ttu-id="fa92e-138">Идентификатор базового шаблона</span><span class="sxs-lookup"><span data-stu-id="fa92e-138">baseTemplateId</span></span> | <span data-ttu-id="fa92e-139">Базовый шаблон собственные приложения и специальные свойства</span><span class="sxs-lookup"><span data-stu-id="fa92e-139">Base template proprietary apps and special properties</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="fa92e-140">Standard</span><span class="sxs-lookup"><span data-stu-id="fa92e-140">Standard</span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json) | <span data-ttu-id="fa92e-141">Нет дополнительных приложений и свойства</span><span class="sxs-lookup"><span data-stu-id="fa92e-141">No additional apps and properties</span></span> |
| <span data-ttu-id="fa92e-142">Здравоохранение - медицинскими координация</span><span class="sxs-lookup"><span data-stu-id="fa92e-142">Healthcare - care coordination</span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#) | <span data-ttu-id="fa92e-143">Приложения:</span><span class="sxs-lookup"><span data-stu-id="fa92e-143">Apps:</span></span><br/> <span data-ttu-id="fa92e-144">-Приложение пострадавших (прикрепленных к вкладке « **Общие** »)</span><span class="sxs-lookup"><span data-stu-id="fa92e-144">- Patients app (pinned to the **General** tab)</span></span><br/> <br/><span data-ttu-id="fa92e-145">Каналы:</span><span class="sxs-lookup"><span data-stu-id="fa92e-145">Channels:</span></span> <br/> <span data-ttu-id="fa92e-146">-Объявления</span><span class="sxs-lookup"><span data-stu-id="fa92e-146">- Announcements</span></span><br/> <span data-ttu-id="fa92e-147">-Diabetes</span><span class="sxs-lookup"><span data-stu-id="fa92e-147">- Diabetes</span></span><br/> <span data-ttu-id="fa92e-148">-Cardiovascular</span><span class="sxs-lookup"><span data-stu-id="fa92e-148">- Cardiovascular</span></span><br/> <span data-ttu-id="fa92e-149">-Зарегистрированные медсестры</span><span class="sxs-lookup"><span data-stu-id="fa92e-149">- Registered nurses</span></span> |
| <span data-ttu-id="fa92e-150">Здравоохранение - ютиться процесса</span><span class="sxs-lookup"><span data-stu-id="fa92e-150">Healthcare - process huddle</span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#) | <span data-ttu-id="fa92e-151">Каналы:</span><span class="sxs-lookup"><span data-stu-id="fa92e-151">Channels:</span></span><br/> <span data-ttu-id="fa92e-152">-Вызывает писателем в мире</span><span class="sxs-lookup"><span data-stu-id="fa92e-152">- Avoidable deaths</span></span><br/> <span data-ttu-id="fa92e-153">-Обзор mortality</span><span class="sxs-lookup"><span data-stu-id="fa92e-153">- Mortality review</span></span> <br/> <span data-ttu-id="fa92e-154">-Предотвращение представлена</span><span class="sxs-lookup"><span data-stu-id="fa92e-154">- Preventing falls</span></span> <br/> <span data-ttu-id="fa92e-155">-Планы sepsis</span><span class="sxs-lookup"><span data-stu-id="fa92e-155">- Sepsis plans</span></span> |
| <span data-ttu-id="fa92e-156">Образование - класс группы<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="fa92e-156">Education - Class team<sup>1</sup></span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#) | <span data-ttu-id="fa92e-157">Приложения:</span><span class="sxs-lookup"><span data-stu-id="fa92e-157">Apps:</span></span><br/> <span data-ttu-id="fa92e-158">-Класс заметки (прикрепленных к вкладке « **Общие** »)</span><span class="sxs-lookup"><span data-stu-id="fa92e-158">- OneNote Class Notebook (pinned to the **General** tab)</span></span> <br/> <span data-ttu-id="fa92e-159">-Приложение назначений (прикрепленных к вкладке « **Общие** »)</span><span class="sxs-lookup"><span data-stu-id="fa92e-159">- Assignments app (pinned to the **General** tab)</span></span> <br/><br/> <span data-ttu-id="fa92e-160">Свойства группы</span><span class="sxs-lookup"><span data-stu-id="fa92e-160">Team properties</span></span> <br/> <span data-ttu-id="fa92e-161">-Задайте значение **HiddenMembership** (не может быть переопределен) видимости подключения группой разработки</span><span class="sxs-lookup"><span data-stu-id="fa92e-161">- Team visibility set to **HiddenMembership** (cannot be overridden)</span></span> |
| <span data-ttu-id="fa92e-162">Образование - персонала группы<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="fa92e-162">Education - Staff team<sup>1</sup></span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#) | <span data-ttu-id="fa92e-163">Приложения</span><span class="sxs-lookup"><span data-stu-id="fa92e-163">Apps</span></span><br/> <span data-ttu-id="fa92e-164">-Персонала заметки (прикрепленных к вкладке « **Общие** »)</span><span class="sxs-lookup"><span data-stu-id="fa92e-164">- OneNote Staff Notebook (pinned to the **General** tab)</span></span> |

<span data-ttu-id="fa92e-165"><sup>1</sup> публикации в конце октября 2018 г.</span><span class="sxs-lookup"><span data-stu-id="fa92e-165"><sup>1</sup> Publication in late October, 2018</span></span>

> [!NOTE]
> <span data-ttu-id="fa92e-166">Мы будем добавлять дополнительные базового шаблона в следующих типов выпусков группами Майкрософт, чтобы проверять обратно на самые последние сведения о поддерживаемых свойств.</span><span class="sxs-lookup"><span data-stu-id="fa92e-166">We'll be adding more base template types in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="examples"></a><span data-ttu-id="fa92e-167">Примеры</span><span class="sxs-lookup"><span data-stu-id="fa92e-167">Examples</span></span> 

<span data-ttu-id="fa92e-168">Можно приступать к созданию группы с помощью шаблона, установив [Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/overview).</span><span class="sxs-lookup"><span data-stu-id="fa92e-168">You can start creating a team via template by installing [Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/overview).</span></span>

### <a name="create-a-team-from-a-template"></a><span data-ttu-id="fa92e-169">Создание группы на основе шаблона</span><span class="sxs-lookup"><span data-stu-id="fa92e-169">Create a team from a template</span></span>

#### <a name="requests"></a><span data-ttu-id="fa92e-170">Запросы</span><span class="sxs-lookup"><span data-stu-id="fa92e-170">Requests</span></span>

<span data-ttu-id="fa92e-171">**Запрос на создание группы с помощью стандартных базового шаблона**</span><span class="sxs-lookup"><span data-stu-id="fa92e-171">**Request to create a team with the standard base template**</span></span>

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
}

~~~

<span data-ttu-id="fa92e-172">**Запрос на создание группы с помощью дополнительных канала и запретить члены из каналы**</span><span class="sxs-lookup"><span data-stu-id="fa92e-172">**Request to create a team with an extra channel and disallow members from deleting channels**</span></span>

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
    "channels": [
        {
            "displayName": "Interns",
            "autoFavorite": false
        }
    ],
    "memberSettings": {
        "allowDeleteChannels": false,
    }
}

~~~

<span data-ttu-id="fa92e-173">**Запрос на создание группы Все поддерживаемые свойства**</span><span class="sxs-lookup"><span data-stu-id="fa92e-173">**Request to create a team with all supported properties**</span></span>

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
 
    "teamType": "Healthcare_CareCoordination",
    "visibility": "Private",
    "teamDisplayName": "My Care Team",
    "teamDescription": "My Care Team’s description",
 
    "channels": [
        {
            "displayName": "General  ",
            "autoFavorite": true,
            "tabs": [
                   {
                       "appId": "0d820ecd-def2-4297-adad-78056cde7c78",
                       "tabDisplayName": "Intranet”
                   }
               ]
        },
        {
            "displayName": "Announcements",
            "autoFavorite": true
        },
        {
            "displayName": "Diabetes",
            "autoFavorite": true
        },
        {
            "displayName": "Cardiovascular",
            "autoFavorite": true
        },
        {
            "displayName": "Registered Nurses",
            "autoFavorite": true
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
 
      "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
      },
 
      "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
      }
 
 
    "installedApplications": [
      {
        "id": "0d820ecd-def2-4297-adad-78056cde7c78"
      }
    ]
}
~~~

#### <a name="response"></a><span data-ttu-id="fa92e-174">Response (Ответ)</span><span class="sxs-lookup"><span data-stu-id="fa92e-174">Response</span></span>

~~~
HTTP/1.1 202 Accepted
Content-Type: application/json
Location: /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
{
    "workflowId": "c953c202-7b44-4a63-aa33-364fcb2d65aa",
    "statusUri": "https://<apihostandpath>/workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa"
}
~~~

### <a name="get-status"></a><span data-ttu-id="fa92e-175">Получить сведения о состоянии</span><span class="sxs-lookup"><span data-stu-id="fa92e-175">Get status</span></span>

#### <a name="request"></a><span data-ttu-id="fa92e-176">Запрос</span><span class="sxs-lookup"><span data-stu-id="fa92e-176">Request</span></span>

~~~
GET   /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
Authorization: Bearer <TOKEN>
~~~

#### <a name="response"></a><span data-ttu-id="fa92e-177">Response (Ответ)</span><span class="sxs-lookup"><span data-stu-id="fa92e-177">Response</span></span>

~~~
HTTP/1.1 200 OK
Content-Type: application/json
{
    "status": "[InProgress|Completed|Cancelled|Failed]"
}
~~~

## <a name="related-topics"></a><span data-ttu-id="fa92e-178">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="fa92e-178">Related topics</span></span>

- <span data-ttu-id="fa92e-179">[Создание группы](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/team_put_teams) (в предварительной версии)</span><span class="sxs-lookup"><span data-stu-id="fa92e-179">[Create team](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/team_put_teams) (in preview)</span></span>
- [<span data-ttu-id="fa92e-180">Новые группы</span><span class="sxs-lookup"><span data-stu-id="fa92e-180">New-Team</span></span>](https://docs.microsoft.com/en-us/powershell/module/teams/New-Team?view=teams-ps)
- [<span data-ttu-id="fa92e-181">Обучение ИТ-администратора для работы с Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fa92e-181">Admin training for Microsoft Teams</span></span>](itadmin-readiness.md)