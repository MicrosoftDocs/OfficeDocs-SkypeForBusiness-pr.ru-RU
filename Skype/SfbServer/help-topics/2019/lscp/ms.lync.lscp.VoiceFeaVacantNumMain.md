---
title: Неназначенный номер телефона
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
ROBOTS: NOINDEX, NOFOLLOW
description: Неназначенные номера — это телефонные номера, допустимые для вашей организации, но не назначенные пользователю или телефону. В таблице неназначенных номеров указывается, как обрабатываются такие номера.
ms.openlocfilehash: 2b2c8637e1fa44d8852465b21d2cf494442978b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830139"
---
# <a name="unassigned-phone-number"></a><span data-ttu-id="02021-104">Неназначенный номер телефона</span><span class="sxs-lookup"><span data-stu-id="02021-104">Unassigned Phone Number</span></span>

> [!NOTE]
> <span data-ttu-id="02021-105">При интеграции Skype для бизнеса 2019 с Exchange 2013 или Exchange 2016 в Skype для бизнеса Server 2019 остается доступной um exchange.</span><span class="sxs-lookup"><span data-stu-id="02021-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="02021-106">Из-за изменений в поддержке в Exchange 2019 интеграция с exchange UM будет отостановка в пользу функций облачной голосовой почты и облачных автосекретарь.</span><span class="sxs-lookup"><span data-stu-id="02021-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="02021-p103">Неназначенные номера — это телефонные номера, допустимые для вашей организации, но не назначенные пользователю или телефону. В таблице неназначенных номеров указывается, как обрабатываются такие номера.</span><span class="sxs-lookup"><span data-stu-id="02021-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

<span data-ttu-id="02021-p104">Способ настройки таблицы неназначенных номеров зависит от того, как вы хотите ее использовать. Вы можете настроить таблицу с учетом всех допустимых добавочных номеров для своей организации, только неназначенных добавочных номеров или сочетания обоих типов номеров. Таблица неназначенных номеров может включать в себя как назначенные, так и неназначенные номера, но она вызывается только в том случае, когда звонящий набирает номер, который в данный момент не назначен. Если вы включаете в таблицу неназначенных номеров все допустимые добавочные номера, то можете указать действие, которое выполняется при увольнении человека из организации, благодаря чему вам не требуется изменять настройку данной таблицы. Если вы включаете в таблицу неназначенные добавочные номера, то можете настроить действие, выполняемое для отдельных номеров. Например, если вы изменяете добавочный номер для своего отдела обслуживания клиентов, то можете включить таблицу старый номер этого отдела и назначить ему извещение, содержащее новый номер.</span><span class="sxs-lookup"><span data-stu-id="02021-p104">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02021-115">Перед настройкой таблицы неназначенных номеров следует уже иметь одно или несколько настроенных извещений или настроить автосекретарь единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="02021-115">Before you configure the unassigned number table, you must have already either defined one or more announcements or set up an Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="02021-116">На странице **Неназначенный номер** отображается список диапазонов неназначенных номеров, определенных для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="02021-116">The **Unassigned Number** page displays a list of the unassigned numbers ranges defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="02021-117">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="02021-117">Tasks you can perform</span></span>

<span data-ttu-id="02021-118">На странице **Неназначенный номер** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="02021-118">You can perform the following tasks from the **Unassigned Number** page:</span></span>

- <span data-ttu-id="02021-119">создать новый диапазон неназначенных номеров;</span><span class="sxs-lookup"><span data-stu-id="02021-119">Create a new unassigned number range</span></span>

- <span data-ttu-id="02021-120">изменить существующий диапазон неназначенных номеров;</span><span class="sxs-lookup"><span data-stu-id="02021-120">Change an existing unassigned number range</span></span>

- <span data-ttu-id="02021-121">удалить диапазон неназначенных номеров;</span><span class="sxs-lookup"><span data-stu-id="02021-121">Delete an unassigned number range</span></span>

- <span data-ttu-id="02021-122">изменить порядок диапазонов неназначенных номеров, чтобы определить, какое действие первым выполняется для входящего звонка, сопоставленного с неназначенным номером.</span><span class="sxs-lookup"><span data-stu-id="02021-122">Change the order of the unassigned number ranges to determine which action should be applied first to an incoming call that matches an unassigned number.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="02021-123">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="02021-123">UI Reference</span></span>

<span data-ttu-id="02021-124">В следующем списке описываются команды на странице.</span><span class="sxs-lookup"><span data-stu-id="02021-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="02021-125">**Новый** Запускает новый диапазон ненаписаных номеров.</span><span class="sxs-lookup"><span data-stu-id="02021-125">**New** Starts a new unassigned number range.</span></span>

