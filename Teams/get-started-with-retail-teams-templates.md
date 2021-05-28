---
title: Начало работы с шаблоном команды в розничной сети
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
description: Узнайте, как с помощью шаблонов команд создавать структуры команд, разработанные для потребностей розничного продавца, предоставляя предварительно заранее задав параметры, каналы и приложения.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: edc3b646af4577199b13a5803837625b8a9ea354
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684557"
---
# <a name="create-a-team-using-retail-team-templates"></a><span data-ttu-id="555ec-103">Создание команды с использованием шаблонов розничных команд</span><span class="sxs-lookup"><span data-stu-id="555ec-103">Create a team using retail team templates</span></span>

<span data-ttu-id="555ec-104">Шаблоны команд Майкрософт позволяют быстро и легко создавать команды, предоставляя предопределяющий шаблон параметров, каналов и предварительно установленных приложений.</span><span class="sxs-lookup"><span data-stu-id="555ec-104">Microsoft team templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="555ec-105">Шаблоны команд имеют встроенные определения структур группы, разработанные для потребностей розничного продавца.</span><span class="sxs-lookup"><span data-stu-id="555ec-105">Team templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="555ec-106">Шаблоны групп можно использовать для быстрого создания типов команд, которые хорошо работают для розничных продавцов, и их развертывания в организации.</span><span class="sxs-lookup"><span data-stu-id="555ec-106">You can use team templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="555ec-107">Вы также можете расширить шаблоны команд для создания команд, специально разработанных для ваших организационных потребностей.</span><span class="sxs-lookup"><span data-stu-id="555ec-107">You can also extend the team templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="555ec-108">В этой статье мы познакомимся с каждым шаблоном команды и посоветуем использовать их.</span><span class="sxs-lookup"><span data-stu-id="555ec-108">In this article, we'll introduce each of the team templates and recommend how to use them.</span></span>

