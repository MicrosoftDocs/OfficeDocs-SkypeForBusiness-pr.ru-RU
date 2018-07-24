---
title: Политика версий клиентов
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
ROBOTS: NOINDEX, NOFOLLOW
description: Вы может указать версию клиентов, поддерживаемых в вашей среде. При взаимодействии двух клиентов с разными версиями возможности, доступные обоим клиентам, могут быть ограничены возможностями другого клиента.
ms.openlocfilehash: 2743c62f6fbd692723c4ed9ea464e665a65d0abc
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21009696"
---
# <a name="client-version-policy"></a><span data-ttu-id="d2e8c-104">Политика версий клиентов</span><span class="sxs-lookup"><span data-stu-id="d2e8c-104">Client Version Policy</span></span>
 
<span data-ttu-id="d2e8c-105">Вы может указать версию клиентов, поддерживаемых в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="d2e8c-105">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="d2e8c-106">При взаимодействии двух клиентов с разными версиями возможности, доступные обоим клиентам, могут быть ограничены возможностями другого клиента.</span><span class="sxs-lookup"><span data-stu-id="d2e8c-106">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="d2e8c-107">Важнейшим использования компонентов, содержащихся в Скайп для Business Server и улучшить работу пользователей в целом, можно использовать фильтр версий клиентов для ограничения версий клиентов, которые используются в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="d2e8c-107">To make the greatest use of features included in Skype for Business Server and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="d2e8c-108">Используя этот фильтр, вы также можете сократить расходы, связанные с поддержкой нескольких версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="d2e8c-108">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="d2e8c-109">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="d2e8c-109">Tasks you can perform</span></span>

<span data-ttu-id="d2e8c-110">На странице **Политика версий клиента** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="d2e8c-110">You can perform the following tasks on the **Client Version Policy** page:</span></span>
  
- <span data-ttu-id="d2e8c-111">Изменение политики версий клиентов по умолчанию ( **Глобальная**).</span><span class="sxs-lookup"><span data-stu-id="d2e8c-111">Edit the default ( **Global**) client version policy.</span></span>
    
- <span data-ttu-id="d2e8c-112">создать политики версий клиентов для конкретного сайта или пула;</span><span class="sxs-lookup"><span data-stu-id="d2e8c-112">Create client version policies for a particular site or pool.</span></span>
    
- <span data-ttu-id="d2e8c-113">создать политики версий клиентов, которые можно назначить отдельным пользователям.</span><span class="sxs-lookup"><span data-stu-id="d2e8c-113">Create client version policies that can be assigned to individual users.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d2e8c-114">Поскольку анонимные пользователи не связаны с пользователями, сайтами или службами, к ним могут применяться только политики глобального уровня.</span><span class="sxs-lookup"><span data-stu-id="d2e8c-114">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span> 
  
## <a name="ui-reference"></a><span data-ttu-id="d2e8c-115">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="d2e8c-115">UI Reference</span></span>

<span data-ttu-id="d2e8c-116">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="d2e8c-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="d2e8c-117">**Новые** Можно создать одно или несколько из них следующие политики версий клиентов:</span><span class="sxs-lookup"><span data-stu-id="d2e8c-117">**New** You can create one or more of each of the following client version policies:</span></span>
    
  - <span data-ttu-id="d2e8c-118">Политика сайта</span><span class="sxs-lookup"><span data-stu-id="d2e8c-118">Site policy</span></span>
    
  - <span data-ttu-id="d2e8c-119">Политика пула</span><span class="sxs-lookup"><span data-stu-id="d2e8c-119">Pool policy</span></span>
    
  - <span data-ttu-id="d2e8c-120">Политика пользователя</span><span class="sxs-lookup"><span data-stu-id="d2e8c-120">User policy</span></span>
    
- <span data-ttu-id="d2e8c-121">**Изменение** Можно изменить параметры любого из политики версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="d2e8c-121">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="d2e8c-122">С помощью этого параметра можно выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="d2e8c-122">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="d2e8c-123">**Показать подробности** Этот параметр открывает диалоговое окно, в котором можно изменить параметры для политики версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="d2e8c-123">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>
    
  - <span data-ttu-id="d2e8c-124">**Выделить все** Этот параметр выбирает все политики версий клиентов в списке.</span><span class="sxs-lookup"><span data-stu-id="d2e8c-124">**Select All** This option selects all client version policies in the list.</span></span>
    
  - <span data-ttu-id="d2e8c-125">**Удаление** Этот параметр удаляет все политики версий выбранного клиента.</span><span class="sxs-lookup"><span data-stu-id="d2e8c-125">**Delete** This option deletes all selected client version policies.</span></span>
    
- <span data-ttu-id="d2e8c-126">**Обновление** Можно обновить списке политика версий клиентов, чтобы проверить состояние параметров всех политик версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="d2e8c-126">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>
    
<span data-ttu-id="d2e8c-127">Для получения дополнительных сведений о взаимодействии между клиентами и их версий в документации по планированию показано [Взаимодействие с клиентом](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) .</span><span class="sxs-lookup"><span data-stu-id="d2e8c-127">For details about interoperability among clients and client versions, see [Client Interoperability](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="d2e8c-128">Для получения дополнительных сведений о работе с политики версий клиентов см [Версий клиента, поддерживаемые в вашей организации](http://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="d2e8c-128">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](http://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

