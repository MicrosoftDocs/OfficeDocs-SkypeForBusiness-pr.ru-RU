---
title: Неназначенный номер телефона
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
ROBOTS: NOINDEX, NOFOLLOW
description: Неназначенные номера — это телефонные номера, допустимые для вашей организации, но не назначенные пользователю или телефону. В таблице неназначенных номеров указывается, как обрабатываются такие номера.
ms.openlocfilehash: 1a8992c70d2eb5d82350e4c502f39b6a6641e3c1
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835321"
---
# <a name="unassigned-phone-number"></a><span data-ttu-id="7d9f3-104">Неназначенный номер телефона</span><span class="sxs-lookup"><span data-stu-id="7d9f3-104">Unassigned Phone Number</span></span>

> [!NOTE]
> <span data-ttu-id="7d9f3-105">Exchange единой системы обмена СООБЩЕНИЯМИ остается доступным в Скайп для Business Server 2019 при Скайп для бизнеса 2019 интеграции с Exchange 2013 или Exchange 2016.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="7d9f3-106">Из-за изменения в поддержке в Exchange 2019 интеграции с Exchange единой системы обмена СООБЩЕНИЯМИ, рекомендуется вместо функции голосовой почты в облаке и облачных автосекретаря.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="7d9f3-p103">Неназначенные номера — это телефонные номера, допустимые для вашей организации, но не назначенные пользователю или телефону. В таблице неназначенных номеров указывается, как обрабатываются такие номера.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

<span data-ttu-id="7d9f3-p104">Настройка таблицы неназначенных номеров зависит от способа ее использования. В эту таблицу можно добавить все добавочные номера, используемые в организации, добавить только неназначенные добавочные номера или добавить номера обоих типов. Таблица неназначенных номеров может содержать назначенные и неназначенные номера, но вызывается только в том случае, если звонящий набирает номер, который в настоящее время не назначен. Если вы добавили в таблицу неназначенных номеров все допустимые добавочные номера, то вы можете указать действие, выполняемое при выходе сотрудника в отпуск без необходимости дополнительной настройки таблицы. Если вы добавили в таблицу неназначенные добавочные номера, то вы можете указать действие, выполняемое для определенных номеров. Например, при изменении добавочного номера службы поддержки клиентов вы можете добавить в таблицу старый номер службы поддержки и назначить ему оповещение, которое сообщает новый номер.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-p104">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d9f3-115">Перед настройкой таблицы неназначенных номеров следует уже иметь одно или несколько настроенных извещений или настроить автосекретарь единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-115">Before you configure the unassigned number table, you must have already either defined one or more announcements or set up an Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="7d9f3-116">На странице **Неназначенный номер** отображается список диапазонов неназначенных номеров, определенных для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-116">The **Unassigned Number** page displays a list of the unassigned numbers ranges defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="7d9f3-117">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="7d9f3-117">Tasks you can perform</span></span>

<span data-ttu-id="7d9f3-118">На странице **Неназначенный номер** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="7d9f3-118">You can perform the following tasks from the **Unassigned Number** page:</span></span>

- <span data-ttu-id="7d9f3-119">создать новый диапазон неназначенных номеров;</span><span class="sxs-lookup"><span data-stu-id="7d9f3-119">Create a new unassigned number range</span></span>

- <span data-ttu-id="7d9f3-120">изменить существующий диапазон неназначенных номеров;</span><span class="sxs-lookup"><span data-stu-id="7d9f3-120">Change an existing unassigned number range</span></span>

- <span data-ttu-id="7d9f3-121">удалить диапазон неназначенных номеров;</span><span class="sxs-lookup"><span data-stu-id="7d9f3-121">Delete an unassigned number range</span></span>

- <span data-ttu-id="7d9f3-122">изменить порядок диапазонов неназначенных номеров, чтобы определить, какое действие первым выполняется для входящего звонка, сопоставленного с неназначенным номером.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-122">Change the order of the unassigned number ranges to determine which action should be applied first to an incoming call that matches an unassigned number.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="7d9f3-123">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="7d9f3-123">UI Reference</span></span>