<span data-ttu-id="555ec-109">Эта статья предназначена для вас, если вы отвечаете за планирование, развертывание и управление несколькими командами в своей организации розничной торговли.</span><span class="sxs-lookup"><span data-stu-id="555ec-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="555ec-110">Вы уже развернули службу Teams в своей организации.</span><span class="sxs-lookup"><span data-stu-id="555ec-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="555ec-111">Если вы еще не развернули Teams, см. статью [Как развернуть Microsoft Teams](./deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="555ec-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="555ec-112">Дополнительные информацию о шаблонах команд в целом можно найти в этой ссылке: Начало [работы с шаблонами команд.](get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="555ec-112">To learn more about team templates in general, refer to [Get started with team templates](get-started-with-teams-templates.md).</span></span>

| <span data-ttu-id="555ec-113">Кто</span><span class="sxs-lookup"><span data-stu-id="555ec-113">Who</span></span> | <span data-ttu-id="555ec-114">Используемый метод:</span><span class="sxs-lookup"><span data-stu-id="555ec-114">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="555ec-115">Администраторы и ИТ-специалисты</span><span class="sxs-lookup"><span data-stu-id="555ec-115">Admins and IT Professionals</span></span> | <span data-ttu-id="555ec-116">[Используйте центр Teams для](#use-the-team-templates-in-the-teams-admin-center) создания команд на основе шаблонов розничных команд.</span><span class="sxs-lookup"><span data-stu-id="555ec-116">[Use the Teams admin center](#use-the-team-templates-in-the-teams-admin-center) to create teams based on the retail team templates.</span></span>|
| <span data-ttu-id="555ec-117">Разработчики и системные интеграторы</span><span class="sxs-lookup"><span data-stu-id="555ec-117">Developers and systems integrators</span></span> | <span data-ttu-id="555ec-118">[Используйте microsoft Graph](#use-the-team-templates-with-the-microsoft-graph) для создания команд на основе шаблонов розничных групп.</span><span class="sxs-lookup"><span data-stu-id="555ec-118">[Use the Microsoft Graph](#use-the-team-templates-with-the-microsoft-graph) to create teams based on the retail team templates.</span></span> |

## <a name="use-the-team-templates-in-the-teams-admin-center"></a><span data-ttu-id="555ec-119">Использование шаблонов групп в Центре Teams администрирования</span><span class="sxs-lookup"><span data-stu-id="555ec-119">Use the team templates in the Teams admin center</span></span>

### <a name="organize-a-store"></a><span data-ttu-id="555ec-120">Организация магазина</span><span class="sxs-lookup"><span data-stu-id="555ec-120">Organize a store</span></span>

<span data-ttu-id="555ec-121">Объедините своих сотрудников розничной торговли в едином интерфейсе для управления задачами, обмена документами и решения проблем клиентов.</span><span class="sxs-lookup"><span data-stu-id="555ec-121">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="555ec-122">Интегрируйте дополнительные приложения для упрощения начала и завершения смен.</span><span class="sxs-lookup"><span data-stu-id="555ec-122">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="555ec-123">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="555ec-123">Base template type</span></span> |<span data-ttu-id="555ec-124">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="555ec-124">baseTemplateId</span></span> | <span data-ttu-id="555ec-125">Свойства базового шаблона</span><span class="sxs-lookup"><span data-stu-id="555ec-125">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="555ec-126">Организация магазина</span><span class="sxs-lookup"><span data-stu-id="555ec-126">Organize a store</span></span>|`retailStore`|<span data-ttu-id="555ec-127">Каналы:</span><span class="sxs-lookup"><span data-stu-id="555ec-127">Channels:</span></span> <ul><li><span data-ttu-id="555ec-128">Общий</span><span class="sxs-lookup"><span data-stu-id="555ec-128">General</span></span><li><span data-ttu-id="555ec-129">Передача смены</span><span class="sxs-lookup"><span data-stu-id="555ec-129">Shift handoff</span></span></li><li><span data-ttu-id="555ec-130">Обучение</span><span class="sxs-lookup"><span data-stu-id="555ec-130">Learning</span></span></li></ul> <span data-ttu-id="555ec-131">Приложения:</span><span class="sxs-lookup"><span data-stu-id="555ec-131">Apps:</span></span> <ul><li><span data-ttu-id="555ec-132">Вики</span><span class="sxs-lookup"><span data-stu-id="555ec-132">Wiki</span></span></li></ul>|
||||

### <a name="manager-collaboration"></a><span data-ttu-id="555ec-133">Взаимодействие руководителей</span><span class="sxs-lookup"><span data-stu-id="555ec-133">Manager Collaboration</span></span>

<span data-ttu-id="555ec-134">Шаблон Совместной работы руководителя идеально подходит для создания команды для группы руководителей для совместной работы в магазинах или регионах и т. д. Например, если в вашей организации есть регионы, вы можете создать команду для совместной работы руководителя для региона Новграда и включить в нее всех руководителей магазинов в этом регионе вместе с региональным руководителем.</span><span class="sxs-lookup"><span data-stu-id="555ec-134">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, along with the regional manager for that region.</span></span>

| <span data-ttu-id="555ec-135">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="555ec-135">Base template type</span></span>| <span data-ttu-id="555ec-136">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="555ec-136">baseTemplateId</span></span> | <span data-ttu-id="555ec-137">Свойства базового шаблона</span><span class="sxs-lookup"><span data-stu-id="555ec-137">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="555ec-138">Розничная торговля — взаимодействие руководителей</span><span class="sxs-lookup"><span data-stu-id="555ec-138">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="555ec-139">Каналы:</span><span class="sxs-lookup"><span data-stu-id="555ec-139">Channels:</span></span> <ul><li><span data-ttu-id="555ec-140">Общий</span><span class="sxs-lookup"><span data-stu-id="555ec-140">General</span></span><li><span data-ttu-id="555ec-141">Операции</span><span class="sxs-lookup"><span data-stu-id="555ec-141">Operations</span></span></li><li><span data-ttu-id="555ec-142">Обучение</span><span class="sxs-lookup"><span data-stu-id="555ec-142">Learning</span></span></li></ul> <span data-ttu-id="555ec-143">Приложения:</span><span class="sxs-lookup"><span data-stu-id="555ec-143">Apps:</span></span> <ul><li><span data-ttu-id="555ec-144">Вики</span><span class="sxs-lookup"><span data-stu-id="555ec-144">Wiki</span></span></li></ul>|
||||

## <a name="use-the-team-templates-with-the-microsoft-graph"></a><span data-ttu-id="555ec-145">Использование шаблонов команд в microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="555ec-145">Use the team templates with the Microsoft Graph</span></span>

### <a name="store-template"></a><span data-ttu-id="555ec-146">Шаблон магазина</span><span class="sxs-lookup"><span data-stu-id="555ec-146">Store template</span></span>

<span data-ttu-id="555ec-147">Шаблон магазина идеально подходит для создания команды, представляющей отдельно расположенный розничный магазин.</span><span class="sxs-lookup"><span data-stu-id="555ec-147">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="555ec-148">С помощью шаблона магазина можно создать команду для каждого расположения розничного магазина в организации.</span><span class="sxs-lookup"><span data-stu-id="555ec-148">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="555ec-149">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="555ec-149">Base template type</span></span> | <span data-ttu-id="555ec-150">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="555ec-150">baseTemplateId</span></span> | <span data-ttu-id="555ec-151">Свойства базового шаблона</span><span class="sxs-lookup"><span data-stu-id="555ec-151">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="555ec-152">Розничная торговля —</span><span class="sxs-lookup"><span data-stu-id="555ec-152">Retail -</span></span> <br><span data-ttu-id="555ec-153">Магазин</span><span class="sxs-lookup"><span data-stu-id="555ec-153">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="555ec-154">Каналы</span><span class="sxs-lookup"><span data-stu-id="555ec-154">Channels</span></span> <ul><li><span data-ttu-id="555ec-155">Передача смен\*</span><span class="sxs-lookup"><span data-stu-id="555ec-155">Shifts handoff\*</span></span></li><li><span data-ttu-id="555ec-156">Обучение\*</span><span class="sxs-lookup"><span data-stu-id="555ec-156">Learning\*</span></span></li></ul><span data-ttu-id="555ec-157">\*Автоматически добавленные в избранное каналы</span><span class="sxs-lookup"><span data-stu-id="555ec-157">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="555ec-158">Свойства команды</span><span class="sxs-lookup"><span data-stu-id="555ec-158">Team properties</span></span> <ul><li><span data-ttu-id="555ec-159">Установлен параметр видимости команды "Общедоступная"</span><span class="sxs-lookup"><span data-stu-id="555ec-159">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="555ec-160">Разрешения для участников</span><span class="sxs-lookup"><span data-stu-id="555ec-160">Member permissions</span></span> <ul><li><span data-ttu-id="555ec-161">Не может создавать, обновлять и удалять каналы</span><span class="sxs-lookup"><span data-stu-id="555ec-161">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="555ec-162">Не может добавлять и удалять приложения</span><span class="sxs-lookup"><span data-stu-id="555ec-162">Can't add/remove apps</span></span> </li><li><span data-ttu-id="555ec-163">Не может создавать, обновлять и удалять вкладки</span><span class="sxs-lookup"><span data-stu-id="555ec-163">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="555ec-164">Не может создавать, обновлять и удалять соединители</span><span class="sxs-lookup"><span data-stu-id="555ec-164">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="555ec-165">Рекомендуемые способы настройки шаблона магазина для организации:</span><span class="sxs-lookup"><span data-stu-id="555ec-165">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="555ec-166">Если в вашей организации есть отделы в каждом магазине, добавьте канал для каждого отдела.</span><span class="sxs-lookup"><span data-stu-id="555ec-166">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="555ec-167">Добавление канала упрощает взаимодействие и совместную работу в отделе.</span><span class="sxs-lookup"><span data-stu-id="555ec-167">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="555ec-168">Если в вашей организации есть внутренние веб-сайты (например, сайт SharePoint), рассмотрите возможность закрепления их в качестве вкладок в соответствующем канале команды.</span><span class="sxs-lookup"><span data-stu-id="555ec-168">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="555ec-169">Инструкции можно найти в этой ссылке: Начало работы с [шаблонами](get-started-with-teams-templates.md) команд.</span><span class="sxs-lookup"><span data-stu-id="555ec-169">Refer to [Get started with team templates](get-started-with-teams-templates.md) for instructions.</span></span>

### <a name="manager-collaboration-template"></a><span data-ttu-id="555ec-170">Шаблон взаимодействия руководителей</span><span class="sxs-lookup"><span data-stu-id="555ec-170">Manager Collaboration template</span></span>

<span data-ttu-id="555ec-171">Шаблон совместной работы руководителя — это еще один из шаблонов команд, разработанных для розничной торговли.</span><span class="sxs-lookup"><span data-stu-id="555ec-171">The Manager Collaboration template is another one of the team templates designed around retailer needs.</span></span> <span data-ttu-id="555ec-172">Шаблон взаимодействия руководителей идеально подходит, чтобы создать команду для группы руководителей с целью совместной работы в магазинах, регионах и т. д.</span><span class="sxs-lookup"><span data-stu-id="555ec-172">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="555ec-173">Например, если в вашей организации есть регионы, вы можете создать команду взаимодействия руководителей для Московской области и включить в нее всех руководителей магазинов в этом регионе, а также регионального руководителя.</span><span class="sxs-lookup"><span data-stu-id="555ec-173">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="555ec-174">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="555ec-174">Base template type</span></span> | <span data-ttu-id="555ec-175">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="555ec-175">baseTemplateId</span></span> | <span data-ttu-id="555ec-176">Свойства базового шаблона</span><span class="sxs-lookup"><span data-stu-id="555ec-176">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="555ec-177">Розничная торговля —</span><span class="sxs-lookup"><span data-stu-id="555ec-177">Retail -</span></span> <br><span data-ttu-id="555ec-178">Магазин</span><span class="sxs-lookup"><span data-stu-id="555ec-178">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="555ec-179">Каналы</span><span class="sxs-lookup"><span data-stu-id="555ec-179">Channels</span></span> <ul><li><span data-ttu-id="555ec-180">Операции\*</span><span class="sxs-lookup"><span data-stu-id="555ec-180">Operations\*</span></span></li><li><span data-ttu-id="555ec-181">Обучение\*</span><span class="sxs-lookup"><span data-stu-id="555ec-181">Learning\*</span></span></li></ul><span data-ttu-id="555ec-182">\*Автоматически добавленные в избранное каналы</span><span class="sxs-lookup"><span data-stu-id="555ec-182">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="555ec-183">Свойства команды</span><span class="sxs-lookup"><span data-stu-id="555ec-183">Team properties</span></span> <ul><li><span data-ttu-id="555ec-184">Установлен параметр видимости команды "Закрытая"</span><span class="sxs-lookup"><span data-stu-id="555ec-184">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="555ec-185">Разрешения для участников</span><span class="sxs-lookup"><span data-stu-id="555ec-185">Member permissions</span></span> <ul><li><span data-ttu-id="555ec-186">Может создавать, обновлять и удалять каналы</span><span class="sxs-lookup"><span data-stu-id="555ec-186">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="555ec-187">Может добавлять и удалять приложения</span><span class="sxs-lookup"><span data-stu-id="555ec-187">Can add/remove apps</span></span> </li><li><span data-ttu-id="555ec-188">Может создавать, обновлять и удалять вкладки</span><span class="sxs-lookup"><span data-stu-id="555ec-188">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="555ec-189">Может создавать, обновлять и удалять соединители</span><span class="sxs-lookup"><span data-stu-id="555ec-189">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="555ec-190">Рекомендуемые способы настройки шаблона взаимодействия руководителей для организации:</span><span class="sxs-lookup"><span data-stu-id="555ec-190">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="555ec-191">Если в вашей организации есть внутренние веб-сайты (например, сайт SharePoint), важные для руководителей, рассмотрите возможность закрепления их в качестве вкладок в соответствующем канале команды.</span><span class="sxs-lookup"><span data-stu-id="555ec-191">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="555ec-192">Инструкции можно найти [в](get-started-with-teams-templates.md) документации по шаблонам группы Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="555ec-192">You can take a look at the [Microsoft team Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="555ec-193">Использование собственных шаблонов</span><span class="sxs-lookup"><span data-stu-id="555ec-193">How to use first-party templates</span></span>

<span data-ttu-id="555ec-194">Чтобы использовать эти шаблоны, измените свойство template@odata.bind в тексте запроса со standard на TemplateID, указанные выше.</span><span class="sxs-lookup"><span data-stu-id="555ec-194">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="555ec-195">Дополнительные сведения о развертывании шаблонов группы см. в статье microsoft Graph о том, как [создать команду.](/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="555ec-195">For more information on how to deploy team templates, see the Microsoft Graph article on how to [create a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="555ec-196">Каналы в шаблоне будут автоматически созданы на вкладке "Общий".</span><span class="sxs-lookup"><span data-stu-id="555ec-196">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="555ec-197">Пример: сценарий расширения шаблона магазина</span><span class="sxs-lookup"><span data-stu-id="555ec-197">Example: Store template extension script</span></span>

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
