---
title: 'Политика версий клиентов: создание новой или редактирование существующей'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
ROBOTS: NOINDEX, NOFOLLOW
description: Вы может указать версию клиентов, поддерживаемых в вашей среде. При взаимодействии двух клиентов с разными версиями возможности, доступные обоим клиентам, могут быть ограничены возможностями другого клиента.
ms.openlocfilehash: c2d6dc4f68a7c40668db9042d420f2f341e35ca0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824899"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="ca01b-104">Политика версий клиентов: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="ca01b-104">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="ca01b-105">Вы может указать версию клиентов, поддерживаемых в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="ca01b-105">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="ca01b-106">При взаимодействии двух клиентов с разными версиями возможности, доступные обоим клиентам, могут быть ограничены возможностями другого клиента.</span><span class="sxs-lookup"><span data-stu-id="ca01b-106">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="ca01b-107">Чтобы максимально использовать функции, включенные в Skype для бизнеса Server, и улучшить общий пользовательский интерфейс, можно использовать фильтр версий клиентов, чтобы ограничить версии клиентов, используемые в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="ca01b-107">To make the greatest use of features included in Skype for Business Server and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="ca01b-108">Используя этот фильтр, вы также можете сократить расходы, связанные с поддержкой нескольких версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="ca01b-108">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ca01b-p103">Фильтры указаны в порядке приоритета. Например, если вы используете фильтр, который разрешает клиента использовать для подключения версию 1.5, за которым идет фильтр, блокирующий клиенты с версией ниже 2.0, первый фильтр имеет более высокий приоритет, поэтому клиентам с версией 1.5 разрешено осуществлять подключение.</span><span class="sxs-lookup"><span data-stu-id="ca01b-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="ca01b-111">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="ca01b-111">Tasks you can perform</span></span>

<span data-ttu-id="ca01b-112">На странице **Создание новой политики версий клиента** или **Изменение политики версий клиента** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="ca01b-112">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="ca01b-113">добавить или изменить имя или описание политики версий клиентов;</span><span class="sxs-lookup"><span data-stu-id="ca01b-113">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="ca01b-114">добавить или изменить правила версий клиентов для политики версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="ca01b-114">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="ca01b-115">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="ca01b-115">UI Reference</span></span>

<span data-ttu-id="ca01b-116">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="ca01b-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="ca01b-117">**Область действия** Определяет область (сайт, пул или пользователь) политики версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="ca01b-117">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="ca01b-118">**Имя** Можно добавить или изменить имя политики версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="ca01b-118">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="ca01b-119">**Описание** Вы можете добавить описание, чтобы определить политику в списке на странице "Политика версий клиентов".</span><span class="sxs-lookup"><span data-stu-id="ca01b-119">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="ca01b-120">**Новый** В политику можно добавить новое правило версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="ca01b-120">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="ca01b-121">**Показать подробности** Этот параметр открывает диалоговое окно, в котором можно изменить параметры правила версии клиента.</span><span class="sxs-lookup"><span data-stu-id="ca01b-121">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="ca01b-122">**Удаление** Этот параметр удаляет выбранное правило версий клиентов из политики.</span><span class="sxs-lookup"><span data-stu-id="ca01b-122">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="ca01b-123">**Стрелки вверх и вниз** Этот параметр перемещает выбранное правило версий клиентов вверх или вниз по приоритету.</span><span class="sxs-lookup"><span data-stu-id="ca01b-123">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="ca01b-124">Правила обрабатываются в порядке, который указан в списке.</span><span class="sxs-lookup"><span data-stu-id="ca01b-124">Rules are processed in the order listed.</span></span>

<span data-ttu-id="ca01b-125">Подробные сведения о взаимосвязи между клиентами и версиями клиентов см. в этой [теме.](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)</span><span class="sxs-lookup"><span data-stu-id="ca01b-125">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx).</span></span> <span data-ttu-id="ca01b-126">Дополнительные сведения о работе с политиками версий клиентов см. в разделе [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) в документации по применению.</span><span class="sxs-lookup"><span data-stu-id="ca01b-126">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

