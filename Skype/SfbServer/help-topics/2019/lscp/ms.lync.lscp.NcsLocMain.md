---
title: Политика определения местонахождения
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
ROBOTS: NOINDEX, NOFOLLOW
description: Политики расположения определяют, включена ли технология Enhanced 9-1-1 (E9-1-1) и как она используется, а также определяют, как сведения о расположении применяются для пользователей и контактов.
ms.openlocfilehash: 82126acf09ed4e0cd1b98b20f22760f23038226c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41704614"
---
# <a name="location-policy"></a><span data-ttu-id="e12e8-103">Политика определения местонахождения</span><span class="sxs-lookup"><span data-stu-id="e12e8-103">Location Policy</span></span>

<span data-ttu-id="e12e8-104">Политики расположения определяют, включена ли технология Enhanced 9-1-1 (E9-1-1) и как она используется, а также определяют, как сведения о расположении применяются для пользователей и контактов.</span><span class="sxs-lookup"><span data-stu-id="e12e8-104">Location policies determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

<span data-ttu-id="e12e8-105">Политики расположения включают в себя глобальную политику и, возможно, одну или несколько политик пользователей и сайтов:</span><span class="sxs-lookup"><span data-stu-id="e12e8-105">Location policies include the global policy and, optionally, one or more site and user policies:</span></span>

- <span data-ttu-id="e12e8-106">**Глобальная политика:** Глобальная политика создается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e12e8-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="e12e8-107">Вы можете изменить ее, но не можете удалить.</span><span class="sxs-lookup"><span data-stu-id="e12e8-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="e12e8-108">Если попытаться удалить глобальную политику, для всех параметров восстанавливаются значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e12e8-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="e12e8-109">**Политики сайта (необязательно):** Вы можете создать одну или несколько политик расположения сайта, каждый из которых будет применяться к определенному сайту.</span><span class="sxs-lookup"><span data-stu-id="e12e8-109">**Site policies (optional):** You can create one or more site location policies, each of which applies to a specific site.</span></span> <span data-ttu-id="e12e8-110">Политики для сайтов переопределяют глобальную политику.</span><span class="sxs-lookup"><span data-stu-id="e12e8-110">Site policies override the global policy.</span></span>

- <span data-ttu-id="e12e8-111">**Пользовательские политики (необязательно):** Вы можете создать одну или несколько политик расположения пользователей, каждый из которых будет применяться к определенному пользователю или группе пользователей.</span><span class="sxs-lookup"><span data-stu-id="e12e8-111">**User policies (optional):** You can create one or more user location policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="e12e8-112">Политики для пользователей переопределяют глобальную политику и политики для сайтов.</span><span class="sxs-lookup"><span data-stu-id="e12e8-112">User policies override the global policy and site policies.</span></span>

