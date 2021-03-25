---
title: Неназначенный номер телефона
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
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
description: Неназначенные номера — это телефонные номера, допустимые для вашей организации, но не назначенные пользователю или телефону. В таблице неназначенных номеров указывается, как обрабатываются такие номера.
ms.openlocfilehash: aeb81aef1b2dba23dc3daaa6ec8a788c0b232529
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122523"
---
# <a name="unassigned-phone-number"></a><span data-ttu-id="da268-104">Неназначенный номер телефона</span><span class="sxs-lookup"><span data-stu-id="da268-104">Unassigned Phone Number</span></span>

<span data-ttu-id="da268-p102">Неназначенные номера — это телефонные номера, допустимые для вашей организации, но не назначенные пользователю или телефону. В таблице неназначенных номеров указывается, как обрабатываются такие номера.</span><span class="sxs-lookup"><span data-stu-id="da268-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

<span data-ttu-id="da268-p103">Способ настройки таблицы неназначенных номеров зависит от того, как вы хотите ее использовать. Вы можете настроить таблицу с учетом всех допустимых добавочных номеров для своей организации, только неназначенных добавочных номеров или сочетания обоих типов номеров. Таблица неназначенных номеров может включать в себя как назначенные, так и неназначенные номера, но она вызывается только в том случае, когда звонящий набирает номер, который в данный момент не назначен. Если вы включаете в таблицу неназначенных номеров все допустимые добавочные номера, то можете указать действие, которое выполняется при увольнении человека из организации, благодаря чему вам не требуется изменять настройку данной таблицы. Если вы включаете в таблицу неназначенные добавочные номера, то можете настроить действие, выполняемое для отдельных номеров. Например, если вы изменяете добавочный номер для своего отдела обслуживания клиентов, то можете включить таблицу старый номер этого отдела и назначить ему извещение, содержащее новый номер.</span><span class="sxs-lookup"><span data-stu-id="da268-p103">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="da268-113">Перед настройкой таблицы неназначенных номеров следует уже иметь одно или несколько настроенных извещений или настроить автосекретарь единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="da268-113">Before you configure the unassigned number table, you must have already either defined one or more announcements or set up an Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="da268-114">На странице **Неназначенный номер** отображается список диапазонов неназначенных номеров, определенных для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="da268-114">The **Unassigned Number** page displays a list of the unassigned numbers ranges defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="da268-115">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="da268-115">Tasks you can perform</span></span>

<span data-ttu-id="da268-116">На странице **Неназначенный номер** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="da268-116">You can perform the following tasks from the **Unassigned Number** page:</span></span>

- <span data-ttu-id="da268-117">создать новый диапазон неназначенных номеров;</span><span class="sxs-lookup"><span data-stu-id="da268-117">Create a new unassigned number range</span></span>

- <span data-ttu-id="da268-118">изменить существующий диапазон неназначенных номеров;</span><span class="sxs-lookup"><span data-stu-id="da268-118">Change an existing unassigned number range</span></span>

- <span data-ttu-id="da268-119">удалить диапазон неназначенных номеров;</span><span class="sxs-lookup"><span data-stu-id="da268-119">Delete an unassigned number range</span></span>

- <span data-ttu-id="da268-120">изменить порядок диапазонов неназначенных номеров, чтобы определить, какое действие первым выполняется для входящего звонка, сопоставленного с неназначенным номером.</span><span class="sxs-lookup"><span data-stu-id="da268-120">Change the order of the unassigned number ranges to determine which action should be applied first to an incoming call that matches an unassigned number.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="da268-121">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="da268-121">UI Reference</span></span>

<span data-ttu-id="da268-122">В следующем списке описываются команды на странице.</span><span class="sxs-lookup"><span data-stu-id="da268-122">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="da268-123">**Новые** Запускает новый диапазон ненаписаных номеров.</span><span class="sxs-lookup"><span data-stu-id="da268-123">**New** Starts a new unassigned number range.</span></span>

- <span data-ttu-id="da268-124">**Изменение** Открывает выбранный диапазон ненаназранных номеров для редактирования, выбирает все ненаназранные диапазоны номеров в списке или удаляет выбранный диапазон ненаназранных номеров.</span><span class="sxs-lookup"><span data-stu-id="da268-124">**Edit** Opens the selected unassigned number range for editing, selects all the unassigned number ranges in the list, or deletes the selected unassigned number range.</span></span>

