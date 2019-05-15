---
title: Неназначенный номер телефона
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
description: Неназначенные номера — это телефонные номера, допустимые для вашей организации, но не назначенные пользователю или телефону. В таблице неназначенных номеров указывается, как обрабатываются такие номера.
ms.openlocfilehash: fc182388af06d75c6a9f7762127c74daf7cd4f0b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929043"
---
# <a name="unassigned-phone-number"></a><span data-ttu-id="f3e9b-104">Неназначенный номер телефона</span><span class="sxs-lookup"><span data-stu-id="f3e9b-104">Unassigned Phone Number</span></span>

<span data-ttu-id="f3e9b-p102">Неназначенные номера — это телефонные номера, допустимые для вашей организации, но не назначенные пользователю или телефону. В таблице неназначенных номеров указывается, как обрабатываются такие номера.</span><span class="sxs-lookup"><span data-stu-id="f3e9b-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

<span data-ttu-id="f3e9b-p103">Настройка таблицы неназначенных номеров зависит от способа ее использования. В эту таблицу можно добавить все добавочные номера, используемые в организации, добавить только неназначенные добавочные номера или добавить номера обоих типов. Таблица неназначенных номеров может содержать назначенные и неназначенные номера, но вызывается только в том случае, если звонящий набирает номер, который в настоящее время не назначен. Если вы добавили в таблицу неназначенных номеров все допустимые добавочные номера, то вы можете указать действие, выполняемое при выходе сотрудника в отпуск без необходимости дополнительной настройки таблицы. Если вы добавили в таблицу неназначенные добавочные номера, то вы можете указать действие, выполняемое для определенных номеров. Например, при изменении добавочного номера службы поддержки клиентов вы можете добавить в таблицу старый номер службы поддержки и назначить ему оповещение, которое сообщает новый номер.</span><span class="sxs-lookup"><span data-stu-id="f3e9b-p103">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f3e9b-113">Перед настройкой таблицы неназначенных номеров следует уже иметь одно или несколько настроенных извещений или настроить автосекретарь единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="f3e9b-113">Before you configure the unassigned number table, you must have already either defined one or more announcements or set up an Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="f3e9b-114">На странице **Неназначенный номер** отображается список диапазонов неназначенных номеров, определенных для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f3e9b-114">The **Unassigned Number** page displays a list of the unassigned numbers ranges defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="f3e9b-115">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="f3e9b-115">Tasks you can perform</span></span>

<span data-ttu-id="f3e9b-116">На странице **Неназначенный номер** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="f3e9b-116">You can perform the following tasks from the **Unassigned Number** page:</span></span>

- <span data-ttu-id="f3e9b-117">создать новый диапазон неназначенных номеров;</span><span class="sxs-lookup"><span data-stu-id="f3e9b-117">Create a new unassigned number range</span></span>

- <span data-ttu-id="f3e9b-118">изменить существующий диапазон неназначенных номеров;</span><span class="sxs-lookup"><span data-stu-id="f3e9b-118">Change an existing unassigned number range</span></span>

- <span data-ttu-id="f3e9b-119">удалить диапазон неназначенных номеров;</span><span class="sxs-lookup"><span data-stu-id="f3e9b-119">Delete an unassigned number range</span></span>

- <span data-ttu-id="f3e9b-120">изменить порядок диапазонов неназначенных номеров, чтобы определить, какое действие первым выполняется для входящего звонка, сопоставленного с неназначенным номером.</span><span class="sxs-lookup"><span data-stu-id="f3e9b-120">Change the order of the unassigned number ranges to determine which action should be applied first to an incoming call that matches an unassigned number.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="f3e9b-121">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="f3e9b-121">UI Reference</span></span>

<span data-ttu-id="f3e9b-122">В следующем списке описываются команды на странице.</span><span class="sxs-lookup"><span data-stu-id="f3e9b-122">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="f3e9b-123">**Новые** Создает новый диапазон неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="f3e9b-123">**New** Starts a new unassigned number range.</span></span>

