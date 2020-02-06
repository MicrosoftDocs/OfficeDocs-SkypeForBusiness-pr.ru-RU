---
title: Неназначенный номер телефона
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 622651aa623cba3c7eb5e2a4d9566009dd361e46
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41792157"
---
# <a name="unassigned-phone-number"></a><span data-ttu-id="c023a-104">Неназначенный номер телефона</span><span class="sxs-lookup"><span data-stu-id="c023a-104">Unassigned Phone Number</span></span>

> [!NOTE]
> <span data-ttu-id="c023a-105">Единая система обмена сообщениями Exchange остается доступной в Skype для бизнеса Server 2019 при интеграции Skype для бизнеса 2019 с Exchange 2013 или Exchange 2016.</span><span class="sxs-lookup"><span data-stu-id="c023a-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="c023a-106">Из-за изменений в службе поддержки в Exchange 2019 интеграция Exchange UM не выделена в пользу того, чтобы отфильтровать голосовую почту и функции автосекретаря в облаке.</span><span class="sxs-lookup"><span data-stu-id="c023a-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="c023a-p103">Неназначенные номера — это телефонные номера, допустимые для вашей организации, но не назначенные пользователю или телефону. В таблице неназначенных номеров указывается, как обрабатываются такие номера.</span><span class="sxs-lookup"><span data-stu-id="c023a-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

<span data-ttu-id="c023a-p104">Настройка таблицы неназначенных номеров зависит от способа ее использования. В эту таблицу можно добавить все добавочные номера, используемые в организации, добавить только неназначенные добавочные номера или добавить номера обоих типов. Таблица неназначенных номеров может содержать назначенные и неназначенные номера, но вызывается только в том случае, если звонящий набирает номер, который в настоящее время не назначен. Если вы добавили в таблицу неназначенных номеров все допустимые добавочные номера, то вы можете указать действие, выполняемое при выходе сотрудника в отпуск без необходимости дополнительной настройки таблицы. Если вы добавили в таблицу неназначенные добавочные номера, то вы можете указать действие, выполняемое для определенных номеров. Например, при изменении добавочного номера службы поддержки клиентов вы можете добавить в таблицу старый номер службы поддержки и назначить ему оповещение, которое сообщает новый номер.</span><span class="sxs-lookup"><span data-stu-id="c023a-p104">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c023a-115">Перед настройкой таблицы неназначенных номеров следует уже иметь одно или несколько настроенных извещений или настроить автосекретарь единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="c023a-115">Before you configure the unassigned number table, you must have already either defined one or more announcements or set up an Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="c023a-116">На странице **Неназначенный номер** отображается список диапазонов неназначенных номеров, определенных для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c023a-116">The **Unassigned Number** page displays a list of the unassigned numbers ranges defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="c023a-117">Задачи, которые вы можете выполнить</span><span class="sxs-lookup"><span data-stu-id="c023a-117">Tasks you can perform</span></span>

<span data-ttu-id="c023a-118">На странице **Неназначенный номер** можно выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="c023a-118">You can perform the following tasks from the **Unassigned Number** page:</span></span>

- <span data-ttu-id="c023a-119">создать новый диапазон неназначенных номеров;</span><span class="sxs-lookup"><span data-stu-id="c023a-119">Create a new unassigned number range</span></span>

- <span data-ttu-id="c023a-120">изменить существующий диапазон неназначенных номеров;</span><span class="sxs-lookup"><span data-stu-id="c023a-120">Change an existing unassigned number range</span></span>

- <span data-ttu-id="c023a-121">удалить диапазон неназначенных номеров;</span><span class="sxs-lookup"><span data-stu-id="c023a-121">Delete an unassigned number range</span></span>

- <span data-ttu-id="c023a-122">изменить порядок диапазонов неназначенных номеров, чтобы определить, какое действие первым выполняется для входящего звонка, сопоставленного с неназначенным номером.</span><span class="sxs-lookup"><span data-stu-id="c023a-122">Change the order of the unassigned number ranges to determine which action should be applied first to an incoming call that matches an unassigned number.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="c023a-123">Ссылка на пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="c023a-123">UI Reference</span></span>

<span data-ttu-id="c023a-124">В следующем списке описываются команды на странице.</span><span class="sxs-lookup"><span data-stu-id="c023a-124">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="c023a-125">**Новые** Начало нового неназначенного диапазона номеров.</span><span class="sxs-lookup"><span data-stu-id="c023a-125">**New** Starts a new unassigned number range.</span></span>

