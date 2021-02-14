---
title: Начало работы с шаблонами Teams для розничной торговли
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Узнайте, как с помощью шаблонов Teams создавать структуры групп, разработанные для потребностей розничного продавца, предоставляя предопределять параметры, каналы и предварительно установленные приложения.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f226b60bfc3a054166eb48596c505ccd7fa5ac9
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424639"
---
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="d0eee-103">Начало работы с шаблонами Teams для розничной торговли</span><span class="sxs-lookup"><span data-stu-id="d0eee-103">Get started with Teams templates in retail</span></span>

<span data-ttu-id="d0eee-104">Шаблоны Teams позволяют быстро и легко создавать команды, предоставляя предопределяющий шаблон настроек, каналов и предварительно установленных приложений.</span><span class="sxs-lookup"><span data-stu-id="d0eee-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="d0eee-105">Шаблоны Teams имеют встроенные определения структур групп, разработанных для потребностей розничного продавца.</span><span class="sxs-lookup"><span data-stu-id="d0eee-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="d0eee-106">Вы можете использовать шаблоны Teams для быстрого создания типов команд, которые хорошо работают для розничных продавцов, и их развертывания в организации.</span><span class="sxs-lookup"><span data-stu-id="d0eee-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="d0eee-107">Вы также можете расширить шаблоны Teams для создания команд, специально разработанных для ваших организационных потребностей.</span><span class="sxs-lookup"><span data-stu-id="d0eee-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="d0eee-108">В этой статье мы введем каждый из шаблонов Teams и посоветуем использовать их.</span><span class="sxs-lookup"><span data-stu-id="d0eee-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="d0eee-109">Эта статья для вас, если вы отвечаете за планирование, развертывание и управление несколькими командами в розничной сети.</span><span class="sxs-lookup"><span data-stu-id="d0eee-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="d0eee-110">Вы уже развернули службу Teams в своей организации.</span><span class="sxs-lookup"><span data-stu-id="d0eee-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="d0eee-111">Если вы еще не начали работу с Teams, начните с того, как [это сделать.](How-to-roll-out-teams.md)</span><span class="sxs-lookup"><span data-stu-id="d0eee-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="d0eee-112">Подробнее о шаблонах команд читайте в теме "Начало [работы с шаблонами Teams".](get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="d0eee-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="d0eee-113">Шаблон Магазина</span><span class="sxs-lookup"><span data-stu-id="d0eee-113">Store template</span></span>

<span data-ttu-id="d0eee-114">Шаблон Магазина идеально подходит для того, чтобы создать команду для представления отдельного расположения в розничном магазине.</span><span class="sxs-lookup"><span data-stu-id="d0eee-114">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="d0eee-115">С помощью шаблона "Магазин" вы можете создать команду для каждого расположения в розничном магазине в организации.</span><span class="sxs-lookup"><span data-stu-id="d0eee-115">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="d0eee-116">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="d0eee-116">Base template type</span></span> | <span data-ttu-id="d0eee-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="d0eee-117">baseTemplateId</span></span> | <span data-ttu-id="d0eee-118">Свойства, которые доступны с этим базовым шаблоном</span><span class="sxs-lookup"><span data-stu-id="d0eee-118">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="d0eee-119">Розничная торговля —</span><span class="sxs-lookup"><span data-stu-id="d0eee-119">Retail -</span></span> <br><span data-ttu-id="d0eee-120">Хранилище</span><span class="sxs-lookup"><span data-stu-id="d0eee-120">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="d0eee-121">Каналы</span><span class="sxs-lookup"><span data-stu-id="d0eee-121">Channels</span></span> <ul><li><span data-ttu-id="d0eee-122">Смены\*</span><span class="sxs-lookup"><span data-stu-id="d0eee-122">Shifts handoff\*</span></span></li><li><span data-ttu-id="d0eee-123">Обучение\*</span><span class="sxs-lookup"><span data-stu-id="d0eee-123">Learning\*</span></span></li></ul><span data-ttu-id="d0eee-124">\*Автоматически избранные каналы</span><span class="sxs-lookup"><span data-stu-id="d0eee-124">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="d0eee-125">Свойства группы</span><span class="sxs-lookup"><span data-stu-id="d0eee-125">Team properties</span></span> <ul><li><span data-ttu-id="d0eee-126">Видимость группы с установленным на "Общедоступный"</span><span class="sxs-lookup"><span data-stu-id="d0eee-126">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="d0eee-127">Разрешения для членов группы</span><span class="sxs-lookup"><span data-stu-id="d0eee-127">Member permissions</span></span> <ul><li><span data-ttu-id="d0eee-128">Не может создавать, обновлять или удалять каналы</span><span class="sxs-lookup"><span data-stu-id="d0eee-128">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="d0eee-129">Не может добавлять и удалять приложения</span><span class="sxs-lookup"><span data-stu-id="d0eee-129">Can't add/remove apps</span></span> </li><li><span data-ttu-id="d0eee-130">Не может создавать, обновлять или удалять вкладки</span><span class="sxs-lookup"><span data-stu-id="d0eee-130">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="d0eee-131">Не может создать, обновить или удалить соединители</span><span class="sxs-lookup"><span data-stu-id="d0eee-131">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="d0eee-132">Рекомендуемые способы настройки шаблона Магазина для организации:</span><span class="sxs-lookup"><span data-stu-id="d0eee-132">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="d0eee-133">Если в вашей организации есть отделы в каждом магазине, добавьте канал для каждого отдела.</span><span class="sxs-lookup"><span data-stu-id="d0eee-133">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="d0eee-134">Добавление канала упрощает взаимодействие и совместную работу внутри отдела.</span><span class="sxs-lookup"><span data-stu-id="d0eee-134">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="d0eee-135">Если в вашей организации есть внутренние веб-сайты (например, сайт SharePoint), их можно закрепление в качестве вкладок в соответствующем канале группы.</span><span class="sxs-lookup"><span data-stu-id="d0eee-135">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="d0eee-136">Инструкции [по началу работы с шаблонами Teams](get-started-with-teams-templates.md) можно найти в этой ссылке.</span><span class="sxs-lookup"><span data-stu-id="d0eee-136">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="d0eee-137">Шаблон совместной работы руководителя</span><span class="sxs-lookup"><span data-stu-id="d0eee-137">Manager Collaboration template</span></span>

<span data-ttu-id="d0eee-138">Шаблон совместной работы руководителя — это еще один шаблон Teams, разработанный для розничного продавца.</span><span class="sxs-lookup"><span data-stu-id="d0eee-138">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="d0eee-139">Шаблон совместной работы руководителя идеально подходит для создания команды для группы руководителей для совместной работы в магазинах и регионах и не только.</span><span class="sxs-lookup"><span data-stu-id="d0eee-139">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="d0eee-140">Например, если в вашей организации есть регионы, вы можете создать команду совместной работы руководителя для Калифорнии и включить в нее всех менеджеров магазинов в этом регионе, а также регионального руководителя для этого региона.</span><span class="sxs-lookup"><span data-stu-id="d0eee-140">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="d0eee-141">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="d0eee-141">Base template type</span></span> | <span data-ttu-id="d0eee-142">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="d0eee-142">baseTemplateId</span></span> | <span data-ttu-id="d0eee-143">Свойства, которые доступны с этим базовым шаблоном</span><span class="sxs-lookup"><span data-stu-id="d0eee-143">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="d0eee-144">Розничная торговля —</span><span class="sxs-lookup"><span data-stu-id="d0eee-144">Retail -</span></span> <br><span data-ttu-id="d0eee-145">Хранилище</span><span class="sxs-lookup"><span data-stu-id="d0eee-145">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="d0eee-146">Каналы</span><span class="sxs-lookup"><span data-stu-id="d0eee-146">Channels</span></span> <ul><li><span data-ttu-id="d0eee-147">Операции\*</span><span class="sxs-lookup"><span data-stu-id="d0eee-147">Operations\*</span></span></li><li><span data-ttu-id="d0eee-148">Обучение\*</span><span class="sxs-lookup"><span data-stu-id="d0eee-148">Learning\*</span></span></li></ul><span data-ttu-id="d0eee-149">\*Автоматически избранные каналы</span><span class="sxs-lookup"><span data-stu-id="d0eee-149">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="d0eee-150">Свойства группы</span><span class="sxs-lookup"><span data-stu-id="d0eee-150">Team properties</span></span> <ul><li><span data-ttu-id="d0eee-151">Видимость группы с установленным на "Частное"</span><span class="sxs-lookup"><span data-stu-id="d0eee-151">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="d0eee-152">Разрешения для членов группы</span><span class="sxs-lookup"><span data-stu-id="d0eee-152">Member permissions</span></span> <ul><li><span data-ttu-id="d0eee-153">Создание, обновление и удаление каналов</span><span class="sxs-lookup"><span data-stu-id="d0eee-153">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="d0eee-154">Добавление и удаление приложений</span><span class="sxs-lookup"><span data-stu-id="d0eee-154">Can add/remove apps</span></span> </li><li><span data-ttu-id="d0eee-155">Создание, обновление и удаление вкладок</span><span class="sxs-lookup"><span data-stu-id="d0eee-155">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="d0eee-156">Создание, обновление и удаление соединители</span><span class="sxs-lookup"><span data-stu-id="d0eee-156">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="d0eee-157">Рекомендуемые способы настройки шаблона совместной работы руководителя в организации:</span><span class="sxs-lookup"><span data-stu-id="d0eee-157">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="d0eee-158">Если в вашей организации есть какие-либо внутренние веб-сайты, например сайт SharePoint, которые важны для руководителей, их можно закрепление в качестве вкладок в соответствующем канале группы.</span><span class="sxs-lookup"><span data-stu-id="d0eee-158">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="d0eee-159">Инструкции вы можете найти в документации по шаблонам [Microsoft Teams.](get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="d0eee-159">You can take a look at the [Microsoft Teams Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="d0eee-160">Использование шаблонов от первой стороны</span><span class="sxs-lookup"><span data-stu-id="d0eee-160">How to use first party templates</span></span>

<span data-ttu-id="d0eee-161">Чтобы использовать эти шаблоны, измените свойство template@odata.bind" в теле запроса со стандартного на шаблон TemplateIDs выше.</span><span class="sxs-lookup"><span data-stu-id="d0eee-161">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="d0eee-162">Дополнительные сведения о развертывании шаблонов Teams см. в статье Microsoft Graph о том, как [создать команду.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="d0eee-162">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="d0eee-163">Каналы в шаблоне будут автоматически созданы на вкладке "Общие".</span><span class="sxs-lookup"><span data-stu-id="d0eee-163">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="d0eee-164">Пример: сценарий расширения шаблона Store</span><span class="sxs-lookup"><span data-stu-id="d0eee-164">Example: Store template extension script</span></span>

``` PowerShell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('retailStore')",
  "DisplayName": "Contoso Store",
  "Description": "Team for all staff in Contoso Store",
  "Channels": [
    {
      "displayName": "Additional store channel",
      "IsFavoriteByDefault": false
    }
  ]
}
```
## <a name="relate-topic"></a><span data-ttu-id="d0eee-165">Связать тему</span><span class="sxs-lookup"><span data-stu-id="d0eee-165">Relate topic</span></span>

[<span data-ttu-id="d0eee-166">Начало работы с шаблонами Teams в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="d0eee-166">Get started with Teams templates in the Admin center</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
