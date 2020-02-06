---
title: Конфигурация собрания
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 24e8f749-d54c-4315-a8fe-bb9303b356ef
ROBOTS: NOINDEX, NOFOLLOW
description: Параметры конфигурации собрания определяют типы конференций (также калледмитингс), которые пользователи могут создавать, и определяют, как анонимные пользователи и пользователи конференц-связи с телефонным подключением могут присоединиться к этим конференциям. Эти параметры распространяются только на запланированные собрания. Они не распространяются на одноранговые собрания, созданные посредством выбора элемента "Провести собрание" в клиенте.
ms.openlocfilehash: 66a1ff8134eec701cd3bd11b305c4e04e18ef99a
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798586"
---
# <a name="meeting-configuration"></a><span data-ttu-id="7e62d-105">Конфигурация собрания</span><span class="sxs-lookup"><span data-stu-id="7e62d-105">Meeting Configuration</span></span>

<span data-ttu-id="7e62d-p102">Параметры конфигурации собраний определяют тип конференций (которые также называются "собраниями"), который может создаваться пользователями и управлять тем, как анонимные пользователи и пользователи, участвующие в конференц-связи с телефонным подключением, могут присоединяться к этим конференциям (или даже тем, могут ли они присоединяться). Эти параметры распространяются только на запланированные собрания. Они не распространяются на одноранговые собрания, созданные посредством выбора элемента "Провести собрание" в клиенте.</span><span class="sxs-lookup"><span data-stu-id="7e62d-p102">Meeting configuration settings define the type of conferences (also called "meetings") that users can create, and control how (or whether) anonymous users and dial-in conferencing users can join these conferences. These settings only apply to scheduled meetings. They do not apply to ad-hoc meetings created by clicking the Meet Now option in the client.</span></span>

<span data-ttu-id="7e62d-109">Конфигурации собрания применяются на глобальном уровне, уровне сайта или уровне пула:</span><span class="sxs-lookup"><span data-stu-id="7e62d-109">Meeting configurations apply on the global, site, or pool level:</span></span>

- <span data-ttu-id="7e62d-110">**Глобальная настройка собрания:** По умолчанию создается Глобальная конфигурация собрания.</span><span class="sxs-lookup"><span data-stu-id="7e62d-110">**Global meeting configuration:** The global meeting configuration is created by default.</span></span> <span data-ttu-id="7e62d-111">Вы можете изменить ее, но не можете удалить.</span><span class="sxs-lookup"><span data-stu-id="7e62d-111">You can edit the global meeting configuration, but you cannot delete it.</span></span> <span data-ttu-id="7e62d-112">Если попытаться удалить глобальную конфигурацию собрания, для всех параметров восстанавливаются значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7e62d-112">If you try to remove the global meeting configuration, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="7e62d-113">**Настройка собрания сайта (необязательно):** Вы можете создать одну или несколько конфигураций для собрания сайта, каждый из которых будет применяться к определенному сайту.</span><span class="sxs-lookup"><span data-stu-id="7e62d-113">**Site meeting configuration (optional):** You can create one or more site meeting configurations, each of which applies to a specific site.</span></span> <span data-ttu-id="7e62d-114">Конфигурации для сайтов переопределяют глобальную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="7e62d-114">Site configurations override the global configuration.</span></span>

- <span data-ttu-id="7e62d-115">**Настройка собрания в пуле (необязательно):** Вы можете создать одну или несколько конфигураций собраний для пула, каждый из которых будет применяться к определенному пулу.</span><span class="sxs-lookup"><span data-stu-id="7e62d-115">**Pool meeting configuration (optional):** You can create one or more pool meeting configurations, each of which applies to a specific pool.</span></span> <span data-ttu-id="7e62d-116">Конфигурации для пулов переопределяют глобальную конфигурацию и конфигурации для сайтов.</span><span class="sxs-lookup"><span data-stu-id="7e62d-116">Pool configurations override the global configuration and site configurations.</span></span>

<span data-ttu-id="7e62d-117">На странице **Конфигурация собрания** отображается список всех конфигураций собрания, определенных для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7e62d-117">The **Meeting Configuration** page displays a list of all the meeting configurations that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="7e62d-118">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="7e62d-118">Tasks you can perform</span></span>

<span data-ttu-id="7e62d-119">На странице **Конфигурация собрания** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="7e62d-119">You can perform the following tasks from the **Meeting Configuration** page:</span></span>

- <span data-ttu-id="7e62d-120">создать новую конфигурацию собрания для сайта или пула;</span><span class="sxs-lookup"><span data-stu-id="7e62d-120">Create a new site meeting configuration or pool meeting configuration</span></span>

- <span data-ttu-id="7e62d-121">изменить глобальную конфигурацию или существующую конфигурацию для сайта или пула;</span><span class="sxs-lookup"><span data-stu-id="7e62d-121">Change the global configuration or an existing site configuration or pool configuration</span></span>

- <span data-ttu-id="7e62d-122">удалить конфигурацию для сайта или пула.</span><span class="sxs-lookup"><span data-stu-id="7e62d-122">Delete a site configuration or pool configuration</span></span>

## <a name="ui-reference"></a><span data-ttu-id="7e62d-123">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="7e62d-123">UI Reference</span></span>

<span data-ttu-id="7e62d-124">В следующем списке описываются команды на странице.</span><span class="sxs-lookup"><span data-stu-id="7e62d-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="7e62d-125">**Новые** Запуск новой конфигурации собрания сайта или конфигурации собрания пула.</span><span class="sxs-lookup"><span data-stu-id="7e62d-125">**New** Starts a new site meeting configuration or pool meeting configuration.</span></span>

- <span data-ttu-id="7e62d-126">**Изменить** Открытие выбранной конфигурации собрания для редактирования, выбор всех конфигураций собраний в списке или удаление конфигурации выбранной конфигурации сайта или пула.</span><span class="sxs-lookup"><span data-stu-id="7e62d-126">**Edit** Opens the selected meeting configuration to edit it, selects all meeting configurations in the list, or deletes the selected site configuration or pool configuration.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7e62d-127">Для глобальной конфигурации собрания команда **Удалить** восстанавливает значения параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7e62d-127">For the global meeting configuration, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="7e62d-128">**Обновить** Обновляет список конфигураций собраний.</span><span class="sxs-lookup"><span data-stu-id="7e62d-128">**Refresh** Refreshes the list of meeting configurations.</span></span>

<span data-ttu-id="7e62d-129">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="7e62d-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="7e62d-130">**Name (имя** ) Определяет конфигурацию собрания.</span><span class="sxs-lookup"><span data-stu-id="7e62d-130">**Name** Identifies the meeting configuration.</span></span>

- <span data-ttu-id="7e62d-131">**Область действия** Определяет область конфигурации собрания: глобально, на сайте или в пуле.</span><span class="sxs-lookup"><span data-stu-id="7e62d-131">**Scope** Identifies the scope of the meeting configuration: global, site, or pool.</span></span>

<span data-ttu-id="7e62d-132">Дополнительные сведения о работе с конфигурациями собраний см. в разделе [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="7e62d-132">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](https://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx) in the Operations documentation.</span></span>


