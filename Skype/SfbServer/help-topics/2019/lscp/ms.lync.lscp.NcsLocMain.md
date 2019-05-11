---
title: Политика определения местонахождения
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
ROBOTS: NOINDEX, NOFOLLOW
description: Политики расположения определяют, включена ли технология Enhanced 9-1-1 (E9-1-1) и как она используется, а также определяют, как сведения о расположении применяются для пользователей и контактов.
ms.openlocfilehash: 133fd96bbceab7971196147d604ed582d5584f1a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891133"
---
# <a name="location-policy"></a><span data-ttu-id="38545-103">Политика определения местонахождения</span><span class="sxs-lookup"><span data-stu-id="38545-103">Location Policy</span></span>

<span data-ttu-id="38545-104">Политики расположения определяют, включена ли технология Enhanced 9-1-1 (E9-1-1) и как она используется, а также определяют, как сведения о расположении применяются для пользователей и контактов.</span><span class="sxs-lookup"><span data-stu-id="38545-104">Location policies determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

<span data-ttu-id="38545-105">Политики расположения включают в себя глобальную политику и, возможно, одну или несколько политик пользователей и сайтов:</span><span class="sxs-lookup"><span data-stu-id="38545-105">Location policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="38545-106">**Глобальной политики:** По умолчанию создается глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="38545-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="38545-107">Вы можете изменить ее, но не можете удалить.</span><span class="sxs-lookup"><span data-stu-id="38545-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="38545-108">Если попытаться удалить глобальную политику, для всех параметров восстанавливаются значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="38545-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="38545-109">**(Необязательно) политики сайта:** Можно создать одну или несколько сайтов расположение политик, каждая из которых применяется для определенного сайта.</span><span class="sxs-lookup"><span data-stu-id="38545-109">**Site policies (optional):** You can create one or more site location policies, each of which applies to a specific site.</span></span> <span data-ttu-id="38545-110">Политики для сайтов переопределяют глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="38545-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="38545-111">**Политик пользователей (необязательно):** Можно создать одну или несколько пользователей расположение политик, каждая из которых применяется для определенного пользователя или группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="38545-111">**User policies (optional):** You can create one or more user location policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="38545-112">Политики для пользователей переопределяют глобальную политику и политики для сайтов.</span><span class="sxs-lookup"><span data-stu-id="38545-112">User policies override the global policy and site policies.</span></span>

