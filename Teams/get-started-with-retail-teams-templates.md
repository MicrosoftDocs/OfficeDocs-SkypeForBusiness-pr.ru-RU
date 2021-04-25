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
ms.openlocfilehash: 8d72f88bb33dca16254ec09a2ea89ac90a0e7aca
ms.sourcegitcommit: 900f28c4ac12d65ccbd996028205ba183b4afb03
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995147"
---
# <a name="create-a-team-using-teams-retail-templates"></a><span data-ttu-id="d3108-103">Создание команды с помощью розничных шаблонов Teams</span><span class="sxs-lookup"><span data-stu-id="d3108-103">Create a team using Teams retail templates</span></span>

<span data-ttu-id="d3108-104">С помощью шаблонов Microsoft Teams можно быстро и удобно создавать команды: готовые шаблоны содержат параметры, каналы и предустановленные приложения.</span><span class="sxs-lookup"><span data-stu-id="d3108-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="d3108-105">Шаблоны Teams содержат предварительно созданные определения структур команд, предназначенные для розничной торговли.</span><span class="sxs-lookup"><span data-stu-id="d3108-105">Teams templates have pre-built definitions of team structures designed around retailer needs.</span></span> <span data-ttu-id="d3108-106">Вы можете использовать шаблоны Teams, чтобы быстро создавать команды, подходящие для розничной торговли, и развертывать их в организации.</span><span class="sxs-lookup"><span data-stu-id="d3108-106">You can use Teams templates to quickly create the types of teams that work well for retailers and deploy them across your organization.</span></span> <span data-ttu-id="d3108-107">Вы также можете расширить шаблоны Teams, чтобы создавать команды, адаптированные под конкретные потребности вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d3108-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="d3108-108">В этой статье вы познакомитесь с каждым шаблоном Teams и рекомендуемыми способами их использования.</span><span class="sxs-lookup"><span data-stu-id="d3108-108">In this article, we'll introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="d3108-109">Эта статья предназначена для вас, если вы отвечаете за планирование, развертывание и управление несколькими командами в своей организации розничной торговли.</span><span class="sxs-lookup"><span data-stu-id="d3108-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your retail organization.</span></span> <span data-ttu-id="d3108-110">Вы уже развернули службу Teams в своей организации.</span><span class="sxs-lookup"><span data-stu-id="d3108-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="d3108-111">Если вы еще не развернули Teams, см. статью [Как развернуть Microsoft Teams](./deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d3108-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](./deploy-overview.md).</span></span>

