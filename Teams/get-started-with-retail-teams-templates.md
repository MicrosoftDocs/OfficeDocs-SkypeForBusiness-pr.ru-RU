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
description: Сведения о том, как использовать шаблоны групп для создания структур групп, разработанных для продавцов, предоставляя предопределенные параметры, каналы и предустановленные приложения.
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
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="650bc-103">Начало работы с шаблонами Teams для розничной торговли</span><span class="sxs-lookup"><span data-stu-id="650bc-103">Get started with Teams templates in retail</span></span>

<span data-ttu-id="650bc-104">Шаблоны групп позволяют быстро и легко создавать группы, предоставляя готовый шаблон параметров, каналов и предустановленных приложений.</span><span class="sxs-lookup"><span data-stu-id="650bc-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="650bc-105">Шаблоны групп имеют предварительно составленные определения структур групп, разработанных в отношении потребностей розничной торговли.</span><span class="sxs-lookup"><span data-stu-id="650bc-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="650bc-106">Шаблоны Teams можно использовать для быстрого создания типов рабочих групп, которые подходят для розничных продавцов, и их развертывания в Организации.</span><span class="sxs-lookup"><span data-stu-id="650bc-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="650bc-107">Вы также можете расширять шаблоны групп, чтобы создавать группы, адаптированные в соответствии с конкретными потребностями Организации.</span><span class="sxs-lookup"><span data-stu-id="650bc-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="650bc-108">В этой статье мы рассмотрим каждый из шаблонов Teams и рекомендуем использовать их.</span><span class="sxs-lookup"><span data-stu-id="650bc-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="650bc-109">Эта статья предназначена для вас, если вы несете ответственность за планирование, развертывание и управление несколькими группами в рамках своей организации розничной торговли.</span><span class="sxs-lookup"><span data-stu-id="650bc-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="650bc-110">Вы уже развернули службу Teams в своей организации.</span><span class="sxs-lookup"><span data-stu-id="650bc-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="650bc-111">Если вы еще не выполнили развертывание групп, начните с ознакомления с [развертыванием Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="650bc-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="650bc-112">Дополнительные сведения о шаблонах групп можно найти в разделе [Приступая к работе с шаблонами групп](get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="650bc-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="650bc-113">Шаблон магазина</span><span class="sxs-lookup"><span data-stu-id="650bc-113">Store template</span></span>

<span data-ttu-id="650bc-114">Шаблон магазина идеально подходит для создания группы, представляющей отдельное расположение для розничного магазина.</span><span class="sxs-lookup"><span data-stu-id="650bc-114">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="650bc-115">С помощью шаблона магазина вы можете создать группу для каждого из ее местоположений в розничном магазине.</span><span class="sxs-lookup"><span data-stu-id="650bc-115">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="650bc-116">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="650bc-116">Base template type</span></span> | <span data-ttu-id="650bc-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="650bc-117">baseTemplateId</span></span> | <span data-ttu-id="650bc-118">Свойства, которые поставляются с этим базовым шаблоном</span><span class="sxs-lookup"><span data-stu-id="650bc-118">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="650bc-119">Магазины</span><span class="sxs-lookup"><span data-stu-id="650bc-119">Retail -</span></span> <br><span data-ttu-id="650bc-120">Хранилище</span><span class="sxs-lookup"><span data-stu-id="650bc-120">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="650bc-121">Каналы</span><span class="sxs-lookup"><span data-stu-id="650bc-121">Channels</span></span> <ul><li><span data-ttu-id="650bc-122">Переносится смена\*</span><span class="sxs-lookup"><span data-stu-id="650bc-122">Shifts handoff\*</span></span></li><li><span data-ttu-id="650bc-123">Образователь\*</span><span class="sxs-lookup"><span data-stu-id="650bc-123">Learning\*</span></span></li></ul><span data-ttu-id="650bc-124">\*Автоматически добавленные в избранное каналы</span><span class="sxs-lookup"><span data-stu-id="650bc-124">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="650bc-125">Свойства группы</span><span class="sxs-lookup"><span data-stu-id="650bc-125">Team properties</span></span> <ul><li><span data-ttu-id="650bc-126">Для видимости команды установлено значение Public</span><span class="sxs-lookup"><span data-stu-id="650bc-126">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="650bc-127">Разрешения для участников</span><span class="sxs-lookup"><span data-stu-id="650bc-127">Member permissions</span></span> <ul><li><span data-ttu-id="650bc-128">Не удается создать, обновить или удалить каналы</span><span class="sxs-lookup"><span data-stu-id="650bc-128">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="650bc-129">Не удается добавить или удалить приложения</span><span class="sxs-lookup"><span data-stu-id="650bc-129">Can't add/remove apps</span></span> </li><li><span data-ttu-id="650bc-130">Не удается создать, обновить или удалить вкладки</span><span class="sxs-lookup"><span data-stu-id="650bc-130">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="650bc-131">Не удается создать, обновить или удалить соединительные линии</span><span class="sxs-lookup"><span data-stu-id="650bc-131">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="650bc-132">Рекомендуемые способы настройки шаблона магазина для Организации.</span><span class="sxs-lookup"><span data-stu-id="650bc-132">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="650bc-133">Если в вашей организации есть подразделения в каждом магазине, добавьте канал для каждого отдела.</span><span class="sxs-lookup"><span data-stu-id="650bc-133">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="650bc-134">Добавление канала упрощает общение и совместную работу в рамках Отдела.</span><span class="sxs-lookup"><span data-stu-id="650bc-134">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="650bc-135">Если в вашей организации есть внутренние веб-сайты (например, сайт SharePoint), можно закрепить их в виде вкладок в соответствующем канале группы.</span><span class="sxs-lookup"><span data-stu-id="650bc-135">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="650bc-136">Инструкции можно найти в разделе [Приступая к работе с шаблонами Teams](get-started-with-teams-templates.md) .</span><span class="sxs-lookup"><span data-stu-id="650bc-136">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="650bc-137">Шаблон совместной работы с диспетчером</span><span class="sxs-lookup"><span data-stu-id="650bc-137">Manager Collaboration template</span></span>

<span data-ttu-id="650bc-138">Шаблон совместной работы с руководителем — это еще один из шаблонов групп, разработанных на основе требований продавца.</span><span class="sxs-lookup"><span data-stu-id="650bc-138">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="650bc-139">Шаблон совместной работы с руководителем — это идеальный способ для создания группы для набора руководителей для совместной работы над магазинами и областями, а также многое другое.</span><span class="sxs-lookup"><span data-stu-id="650bc-139">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="650bc-140">Например, если в вашей организации есть регионы, вы можете создать группу совместной работы с руководителем для региона Калифорнии и включить в нее всех руководителей магазина, а также региональных менеджеров для этого региона.</span><span class="sxs-lookup"><span data-stu-id="650bc-140">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="650bc-141">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="650bc-141">Base template type</span></span> | <span data-ttu-id="650bc-142">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="650bc-142">baseTemplateId</span></span> | <span data-ttu-id="650bc-143">Свойства, которые поставляются с этим базовым шаблоном</span><span class="sxs-lookup"><span data-stu-id="650bc-143">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="650bc-144">Магазины</span><span class="sxs-lookup"><span data-stu-id="650bc-144">Retail -</span></span> <br><span data-ttu-id="650bc-145">Хранилище</span><span class="sxs-lookup"><span data-stu-id="650bc-145">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="650bc-146">Каналы</span><span class="sxs-lookup"><span data-stu-id="650bc-146">Channels</span></span> <ul><li><span data-ttu-id="650bc-147">Операции\*</span><span class="sxs-lookup"><span data-stu-id="650bc-147">Operations\*</span></span></li><li><span data-ttu-id="650bc-148">Образователь\*</span><span class="sxs-lookup"><span data-stu-id="650bc-148">Learning\*</span></span></li></ul><span data-ttu-id="650bc-149">\*Автоматически добавленные в избранное каналы</span><span class="sxs-lookup"><span data-stu-id="650bc-149">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="650bc-150">Свойства группы</span><span class="sxs-lookup"><span data-stu-id="650bc-150">Team properties</span></span> <ul><li><span data-ttu-id="650bc-151">Для видимости команды установлено значение Private</span><span class="sxs-lookup"><span data-stu-id="650bc-151">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="650bc-152">Разрешения для участников</span><span class="sxs-lookup"><span data-stu-id="650bc-152">Member permissions</span></span> <ul><li><span data-ttu-id="650bc-153">Может создавать, обновлять и удалять каналы</span><span class="sxs-lookup"><span data-stu-id="650bc-153">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="650bc-154">Можно добавлять и удалять приложения</span><span class="sxs-lookup"><span data-stu-id="650bc-154">Can add/remove apps</span></span> </li><li><span data-ttu-id="650bc-155">Можно создавать, обновлять и удалять вкладки</span><span class="sxs-lookup"><span data-stu-id="650bc-155">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="650bc-156">Может создавать, обновлять и удалять соединители</span><span class="sxs-lookup"><span data-stu-id="650bc-156">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="650bc-157">Рекомендации по настройке шаблона совместной работы для руководителей в Организации.</span><span class="sxs-lookup"><span data-stu-id="650bc-157">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="650bc-158">Если в вашей организации есть внутренние веб-сайты, например сайт SharePoint, которые будут важны для руководителей, рекомендуется закрепить их в виде вкладок в соответствующем канале группы.</span><span class="sxs-lookup"><span data-stu-id="650bc-158">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="650bc-159">Вы можете ознакомиться с [документацией по шаблону Microsoft Teams](get-started-with-teams-templates.md) .</span><span class="sxs-lookup"><span data-stu-id="650bc-159">You can take a look at the [Microsoft Teams Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="650bc-160">Использование шаблонов первого субъекта</span><span class="sxs-lookup"><span data-stu-id="650bc-160">How to use first party templates</span></span>

<span data-ttu-id="650bc-161">Чтобы использовать эти шаблоны, измените свойство "template@odata. Bind" в теле запроса с "Standard" на TemplateIDs выше.</span><span class="sxs-lookup"><span data-stu-id="650bc-161">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="650bc-162">Дополнительные сведения о развертывании шаблонов групп можно найти в статье Microsoft Graph о том, как [создавать группы](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="650bc-162">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="650bc-163">Каналы в шаблоне будут автоматически созданы на вкладке "Общие".</span><span class="sxs-lookup"><span data-stu-id="650bc-163">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="650bc-164">Пример: сценарий расширения шаблона "магазин"</span><span class="sxs-lookup"><span data-stu-id="650bc-164">Example: Store template extension script</span></span>

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
## <a name="relate-topic"></a><span data-ttu-id="650bc-165">Связывание темы</span><span class="sxs-lookup"><span data-stu-id="650bc-165">Relate topic</span></span>

[<span data-ttu-id="650bc-166">Начало работы с шаблонами групп в центре администрирования</span><span class="sxs-lookup"><span data-stu-id="650bc-166">Get started with Teams templates in the Admin center</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
