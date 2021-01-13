---
title: Отчет о заблокированных пользователях STN в Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Используйте отчет о заблокированных пользователях НН В Центре администрирования Microsoft Teams, чтобы получить общие сведения о пользователях Teams вашей организации, которые не могут делать звонки по ДНР.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ed775c3796e40a775b3be2b78f22e162a047bf78
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809339"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a><span data-ttu-id="fda27-103">Отчет о заблокированных пользователях STN в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fda27-103">Microsoft Teams PSTN blocked users report</span></span>

<span data-ttu-id="fda27-104">Отчет о заблокированных пользователях ДНР в Центре администрирования Microsoft Teams содержит пользователей в вашей организации, которым запрещены звонки по ПС в Teams.</span><span class="sxs-lookup"><span data-stu-id="fda27-104">The PSTN blocked users report in the Microsoft Teams admin center shows you the users in your organization who are blocked from making PSTN calls in Teams.</span></span> <span data-ttu-id="fda27-105">Вы можете просмотреть дополнительные сведения о каждом заблокированном пользователе, включая его номер телефона и причину блокировки звонков.</span><span class="sxs-lookup"><span data-stu-id="fda27-105">You can view more information about each blocked user, including their assigned phone number and the reason they were blocked from making calls.</span></span>

## <a name="view-the-pstn-blocked-users-report"></a><span data-ttu-id="fda27-106">Просмотр отчета о заблокированных пользователях ДНР</span><span class="sxs-lookup"><span data-stu-id="fda27-106">View the PSTN blocked users report</span></span>

<span data-ttu-id="fda27-107">В левой области навигации Центра администрирования Microsoft Teams щелкните **"Аналитика** и & отчеты об  >  **использовании".**</span><span class="sxs-lookup"><span data-stu-id="fda27-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="fda27-108">На **вкладке "Просмотр отчетов" в** **области "Отчет"** выберите пользователей, заблокированных по ДНР, и нажмите кнопку "Выполнить **отчет".**</span><span class="sxs-lookup"><span data-stu-id="fda27-108">On the **View reports** tab, under **Report**, select **PSTN blocked users**, and then click **Run report**.</span></span>

