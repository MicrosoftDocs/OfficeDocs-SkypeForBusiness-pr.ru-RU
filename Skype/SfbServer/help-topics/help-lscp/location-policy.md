---
title: Политика определения местонахождения
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: Политики расположения определяют, включена ли технология Enhanced 9-1-1 (E9-1-1) и как она используется, а также определяют, как сведения о расположении применяются для пользователей и контактов.
ms.openlocfilehash: 948fb5cb6a5457b512af3fc7d230adf27c304bd2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803959"
---
# <a name="location-policy"></a><span data-ttu-id="4ec96-103">Политика определения местонахождения</span><span class="sxs-lookup"><span data-stu-id="4ec96-103">Location Policy</span></span>

<span data-ttu-id="4ec96-104">Политики расположения определяют, включена ли технология Enhanced 9-1-1 (E9-1-1) и как она используется, а также определяют, как сведения о расположении применяются для пользователей и контактов.</span><span class="sxs-lookup"><span data-stu-id="4ec96-104">Location policies determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

<span data-ttu-id="4ec96-105">Политики расположения включают в себя глобальную политику и, возможно, одну или несколько политик пользователей и сайтов:</span><span class="sxs-lookup"><span data-stu-id="4ec96-105">Location policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="4ec96-106">**Глобальная политика:** Глобальная политика создается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4ec96-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="4ec96-107">Вы можете изменить ее, но не удалить.</span><span class="sxs-lookup"><span data-stu-id="4ec96-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="4ec96-108">Если попытаться удалить глобальную политику, для всех параметров восстанавливаются значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4ec96-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="4ec96-109">**Политики сайта (необязательно):** Можно создать одну или несколько политик расположения сайта, каждая из которых применяется к определенному сайту.</span><span class="sxs-lookup"><span data-stu-id="4ec96-109">**Site policies (optional):** You can create one or more site location policies, each of which applies to a specific site.</span></span> <span data-ttu-id="4ec96-110">Политики для сайтов переопределяют глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="4ec96-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="4ec96-111">**Политики пользователей (необязательно):** Можно создать одну или несколько политик расположения пользователей, каждая из которых применяется к определенному пользователю или группе пользователей.</span><span class="sxs-lookup"><span data-stu-id="4ec96-111">**User policies (optional):** You can create one or more user location policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="4ec96-112">Политики для пользователей переопределяют глобальную политику и политики для сайтов.</span><span class="sxs-lookup"><span data-stu-id="4ec96-112">User policies override the global policy and site policies.</span></span>

