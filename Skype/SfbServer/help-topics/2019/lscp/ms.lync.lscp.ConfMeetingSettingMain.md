---
title: Конфигурация собрания
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Параметры конфигурации собраний определяют тип конференций (также называемыхmeetings), которые пользователи могут создавать, и контролировать, как анонимные пользователи и пользователи конференц-конференций с диалогом могут присоединяться к этим конференциям. Эти параметры распространяются только на запланированные собрания. Они не применяются к ad-hoc собраниям, созданным путем нажатия параметра Meet Now в клиенте.
ms.openlocfilehash: 053378ef694a66413f11760be5f449cd21e6b764
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095973"
---
# <a name="meeting-configuration"></a><span data-ttu-id="05b30-105">Конфигурация собрания</span><span class="sxs-lookup"><span data-stu-id="05b30-105">Meeting Configuration</span></span>

<span data-ttu-id="05b30-106">Параметры конфигурации собраний определяют тип конференций (которые также называются "собраниями"), который может создаваться пользователями, и управлять тем, как анонимные пользователи и пользователи, участвующие в конференц-связи с телефонным подключением, могут присоединяться к этим конференциям (или даже тем, могут ли они присоединяться).</span><span class="sxs-lookup"><span data-stu-id="05b30-106">Meeting configuration settings define the type of conferences (also called "meetings") that users can create, and control how (or whether) anonymous users and dial-in conferencing users can join these conferences.</span></span> <span data-ttu-id="05b30-107">Эти параметры распространяются только на запланированные собрания.</span><span class="sxs-lookup"><span data-stu-id="05b30-107">These settings only apply to scheduled meetings.</span></span> <span data-ttu-id="05b30-108">Они не применяются к ad-hoc собраниям, созданным путем нажатия параметра Meet Now в клиенте.</span><span class="sxs-lookup"><span data-stu-id="05b30-108">They do not apply to ad-hoc meetings created by clicking the Meet Now option in the client.</span></span>

<span data-ttu-id="05b30-109">Конфигурации собрания применяются на глобальном уровне, уровне сайта или уровне пула:</span><span class="sxs-lookup"><span data-stu-id="05b30-109">Meeting configurations apply on the global, site, or pool level:</span></span>

- <span data-ttu-id="05b30-110">**Глобальная конфигурация собраний:** Глобальная конфигурация собраний создается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="05b30-110">**Global meeting configuration:** The global meeting configuration is created by default.</span></span> <span data-ttu-id="05b30-111">Вы можете изменить ее, но не удалить.</span><span class="sxs-lookup"><span data-stu-id="05b30-111">You can edit the global meeting configuration, but you cannot delete it.</span></span> <span data-ttu-id="05b30-112">Если попытаться удалить глобальную конфигурацию собрания, для всех параметров восстанавливаются значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="05b30-112">If you try to remove the global meeting configuration, all the settings are reset to the default values.</span></span>

- <span data-ttu-id="05b30-113">**Конфигурация собрания сайта (необязательная):** Можно создать одну или несколько конфигураций собраний сайтов, каждая из которых применяется к определенному сайту.</span><span class="sxs-lookup"><span data-stu-id="05b30-113">**Site meeting configuration (optional):** You can create one or more site meeting configurations, each of which applies to a specific site.</span></span> <span data-ttu-id="05b30-114">Конфигурации для сайтов переопределяют глобальную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="05b30-114">Site configurations override the global configuration.</span></span>

- <span data-ttu-id="05b30-115">**Конфигурация собраний пула (необязательная):** Можно создать одну или несколько конфигураций собраний пула, каждая из которых применяется к определенному пулу.</span><span class="sxs-lookup"><span data-stu-id="05b30-115">**Pool meeting configuration (optional):** You can create one or more pool meeting configurations, each of which applies to a specific pool.</span></span> <span data-ttu-id="05b30-116">Конфигурации для пулов переопределяют глобальную конфигурацию и конфигурации для сайтов.</span><span class="sxs-lookup"><span data-stu-id="05b30-116">Pool configurations override the global configuration and site configurations.</span></span>

<span data-ttu-id="05b30-117">На странице **Конфигурация собрания** отображается список всех конфигураций собрания, определенных для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="05b30-117">The **Meeting Configuration** page displays a list of all the meeting configurations that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="05b30-118">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="05b30-118">Tasks you can perform</span></span>

<span data-ttu-id="05b30-119">На странице **Конфигурация собрания** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="05b30-119">You can perform the following tasks from the **Meeting Configuration** page:</span></span>

- <span data-ttu-id="05b30-120">создать новую конфигурацию собрания для сайта или пула;</span><span class="sxs-lookup"><span data-stu-id="05b30-120">Create a new site meeting configuration or pool meeting configuration</span></span>

- <span data-ttu-id="05b30-121">изменить глобальную конфигурацию или существующую конфигурацию для сайта или пула;</span><span class="sxs-lookup"><span data-stu-id="05b30-121">Change the global configuration or an existing site configuration or pool configuration</span></span>

- <span data-ttu-id="05b30-122">удалить конфигурацию для сайта или пула.</span><span class="sxs-lookup"><span data-stu-id="05b30-122">Delete a site configuration or pool configuration</span></span>

## <a name="ui-reference"></a><span data-ttu-id="05b30-123">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="05b30-123">UI Reference</span></span>

<span data-ttu-id="05b30-124">В следующем списке описываются команды на странице.</span><span class="sxs-lookup"><span data-stu-id="05b30-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="05b30-125">**Новые** Запускает новую конфигурацию собрания сайта или конфигурацию собраний пула.</span><span class="sxs-lookup"><span data-stu-id="05b30-125">**New** Starts a new site meeting configuration or pool meeting configuration.</span></span>

- <span data-ttu-id="05b30-126">**Изменение** Открывает выбранную конфигурацию собрания для ее редактирования, выбирает все конфигурации собраний в списке или удаляет выбранную конфигурацию сайта или конфигурацию пула.</span><span class="sxs-lookup"><span data-stu-id="05b30-126">**Edit** Opens the selected meeting configuration to edit it, selects all meeting configurations in the list, or deletes the selected site configuration or pool configuration.</span></span>

    > [!NOTE]
    > <span data-ttu-id="05b30-127">Для глобальной конфигурации собрания команда **Удалить** восстанавливает значения параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="05b30-127">For the global meeting configuration, **Delete** resets the settings to the default values.</span></span>

- <span data-ttu-id="05b30-128">**Обновление** Обновляет список конфигураций собраний.</span><span class="sxs-lookup"><span data-stu-id="05b30-128">**Refresh** Refreshes the list of meeting configurations.</span></span>

<span data-ttu-id="05b30-129">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="05b30-129">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="05b30-130">**Имя** Определяет конфигурацию собрания.</span><span class="sxs-lookup"><span data-stu-id="05b30-130">**Name** Identifies the meeting configuration.</span></span>

- <span data-ttu-id="05b30-131">**Область** Определяет область конфигурации собрания: глобальную, сайт или пул.</span><span class="sxs-lookup"><span data-stu-id="05b30-131">**Scope** Identifies the scope of the meeting configuration: global, site, or pool.</span></span>

<span data-ttu-id="05b30-132">Дополнительные сведения о работе с конфигурациями собрания см. в разделе [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="05b30-132">For details about working with meeting configurations, see [Create a or modify a Collection of Meeting Configuration Settings](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings) in the Operations documentation.</span></span>