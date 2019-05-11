---
title: Создание новой или редактирование существующей политики версий клиентов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
ROBOTS: NOINDEX, NOFOLLOW
description: Вы может указать версию клиентов, поддерживаемых в вашей среде. При взаимодействии двух клиентов с разными версиями возможности, доступные обоим клиентам, могут быть ограничены возможностями другого клиента.
ms.openlocfilehash: 298610084be12606eedf09331ad39beea8add9ae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891910"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="5f670-104">Политика версии клиента: создание новой или редактирование существующей</span><span class="sxs-lookup"><span data-stu-id="5f670-104">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="5f670-105">Вы может указать версию клиентов, поддерживаемых в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="5f670-105">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="5f670-106">При взаимодействии двух клиентов с разными версиями возможности, доступные обоим клиентам, могут быть ограничены возможностями другого клиента.</span><span class="sxs-lookup"><span data-stu-id="5f670-106">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="5f670-107">Важнейшим использования компонентов, содержащихся в Скайп для Business Server и улучшить работу пользователей в целом, можно использовать фильтр версий клиентов для ограничения версий клиентов, которые используются в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="5f670-107">To make the greatest use of features included in Skype for Business Server and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="5f670-108">Используя этот фильтр, вы также можете сократить расходы, связанные с поддержкой нескольких версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="5f670-108">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f670-p103">Фильтры перечислены в списке в порядке приоритета. Например, если есть фильтр, который разрешает подключение клиентов с версией 1.5, за которым следует фильтр, блокирующий клиенты, версии которых предшествуют 2.0, преимуществом будет пользоваться первый фильтр, поэтому клиентам версии 1.5 будет разрешено выполнять подключение.</span><span class="sxs-lookup"><span data-stu-id="5f670-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="5f670-111">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="5f670-111">Tasks you can perform</span></span>

<span data-ttu-id="5f670-112">На странице **Создание новой политики версий клиента** или **Изменение политики версий клиента** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="5f670-112">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="5f670-113">добавить или изменить имя или описание политики версий клиентов;</span><span class="sxs-lookup"><span data-stu-id="5f670-113">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="5f670-114">добавить или изменить правила версий клиентов для политики версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="5f670-114">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="5f670-115">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="5f670-115">UI Reference</span></span>

<span data-ttu-id="5f670-116">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="5f670-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="5f670-117">**Область** Определяет область (узел, пул или пользователей) политики версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="5f670-117">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="5f670-118">**Имя** Вы можете добавить или изменить имя политики версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="5f670-118">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="5f670-119">**Описание** Можно добавить описание, помогающее идентифицировать политику в списке на странице политика версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="5f670-119">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="5f670-120">**Новые** Можно добавить новое правило версий клиентов в политике.</span><span class="sxs-lookup"><span data-stu-id="5f670-120">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="5f670-121">**Показать подробности** Этот параметр открывает диалоговое окно, в котором можно изменить параметры для правила версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="5f670-121">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="5f670-122">**Удаление** Этот параметр удаляет правило версий выбранного клиентов из политики.</span><span class="sxs-lookup"><span data-stu-id="5f670-122">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="5f670-123">**Стрелки вверх и вниз** Этот параметр перемещает правило версий клиентов выбранного вверх или вниз в приоритет.</span><span class="sxs-lookup"><span data-stu-id="5f670-123">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="5f670-124">Правила обрабатываются в указанном порядке.</span><span class="sxs-lookup"><span data-stu-id="5f670-124">Rules are processed in the order listed.</span></span>

<span data-ttu-id="5f670-125">Для получения дополнительных сведений о взаимодействии между клиентами и версий клиентов видеть [Взаимодействие с клиентом](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx).</span><span class="sxs-lookup"><span data-stu-id="5f670-125">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx).</span></span> <span data-ttu-id="5f670-126">Дополнительные сведения о работе с политиками версий клиентов см. в разделе [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="5f670-126">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