- <span data-ttu-id="c023a-126">**Изменить** Открытие выделенного диапазона чисел, неназначенных для редактирования, выбор всех неназначенных диапазонов номеров в списке или удаление выделенного диапазона номеров, неназначенных.</span><span class="sxs-lookup"><span data-stu-id="c023a-126">**Edit** Opens the selected unassigned number range for editing, selects all the unassigned number ranges in the list, or deletes the selected unassigned number range.</span></span>

- <span data-ttu-id="c023a-127">**Переместить вверх** Перемещение выделенного диапазона неназначенных номеров вверх в списке, чтобы приложение Skype для бизнеса Server обнаружило ее раньше и применяет указанные действия для других диапазонов в списке.</span><span class="sxs-lookup"><span data-stu-id="c023a-127">**Move up** Moves the selected unassigned number range up in the list so that Skype for Business Server finds it sooner and applies the specified action before applying actions specified for other ranges in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c023a-128">Skype для бизнеса Server ищет в таблице неназначенные номера сверху вниз и использует первый диапазон, который соответствует неназначенному номеру.</span><span class="sxs-lookup"><span data-stu-id="c023a-128">Skype for Business Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="c023a-129">Например, если у вас есть диапазон, который задает действие, выполняемое в исключительных обстоятельствах, убедитесь, что этот диапазон находится внизу списка.</span><span class="sxs-lookup"><span data-stu-id="c023a-129">For example, if you have a range that specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

- <span data-ttu-id="c023a-130">**Переместить вниз** Перемещение выбранного диапазона неназначенных номеров вниз в списке.</span><span class="sxs-lookup"><span data-stu-id="c023a-130">**Move down** Moves the selected unassigned number range down in the list.</span></span>

- <span data-ttu-id="c023a-131">**Зафиксировать все** Сохранение всех изменений, внесенных в неназначенные диапазоны номеров.</span><span class="sxs-lookup"><span data-stu-id="c023a-131">**Commit all** Saves all the changes you made to unassigned number ranges.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c023a-132">Эта команда сохраняет все изменения, которые вы внесли на странице **Создание неназначенного номера** и на странице **Изменение неназначенного номера**.</span><span class="sxs-lookup"><span data-stu-id="c023a-132">This command saves all the changes that you made on the **New Unassigned Number** page and the **Edit Unassigned Number** page.</span></span>

- <span data-ttu-id="c023a-133">**Обновить** Обновляет список неназначенных диапазонов номеров.</span><span class="sxs-lookup"><span data-stu-id="c023a-133">**Refresh** Refreshes the list of unassigned number ranges.</span></span>

<span data-ttu-id="c023a-134">В следующем списке описываются поля на странице.</span><span class="sxs-lookup"><span data-stu-id="c023a-134">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="c023a-135">**Name (имя** ) Уникальное имя, определяющее неназначенный диапазон номеров.</span><span class="sxs-lookup"><span data-stu-id="c023a-135">**Name** The unique name that identifies the unassigned number range.</span></span>

- <span data-ttu-id="c023a-136">**Состояние** Показывает, какие диапазоны номеров были сохранены в базе данных, а какие — нет.</span><span class="sxs-lookup"><span data-stu-id="c023a-136">**State** Shows which number ranges have been saved to the database and which have not.</span></span>

- <span data-ttu-id="c023a-137">**Начальный диапазон** Начальный номер диапазона неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="c023a-137">**Start range** The beginning number of the unassigned number range.</span></span>

- <span data-ttu-id="c023a-138">**Конечный диапазон** Конечный номер диапазона неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="c023a-138">**End range** The ending number of the unassigned number range.</span></span>

- <span data-ttu-id="c023a-139">**Destination (назначение** ) Идентификатор службы приложения, на котором размещается приложение объявления, которое будет обрабатывать входящие звонки в этот диапазон неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="c023a-139">**Destination** The service ID of the Application service that hosts the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

- <span data-ttu-id="c023a-140">**Объявление** Объявление, которое будет воспроизводиться для этого диапазона неназначенных номеров.</span><span class="sxs-lookup"><span data-stu-id="c023a-140">**Announcement** The announcement that will be played for this range of unassigned numbers.</span></span>

<span data-ttu-id="c023a-141">Дополнительные сведения о функциях и возможностях объявлений вы увидите в разделе [Планирование приложения для объявлений в Skype для бизнеса](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="c023a-141">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="c023a-142">Дополнительные сведения о работе с диапазонами неназначенных номеров см. в разделе [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) документации по использованию.</span><span class="sxs-lookup"><span data-stu-id="c023a-142">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


