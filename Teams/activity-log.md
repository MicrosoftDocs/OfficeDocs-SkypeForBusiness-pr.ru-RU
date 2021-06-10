---
title: Просмотр заданий политики в журнале действий в центре Microsoft Teams администрирования
author: cichur
ms.author: v-cichur
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Узнайте, как просматривать действия с назначением политики в журнале действий в Microsoft Teams администрирования.
localization_priority: Normal
f1.keywords:
- CSH
- ms.teamsadmincenter.dashboard.activitylog.overview
ms.custom: ''
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a8d1d49d187808b768b4a92c64c4e667ca0ea8f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821319"
---
# <a name="view-your-policy-assignments-in-the-activity-log"></a><span data-ttu-id="bb2a9-103">Просмотр назначений политики в журнале действий</span><span class="sxs-lookup"><span data-stu-id="bb2a9-103">View your policy assignments in the Activity log</span></span>

<span data-ttu-id="bb2a9-104">При назначении политик пользователям в центре администрирования Microsoft Teams вы можете просмотреть их состояние в журнале действий.</span><span class="sxs-lookup"><span data-stu-id="bb2a9-104">When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log.</span></span> <span data-ttu-id="bb2a9-105">В журнале действий показаны назначения политик более чем 20 пользователям через Microsoft Teams центре администрирования за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="bb2a9-105">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="bb2a9-106">Имейте в виду, что в журнале действий не вы можете показывать назначения пакетов политик, назначения политик пакетам менее 20 пользователей через Центр администрирования Microsoft Teams или назначения политик с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb2a9-106">Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.</span></span>

![Снимок экрана: страница журнала действий](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a><span data-ttu-id="bb2a9-108">Просмотр действий с назначением политики в журнале действий</span><span class="sxs-lookup"><span data-stu-id="bb2a9-108">View your policy assignment activities in the Activity log</span></span>

<span data-ttu-id="bb2a9-109">Чтобы просмотреть назначения политик в журнале действий:</span><span class="sxs-lookup"><span data-stu-id="bb2a9-109">To view your policy assignments in the Activity log:</span></span>

1. <span data-ttu-id="bb2a9-110">В левой области навигации центра администрирования Microsoft Teams панели мониторинга **,** а затем в поле Журнал действий **выберите** **Просмотреть сведения**.</span><span class="sxs-lookup"><span data-stu-id="bb2a9-110">In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.</span></span>
2. <span data-ttu-id="bb2a9-111">Вы можете просмотреть все назначения политик или отфильтровать список по статусу, чтобы отфильтровать только те назначения, которые не были на запущены, завершены или **завершены.**</span><span class="sxs-lookup"><span data-stu-id="bb2a9-111">You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**.</span></span> <span data-ttu-id="bb2a9-112">Вы увидите следующие сведения о каждом задании:</span><span class="sxs-lookup"><span data-stu-id="bb2a9-112">You'll see the following information about each assignment:</span></span>
    - <span data-ttu-id="bb2a9-113">**Name**(Имя). Имя назначения политики.</span><span class="sxs-lookup"><span data-stu-id="bb2a9-113">**Name**: The name of the policy assignment.</span></span> <span data-ttu-id="bb2a9-114">Щелкните ссылку, чтобы просмотреть дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="bb2a9-114">Click the link to view more details.</span></span> <span data-ttu-id="bb2a9-115">Это число пользователей, которые были назначены политике, а также количество заданий, которые были выполнены, уже выполнены и не наступались.</span><span class="sxs-lookup"><span data-stu-id="bb2a9-115">This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started.</span></span> <span data-ttu-id="bb2a9-116">Вы также увидите список пользователей в пакете, а также состояние и результат для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="bb2a9-116">You'll also see the list of users in the batch, and the status and result for each user.</span></span> <span data-ttu-id="bb2a9-117">Ниже приводится пример.</span><span class="sxs-lookup"><span data-stu-id="bb2a9-117">Here's an example:</span></span>

        ![Снимок экрана:](media/activity-log-policy-assignment-detail.png)

    - <span data-ttu-id="bb2a9-119">**Отправлено:** дата и время отправки назначения политики.</span><span class="sxs-lookup"><span data-stu-id="bb2a9-119">**Submitted**: Date and time the policy assignment was submitted.</span></span>
    - <span data-ttu-id="bb2a9-120">**Время завершения:** дата и время завершения назначения политики.</span><span class="sxs-lookup"><span data-stu-id="bb2a9-120">**Completion time**: Date and time the policy assignment was completed.</span></span>
    - <span data-ttu-id="bb2a9-121">**Влияние на**: количество пользователей в пакете.</span><span class="sxs-lookup"><span data-stu-id="bb2a9-121">**Impact on**: Number of users in the batch.</span></span>
    - <span data-ttu-id="bb2a9-122">**Общее состояние:** состояние назначения политики.</span><span class="sxs-lookup"><span data-stu-id="bb2a9-122">**Overall status**: Status of the policy assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="bb2a9-123">Вы также можете зайти в журнал действий на **странице Пользователи.**</span><span class="sxs-lookup"><span data-stu-id="bb2a9-123">You can also get to the Activity log from the **Users** page.</span></span> <span data-ttu-id="bb2a9-124">После того  как вы нажмете кнопку Применить, чтобы отправить задание массовой политики, вы увидите баннер в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="bb2a9-124">After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page.</span></span> <span data-ttu-id="bb2a9-125">Щелкните **ссылку Журнал действий** в заголовке.</span><span class="sxs-lookup"><span data-stu-id="bb2a9-125">Click the **Activity log** link in the banner.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bb2a9-126">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="bb2a9-126">Related topics</span></span>

- [<span data-ttu-id="bb2a9-127">Назначение политик пользователям</span><span class="sxs-lookup"><span data-stu-id="bb2a9-127">Assign policies to users</span></span>](assign-policies.md)