- <span data-ttu-id="f3e9b-124">**Изменение** Открывает выбранный диапазон неназначенных номеров для правки, выбирает все диапазоны неназначенных номеров в списке или удаляет выбранный диапазон неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="f3e9b-124">**Edit** Opens the selected unassigned number range for editing, selects all the unassigned number ranges in the list, or deletes the selected unassigned number range.</span></span>

- <span data-ttu-id="f3e9b-125">**Перемещение вверх** Перемещает выбранный диапазон неназначенных номеров копирования в списке, чтобы Скайп для Business Server находит быстрее и применяет указанное действие перед применением действия, указанные для других диапазонов в списке.</span><span class="sxs-lookup"><span data-stu-id="f3e9b-125">**Move up** Moves the selected unassigned number range up in the list so that Skype for Business Server finds it sooner and applies the specified action before applying actions specified for other ranges in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f3e9b-126">Скайп для Business Server выполняет таблицы неназначенных номеров сверху вниз и использует первый диапазон, соответствующий неназначенный номер.</span><span class="sxs-lookup"><span data-stu-id="f3e9b-126">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="f3e9b-127">Например, если у вас есть диапазон, который задает действие, выполняемое в исключительных обстоятельствах, убедитесь, что этот диапазон находится внизу списка.</span><span class="sxs-lookup"><span data-stu-id="f3e9b-127">For example, if you have a range that specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

- <span data-ttu-id="f3e9b-128">**Перемещение вниз** Перемещает выбранный диапазон неназначенных номеров вниз в списке.</span><span class="sxs-lookup"><span data-stu-id="f3e9b-128">**Move down** Moves the selected unassigned number range down in the list.</span></span>

- <span data-ttu-id="f3e9b-129">**Сохранить все** Сохраняет все изменения, внесенные в диапазоны неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="f3e9b-129">**Commit all** Saves all the changes you made to unassigned number ranges.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f3e9b-130">Эта команда сохраняет все изменения, которые вы внесли на странице **Создание неназначенного номера** и на странице **Изменение неназначенного номера**.</span><span class="sxs-lookup"><span data-stu-id="f3e9b-130">This command saves all the changes that you made on the **New Unassigned Number** page and the **Edit Unassigned Number** page.</span></span>

- <span data-ttu-id="f3e9b-131">**Обновление** Обновляет список диапазонов неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="f3e9b-131">**Refresh** Refreshes the list of unassigned number ranges.</span></span>

<span data-ttu-id="f3e9b-132">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="f3e9b-132">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="f3e9b-133">**Имя** Уникальное имя диапазона неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="f3e9b-133">**Name** The unique name that identifies the unassigned number range.</span></span>

- <span data-ttu-id="f3e9b-134">**Состояние** Показывает, какие диапазоны номеров были сохранены в базу данных и какие — нет.</span><span class="sxs-lookup"><span data-stu-id="f3e9b-134">**State** Shows which number ranges have been saved to the database and which have not.</span></span>

- <span data-ttu-id="f3e9b-135">**Начало диапазона** Первый номер диапазона неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="f3e9b-135">**Start range** The beginning number of the unassigned number range.</span></span>

- <span data-ttu-id="f3e9b-136">**Конец диапазона** Последний номер диапазона неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="f3e9b-136">**End range** The ending number of the unassigned number range.</span></span>

- <span data-ttu-id="f3e9b-137">**Назначения** Идентификатор службы службы приложения, на котором размещается приложение оповещения, который будет обрабатывать входящие звонки для этого диапазона неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="f3e9b-137">**Destination** The service ID of the Application service that hosts the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

- <span data-ttu-id="f3e9b-138">**Оповещения** Извещение, воспроизводимое для этого диапазона неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="f3e9b-138">**Announcement** The announcement that will be played for this range of unassigned numbers.</span></span>

<span data-ttu-id="f3e9b-139">Для получения дополнительных сведений о объявления функций и возможностей см [в приложении объявлений в Скайп для бизнеса 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="f3e9b-139">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="f3e9b-140">Дополнительные сведения о работе с диапазонами неназначенных номеров см. в разделе [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="f3e9b-140">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


