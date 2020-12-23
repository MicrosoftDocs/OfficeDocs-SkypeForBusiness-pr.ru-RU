---
title: Просмотр заданий политики в журнале действий в Центре администрирования Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Узнайте, как просматривать действия с назначением политики в журнале действий в Центре администрирования Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f85899869a8578df59516d0e0d702f8e36bd951
ms.sourcegitcommit: 47637ed816b471fe689e7bdac27b73e6efced60c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44374297"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a><span data-ttu-id="64a2c-103">Просмотр назначений политики в журнале действий</span><span class="sxs-lookup"><span data-stu-id="64a2c-103">View your policy assignments in the Activity log</span></span>

<span data-ttu-id="64a2c-104">Назначая политики пользователям в Центре администрирования Microsoft Teams, вы можете просматривать их состояние в журнале действий.</span><span class="sxs-lookup"><span data-stu-id="64a2c-104">When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log.</span></span> <span data-ttu-id="64a2c-105">В журнале действий показаны назначения политик более чем 20 пользователям через Центр администрирования Microsoft Teams за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="64a2c-105">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="64a2c-106">Имейте в виду, что в журнале действий не показываются назначения пакетов политики, назначения политик пакетам менее 20 пользователей через Центр администрирования Microsoft Teams или назначения политик через PowerShell.</span><span class="sxs-lookup"><span data-stu-id="64a2c-106">Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.</span></span>

![Снимок экрана: страница журнала действий](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a><span data-ttu-id="64a2c-108">Просмотр действий с назначением политики в журнале действий</span><span class="sxs-lookup"><span data-stu-id="64a2c-108">View your policy assignment activities in the Activity log</span></span>

<span data-ttu-id="64a2c-109">Чтобы просмотреть назначения политики в журнале действий:</span><span class="sxs-lookup"><span data-stu-id="64a2c-109">To view your policy assignments in the Activity log:</span></span>

1. <span data-ttu-id="64a2c-110">В левой области навигации Центра администрирования Microsoft Teams перейдите на панель **мониторинга,** а затем в журнале действий выберите "Просмотреть **сведения".**</span><span class="sxs-lookup"><span data-stu-id="64a2c-110">In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.</span></span>
2. <span data-ttu-id="64a2c-111">Вы можете просмотреть все назначения политики или отфильтровать список по статусу, чтобы отфильтровать только те **назначения,** которые не были на запущены, выполнены или **завершены.**</span><span class="sxs-lookup"><span data-stu-id="64a2c-111">You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**.</span></span> <span data-ttu-id="64a2c-112">Вы увидите следующие сведения о каждом задании:</span><span class="sxs-lookup"><span data-stu-id="64a2c-112">You'll see the following information about each assignment:</span></span>
    - <span data-ttu-id="64a2c-113">**Name**: имя назначения политики.</span><span class="sxs-lookup"><span data-stu-id="64a2c-113">**Name**: The name of the policy assignment.</span></span> <span data-ttu-id="64a2c-114">Щелкните ссылку, чтобы просмотреть дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="64a2c-114">Click the link to view more details.</span></span> <span data-ttu-id="64a2c-115">Это включает количество пользователей, которые назначены политике, и количество заданий, которые были выполнены, выполнены и не на начато.</span><span class="sxs-lookup"><span data-stu-id="64a2c-115">This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started.</span></span> <span data-ttu-id="64a2c-116">Вы также увидите список пользователей в пакете, а также состояние и результат для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="64a2c-116">You'll also see the list of users in the batch, and the status and result for each user.</span></span> <span data-ttu-id="64a2c-117">Ниже приводится пример.</span><span class="sxs-lookup"><span data-stu-id="64a2c-117">Here's an example:</span></span>

        ![Снимок экрана:](media/activity-log-policy-assignment-detail.png)

    - <span data-ttu-id="64a2c-119">**Отправлено:** дата и время отправки назначения политики.</span><span class="sxs-lookup"><span data-stu-id="64a2c-119">**Submitted**: Date and time the policy assignment was submitted.</span></span>
    - <span data-ttu-id="64a2c-120">**Время завершения:** дата и время завершения назначения политики.</span><span class="sxs-lookup"><span data-stu-id="64a2c-120">**Completion time**: Date and time the policy assignment was completed.</span></span>
    - <span data-ttu-id="64a2c-121">**Влияние на:** количество пользователей в пакете.</span><span class="sxs-lookup"><span data-stu-id="64a2c-121">**Impact on**: Number of users in the batch.</span></span>
    - <span data-ttu-id="64a2c-122">**Общее состояние:** состояние назначения политики.</span><span class="sxs-lookup"><span data-stu-id="64a2c-122">**Overall status**: Status of the policy assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="64a2c-123">Вы также можете зайти в журнал действий на странице **"Пользователи".**</span><span class="sxs-lookup"><span data-stu-id="64a2c-123">You can also get to the Activity log from the **Users** page.</span></span> <span data-ttu-id="64a2c-124">После того  как вы нажмете кнопку "Применить", чтобы отправить массовое назначение политики, вы увидите баннер в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="64a2c-124">After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page.</span></span> <span data-ttu-id="64a2c-125">Щелкните **ссылку журнала действий** в заголовке.</span><span class="sxs-lookup"><span data-stu-id="64a2c-125">Click the **Activity log** link in the banner.</span></span>

## <a name="related-topics"></a><span data-ttu-id="64a2c-126">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="64a2c-126">Related topics</span></span>

- [<span data-ttu-id="64a2c-127">Назначение политик пользователям</span><span class="sxs-lookup"><span data-stu-id="64a2c-127">Assign policies to users</span></span>](assign-policies.md)