<span data-ttu-id="7d9f3-124">В следующем списке описываются команды на странице.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="7d9f3-125">**Новые** Создает новый диапазон неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-125">**New** Starts a new unassigned number range.</span></span>

- <span data-ttu-id="7d9f3-126">**Изменение** Открывает выбранный диапазон неназначенных номеров для правки, выбирает все диапазоны неназначенных номеров в списке или удаляет выбранный диапазон неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-126">**Edit** Opens the selected unassigned number range for editing, selects all the unassigned number ranges in the list, or deletes the selected unassigned number range.</span></span>

- <span data-ttu-id="7d9f3-127">**Перемещение вверх** Перемещает выбранный диапазон неназначенных номеров копирования в списке, чтобы Скайп для Business Server находит быстрее и применяет указанное действие перед применением действия, указанные для других диапазонов в списке.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-127">**Move up** Moves the selected unassigned number range up in the list so that Skype for Business Server finds it sooner and applies the specified action before applying actions specified for other ranges in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7d9f3-128">Скайп для Business Server выполняет таблицы неназначенных номеров сверху вниз и использует первый диапазон, соответствующий неназначенный номер.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-128">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="7d9f3-129">Например, если у вас есть диапазон, который задает действие, выполняемое в исключительных обстоятельствах, убедитесь, что этот диапазон находится внизу списка.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-129">For example, if you have a range that specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

- <span data-ttu-id="7d9f3-130">**Перемещение вниз** Перемещает выбранный диапазон неназначенных номеров вниз в списке.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-130">**Move down** Moves the selected unassigned number range down in the list.</span></span>

- <span data-ttu-id="7d9f3-131">**Сохранить все** Сохраняет все изменения, внесенные в диапазоны неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-131">**Commit all** Saves all the changes you made to unassigned number ranges.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="7d9f3-132">Эта команда сохраняет все изменения, которые вы внесли на странице **Создание неназначенного номера** и на странице **Изменение неназначенного номера**.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-132">This command saves all the changes that you made on the **New Unassigned Number** page and the **Edit Unassigned Number** page.</span></span>

- <span data-ttu-id="7d9f3-133">**Обновление** Обновляет список диапазонов неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-133">**Refresh** Refreshes the list of unassigned number ranges.</span></span>

<span data-ttu-id="7d9f3-134">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-134">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="7d9f3-135">**Имя** Уникальное имя диапазона неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-135">**Name** The unique name that identifies the unassigned number range.</span></span>

- <span data-ttu-id="7d9f3-136">**Состояние** Показывает, какие диапазоны номеров были сохранены в базу данных и какие — нет.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-136">**State** Shows which number ranges have been saved to the database and which have not.</span></span>

- <span data-ttu-id="7d9f3-137">**Начало диапазона** Первый номер диапазона неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-137">**Start range** The beginning number of the unassigned number range.</span></span>

- <span data-ttu-id="7d9f3-138">**Конец диапазона** Последний номер диапазона неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-138">**End range** The ending number of the unassigned number range.</span></span>

- <span data-ttu-id="7d9f3-139">**Назначения** Идентификатор службы службы приложения, на котором размещается приложение оповещения, который будет обрабатывать входящие звонки для этого диапазона неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-139">**Destination** The service ID of the Application service that hosts the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

- <span data-ttu-id="7d9f3-140">**Оповещения** Извещение, воспроизводимое для этого диапазона неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-140">**Announcement** The announcement that will be played for this range of unassigned numbers.</span></span>

<span data-ttu-id="7d9f3-141">Для получения дополнительных сведений о объявления функций и возможностей см [в приложении объявлений в Скайп для бизнеса](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-141">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="7d9f3-142">Дополнительные сведения о работе с диапазонами неназначенных номеров см. в разделе [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="7d9f3-142">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


