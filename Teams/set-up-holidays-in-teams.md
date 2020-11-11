---
title: Настройка выходных в Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.holidays.overview
- seo-marvel-apr2020
description: Сведения о том, как настроить праздники в Microsoft Teams для использования с автоматическими ассистентами.
ms.openlocfilehash: ff87a3888bc98e1794f8074052aae4c0bbe3545d
ms.sourcegitcommit: 247b2587a60b1609947310ec82d51f47cf829703
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "48993475"
---
# <a name="set-up-holidays-in-microsoft-teams"></a><span data-ttu-id="16058-103">Настройка выходных в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="16058-103">Set up holidays in Microsoft Teams</span></span>

<span data-ttu-id="16058-104">Вы можете использовать функцию "праздники группы" для предоставления альтернативных сообщений и перенаправления тем, чтобы они выработали определенные даты и время, когда отделы, очереди звонков и пользователи в вашей организации будут находиться в разных рабочих часах или не будут доступны.</span><span class="sxs-lookup"><span data-stu-id="16058-104">You can use the Teams Holidays feature to provide alternate messages and routing to callers for specific dates and times when departments, call queues or people in your organization will be following different working hours or won't be available.</span></span> <span data-ttu-id="16058-105">Например, вы можете создать праздничный день для нового года, когда ваша организация может быть закрыта.</span><span class="sxs-lookup"><span data-stu-id="16058-105">For example, you might create a holiday for New Year's day when your organization may be closed.</span></span>

<span data-ttu-id="16058-106">Праздничные дни, которые вы создаете, доступны при [настройке автосекретаря](create-a-phone-system-auto-attendant.md), каждый из которых имеет собственное приветствие и настройки маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="16058-106">The holidays you create here are available when you [set up an auto attendant](create-a-phone-system-auto-attendant.md), each with its own greeting and call routing settings.</span></span>

## <a name="create-a-holiday"></a><span data-ttu-id="16058-107">Создание праздника</span><span class="sxs-lookup"><span data-stu-id="16058-107">Create a holiday</span></span>

<span data-ttu-id="16058-108">Создание праздника</span><span class="sxs-lookup"><span data-stu-id="16058-108">To create a holiday</span></span>

1. <span data-ttu-id="16058-109">В центре администрирования Microsoft Teams перейдите в раздел "Праздничные параметры" в **Организации**  >  **Holidays**.</span><span class="sxs-lookup"><span data-stu-id="16058-109">In the Microsoft Teams admin center, go to **Org-wide settings** > **Holidays**.</span></span>

2. <span data-ttu-id="16058-110">Выберите **новый праздник**.</span><span class="sxs-lookup"><span data-stu-id="16058-110">Select **New holiday**.</span></span>

3. <span data-ttu-id="16058-111">Введите имя праздника.</span><span class="sxs-lookup"><span data-stu-id="16058-111">Enter a name for the holiday.</span></span>

4. <span data-ttu-id="16058-112">Нажмите кнопку **Добавить новую дату**.</span><span class="sxs-lookup"><span data-stu-id="16058-112">Select **Add new date**.</span></span>

5. <span data-ttu-id="16058-113">В разделе **время начала** щелкните значок календаря и выберите дату начала праздника.</span><span class="sxs-lookup"><span data-stu-id="16058-113">Under **Start time** , select the calendar icon and choose the date when you'd like the holiday to begin.</span></span>

6. <span data-ttu-id="16058-114">С помощью раскрывающегося списка выберите время начала праздника.</span><span class="sxs-lookup"><span data-stu-id="16058-114">Use the drop-down list to select a start time for the holiday.</span></span>

7. <span data-ttu-id="16058-115">В разделе **время окончания** щелкните значок календаря и выберите дату окончания праздника.</span><span class="sxs-lookup"><span data-stu-id="16058-115">Under **End time** , select the calendar icon and choose the date when you'd like the holiday to end.</span></span>

