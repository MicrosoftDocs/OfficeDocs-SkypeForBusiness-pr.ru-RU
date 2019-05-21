---
title: Политика версии клиента создание новых и изменение существующих
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: Вы может указать версию клиентов, поддерживаемых в вашей среде. При взаимодействии двух клиентов с разными версиями возможности, доступные обоим клиентам, могут быть ограничены возможностями другого клиента. Чтобы обеспечить максимально эффективное использование функций, включенных в Skype для бизнеса Server 2015, и улучшить общее взаимодействие с пользователем, вы можете использовать фильтр клиентской версии для ограничения версий клиентов, используемых в среде. Используя этот фильтр, вы также можете сократить расходы, связанные с поддержкой нескольких версий клиентов.
ms.openlocfilehash: f89089f34086a36c3e652bf8527ba4db7d108a11
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300016"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="48b70-106">Политика версии клиента: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="48b70-106">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="48b70-107">Вы может указать версию клиентов, поддерживаемых в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="48b70-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="48b70-108">При взаимодействии двух клиентов с разными версиями возможности, доступные обоим клиентам, могут быть ограничены возможностями другого клиента.</span><span class="sxs-lookup"><span data-stu-id="48b70-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="48b70-109">Чтобы обеспечить максимально эффективное использование функций, включенных в Skype для бизнеса Server 2015, и улучшить общее взаимодействие с пользователем, вы можете использовать фильтр клиентской версии для ограничения версий клиентов, используемых в среде.</span><span class="sxs-lookup"><span data-stu-id="48b70-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="48b70-110">Используя этот фильтр, вы также можете сократить расходы, связанные с поддержкой нескольких версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="48b70-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="48b70-p103">Фильтры перечислены в списке в порядке приоритета. Например, если есть фильтр, который разрешает подключение клиентов с версией 1.5, за которым следует фильтр, блокирующий клиенты, версии которых предшествуют 2.0, преимуществом будет пользоваться первый фильтр, поэтому клиентам версии 1.5 будет разрешено выполнять подключение.</span><span class="sxs-lookup"><span data-stu-id="48b70-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="48b70-113">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="48b70-113">Tasks you can perform</span></span>

<span data-ttu-id="48b70-114">На странице **Создание новой политики версий клиента** или **Изменение политики версий клиента** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="48b70-114">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="48b70-115">добавить или изменить имя или описание политики версий клиентов;</span><span class="sxs-lookup"><span data-stu-id="48b70-115">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="48b70-116">добавить или изменить правила версий клиентов для политики версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="48b70-116">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="48b70-117">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="48b70-117">UI Reference</span></span>

<span data-ttu-id="48b70-118">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="48b70-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="48b70-119">**Область действия** Определяет область (сайт, пул или пользователя) политики версии клиента.</span><span class="sxs-lookup"><span data-stu-id="48b70-119">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="48b70-120">**Name (имя** ) Вы можете добавить или изменить имя политики версии клиента.</span><span class="sxs-lookup"><span data-stu-id="48b70-120">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="48b70-121">**Description (описание** ) Вы можете добавить описание, которое поможет идентифицировать политику в списке на странице "Политика клиентской версии".</span><span class="sxs-lookup"><span data-stu-id="48b70-121">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="48b70-122">**Новые** Вы можете добавить новое правило клиентской версии для политики.</span><span class="sxs-lookup"><span data-stu-id="48b70-122">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="48b70-123">**Показать подробности** Этот параметр открывает диалоговое окно, в котором можно изменить параметры правила клиентской версии.</span><span class="sxs-lookup"><span data-stu-id="48b70-123">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="48b70-124">**Удалить** Этот параметр удаляет выбранное правило клиентской версии из политики.</span><span class="sxs-lookup"><span data-stu-id="48b70-124">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="48b70-125">**Стрелки вверх и вниз** Этот параметр Перемещает выбранное правило клиентской версии вверх или вниз по приоритету.</span><span class="sxs-lookup"><span data-stu-id="48b70-125">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="48b70-126">Правила обрабатываются в указанном порядке.</span><span class="sxs-lookup"><span data-stu-id="48b70-126">Rules are processed in the order listed.</span></span>

<span data-ttu-id="48b70-p105">Дополнительные сведения о взаимодействии клиентов и версиях клиентов см. в разделе[Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) в документации по планированию. Дополнительные сведения о работе с политиками версий клиентов см. в разделе [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="48b70-p105">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