- <span data-ttu-id="02021-126">**Правка** Открывает выбранный диапазон ненаписаных номеров для редактирования, выбирает все диапазоны ненаписаных номеров в списке или удаляет выбранный диапазон ненаписаных номеров.</span><span class="sxs-lookup"><span data-stu-id="02021-126">**Edit** Opens the selected unassigned number range for editing, selects all the unassigned number ranges in the list, or deletes the selected unassigned number range.</span></span>

- <span data-ttu-id="02021-127">**Вверх** Перемещает выбранный диапазон ненаписаных номеров вверх в списке, чтобы Skype для бизнеса Server быстрее находит его и применяет указанное действие, прежде чем применять действия, указанные для других диапазонов в списке.</span><span class="sxs-lookup"><span data-stu-id="02021-127">**Move up** Moves the selected unassigned number range up in the list so that Skype for Business Server finds it sooner and applies the specified action before applying actions specified for other ranges in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="02021-128">Skype для бизнеса Server выполняет поиск в таблице ненаписаных номеров сверху вниз и использует первый диапазон, соответствующий нена назначенного номера.</span><span class="sxs-lookup"><span data-stu-id="02021-128">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="02021-129">Например, если у вас есть диапазон, который задает действие, выполняемое в исключительных обстоятельствах, убедитесь, что этот диапазон находится внизу списка.</span><span class="sxs-lookup"><span data-stu-id="02021-129">For example, if you have a range that specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

- <span data-ttu-id="02021-130">**Перемещение вниз** Перемещает выбранный диапазон ненаписаных номеров вниз по списку.</span><span class="sxs-lookup"><span data-stu-id="02021-130">**Move down** Moves the selected unassigned number range down in the list.</span></span>

- <span data-ttu-id="02021-131">**Зафиксировать все** Сохраняет все изменения, внесенные в диапазоны ненаписаных номеров.</span><span class="sxs-lookup"><span data-stu-id="02021-131">**Commit all** Saves all the changes you made to unassigned number ranges.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="02021-132">Эта команда сохраняет все изменения, которые вы внесли на странице **Создание неназначенного номера** и странице **Изменение неназначенного номера**.</span><span class="sxs-lookup"><span data-stu-id="02021-132">This command saves all the changes that you made on the **New Unassigned Number** page and the **Edit Unassigned Number** page.</span></span>

- <span data-ttu-id="02021-133">**Обновление** Обновляет список диапазонов ненаписаных номеров.</span><span class="sxs-lookup"><span data-stu-id="02021-133">**Refresh** Refreshes the list of unassigned number ranges.</span></span>

<span data-ttu-id="02021-134">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="02021-134">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="02021-135">**Имя** Уникальное имя, идентифицирует диапазон ненаписаных номеров.</span><span class="sxs-lookup"><span data-stu-id="02021-135">**Name** The unique name that identifies the unassigned number range.</span></span>

- <span data-ttu-id="02021-136">**Состояние** Показывает, какие диапазоны номеров были сохранены в базе данных, а какие нет.</span><span class="sxs-lookup"><span data-stu-id="02021-136">**State** Shows which number ranges have been saved to the database and which have not.</span></span>

- <span data-ttu-id="02021-137">**Диапазон начала** Первый номер диапазона ненаписаных номеров.</span><span class="sxs-lookup"><span data-stu-id="02021-137">**Start range** The beginning number of the unassigned number range.</span></span>

- <span data-ttu-id="02021-138">**Конечный диапазон** Конец диапазона ненаписаных номеров.</span><span class="sxs-lookup"><span data-stu-id="02021-138">**End range** The ending number of the unassigned number range.</span></span>

- <span data-ttu-id="02021-139">**Назначение** ИД службы приложения, в котором размещено приложение "Извещая", которое будет обрабатывать входящие вызовы для этого диапазона ненаписаных номеров.</span><span class="sxs-lookup"><span data-stu-id="02021-139">**Destination** The service ID of the Application service that hosts the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

- <span data-ttu-id="02021-140">**Объявление** Объявление, которое будет играть для этого диапазона ненаписаных номеров.</span><span class="sxs-lookup"><span data-stu-id="02021-140">**Announcement** The announcement that will be played for this range of unassigned numbers.</span></span>

<span data-ttu-id="02021-141">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span><span class="sxs-lookup"><span data-stu-id="02021-141">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="02021-142">Дополнительные сведения о работе с диапазонами неназначенных номеров см. в разделе [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) в документации по применению.</span><span class="sxs-lookup"><span data-stu-id="02021-142">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