<span data-ttu-id="d3108-112">Другие общие сведения о шаблонах команд см. в статье [Начало работы с шаблонами Teams](get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="d3108-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

| <span data-ttu-id="d3108-113">Кто</span><span class="sxs-lookup"><span data-stu-id="d3108-113">Who</span></span> | <span data-ttu-id="d3108-114">Используемый метод:</span><span class="sxs-lookup"><span data-stu-id="d3108-114">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="d3108-115">Администраторы и ИТ-специалисты</span><span class="sxs-lookup"><span data-stu-id="d3108-115">Admins and IT Professionals</span></span> | <span data-ttu-id="d3108-116">[Используйте Центр администрирования Teams для](#use-the-teams-templates-in-the-teams-admin-center) создания команд на основе шаблонов Teams в розничной сети.</span><span class="sxs-lookup"><span data-stu-id="d3108-116">[Use the Teams admin center](#use-the-teams-templates-in-the-teams-admin-center) to create teams based on the retail Teams templates.</span></span>|
| <span data-ttu-id="d3108-117">Разработчики и системные интеграторы</span><span class="sxs-lookup"><span data-stu-id="d3108-117">Developers and systems integrators</span></span> | <span data-ttu-id="d3108-118">[Используйте Microsoft Graph для](#use-the-teams-templates-with-the-microsoft-graph) создания команд на основе шаблонов Teams в розничной сети.</span><span class="sxs-lookup"><span data-stu-id="d3108-118">[Use the Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) to create teams based on the retail Teams templates.</span></span> |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a><span data-ttu-id="d3108-119">Использование шаблонов Teams в Центре администрирования Teams</span><span class="sxs-lookup"><span data-stu-id="d3108-119">Use the Teams templates in the Teams admin center</span></span>

### <a name="organize-a-store"></a><span data-ttu-id="d3108-120">Организация магазина</span><span class="sxs-lookup"><span data-stu-id="d3108-120">Organize a store</span></span>

<span data-ttu-id="d3108-121">Объедините своих сотрудников розничной торговли в едином интерфейсе для управления задачами, обмена документами и решения проблем клиентов.</span><span class="sxs-lookup"><span data-stu-id="d3108-121">Bring your retail employees together in one central experience to manage tasks, share documents and resolve customer issues.</span></span> <span data-ttu-id="d3108-122">Интегрируйте дополнительные приложения для упрощения начала и завершения смен.</span><span class="sxs-lookup"><span data-stu-id="d3108-122">Integrate additional applications to streamline shift start & end processes.</span></span>

| <span data-ttu-id="d3108-123">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="d3108-123">Base template type</span></span> |<span data-ttu-id="d3108-124">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="d3108-124">baseTemplateId</span></span> | <span data-ttu-id="d3108-125">Свойства базового шаблона</span><span class="sxs-lookup"><span data-stu-id="d3108-125">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="d3108-126">Организация магазина</span><span class="sxs-lookup"><span data-stu-id="d3108-126">Organize a store</span></span>|`retailStore`|<span data-ttu-id="d3108-127">Каналы:</span><span class="sxs-lookup"><span data-stu-id="d3108-127">Channels:</span></span> <ul><li><span data-ttu-id="d3108-128">Общий</span><span class="sxs-lookup"><span data-stu-id="d3108-128">General</span></span><li><span data-ttu-id="d3108-129">Передача смены</span><span class="sxs-lookup"><span data-stu-id="d3108-129">Shift handoff</span></span></li><li><span data-ttu-id="d3108-130">Обучение</span><span class="sxs-lookup"><span data-stu-id="d3108-130">Learning</span></span></li></ul> <span data-ttu-id="d3108-131">Приложения:</span><span class="sxs-lookup"><span data-stu-id="d3108-131">Apps:</span></span> <ul><li><span data-ttu-id="d3108-132">Вики</span><span class="sxs-lookup"><span data-stu-id="d3108-132">Wiki</span></span></li></ul>|
||||

### <a name="manager-collaboration"></a><span data-ttu-id="d3108-133">Взаимодействие руководителей</span><span class="sxs-lookup"><span data-stu-id="d3108-133">Manager Collaboration</span></span>

<span data-ttu-id="d3108-134">Шаблон Совместной работы руководителя идеально подходит для создания команды для группы руководителей для совместной работы в магазинах или регионах и т. д. Например, если в вашей организации есть регионы, вы можете создать команду для совместной работы руководителя для региона Новграда и включить в нее всех руководителей магазинов в этом регионе вместе с региональным руководителем.</span><span class="sxs-lookup"><span data-stu-id="d3108-134">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, etc. For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, along with the regional manager for that region.</span></span>

| <span data-ttu-id="d3108-135">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="d3108-135">Base template type</span></span>| <span data-ttu-id="d3108-136">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="d3108-136">baseTemplateId</span></span> | <span data-ttu-id="d3108-137">Свойства базового шаблона</span><span class="sxs-lookup"><span data-stu-id="d3108-137">Properties that come with this base template</span></span> |
| ------------------|- |----------------------------------------------------- |
|<span data-ttu-id="d3108-138">Розничная торговля — взаимодействие руководителей</span><span class="sxs-lookup"><span data-stu-id="d3108-138">Retail - manager collaboration</span></span>|`retailManagerCollaboration` |<span data-ttu-id="d3108-139">Каналы:</span><span class="sxs-lookup"><span data-stu-id="d3108-139">Channels:</span></span> <ul><li><span data-ttu-id="d3108-140">Общий</span><span class="sxs-lookup"><span data-stu-id="d3108-140">General</span></span><li><span data-ttu-id="d3108-141">Операции</span><span class="sxs-lookup"><span data-stu-id="d3108-141">Operations</span></span></li><li><span data-ttu-id="d3108-142">Обучение</span><span class="sxs-lookup"><span data-stu-id="d3108-142">Learning</span></span></li></ul> <span data-ttu-id="d3108-143">Приложения:</span><span class="sxs-lookup"><span data-stu-id="d3108-143">Apps:</span></span> <ul><li><span data-ttu-id="d3108-144">Вики</span><span class="sxs-lookup"><span data-stu-id="d3108-144">Wiki</span></span></li></ul>|
||||

## <a name="use-the-teams-templates-with-the-microsoft-graph"></a><span data-ttu-id="d3108-145">Использование шаблонов Teams с Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="d3108-145">Use the Teams templates with the Microsoft Graph</span></span>

### <a name="store-template"></a><span data-ttu-id="d3108-146">Шаблон магазина</span><span class="sxs-lookup"><span data-stu-id="d3108-146">Store template</span></span>

<span data-ttu-id="d3108-147">Шаблон магазина идеально подходит для создания команды, представляющей отдельно расположенный розничный магазин.</span><span class="sxs-lookup"><span data-stu-id="d3108-147">The Store template is ideal for creating a team to represent an individual retail store location.</span></span> <span data-ttu-id="d3108-148">С помощью шаблона магазина можно создать команду для каждого расположения розничного магазина в организации.</span><span class="sxs-lookup"><span data-stu-id="d3108-148">Using the Store template, you can create a team for each retail store location in your organization.</span></span>

| <span data-ttu-id="d3108-149">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="d3108-149">Base template type</span></span> | <span data-ttu-id="d3108-150">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="d3108-150">baseTemplateId</span></span> | <span data-ttu-id="d3108-151">Свойства базового шаблона</span><span class="sxs-lookup"><span data-stu-id="d3108-151">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="d3108-152">Розничная торговля —</span><span class="sxs-lookup"><span data-stu-id="d3108-152">Retail -</span></span> <br><span data-ttu-id="d3108-153">Магазин</span><span class="sxs-lookup"><span data-stu-id="d3108-153">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| <span data-ttu-id="d3108-154">Каналы</span><span class="sxs-lookup"><span data-stu-id="d3108-154">Channels</span></span> <ul><li><span data-ttu-id="d3108-155">Передача смен\*</span><span class="sxs-lookup"><span data-stu-id="d3108-155">Shifts handoff\*</span></span></li><li><span data-ttu-id="d3108-156">Обучение\*</span><span class="sxs-lookup"><span data-stu-id="d3108-156">Learning\*</span></span></li></ul><span data-ttu-id="d3108-157">\*Автоматически добавленные в избранное каналы</span><span class="sxs-lookup"><span data-stu-id="d3108-157">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="d3108-158">Свойства команды</span><span class="sxs-lookup"><span data-stu-id="d3108-158">Team properties</span></span> <ul><li><span data-ttu-id="d3108-159">Установлен параметр видимости команды "Общедоступная"</span><span class="sxs-lookup"><span data-stu-id="d3108-159">Team visibility set to Public</span></span></li></ul> <br><span data-ttu-id="d3108-160">Разрешения для участников</span><span class="sxs-lookup"><span data-stu-id="d3108-160">Member permissions</span></span> <ul><li><span data-ttu-id="d3108-161">Не может создавать, обновлять и удалять каналы</span><span class="sxs-lookup"><span data-stu-id="d3108-161">Can't create/update/delete channels</span></span> </li><li><span data-ttu-id="d3108-162">Не может добавлять и удалять приложения</span><span class="sxs-lookup"><span data-stu-id="d3108-162">Can't add/remove apps</span></span> </li><li><span data-ttu-id="d3108-163">Не может создавать, обновлять и удалять вкладки</span><span class="sxs-lookup"><span data-stu-id="d3108-163">Can't create/update/remove tabs</span></span></li><li><span data-ttu-id="d3108-164">Не может создавать, обновлять и удалять соединители</span><span class="sxs-lookup"><span data-stu-id="d3108-164">Can't create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="d3108-165">Рекомендуемые способы настройки шаблона магазина для организации:</span><span class="sxs-lookup"><span data-stu-id="d3108-165">Recommended ways to customize the Store template for your organization:</span></span>

- <span data-ttu-id="d3108-166">Если в вашей организации есть отделы в каждом магазине, добавьте канал для каждого отдела.</span><span class="sxs-lookup"><span data-stu-id="d3108-166">If your organization has departments within each store, add a channel for each department.</span></span> <span data-ttu-id="d3108-167">Добавление канала упрощает взаимодействие и совместную работу в отделе.</span><span class="sxs-lookup"><span data-stu-id="d3108-167">Adding a channel facilitates communication and collaboration within the department.</span></span>

- <span data-ttu-id="d3108-168">Если в вашей организации есть внутренние веб-сайты (например, сайт SharePoint), рассмотрите возможность закрепления их в качестве вкладок в соответствующем канале команды.</span><span class="sxs-lookup"><span data-stu-id="d3108-168">If your organization has any internal websites (for example, a SharePoint site), consider pinning them as tabs in the relevant team channel.</span></span> <span data-ttu-id="d3108-169">Инструкции см. в статье [Начало работы с шаблонами Teams](get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="d3108-169">Refer to [Get started with Teams templates](get-started-with-teams-templates.md) for instructions.</span></span>

### <a name="manager-collaboration-template"></a><span data-ttu-id="d3108-170">Шаблон взаимодействия руководителей</span><span class="sxs-lookup"><span data-stu-id="d3108-170">Manager Collaboration template</span></span>

<span data-ttu-id="d3108-171">Шаблон взаимодействия руководителей — это еще один из шаблонов Teams, предназначенных для розничной торговли.</span><span class="sxs-lookup"><span data-stu-id="d3108-171">The Manager Collaboration template is another one of the Teams templates designed around retailer needs.</span></span> <span data-ttu-id="d3108-172">Шаблон взаимодействия руководителей идеально подходит, чтобы создать команду для группы руководителей с целью совместной работы в магазинах, регионах и т. д.</span><span class="sxs-lookup"><span data-stu-id="d3108-172">The Manager Collaboration template is ideal for creating a team for a set of managers to collaborate across stores/regions, and more.</span></span> <span data-ttu-id="d3108-173">Например, если в вашей организации есть регионы, вы можете создать команду взаимодействия руководителей для Московской области и включить в нее всех руководителей магазинов в этом регионе, а также регионального руководителя.</span><span class="sxs-lookup"><span data-stu-id="d3108-173">For example, if your organization has regions, you might create a Manager Collaboration team for the California Region and include all the store managers in that region, as well as the regional manager for that region.</span></span>

| <span data-ttu-id="d3108-174">Тип базового шаблона</span><span class="sxs-lookup"><span data-stu-id="d3108-174">Base template type</span></span> | <span data-ttu-id="d3108-175">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="d3108-175">baseTemplateId</span></span> | <span data-ttu-id="d3108-176">Свойства базового шаблона</span><span class="sxs-lookup"><span data-stu-id="d3108-176">Properties that come with this base template</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="d3108-177">Розничная торговля —</span><span class="sxs-lookup"><span data-stu-id="d3108-177">Retail -</span></span> <br><span data-ttu-id="d3108-178">Магазин</span><span class="sxs-lookup"><span data-stu-id="d3108-178">Store</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| <span data-ttu-id="d3108-179">Каналы</span><span class="sxs-lookup"><span data-stu-id="d3108-179">Channels</span></span> <ul><li><span data-ttu-id="d3108-180">Операции\*</span><span class="sxs-lookup"><span data-stu-id="d3108-180">Operations\*</span></span></li><li><span data-ttu-id="d3108-181">Обучение\*</span><span class="sxs-lookup"><span data-stu-id="d3108-181">Learning\*</span></span></li></ul><span data-ttu-id="d3108-182">\*Автоматически добавленные в избранное каналы</span><span class="sxs-lookup"><span data-stu-id="d3108-182">\*Auto-favorited channels</span></span><br><br><span data-ttu-id="d3108-183">Свойства команды</span><span class="sxs-lookup"><span data-stu-id="d3108-183">Team properties</span></span> <ul><li><span data-ttu-id="d3108-184">Установлен параметр видимости команды "Закрытая"</span><span class="sxs-lookup"><span data-stu-id="d3108-184">Team visibility set to Private</span></span></li></ul> <br><span data-ttu-id="d3108-185">Разрешения для участников</span><span class="sxs-lookup"><span data-stu-id="d3108-185">Member permissions</span></span> <ul><li><span data-ttu-id="d3108-186">Может создавать, обновлять и удалять каналы</span><span class="sxs-lookup"><span data-stu-id="d3108-186">Can create/update/delete channels</span></span> </li><li><span data-ttu-id="d3108-187">Может добавлять и удалять приложения</span><span class="sxs-lookup"><span data-stu-id="d3108-187">Can add/remove apps</span></span> </li><li><span data-ttu-id="d3108-188">Может создавать, обновлять и удалять вкладки</span><span class="sxs-lookup"><span data-stu-id="d3108-188">Can create/update/remove tabs</span></span></li><li><span data-ttu-id="d3108-189">Может создавать, обновлять и удалять соединители</span><span class="sxs-lookup"><span data-stu-id="d3108-189">Can create/update/remove connectors</span></span></li><ul>|
||||

<span data-ttu-id="d3108-190">Рекомендуемые способы настройки шаблона взаимодействия руководителей для организации:</span><span class="sxs-lookup"><span data-stu-id="d3108-190">Recommended ways to customize the Manager Collaboration template for your organization:</span></span>

- <span data-ttu-id="d3108-191">Если в вашей организации есть внутренние веб-сайты (например, сайт SharePoint), важные для руководителей, рассмотрите возможность закрепления их в качестве вкладок в соответствующем канале команды.</span><span class="sxs-lookup"><span data-stu-id="d3108-191">If your organization has any internal websites, such as a SharePoint site, that are relevant for managers, consider pinning them as tabs in a relevant team channel.</span></span> <span data-ttu-id="d3108-192">Инструкции см. в [документации по Microsoft Teams](get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="d3108-192">You can take a look at the [Microsoft Teams Template documentation](get-started-with-teams-templates.md) for instructions.</span></span>

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="d3108-193">Использование собственных шаблонов</span><span class="sxs-lookup"><span data-stu-id="d3108-193">How to use first party templates</span></span>

<span data-ttu-id="d3108-194">Чтобы использовать эти шаблоны, измените свойство template@odata.bind в тексте запроса со standard на TemplateID, указанные выше.</span><span class="sxs-lookup"><span data-stu-id="d3108-194">To use these templates, change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="d3108-195">Дополнительные сведения о развертывании шаблонов Teams см. в статье Microsoft Graph о том, как [создать команду](/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="d3108-195">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="d3108-196">Каналы в шаблоне будут автоматически созданы на вкладке "Общий".</span><span class="sxs-lookup"><span data-stu-id="d3108-196">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-store-template-extension-script"></a><span data-ttu-id="d3108-197">Пример: сценарий расширения шаблона магазина</span><span class="sxs-lookup"><span data-stu-id="d3108-197">Example: Store template extension script</span></span>

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