<span data-ttu-id="fda27-109">![Снимок экрана: отчет о заблокированных пользователях ННР в Центре администрирования](../media/teams-reports-pstn-blocked-users-with-callouts.png "Снимок экрана: отчет о заблокированных пользователях через ДНР в Центре администрирования Microsoft Teams с пронуненными перетаском")</span><span class="sxs-lookup"><span data-stu-id="fda27-109">![Screenshot of the PSTN blocked users report report in the admin center](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot of the PSTN blocked users report in the Microsoft Teams admin center with numbered callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="fda27-110">Толкование отчета</span><span class="sxs-lookup"><span data-stu-id="fda27-110">Interpret the report</span></span>

|<span data-ttu-id="fda27-111">Выноска</span><span class="sxs-lookup"><span data-stu-id="fda27-111">Callout</span></span> |<span data-ttu-id="fda27-112">Описание</span><span class="sxs-lookup"><span data-stu-id="fda27-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="fda27-113">**1**</span><span class="sxs-lookup"><span data-stu-id="fda27-113">**1**</span></span>   |<span data-ttu-id="fda27-114">В каждом отчете есть дата, на протяжении которых он был создан.</span><span class="sxs-lookup"><span data-stu-id="fda27-114">Each report has a date for when it was generated.</span></span> <span data-ttu-id="fda27-115">Действия обычно отражаются в отчетах с задержкой в 24-48 ч.</span><span class="sxs-lookup"><span data-stu-id="fda27-115">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="fda27-116">**2**</span><span class="sxs-lookup"><span data-stu-id="fda27-116">**2**</span></span>   |<span data-ttu-id="fda27-117">Ось X — это дата.</span><span class="sxs-lookup"><span data-stu-id="fda27-117">The X axis is the date.</span></span> <span data-ttu-id="fda27-118">Ось Y — это количество пользователей.</span><span class="sxs-lookup"><span data-stu-id="fda27-118">The Y axis is the number of users.</span></span> <br><span data-ttu-id="fda27-119">Наведите курсор на точку в заданную дату, чтобы узнать количество пользователей, заблокированных в этот день.</span><span class="sxs-lookup"><span data-stu-id="fda27-119">Hover over the dot on a given date to see the number of users blocked on that date.</span></span> |
|<span data-ttu-id="fda27-120">**3**</span><span class="sxs-lookup"><span data-stu-id="fda27-120">**3**</span></span>   |<span data-ttu-id="fda27-121">В таблице приводится разбивка всех пользователей, которым не заблокирована возможность звонков по ДНР.</span><span class="sxs-lookup"><span data-stu-id="fda27-121">The table gives a breakdown of all users who are blocked from making PSTN calls.</span></span>  <span data-ttu-id="fda27-122">Здесь показаны все пользователи, которым назначена телефонная система или аудиоконференция, и предоставляется больше сведений о каждом из них.</span><span class="sxs-lookup"><span data-stu-id="fda27-122">It shows all users who have Phone System or Audio Conferencing assigned and gives you more information about each user.</span></span> <ul><li><span data-ttu-id="fda27-123">**Отображаемая** имя — это отображаемая имя пользователя.</span><span class="sxs-lookup"><span data-stu-id="fda27-123">**Display name** is the display name of the user.</span></span> <span data-ttu-id="fda27-124">Щелкните отображаемого имя, чтобы перейти на страницу параметров пользователя в Центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fda27-124">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li> <li><span data-ttu-id="fda27-125">**Телефон** — это номер, который назначен пользователю.</span><span class="sxs-lookup"><span data-stu-id="fda27-125">**Phone** is the number that's assigned to the user.</span></span></li> <li><span data-ttu-id="fda27-126">**Причина блокировки —** это причина, по которой пользователь не может звонить.</span><span class="sxs-lookup"><span data-stu-id="fda27-126">**Blocked reason** is the reason the user is blocked from making calls.</span></span></li><li><span data-ttu-id="fda27-127">**Заблокированные действия**  подсказывает, заблокирован ли пользователь или разблокирован в отношении звонков по ДНР в Teams.</span><span class="sxs-lookup"><span data-stu-id="fda27-127">**Blocked action**  tells you whether the user is blocked or unblocked from making PSTN calls in Teams.</span></span></li> <li><span data-ttu-id="fda27-128">**Заблокированные время —** это дата и время (UTC), на которые пользователю было заблокировано звонки.</span><span class="sxs-lookup"><span data-stu-id="fda27-128">**Blocked time** is the date and time (UTC) that the user was blocked from making calls.</span></span></li></li> </ul><span data-ttu-id="fda27-129">Чтобы нужные сведения отображались в таблице, добавьте в нее соответствующие столбцы.</span><span class="sxs-lookup"><span data-stu-id="fda27-129">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="fda27-130">**4**</span><span class="sxs-lookup"><span data-stu-id="fda27-130">**4**</span></span>   |<span data-ttu-id="fda27-131">Нажмите **Изменение столбцов**, чтобы добавить или удалить столбцы в таблице.</span><span class="sxs-lookup"><span data-stu-id="fda27-131">Select **Edit columns** to add or remove columns in the table.</span></span>|
|<span data-ttu-id="fda27-132">**5**</span><span class="sxs-lookup"><span data-stu-id="fda27-132">**5**</span></span>   |<span data-ttu-id="fda27-133">Чтобы **просмотреть отчет** в полноэкранном режиме, выберите "Во весь экран".</span><span class="sxs-lookup"><span data-stu-id="fda27-133">Select **Full screen** to view the report in full screen mode.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="fda27-134">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="fda27-134">Related topics</span></span>

- [<span data-ttu-id="fda27-135">Аналитика и отчеты Teams</span><span class="sxs-lookup"><span data-stu-id="fda27-135">Teams analytics and reporting</span></span>](teams-reporting-reference.md)