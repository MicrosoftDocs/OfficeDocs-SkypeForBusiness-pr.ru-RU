---
title: Политика версий клиентов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
description: Вы может указать версию клиентов, поддерживаемых в вашей среде. При взаимодействии двух клиентов с разными версиями возможности, доступные обоим клиентам, могут быть ограничены возможностями другого клиента. Важнейшим использования компонентов, содержащихся в Скайп для Business Server 2015 и улучшить работу пользователей в целом, можно использовать фильтр версий клиентов для ограничения версий клиентов, которые используются в вашей среде. Используя этот фильтр, вы также можете сократить расходы, связанные с поддержкой нескольких версий клиентов.
ms.openlocfilehash: 6398c833609f799935148a4dab39810d46f178eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33887246"
---
# <a name="client-version-policy"></a><span data-ttu-id="770e9-106">Политика версий клиентов</span><span class="sxs-lookup"><span data-stu-id="770e9-106">Client Version Policy</span></span>

<span data-ttu-id="770e9-107">Вы может указать версию клиентов, поддерживаемых в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="770e9-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="770e9-108">При взаимодействии двух клиентов с разными версиями возможности, доступные обоим клиентам, могут быть ограничены возможностями другого клиента.</span><span class="sxs-lookup"><span data-stu-id="770e9-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="770e9-109">Важнейшим использования компонентов, содержащихся в Скайп для Business Server 2015 и улучшить работу пользователей в целом, можно использовать фильтр версий клиентов для ограничения версий клиентов, которые используются в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="770e9-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="770e9-110">Используя этот фильтр, вы также можете сократить расходы, связанные с поддержкой нескольких версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="770e9-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="770e9-111">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="770e9-111">Tasks you can perform</span></span>

<span data-ttu-id="770e9-112">На странице **Политика версий клиента** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="770e9-112">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="770e9-113">Изменение политики версий клиентов по умолчанию ( **Глобальная**).</span><span class="sxs-lookup"><span data-stu-id="770e9-113">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="770e9-114">создать политики версий клиентов для конкретного сайта или пула;</span><span class="sxs-lookup"><span data-stu-id="770e9-114">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="770e9-115">создать политики версий клиентов, которые можно назначить отдельным пользователям.</span><span class="sxs-lookup"><span data-stu-id="770e9-115">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="770e9-116">Поскольку анонимные пользователи не связаны с пользователями, сайтами или службами, к ним могут применяться только политики глобального уровня.</span><span class="sxs-lookup"><span data-stu-id="770e9-116">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="770e9-117">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="770e9-117">UI Reference</span></span>

<span data-ttu-id="770e9-118">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="770e9-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="770e9-119">**Новые** Можно создать одно или несколько из них следующие политики версий клиентов:</span><span class="sxs-lookup"><span data-stu-id="770e9-119">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="770e9-120">Политика сайта</span><span class="sxs-lookup"><span data-stu-id="770e9-120">Site policy</span></span>

  - <span data-ttu-id="770e9-121">Политика пула</span><span class="sxs-lookup"><span data-stu-id="770e9-121">Pool policy</span></span>

  - <span data-ttu-id="770e9-122">Политика пользователя</span><span class="sxs-lookup"><span data-stu-id="770e9-122">User policy</span></span>

- <span data-ttu-id="770e9-123">**Изменение** Можно изменить параметры любого из политики версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="770e9-123">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="770e9-124">С помощью этого параметра можно выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="770e9-124">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="770e9-125">**Показать подробности** Этот параметр открывает диалоговое окно, в котором можно изменить параметры для политики версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="770e9-125">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="770e9-126">**Выделить все** Этот параметр выбирает все политики версий клиентов в списке.</span><span class="sxs-lookup"><span data-stu-id="770e9-126">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="770e9-127">**Удаление** Этот параметр удаляет все политики версий выбранного клиента.</span><span class="sxs-lookup"><span data-stu-id="770e9-127">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="770e9-128">**Обновление** Можно обновить списке политика версий клиентов, чтобы проверить состояние параметров всех политик версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="770e9-128">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="770e9-p104">Дополнительные сведения о взаимодействии клиентов и версиях клиентов см. в разделе[Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) в документации по планированию. Дополнительные сведения о работе с политиками версий клиентов см. в разделе [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="770e9-p104">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

