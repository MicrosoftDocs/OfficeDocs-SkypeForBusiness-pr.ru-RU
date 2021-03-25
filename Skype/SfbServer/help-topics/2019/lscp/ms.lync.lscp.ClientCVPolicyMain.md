---
title: Политика версий клиентов
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
ROBOTS: NOINDEX, NOFOLLOW
description: Вы может указать версию клиентов, поддерживаемых в вашей среде. При взаимодействии двух клиентов с разными версиями возможности, доступные обоим клиентам, могут быть ограничены возможностями другого клиента.
ms.openlocfilehash: fd3abdae41b912e63391121c740912cde80e18c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120298"
---
# <a name="client-version-policy"></a><span data-ttu-id="b83d1-104">Политика версий клиентов</span><span class="sxs-lookup"><span data-stu-id="b83d1-104">Client Version Policy</span></span>

<span data-ttu-id="b83d1-105">Вы может указать версию клиентов, поддерживаемых в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="b83d1-105">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="b83d1-106">При взаимодействии двух клиентов с разными версиями возможности, доступные обоим клиентам, могут быть ограничены возможностями другого клиента.</span><span class="sxs-lookup"><span data-stu-id="b83d1-106">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="b83d1-107">Чтобы максимально использовать функции, включенные в Skype для бизнеса Server, и улучшить общий пользовательский интерфейс, можно использовать фильтр клиентских версий для ограничения клиентских версий, используемых в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="b83d1-107">To make the greatest use of features included in Skype for Business Server and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="b83d1-108">Используя этот фильтр, вы также можете сократить расходы, связанные с поддержкой нескольких версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="b83d1-108">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="b83d1-109">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="b83d1-109">Tasks you can perform</span></span>

<span data-ttu-id="b83d1-110">На странице **Политика версий клиента** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="b83d1-110">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="b83d1-111">Изменить политику клиентской версии по умолчанию **(Global).**</span><span class="sxs-lookup"><span data-stu-id="b83d1-111">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="b83d1-112">создать политики версий клиентов для конкретного сайта или пула;</span><span class="sxs-lookup"><span data-stu-id="b83d1-112">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="b83d1-113">создать политики версий клиентов, которые можно назначить отдельным пользователям.</span><span class="sxs-lookup"><span data-stu-id="b83d1-113">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="b83d1-114">Поскольку анонимные пользователи не сопоставлены с пользователем, сайтом или службой, они управляются только политиками глобального уровня.</span><span class="sxs-lookup"><span data-stu-id="b83d1-114">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="b83d1-115">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="b83d1-115">UI Reference</span></span>

<span data-ttu-id="b83d1-116">В следующих списках описываются меню, команды, поля и свойства на этой странице.</span><span class="sxs-lookup"><span data-stu-id="b83d1-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="b83d1-117">**Новые** Можно создать одну или несколько политик каждой из следующих клиентских версий:</span><span class="sxs-lookup"><span data-stu-id="b83d1-117">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="b83d1-118">Политика сайта</span><span class="sxs-lookup"><span data-stu-id="b83d1-118">Site policy</span></span>

  - <span data-ttu-id="b83d1-119">Политика пула</span><span class="sxs-lookup"><span data-stu-id="b83d1-119">Pool policy</span></span>

  - <span data-ttu-id="b83d1-120">Политика пользователя</span><span class="sxs-lookup"><span data-stu-id="b83d1-120">User policy</span></span>

- <span data-ttu-id="b83d1-121">**Изменение** Вы можете изменить параметры любой из политик клиентской версии.</span><span class="sxs-lookup"><span data-stu-id="b83d1-121">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="b83d1-122">С помощью этой команды можно выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b83d1-122">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="b83d1-123">**Демонстрация сведений** Этот параметр открывает диалоговое окно, в котором можно изменить параметры политики клиентской версии.</span><span class="sxs-lookup"><span data-stu-id="b83d1-123">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="b83d1-124">**Выберите все** Этот параметр выбирает все политики клиентской версии в списке.</span><span class="sxs-lookup"><span data-stu-id="b83d1-124">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="b83d1-125">**Удаление** Этот параметр удаляет все выбранные политики клиентской версии.</span><span class="sxs-lookup"><span data-stu-id="b83d1-125">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="b83d1-126">**Обновление** Вы можете обновить список политик клиентской версии, чтобы проверить состояние параметров всех политик клиентских версий.</span><span class="sxs-lookup"><span data-stu-id="b83d1-126">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="b83d1-127">Сведения о взаимосвязи между клиентами и версиями клиентов см. в документации по планированию. [](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013)</span><span class="sxs-lookup"><span data-stu-id="b83d1-127">For details about interoperability among clients and client versions, see [Client Interoperability](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="b83d1-128">Дополнительные сведения о работе с политиками версий клиентов см. в разделе [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) в документации по применению.</span><span class="sxs-lookup"><span data-stu-id="b83d1-128">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) in the Operations documentation.</span></span>