> [!NOTE]
> <span data-ttu-id="e12e8-113">Вы также можете назначать политики расположения сетевым сайтам, которые представляют собой группы подсетей.</span><span class="sxs-lookup"><span data-stu-id="e12e8-113">You can also assign location policies to network sites, which are groups of subnets.</span></span> <span data-ttu-id="e12e8-114">Политики расположения, назначенные сетевым сайтам, имеют приоритет над всеми другими политиками для пользователей.</span><span class="sxs-lookup"><span data-stu-id="e12e8-114">Location policies assigned to network sites take precedence over all other user policies.</span></span> <span data-ttu-id="e12e8-115">Сведения о назначении политик местоположений для сетевых сайтов с помощью командлетов можно найти [в разделе Добавление политики местоположений на сайт сети в Skype для бизнеса Server](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="e12e8-115">For details about assigning location policies to network sites by using cmdlets, see [Add a location policy to a network site in Skype for Business Server](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span></span> <span data-ttu-id="e12e8-116">Дополнительные сведения об использовании панели управления Skype для бизнеса Server для назначения политики расположения сетевому сайту можно найти в разделе [Настройка сайтов сети](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span><span class="sxs-lookup"><span data-stu-id="e12e8-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span></span>

<span data-ttu-id="e12e8-117">На странице **Политика расположения** отображается список всех политик расположения, определенных для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e12e8-117">The **Location Policy** page displays a list of all the location policies that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="e12e8-118">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="e12e8-118">Tasks you can perform</span></span>

<span data-ttu-id="e12e8-119">На странице **Политика расположения** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="e12e8-119">You can perform the following tasks from the **Location Policy** page:</span></span>

- <span data-ttu-id="e12e8-120">создать новую политику расположения для сайта или для пользователя;</span><span class="sxs-lookup"><span data-stu-id="e12e8-120">Create a new site location policy or user location policy</span></span>

- <span data-ttu-id="e12e8-121">изменить глобальную политику или существующую политику сайта или пользователя;</span><span class="sxs-lookup"><span data-stu-id="e12e8-121">Change the global policy or an existing site policy or user policy</span></span>

- <span data-ttu-id="e12e8-122">удалить политику сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="e12e8-122">Delete a site policy or user policy</span></span>

## <a name="ui-reference"></a><span data-ttu-id="e12e8-123">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="e12e8-123">UI Reference</span></span>

<span data-ttu-id="e12e8-124">В следующем списке описываются команды на странице.</span><span class="sxs-lookup"><span data-stu-id="e12e8-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="e12e8-125">**Новые** Запуск новой политики расположения сайта или политики расположения пользователей.</span><span class="sxs-lookup"><span data-stu-id="e12e8-125">**New** Starts a new site location policy or user location policy.</span></span>

- <span data-ttu-id="e12e8-126">**Изменить** Открытие выбранной политики местоположений для ее изменения, выбор всех политик местоположений в списке или удаление выбранной политики сайта или политики пользователей.</span><span class="sxs-lookup"><span data-stu-id="e12e8-126">**Edit** Opens the selected location policy to edit it, selects all location policies in the list, or deletes the selected site policy or user policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e12e8-127">Для глобальной политики команда **Удалить** восстанавливает значения параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e12e8-127">For the global policy, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="e12e8-128">**Обновить** Обновляет список политик местоположений.</span><span class="sxs-lookup"><span data-stu-id="e12e8-128">**Refresh** Refreshes the list of location policies.</span></span>

<span data-ttu-id="e12e8-129">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="e12e8-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="e12e8-130">**Name (имя** ) Определяет политику расположения.</span><span class="sxs-lookup"><span data-stu-id="e12e8-130">**Name** Identifies the location policy.</span></span>

- <span data-ttu-id="e12e8-131">**Область действия** Определяет область политики расположения: глобально, сайт или пользователь.</span><span class="sxs-lookup"><span data-stu-id="e12e8-131">**Scope** Identifies the scope of the location policy: global, site, or user.</span></span>

- <span data-ttu-id="e12e8-132">**E9-1-1** Флажок установлен, если пользователи, которым назначена эта политика расположения, включены для E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="e12e8-132">**E9-1-1** Checked if users assigned this location policy are enabled for E9-1-1.</span></span>

- <span data-ttu-id="e12e8-133">**Расположение** Указывает, должны ли пользователи получать запрос на ввод сведений о расположении, когда их клиент регистрируется в новом расположении, а также от того, есть ли у них отказ в ответ на запрос без ввода сведений о местоположении.</span><span class="sxs-lookup"><span data-stu-id="e12e8-133">**Location** Specifies whether or not users are prompted to enter location information when their client registers with Skype for Business Server at a new location, and whether they see a disclaimer if they dismiss the prompt without entering location information.</span></span>

- <span data-ttu-id="e12e8-134">**Использование PSTN** Указывает использование общественной коммутируемой телефонной сети (КТСОП), используемое для определения голосового маршрута, используемого для маршрутизации экстренных вызовов с клиентов, использующих этот профиль.</span><span class="sxs-lookup"><span data-stu-id="e12e8-134">**PSTN usage** Specifies the public switched telephone network (PSTN) usage that is used to determine the voice route used to route emergency calls from clients using this profile.</span></span>

- <span data-ttu-id="e12e8-135">**E9 – 1 – 1 число** Номер, набираемый для экстренных служб.</span><span class="sxs-lookup"><span data-stu-id="e12e8-135">**E9-1-1 number** Specifies the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="e12e8-136">**E9-1-1 — маска** Указывает номер, который пользователь набирает на номер для экстренного набора номера, который затем транслируется.</span><span class="sxs-lookup"><span data-stu-id="e12e8-136">**E9-1-1 mask** Specifies a number that a user dials that is then translated into the emergency dial number.</span></span>

<span data-ttu-id="e12e8-137">Дополнительные сведения о функциях и возможностях службы экстренной голосовой связи: [Обзор E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="e12e8-137">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="e12e8-138">Дополнительные сведения о работе с политиками расположения см. в разделе [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="e12e8-138">For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>


