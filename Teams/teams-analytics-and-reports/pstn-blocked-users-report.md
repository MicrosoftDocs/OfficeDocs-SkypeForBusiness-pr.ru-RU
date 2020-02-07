---
title: Отчет о заблокированных пользователях в Microsoft Teams КТСОП
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Узнайте о том, как использовать отчет о заблокированных пользователях PSTN в центре администрирования Microsoft Teams, чтобы получить обзор пользователей Teams в вашей организации, которым запрещено совершать звонки PSTN.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ef4dfbab2b32b088c8e2f8b38b55c15a66eb32
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827347"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a><span data-ttu-id="32960-103">Отчет о заблокированных пользователях в Microsoft Teams КТСОП</span><span class="sxs-lookup"><span data-stu-id="32960-103">Microsoft Teams PSTN blocked users report</span></span>

<span data-ttu-id="32960-104">Отчет о заблокированных пользователях PSTN в центре администрирования Microsoft Teams показывает пользователей в вашей организации, которым запрещено совершать звонки по сети PSTN в Teams.</span><span class="sxs-lookup"><span data-stu-id="32960-104">The PSTN blocked users report in the Microsoft Teams admin center shows you the users in your organization who are blocked from making PSTN calls in Teams.</span></span> <span data-ttu-id="32960-105">Вы можете просмотреть дополнительные сведения о каждом заблокированном пользователе, в том числе назначенный им номер телефона и причину, по которой они были заблокированы для совершения звонков.</span><span class="sxs-lookup"><span data-stu-id="32960-105">You can view more information about each blocked user, including their assigned phone number and the reason they were blocked from making calls.</span></span>

## <a name="view-the-report"></a><span data-ttu-id="32960-106">Просмотр отчета</span><span class="sxs-lookup"><span data-stu-id="32960-106">View the report</span></span>

<span data-ttu-id="32960-107">В левой области навигации центра администрирования Microsoft Teams выберите пункт **Analytics & отчеты** > **об использовании**.</span><span class="sxs-lookup"><span data-stu-id="32960-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="32960-108">На вкладке **Просмотр отчетов** в группе **отчет**выберите пункт **Заблокированные пользователи PSTN**и нажмите кнопку **выполнить отчет**.</span><span class="sxs-lookup"><span data-stu-id="32960-108">On the **View reports** tab, under **Report**, select **PSTN blocked users**, and then click **Run report**.</span></span>