- <span data-ttu-id="da268-125">**Перемещение вверх** Перемещает выбранный ненанаданный диапазон номеров в списке, чтобы Skype для бизнеса Server нашел его раньше и применял указанное действие, прежде чем применять действия, указанные для других диапазонов в списке.</span><span class="sxs-lookup"><span data-stu-id="da268-125">**Move up** Moves the selected unassigned number range up in the list so that Skype for Business Server finds it sooner and applies the specified action before applying actions specified for other ranges in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="da268-126">Skype для бизнеса Server выполняет поиск по ненаназвершенной таблице номеров сверху вниз и использует первый диапазон, соответствующий ненаназоватому номеру.</span><span class="sxs-lookup"><span data-stu-id="da268-126">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="da268-127">Например, если у вас есть диапазон, который задает действие, выполняемое в исключительных обстоятельствах, убедитесь, что этот диапазон находится внизу списка.</span><span class="sxs-lookup"><span data-stu-id="da268-127">For example, if you have a range that specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

- <span data-ttu-id="da268-128">**Перемещение вниз** Перемещает выбранный диапазон ненаназранных номеров вниз в списке.</span><span class="sxs-lookup"><span data-stu-id="da268-128">**Move down** Moves the selected unassigned number range down in the list.</span></span>

- <span data-ttu-id="da268-129">**Фиксация всех** Сохраняет все изменения, внесенные в диапазоны ненаписаных номеров.</span><span class="sxs-lookup"><span data-stu-id="da268-129">**Commit all** Saves all the changes you made to unassigned number ranges.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="da268-130">Эта команда сохраняет все изменения, которые вы внесли на странице **Создание неназначенного номера** и странице **Изменение неназначенного номера**.</span><span class="sxs-lookup"><span data-stu-id="da268-130">This command saves all the changes that you made on the **New Unassigned Number** page and the **Edit Unassigned Number** page.</span></span>

- <span data-ttu-id="da268-131">**Обновление** Обновляет список ненаписаных диапазонов номеров.</span><span class="sxs-lookup"><span data-stu-id="da268-131">**Refresh** Refreshes the list of unassigned number ranges.</span></span>

<span data-ttu-id="da268-132">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="da268-132">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="da268-133">**Имя** Уникальное имя, которое идентифицирует диапазон ненаназвных номеров.</span><span class="sxs-lookup"><span data-stu-id="da268-133">**Name** The unique name that identifies the unassigned number range.</span></span>

- <span data-ttu-id="da268-134">**Состояние** Показывает, какие диапазоны номеров сохранены в базе данных, а какие нет.</span><span class="sxs-lookup"><span data-stu-id="da268-134">**State** Shows which number ranges have been saved to the database and which have not.</span></span>

- <span data-ttu-id="da268-135">**Диапазон запуска** Начальский номер диапазона неназнамяных номеров.</span><span class="sxs-lookup"><span data-stu-id="da268-135">**Start range** The beginning number of the unassigned number range.</span></span>

- <span data-ttu-id="da268-136">**Конечный диапазон** Конечное число диапазона неназвных номеров.</span><span class="sxs-lookup"><span data-stu-id="da268-136">**End range** The ending number of the unassigned number range.</span></span>

- <span data-ttu-id="da268-137">**Назначение** ID службы приложения, в котором размещено приложение Announcement, которое будет обрабатывать входящие вызовы в этот диапазон ненаписаных номеров.</span><span class="sxs-lookup"><span data-stu-id="da268-137">**Destination** The service ID of the Application service that hosts the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

- <span data-ttu-id="da268-138">**Объявление** Объявление, которое будет отыграно для этого диапазона неназвных номеров.</span><span class="sxs-lookup"><span data-stu-id="da268-138">**Announcement** The announcement that will be played for this range of unassigned numbers.</span></span>

<span data-ttu-id="da268-139">Подробные сведения о возможностях и возможностях объявления см. в документации По планированию в [Skype for Business 2015.](../../plan-your-deployment/enterprise-voice-solution/announcement.md)</span><span class="sxs-lookup"><span data-stu-id="da268-139">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="da268-140">Дополнительные сведения о работе с диапазонами неназначенных номеров см. в разделе [Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers) в документации по применению.</span><span class="sxs-lookup"><span data-stu-id="da268-140">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers) in the Operations documentation.</span></span>