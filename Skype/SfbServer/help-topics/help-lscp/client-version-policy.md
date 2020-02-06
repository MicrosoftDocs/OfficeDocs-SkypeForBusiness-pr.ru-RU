---
title: Политика версий клиентов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
description: Вы может указать версию клиентов, поддерживаемых в вашей среде. При взаимодействии двух клиентов с разными версиями возможности, доступные обоим клиентам, могут быть ограничены возможностями другого клиента. Чтобы обеспечить максимально эффективное использование функций, включенных в Skype для бизнеса Server 2015, и улучшить общее взаимодействие с пользователем, вы можете использовать фильтр клиентской версии для ограничения версий клиентов, используемых в среде. Используя этот фильтр, вы также можете сократить расходы, связанные с поддержкой нескольких версий клиентов.
ms.openlocfilehash: ac43816dfe3b5afac44bf846f76f92dc80667930
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823072"
---
# <a name="client-version-policy"></a><span data-ttu-id="3733c-106">Политика версий клиентов</span><span class="sxs-lookup"><span data-stu-id="3733c-106">Client Version Policy</span></span>

<span data-ttu-id="3733c-107">Вы может указать версию клиентов, поддерживаемых в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="3733c-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="3733c-108">При взаимодействии двух клиентов с разными версиями возможности, доступные обоим клиентам, могут быть ограничены возможностями другого клиента.</span><span class="sxs-lookup"><span data-stu-id="3733c-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="3733c-109">Чтобы обеспечить максимально эффективное использование функций, включенных в Skype для бизнеса Server 2015, и улучшить общее взаимодействие с пользователем, вы можете использовать фильтр клиентской версии для ограничения версий клиентов, используемых в среде.</span><span class="sxs-lookup"><span data-stu-id="3733c-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="3733c-110">Используя этот фильтр, вы также можете сократить расходы, связанные с поддержкой нескольких версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="3733c-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="3733c-111">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="3733c-111">Tasks you can perform</span></span>

<span data-ttu-id="3733c-112">На странице **Политика версий клиента** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="3733c-112">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="3733c-113">Измените политику версии клиента по умолчанию ( **Global**).</span><span class="sxs-lookup"><span data-stu-id="3733c-113">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="3733c-114">создать политики версий клиентов для конкретного сайта или пула;</span><span class="sxs-lookup"><span data-stu-id="3733c-114">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="3733c-115">создать политики версий клиентов, которые можно назначить отдельным пользователям.</span><span class="sxs-lookup"><span data-stu-id="3733c-115">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="3733c-116">Поскольку анонимные пользователи не связаны с пользователями, сайтами или службами, к ним могут применяться только политики глобального уровня.</span><span class="sxs-lookup"><span data-stu-id="3733c-116">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="3733c-117">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="3733c-117">UI Reference</span></span>

<span data-ttu-id="3733c-118">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="3733c-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="3733c-119">**Новые** Вы можете создать одну или несколько из следующих политик версий клиента:</span><span class="sxs-lookup"><span data-stu-id="3733c-119">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="3733c-120">Политика сайта</span><span class="sxs-lookup"><span data-stu-id="3733c-120">Site policy</span></span>

  - <span data-ttu-id="3733c-121">Политика пула</span><span class="sxs-lookup"><span data-stu-id="3733c-121">Pool policy</span></span>

  - <span data-ttu-id="3733c-122">Политика пользователя</span><span class="sxs-lookup"><span data-stu-id="3733c-122">User policy</span></span>

- <span data-ttu-id="3733c-123">**Изменить** Вы можете изменить параметры любой из политик версии клиента.</span><span class="sxs-lookup"><span data-stu-id="3733c-123">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="3733c-124">С помощью этого параметра можно выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="3733c-124">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="3733c-125">**Показать подробности** Этот параметр открывает диалоговое окно, в котором можно изменить параметры политики версии клиента.</span><span class="sxs-lookup"><span data-stu-id="3733c-125">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="3733c-126">**Выделить все** Этот параметр выбирает все политики версии клиента в списке.</span><span class="sxs-lookup"><span data-stu-id="3733c-126">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="3733c-127">**Delete (удалить** ) Этот параметр удаляет все выбранные политики версии клиента.</span><span class="sxs-lookup"><span data-stu-id="3733c-127">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="3733c-128">**Обновить** Вы можете обновить список политики версии клиента, чтобы проверить состояние параметров всех политик версий клиента.</span><span class="sxs-lookup"><span data-stu-id="3733c-128">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="3733c-p104">Дополнительные сведения о взаимодействии клиентов и версиях клиентов см. в разделе[Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) в документации по планированию. Дополнительные сведения о работе с политиками версий клиентов см. в разделе [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="3733c-p104">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