<span data-ttu-id="32960-109">![Снимок экрана: отчет о заблокированных пользователях PSTN в центре администрирования](../media/teams-reports-pstn-blocked-users-with-callouts.png "Снимок экрана: отчет о заблокированных пользователях PSTN в центре администрирования Microsoft Teams с пронумерованными выносками")</span><span class="sxs-lookup"><span data-stu-id="32960-109">![Screenshot of the PSTN blocked users report report in the admin center](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot of the PSTN blocked users report in the Microsoft Teams admin center with numbered callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="32960-110">Толкование отчета</span><span class="sxs-lookup"><span data-stu-id="32960-110">Interpret the report</span></span>

|<span data-ttu-id="32960-111">Выноска</span><span class="sxs-lookup"><span data-stu-id="32960-111">Callout</span></span> |<span data-ttu-id="32960-112">Описание</span><span class="sxs-lookup"><span data-stu-id="32960-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="32960-113">**1**</span><span class="sxs-lookup"><span data-stu-id="32960-113">**1**</span></span>   |<span data-ttu-id="32960-114">Каждый отчет содержит дату создания.</span><span class="sxs-lookup"><span data-stu-id="32960-114">Each report has a date for when it was generated.</span></span> <span data-ttu-id="32960-115">Действия обычно отражаются в отчетах с задержкой в 24-48 ч.</span><span class="sxs-lookup"><span data-stu-id="32960-115">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="32960-116">**2**</span><span class="sxs-lookup"><span data-stu-id="32960-116">**2**</span></span>   |<span data-ttu-id="32960-117">Ось X — это дата.</span><span class="sxs-lookup"><span data-stu-id="32960-117">The X axis is the date.</span></span> <span data-ttu-id="32960-118">Ось Y — это количество пользователей.</span><span class="sxs-lookup"><span data-stu-id="32960-118">The Y axis is the number of users.</span></span> <br><span data-ttu-id="32960-119">Наведите указатель мыши на точку в заданной дате, чтобы увидеть количество пользователей, которые были заблокированы на указанную дату.</span><span class="sxs-lookup"><span data-stu-id="32960-119">Hover over the dot on a given date to see the number of users blocked on that date.</span></span> |
|<span data-ttu-id="32960-120">**3**</span><span class="sxs-lookup"><span data-stu-id="32960-120">**3**</span></span>   |<span data-ttu-id="32960-121">В таблице приводится разделение всех пользователей, которым запрещено совершать звонки по КТСОП.</span><span class="sxs-lookup"><span data-stu-id="32960-121">The table gives a breakdown of all users who are blocked from making PSTN calls.</span></span>  <span data-ttu-id="32960-122">В нем отображаются все пользователи, которым назначена телефонная система или видеоконференции, и предоставляются дополнительные сведения о каждом пользователе.</span><span class="sxs-lookup"><span data-stu-id="32960-122">It shows all users who have Phone System or Audio Conferencing assigned and gives you more information about each user.</span></span> <ul><li><span data-ttu-id="32960-123">**Отображаемое имя** — это отображаемое имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="32960-123">**Display name** is the display name of the user.</span></span> <span data-ttu-id="32960-124">Вы можете щелкнуть отображаемое имя, чтобы перейти на страницу параметров пользователя в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="32960-124">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li> <li><span data-ttu-id="32960-125">**Phone** — номер, назначенный пользователю.</span><span class="sxs-lookup"><span data-stu-id="32960-125">**Phone** is the number that's assigned to the user.</span></span></li> <li><span data-ttu-id="32960-126">**Причина блокировки** — это причина, по которой пользователю запрещено звонить.</span><span class="sxs-lookup"><span data-stu-id="32960-126">**Blocked reason** is the reason the user is blocked from making calls.</span></span></li><li><span data-ttu-id="32960-127">**Заблокированное действие** , указывающее, блокируется ли пользователь и разблокируется от СОВЕРШЕНия коммутируемых звонков в Teams.</span><span class="sxs-lookup"><span data-stu-id="32960-127">**Blocked action**  tells you whether the user is blocked or unblocked from making PSTN calls in Teams.</span></span></li> <li><span data-ttu-id="32960-128">**Время блокировки** — это дата и время (в формате UTC), на которые пользователь блокировал выполнение звонков.</span><span class="sxs-lookup"><span data-stu-id="32960-128">**Blocked time** is the date and time (UTC) that the user was blocked from making calls.</span></span></li></li> </ul><span data-ttu-id="32960-129">Чтобы нужные сведения отображались в таблице, добавьте в нее соответствующие столбцы.</span><span class="sxs-lookup"><span data-stu-id="32960-129">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="32960-130">**4**</span><span class="sxs-lookup"><span data-stu-id="32960-130">**4**</span></span>   |<span data-ttu-id="32960-131">Нажмите **Изменение столбцов**, чтобы добавить или удалить столбцы в таблице.</span><span class="sxs-lookup"><span data-stu-id="32960-131">Select **Edit columns** to add or remove columns in the table.</span></span>|
|<span data-ttu-id="32960-132">**5**</span><span class="sxs-lookup"><span data-stu-id="32960-132">**5**</span></span>   |<span data-ttu-id="32960-133">Щелкните во **весь экран** , чтобы просмотреть отчет в полноэкранном режиме.</span><span class="sxs-lookup"><span data-stu-id="32960-133">Select **Full screen** to view the report in full screen mode.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="32960-134">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="32960-134">Related topics</span></span>

- [<span data-ttu-id="32960-135">Аналитика и отчеты Teams</span><span class="sxs-lookup"><span data-stu-id="32960-135">Teams analytics and reporting</span></span>](teams-reporting-reference.md)