> [!NOTE]
> <span data-ttu-id="38545-113">Вы также можете назначать политики расположения сетевым сайтам, которые представляют собой группы подсетей.</span><span class="sxs-lookup"><span data-stu-id="38545-113">You can also assign location policies to network sites, which are groups of subnets.</span></span> <span data-ttu-id="38545-114">Политики расположения, назначенные сетевым сайтам, имеют приоритет над всеми другими политиками для пользователей.</span><span class="sxs-lookup"><span data-stu-id="38545-114">Location policies assigned to network sites take precedence over all other user policies.</span></span> <span data-ttu-id="38545-115">Для получения дополнительных сведений о назначении политики расположения для сетевых узлов с помощью командлетов в разделе [Add политику расположения сетевым узлом в Скайп для Business Server](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="38545-115">For details about assigning location policies to network sites by using cmdlets, see [Add a location policy to a network site in Skype for Business Server](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span></span> <span data-ttu-id="38545-116">Для получения дополнительных сведений об использовании Скайп для панели управления сервера Business назначение политики расположения с сетевым узлом видеть [Настройки сетевых узлов](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span><span class="sxs-lookup"><span data-stu-id="38545-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span></span>

<span data-ttu-id="38545-117">На странице **Политика расположения** отображается список всех политик расположения, определенных для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="38545-117">The **Location Policy** page displays a list of all the location policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="38545-118">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="38545-118">Tasks you can perform</span></span>

<span data-ttu-id="38545-119">На странице **Политика расположения** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="38545-119">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="38545-120">создать новую политику расположения для сайта или для пользователя;</span><span class="sxs-lookup"><span data-stu-id="38545-120">Create a new site location policy or user location policy</span></span>

- <span data-ttu-id="38545-121">изменить глобальную политику или существующую политику сайта или пользователя;</span><span class="sxs-lookup"><span data-stu-id="38545-121">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="38545-122">удалить политику сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="38545-122">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="38545-123">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="38545-123">UI Reference</span></span>

<span data-ttu-id="38545-124">В следующем списке описываются команды на странице.</span><span class="sxs-lookup"><span data-stu-id="38545-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="38545-125">**Новые** Создает новую политику расположения для сайта или для пользователя расположения.</span><span class="sxs-lookup"><span data-stu-id="38545-125">**New** Starts a new site location policy or user location policy.</span></span>

- <span data-ttu-id="38545-126">**Изменение** Открывает политики выбранного расположения для ее редактирования, выбирает все политики расположения в списке или удаляет политику выбранного сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="38545-126">**Edit** Opens the selected location policy to edit it, selects all location policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="38545-127">Для глобальной политики команда **Удалить** восстанавливает значения параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="38545-127">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="38545-128">**Обновление** Обновляет список политик расположения.</span><span class="sxs-lookup"><span data-stu-id="38545-128">**Refresh** Refreshes the list of location policies.</span></span>

<span data-ttu-id="38545-129">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="38545-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="38545-130">**Имя** Идентифицирует политику расположения.</span><span class="sxs-lookup"><span data-stu-id="38545-130">**Name** Identifies the location policy.</span></span>

- <span data-ttu-id="38545-131">**Область** Определяет область политики расположения: глобальная, на уровне сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="38545-131">**Scope** Identifies the scope of the location policy: global, site, or user.</span></span>

- <span data-ttu-id="38545-132">**E9-1-1** Проверка, если пользователи, которым назначены данная политика расположения включены для E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="38545-132">**E9-1-1** Checked if users assigned this location policy are enabled for E9-1-1.</span></span>

- <span data-ttu-id="38545-133">**Расположение** Указывает ли пользователям предлагается ввести сведения о расположении при их клиент регистрирует Скайп для Business Server в новое расположение и ли они видят заявление об отказе, если они отклонение строке без ввода сведения о расположении.</span><span class="sxs-lookup"><span data-stu-id="38545-133">**Location** Specifies whether or not users are prompted to enter location information when their client registers with Skype for Business Server at a new location, and whether they see a disclaimer if they dismiss the prompt without entering location information.</span></span>

- <span data-ttu-id="38545-134">**Использование ТСОП** Задает для использования телефонной сети (общего пользования PSTN), который используется для определения маршрута голосовых вызовов, которому направляются экстренные вызовы от клиентов, использующих данный профиль.</span><span class="sxs-lookup"><span data-stu-id="38545-134">**PSTN usage** Specifies the public switched telephone network (PSTN) usage that is used to determine the voice route used to route emergency calls from clients using this profile.</span></span>

- <span data-ttu-id="38545-135">**Номер E9-1-1** Указывает номер, набираемый для связи с аварийными службами.</span><span class="sxs-lookup"><span data-stu-id="38545-135">**E9-1-1 number** Specifies the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="38545-136">**Маска E9-1-1** Указывает набираемый пользователем номер, который затем преобразуется в номер экстренного вызова.</span><span class="sxs-lookup"><span data-stu-id="38545-136">**E9-1-1 mask** Specifies a number that a user dials that is then translated into the emergency dial number.</span></span>

<span data-ttu-id="38545-137">Для получения дополнительных сведений о корпоративной голосовой связи экстренные службы функциях и возможностях просмотра [Обзор службы E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="38545-137">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="38545-138">Дополнительные сведения о работе с политиками расположения см. в разделе [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="38545-138">For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>


