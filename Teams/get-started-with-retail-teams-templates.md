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
description: Узнайте, как использовать шаблоны Teams, чтобы создавать структуры команд для розничной торговли путем предоставления готовых параметров, каналов и предварительно установленных приложений.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e0fecf419f6fc3ac0ef15097fe54571d85018587
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101205"
---
# <a name="get-started-with-teams-templates-in-retail"></a><span data-ttu-id="79cfb-103">Начало работы с шаблонами Teams для розничной торговли</span><span class="sxs-lookup"><span data-stu-id="79cfb-103">Get started with Teams templates in retail</span></span>

<span data-ttu-id="79cfb-104">Шаблоны Teams позволяют быстро и легко создавать команды, предоставляя готовый шаблон параметров, каналов и предварительно установленных приложений.</span><span class="sxs-lookup"><span data-stu-id="79cfb-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="79cfb-105">Шаблоны Teams содержат предварительно созданные определения структур команд, предназначенные для розничной торговли.</span><span class="sxs-lookup"><span data-stu-id="79cfb-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="79cfb-106">Вы можете использовать шаблоны Teams, чтобы быстро создавать команды, подходящие для розничной торговли, и развертывать их в организации.</span><span class="sxs-lookup"><span data-stu-id="79cfb-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="79cfb-107">Вы также можете расширить шаблоны Teams, чтобы создавать команды, адаптированные под конкретные потребности вашей организации.</span><span class="sxs-lookup"><span data-stu-id="79cfb-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="79cfb-108">В этой статье вы познакомитесь с каждым шаблоном Teams и рекомендуемыми способами их использования.</span><span class="sxs-lookup"><span data-stu-id="79cfb-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="79cfb-109">Эта статья предназначена для вас, если вы отвечаете за планирование, развертывание и управление несколькими командами в своей организации розничной торговли.</span><span class="sxs-lookup"><span data-stu-id="79cfb-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="79cfb-110">Вы уже развернули службу Teams в своей организации.</span><span class="sxs-lookup"><span data-stu-id="79cfb-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="79cfb-111">Если вы еще не развернули Teams, см. статью [Как развернуть Microsoft Teams](./deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="79cfb-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="79cfb-112">Другие общие сведения о шаблонах команд см. в статье [Начало работы с шаблонами Teams](get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="79cfb-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="store-template"></a><span data-ttu-id="79cfb-113">Шаблон магазина</span><span class="sxs-lookup"><span data-stu-id="79cfb-113">Store template</span></span>

<span data-ttu-id="79cfb-114">Шаблон магазина идеально подходит для создания команды, представляющей отдельно расположенный розничный магазин.</span><span class="sxs-lookup"><span data-stu-id="79cfb-114">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="79cfb-115">С помощью шаблона магазина можно создать команду для каждого расположения розничного магазина в организации.</span><span class="sxs-lookup"><span data-stu-id="79cfb-115">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="79cfb-116">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="79cfb-116">Base template type</span></span> | <span data-ttu-id="79cfb-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="79cfb-117">baseTemplateId</span></span> | <span data-ttu-id="79cfb-118">Свойства базового шаблона</span><span class="sxs-lookup"><span data-stu-id="79cfb-118">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="79cfb-119">Розничная торговля —</span><span class="sxs-lookup"><span data-stu-id="79cfb-119">Retail -</span></span> <br><span data-ttu-id="79cfb-120">Магазин</span><span class="sxs-lookup"><span data-stu-id="79cfb-120">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="79cfb-121">Каналы</span><span class="sxs-lookup"><span data-stu-id="79cfb-121">Channels</span></span> <ul><li><span data-ttu-id="79cfb-122">Передача смен\*</span><span class="sxs-lookup"><span data-stu-id="79cfb-122">Shifts handoff\*</span></span></li><li><span data-ttu-id="79cfb-123">Обучение\*</span><span class="sxs-lookup"><span data-stu-id="79cfb-123">Learning\*</span></span></li></ul><span data-ttu-id="79cfb-124">\*Автоматически добавленные в избранное каналы</span><span class="sxs-lookup"><span data-stu-id="79cfb-124">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="79cfb-125">Свойства команды</span><span class="sxs-lookup"><span data-stu-id="79cfb-125">Team properties</span></span> <ul><li><span data-ttu-id="79cfb-126">Установлен параметр видимости команды "Общедоступная"</span><span class="sxs-lookup"><span data-stu-id="79cfb-126">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="79cfb-127">Разрешения для участников</span><span class="sxs-lookup"><span data-stu-id="79cfb-127">Member permissions</span></span> <ul><li><span data-ttu-id="79cfb-128">Не может создавать, обновлять и удалять каналы</span><span class="sxs-lookup"><span data-stu-id="79cfb-128">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="79cfb-129">Не может добавлять и удалять приложения</span><span class="sxs-lookup"><span data-stu-id="79cfb-129">Can't add/remove apps</span></span> </li><li><span data-ttu-id="79cfb-130">Не может создавать, обновлять и удалять вкладки</span><span class="sxs-lookup"><span data-stu-id="79cfb-130">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="79cfb-131">Не может создавать, обновлять и удалять соединители</span><span class="sxs-lookup"><span data-stu-id="79cfb-131">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="79cfb-132">Рекомендуемые способы настройки шаблона магазина для организации:</span><span class="sxs-lookup"><span data-stu-id="79cfb-132">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="79cfb-133">Если в вашей организации есть отделы в каждом магазине, добавьте канал для каждого отдела.</span><span class="sxs-lookup"><span data-stu-id="79cfb-133">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="79cfb-134">Добавление канала упрощает взаимодействие и совместную работу в отделе.</span><span class="sxs-lookup"><span data-stu-id="79cfb-134">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="79cfb-135">Если в вашей организации есть внутренние веб-сайты (например, сайт SharePoint), рассмотрите возможность закрепления их в качестве вкладок в соответствующем канале команды.</span><span class="sxs-lookup"><span data-stu-id="79cfb-135">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="79cfb-136">Инструкции см. в статье [Начало работы с шаблонами Teams](get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="79cfb-136">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="manager-collaboration-template"></a><span data-ttu-id="79cfb-137">Шаблон взаимодействия руководителей</span><span class="sxs-lookup"><span data-stu-id="79cfb-137">Manager Collaboration template</span></span>

<span data-ttu-id="79cfb-138">Шаблон взаимодействия руководителей — это еще один из шаблонов Teams, предназначенных для розничной торговли.</span><span class="sxs-lookup"><span data-stu-id="79cfb-138">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="79cfb-139">Шаблон взаимодействия руководителей идеально подходит, чтобы создать команду для группы руководителей с целью совместной работы в магазинах, регионах и т. д.</span><span class="sxs-lookup"><span data-stu-id="79cfb-139">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="79cfb-140">Например, если в вашей организации есть регионы, вы можете создать команду взаимодействия руководителей для Московской области и включить в нее всех руководителей магазинов в этом регионе, а также регионального руководителя.</span><span class="sxs-lookup"><span data-stu-id="79cfb-140">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="79cfb-141">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="79cfb-141">Base template type</span></span> | <span data-ttu-id="79cfb-142">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="79cfb-142">baseTemplateId</span></span> | <span data-ttu-id="79cfb-143">Свойства базового шаблона</span><span class="sxs-lookup"><span data-stu-id="79cfb-143">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="79cfb-144">Розничная торговля —</span><span class="sxs-lookup"><span data-stu-id="79cfb-144">Retail -</span></span> <br><span data-ttu-id="79cfb-145">Магазин</span><span class="sxs-lookup"><span data-stu-id="79cfb-145">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="79cfb-146">Каналы</span><span class="sxs-lookup"><span data-stu-id="79cfb-146">Channels</span></span> <ul><li><span data-ttu-id="79cfb-147">Операции\*</span><span class="sxs-lookup"><span data-stu-id="79cfb-147">Operations\*</span></span></li><li><span data-ttu-id="79cfb-148">Обучение\*</span><span class="sxs-lookup"><span data-stu-id="79cfb-148">Learning\*</span></span></li></ul><span data-ttu-id="79cfb-149">\*Автоматически добавленные в избранное каналы</span><span class="sxs-lookup"><span data-stu-id="79cfb-149">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="79cfb-150">Свойства команды</span><span class="sxs-lookup"><span data-stu-id="79cfb-150">Team properties</span></span> <ul><li><span data-ttu-id="79cfb-151">Установлен параметр видимости команды "Закрытая"</span><span class="sxs-lookup"><span data-stu-id="79cfb-151">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="79cfb-152">Разрешения для участников</span><span class="sxs-lookup"><span data-stu-id="79cfb-152">Member permissions</span></span> <ul><li><span data-ttu-id="79cfb-153">Может создавать, обновлять и удалять каналы</span><span class="sxs-lookup"><span data-stu-id="79cfb-153">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="79cfb-154">Может добавлять и удалять приложения</span><span class="sxs-lookup"><span data-stu-id="79cfb-154">Can add/remove apps</span></span> </li><li><span data-ttu-id="79cfb-155">Может создавать, обновлять и удалять вкладки</span><span class="sxs-lookup"><span data-stu-id="79cfb-155">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="79cfb-156">Может создавать, обновлять и удалять соединители</span><span class="sxs-lookup"><span data-stu-id="79cfb-156">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="79cfb-157">Рекомендуемые способы настройки шаблона взаимодействия руководителей для организации:</span><span class="sxs-lookup"><span data-stu-id="79cfb-157">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="79cfb-158">Если в вашей организации есть внутренние веб-сайты (например, сайт SharePoint), важные для руководителей, рассмотрите возможность закрепления их в качестве вкладок в соответствующем канале команды.</span><span class="sxs-lookup"><span data-stu-id="79cfb-158">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="79cfb-159">Инструкции см. в [документации по Microsoft Teams](get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="79cfb-159">You can take a look at the [Microsoft Teams Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="79cfb-160">Использование собственных шаблонов</span><span class="sxs-lookup"><span data-stu-id="79cfb-160">How to use first party templates</span></span>

<span data-ttu-id="79cfb-161">Чтобы использовать эти шаблоны, измените свойство template@odata.bind в тексте запроса со standard на TemplateID, указанные выше.</span><span class="sxs-lookup"><span data-stu-id="79cfb-161">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="79cfb-162">Дополнительные сведения о развертывании шаблонов Teams см. в статье Microsoft Graph о том, как [создать команду](/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="79cfb-162">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="79cfb-163">Каналы в шаблоне будут автоматически созданы на вкладке "Общий".</span><span class="sxs-lookup"><span data-stu-id="79cfb-163">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="79cfb-164">Пример: сценарий расширения шаблона магазина</span><span class="sxs-lookup"><span data-stu-id="79cfb-164">Example: Store template extension script</span></span>

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
## <a name="relate-topic"></a><span data-ttu-id="79cfb-165">Связанная статья</span><span class="sxs-lookup"><span data-stu-id="79cfb-165">Relate topic</span></span>

[<span data-ttu-id="79cfb-166">Начало работы с шаблонами Teams в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="79cfb-166">Get started with Teams templates in the Admin center</span></span>](get-started-with-teams-templates-in-the-admin-console.md)