> [!NOTE]
> <span data-ttu-id="4ec96-113">Вы также можете назначать политики расположения сетевым сайтам, которые представляют собой группы подсетей.</span><span class="sxs-lookup"><span data-stu-id="4ec96-113">You can also assign location policies to network sites, which are groups of subnets.</span></span> <span data-ttu-id="4ec96-114">Политики расположения, назначенные сетевым сайтам, имеют приоритет над всеми другими политиками для пользователей.</span><span class="sxs-lookup"><span data-stu-id="4ec96-114">Location policies assigned to network sites take precedence over all other user policies.</span></span> <span data-ttu-id="4ec96-115">Дополнительные сведения о назначении политик расположения сетевым сайтам с помощью cmdlets см. в дополнительных сведениях о добавлении политики расположения к сетевому сайту в Skype для бизнеса [Server 2015.](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md)</span><span class="sxs-lookup"><span data-stu-id="4ec96-115">For details about assigning location policies to network sites by using cmdlets, see [Add a location policy to a network site in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span></span> <span data-ttu-id="4ec96-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites.](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx)</span><span class="sxs-lookup"><span data-stu-id="4ec96-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span></span>

<span data-ttu-id="4ec96-117">На странице **Политика расположения** отображается список всех политик расположения, определенных для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4ec96-117">The **Location Policy** page displays a list of all the location policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="4ec96-118">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="4ec96-118">Tasks you can perform</span></span>

<span data-ttu-id="4ec96-119">На странице **Политика расположения** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="4ec96-119">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="4ec96-120">создать новую политику расположения для сайта или для пользователя;</span><span class="sxs-lookup"><span data-stu-id="4ec96-120">Create a new site location policy or user location policy</span></span>

- <span data-ttu-id="4ec96-121">изменить глобальную политику или существующую политику сайта или пользователя;</span><span class="sxs-lookup"><span data-stu-id="4ec96-121">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="4ec96-122">удалить политику сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="4ec96-122">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="4ec96-123">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="4ec96-123">UI Reference</span></span>

<span data-ttu-id="4ec96-124">В следующем списке описываются команды на странице.</span><span class="sxs-lookup"><span data-stu-id="4ec96-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="4ec96-125">**Новый** Запускает новую политику расположения сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="4ec96-125">**New** Starts a new site location policy or user location policy.</span></span>

- <span data-ttu-id="4ec96-126">**Правка** Открывает выбранную политику расположения для ее изменения, выбирает все политики расположения в списке или удаляет выбранную политику сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="4ec96-126">**Edit** Opens the selected location policy to edit it, selects all location policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4ec96-127">Для глобальной политики команда **Удалить** восстанавливает значения параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4ec96-127">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="4ec96-128">**Обновление** Обновляет список политик расположения.</span><span class="sxs-lookup"><span data-stu-id="4ec96-128">**Refresh** Refreshes the list of location policies.</span></span>

<span data-ttu-id="4ec96-129">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="4ec96-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="4ec96-130">**Имя** Определяет политику расположения.</span><span class="sxs-lookup"><span data-stu-id="4ec96-130">**Name** Identifies the location policy.</span></span>

- <span data-ttu-id="4ec96-131">**Область действия** Определяет область действия политики расположения: глобальная, на сайте или на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="4ec96-131">**Scope** Identifies the scope of the location policy: global, site, or user.</span></span>

- <span data-ttu-id="4ec96-132">**E9-1-1** Проверяется, включены ли для пользователей, которые назначены этой политике расположения, E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="4ec96-132">**E9-1-1** Checked if users assigned this location policy are enabled for E9-1-1.</span></span>

- <span data-ttu-id="4ec96-133">**Расположение** Указывает, будет ли пользователям предложено ввести сведения о расположении, когда их клиент регистрируется в Skype для бизнеса Server в новом расположении, и будет ли отклоняться запрос без ввода сведений о расположении.</span><span class="sxs-lookup"><span data-stu-id="4ec96-133">**Location** Specifies whether or not users are prompted to enter location information when their client registers with Skype for Business Server at a new location, and whether they see a disclaimer if they dismiss the prompt without entering location information.</span></span>

- <span data-ttu-id="4ec96-134">**Использование STN** Указывает режим работы с телефонной сетью общего пользования (PSTN), используемый для определения маршрута голосовой связи, используемого для маршрутов экстренных вызовов от клиентов, использующих этот профиль.</span><span class="sxs-lookup"><span data-stu-id="4ec96-134">**PSTN usage** Specifies the public switched telephone network (PSTN) usage that is used to determine the voice route used to route emergency calls from clients using this profile.</span></span>

- <span data-ttu-id="4ec96-135">**Номер E9-1-1** Указывает номер, набираемого для экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="4ec96-135">**E9-1-1 number** Specifies the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="4ec96-136">**Маска E9-1-1** Указывает номер, набираемого пользователем, который затем преобразуется в номер экстренного номера.</span><span class="sxs-lookup"><span data-stu-id="4ec96-136">**E9-1-1 mask** Specifies a number that a user dials that is then translated into the emergency dial number.</span></span>

<span data-ttu-id="4ec96-137">Сведения о Корпоративная голосовая связь и возможностях экстренных служб см. в обзоре [E9-1-1 в](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="4ec96-137">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="4ec96-138">Дополнительные сведения о работе с политиками расположения см. в разделе [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) в документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="4ec96-138">For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>


