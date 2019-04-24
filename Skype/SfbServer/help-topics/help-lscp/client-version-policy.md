---
title: Политика версий клиентов
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
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
ms.openlocfilehash: 823879e254de95fa6150ec3b07b52f0462c6ece8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200907"
---
# <a name="client-version-policy"></a><span data-ttu-id="2a425-106">Политика версий клиентов</span><span class="sxs-lookup"><span data-stu-id="2a425-106">Client Version Policy</span></span>

<span data-ttu-id="2a425-107">Вы может указать версию клиентов, поддерживаемых в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="2a425-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="2a425-108">При взаимодействии двух клиентов с разными версиями возможности, доступные обоим клиентам, могут быть ограничены возможностями другого клиента.</span><span class="sxs-lookup"><span data-stu-id="2a425-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="2a425-109">Важнейшим использования компонентов, содержащихся в Скайп для Business Server 2015 и улучшить работу пользователей в целом, можно использовать фильтр версий клиентов для ограничения версий клиентов, которые используются в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="2a425-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="2a425-110">Используя этот фильтр, вы также можете сократить расходы, связанные с поддержкой нескольких версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="2a425-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="2a425-111">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="2a425-111">Tasks you can perform</span></span>

<span data-ttu-id="2a425-112">На странице **Политика версий клиента** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="2a425-112">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="2a425-113">Изменение политики версий клиентов по умолчанию ( **Глобальная**).</span><span class="sxs-lookup"><span data-stu-id="2a425-113">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="2a425-114">создать политики версий клиентов для конкретного сайта или пула;</span><span class="sxs-lookup"><span data-stu-id="2a425-114">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="2a425-115">создать политики версий клиентов, которые можно назначить отдельным пользователям.</span><span class="sxs-lookup"><span data-stu-id="2a425-115">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="2a425-116">Поскольку анонимные пользователи не связаны с пользователями, сайтами или службами, к ним могут применяться только политики глобального уровня.</span><span class="sxs-lookup"><span data-stu-id="2a425-116">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="2a425-117">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="2a425-117">UI Reference</span></span>

<span data-ttu-id="2a425-118">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="2a425-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="2a425-119">**Новые** Можно создать одно или несколько из них следующие политики версий клиентов:</span><span class="sxs-lookup"><span data-stu-id="2a425-119">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="2a425-120">Политика сайта</span><span class="sxs-lookup"><span data-stu-id="2a425-120">Site policy</span></span>

  - <span data-ttu-id="2a425-121">Политика пула</span><span class="sxs-lookup"><span data-stu-id="2a425-121">Pool policy</span></span>

  - <span data-ttu-id="2a425-122">Политика пользователя</span><span class="sxs-lookup"><span data-stu-id="2a425-122">User policy</span></span>

- <span data-ttu-id="2a425-123">**Изменение** Можно изменить параметры любого из политики версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="2a425-123">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="2a425-124">С помощью этого параметра можно выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="2a425-124">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="2a425-125">**Показать подробности** Этот параметр открывает диалоговое окно, в котором можно изменить параметры для политики версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="2a425-125">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="2a425-126">**Выделить все** Этот параметр выбирает все политики версий клиентов в списке.</span><span class="sxs-lookup"><span data-stu-id="2a425-126">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="2a425-127">**Удаление** Этот параметр удаляет все политики версий выбранного клиента.</span><span class="sxs-lookup"><span data-stu-id="2a425-127">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="2a425-128">**Обновление** Можно обновить списке политика версий клиентов, чтобы проверить состояние параметров всех политик версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="2a425-128">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="2a425-p104">Дополнительные сведения о взаимодействии клиентов и версиях клиентов см. в разделе[Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) в документации по планированию. Дополнительные сведения о работе с политиками версий клиентов см. в разделе [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="2a425-p104">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