8. <span data-ttu-id="16058-116">С помощью раскрывающегося списка выберите время окончания праздника.</span><span class="sxs-lookup"><span data-stu-id="16058-116">Use the drop-down list to select an end time for the holiday.</span></span> <span data-ttu-id="16058-117">**Время окончания** должно быть позже **времени начала**.</span><span class="sxs-lookup"><span data-stu-id="16058-117">The **End time** must be after the **Start time**.</span></span>  

   > [!NOTE]
   > <span data-ttu-id="16058-118">Если праздник за один целый день (например, в течение 24 часов), **время окончания** должно быть установлено на следующий день, а время — на 12:00.</span><span class="sxs-lookup"><span data-stu-id="16058-118">If the holiday is for one full day (i.e., a 24 hour period), the **End time** should be set to the next day and the time to 12:00 AM.</span></span> <span data-ttu-id="16058-119">Например, если ваша организация закрылась 1 января для нового года, установите **время начала** в январе 1 12:00, а затем укажите **время окончания** на 2 января 12:00 г.</span><span class="sxs-lookup"><span data-stu-id="16058-119">For example, if your organization is closed on January 1 for New Year's day, set the **Start time** to January 1 12:00 AM and set the **End time** to January 2 @ 12:00 AM.</span></span>

9. <span data-ttu-id="16058-120">При необходимости добавьте дополнительные даты для повторяющихся праздников.</span><span class="sxs-lookup"><span data-stu-id="16058-120">Optionally, add more dates for recurring holidays.</span></span>

10. <span data-ttu-id="16058-121">Нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="16058-121">Select **Save**.</span></span>

    ![Снимок экрана: Пользовательский интерфейс праздников с датами, заданными в течение трех лет](media/holidays-set-up.png)

## <a name="change-a-holiday"></a><span data-ttu-id="16058-123">Изменение праздника</span><span class="sxs-lookup"><span data-stu-id="16058-123">Change a holiday</span></span>

<span data-ttu-id="16058-124">Изменение праздников</span><span class="sxs-lookup"><span data-stu-id="16058-124">To change a holiday</span></span>

1. <span data-ttu-id="16058-125">В центре администрирования Microsoft Teams перейдите в раздел "Праздничные параметры" в **Организации**  >  **Holidays**.</span><span class="sxs-lookup"><span data-stu-id="16058-125">In the Microsoft Teams admin center, go to **Org-wide settings** > **Holidays**.</span></span>

2. <span data-ttu-id="16058-126">Выберите праздничный день в списке.</span><span class="sxs-lookup"><span data-stu-id="16058-126">Select the holiday from the list.</span></span>

3. <span data-ttu-id="16058-127">В разделе **время начала** щелкните значок календаря и выберите дату начала праздника.</span><span class="sxs-lookup"><span data-stu-id="16058-127">Under **Start time** , select the calendar icon and choose the date when you'd like the holiday to begin.</span></span>

4. <span data-ttu-id="16058-128">С помощью раскрывающегося списка выберите время начала праздника.</span><span class="sxs-lookup"><span data-stu-id="16058-128">Use the drop-down list to select a start time for the holiday.</span></span>

5. <span data-ttu-id="16058-129">В разделе **время окончания** щелкните значок календаря и выберите дату окончания праздника.</span><span class="sxs-lookup"><span data-stu-id="16058-129">Under **End time** , select the calendar icon and choose the date when you'd like the holiday to end.</span></span> 

6. <span data-ttu-id="16058-130">С помощью раскрывающегося списка выберите время окончания праздника.</span><span class="sxs-lookup"><span data-stu-id="16058-130">Use the drop-down list to select an end time for the holiday.</span></span> <span data-ttu-id="16058-131">**Время окончания** должно быть позже **времени начала**.</span><span class="sxs-lookup"><span data-stu-id="16058-131">The **End time** must be after the **Start time**.</span></span>  

7. <span data-ttu-id="16058-132">Нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="16058-132">Select **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="16058-133">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="16058-133">Related topics</span></span>

<span data-ttu-id="16058-134">[Планирование автосекретарей и очередей звонков в Teams](plan-auto-attendant-call-queue.md)</span><span class="sxs-lookup"><span data-stu-id="16058-134">[Plan for Teams auto attendants and call queues](plan-auto-attendant-call-queue.md)?</span></span>
