---
title: Просмотр назначенных политик в журнале активности в центре администрирования Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Сведения о том, как просматривать действия назначений политики в журнале активности в центре администрирования Microsoft Teams.
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
# <a name="view-your-policy-assignments-in-the-activity-log"></a><span data-ttu-id="d9b6a-103">Просмотр назначений политики в журнале активности</span><span class="sxs-lookup"><span data-stu-id="d9b6a-103">View your policy assignments in the Activity log</span></span>

<span data-ttu-id="d9b6a-104">Когда вы назначаете пользователям в центре администрирования Microsoft Teams политику, вы можете просмотреть их состояние в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="d9b6a-104">When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log.</span></span> <span data-ttu-id="d9b6a-105">Журнал активности показывает назначения политики для пакетов более чем из 20 пользователей в центре администрирования Microsoft Teams за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="d9b6a-105">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="d9b6a-106">Имейте в виду, что в журнале активности не отображаются назначения пакетов политики, назначения политик для пакетов менее чем 20 пользователей с помощью центра администрирования Microsoft Teams или назначений политики с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d9b6a-106">Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.</span></span>

![Снимок экрана: страница журнала активности](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a><span data-ttu-id="d9b6a-108">Просмотр действий назначений политики в журнале активности</span><span class="sxs-lookup"><span data-stu-id="d9b6a-108">View your policy assignment activities in the Activity log</span></span>

<span data-ttu-id="d9b6a-109">Чтобы просмотреть назначения политики в журнале активности, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d9b6a-109">To view your policy assignments in the Activity log:</span></span>

1. <span data-ttu-id="d9b6a-110">В левой области навигации центра администрирования Microsoft Teams перейдите на **панель мониторинга**, а затем в разделе **Журнал активности**выберите пункт **Просмотреть сведения**.</span><span class="sxs-lookup"><span data-stu-id="d9b6a-110">In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.</span></span>
2. <span data-ttu-id="d9b6a-111">Вы можете просмотреть все назначения политик или отфильтровать список по статусу, чтобы отображались только задания, которые **не были запущены**, находятся **в процессе**или **завершены**.</span><span class="sxs-lookup"><span data-stu-id="d9b6a-111">You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**.</span></span> <span data-ttu-id="d9b6a-112">Вы увидите следующие сведения о каждом назначении:</span><span class="sxs-lookup"><span data-stu-id="d9b6a-112">You'll see the following information about each assignment:</span></span>
    - <span data-ttu-id="d9b6a-113">**Name (имя**): имя назначения политики.</span><span class="sxs-lookup"><span data-stu-id="d9b6a-113">**Name**: The name of the policy assignment.</span></span> <span data-ttu-id="d9b6a-114">Щелкните ссылку, чтобы просмотреть дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="d9b6a-114">Click the link to view more details.</span></span> <span data-ttu-id="d9b6a-115">Сюда входят количество пользователей, которым была назначена политика, и количество завершенных, выполняющихся и не запущенных.</span><span class="sxs-lookup"><span data-stu-id="d9b6a-115">This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started.</span></span> <span data-ttu-id="d9b6a-116">Вы также увидите список пользователей в пакете, состояние и результат для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="d9b6a-116">You'll also see the list of users in the batch, and the status and result for each user.</span></span> <span data-ttu-id="d9b6a-117">Ниже приводится пример.</span><span class="sxs-lookup"><span data-stu-id="d9b6a-117">Here's an example:</span></span>

        ![Снимок экрана:](media/activity-log-policy-assignment-detail.png)

    - <span data-ttu-id="d9b6a-119">**Отправлено**: Дата и время отправки назначения политики.</span><span class="sxs-lookup"><span data-stu-id="d9b6a-119">**Submitted**: Date and time the policy assignment was submitted.</span></span>
    - <span data-ttu-id="d9b6a-120">**Время завершения**: Дата и время завершения назначения политики.</span><span class="sxs-lookup"><span data-stu-id="d9b6a-120">**Completion time**: Date and time the policy assignment was completed.</span></span>
    - <span data-ttu-id="d9b6a-121">**Влияние на**: количество пользователей в пакете.</span><span class="sxs-lookup"><span data-stu-id="d9b6a-121">**Impact on**: Number of users in the batch.</span></span>
    - <span data-ttu-id="d9b6a-122">**Общее состояние**: состояние назначения политики.</span><span class="sxs-lookup"><span data-stu-id="d9b6a-122">**Overall status**: Status of the policy assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="d9b6a-123">Вы также можете перейти к журналу активности на странице " **Пользователи** ".</span><span class="sxs-lookup"><span data-stu-id="d9b6a-123">You can also get to the Activity log from the **Users** page.</span></span> <span data-ttu-id="d9b6a-124">После нажатия кнопки **Применить** для отправки задания массовой политики вы увидите баннер в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="d9b6a-124">After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page.</span></span> <span data-ttu-id="d9b6a-125">Щелкните ссылку **Журнал активности** в заголовке.</span><span class="sxs-lookup"><span data-stu-id="d9b6a-125">Click the **Activity log** link in the banner.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d9b6a-126">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d9b6a-126">Related topics</span></span>

- [<span data-ttu-id="d9b6a-127">Назначение политик пользователям</span><span class="sxs-lookup"><span data-stu-id="d9b6a-127">Assign policies to users</span></span>](assign-policies.md)
