---
title: Управление доступом пользователей к Education Insights
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Управление доступом пользователей к Education Insights в Microsoft Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32bd773975ff6b67d28ab765ffa7c932e978af7d
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145943"
---
# <a name="manage-user-access-to-education-insights"></a><span data-ttu-id="be0c0-103">Управление доступом пользователей к Education Insights</span><span class="sxs-lookup"><span data-stu-id="be0c0-103">Manage user access to Education Insights</span></span>

<span data-ttu-id="be0c0-104">В этом документе описаны действия, необходимые для управления доступом пользователей к [Education Insights в Microsoft Teams](class-insights.md).</span><span class="sxs-lookup"><span data-stu-id="be0c0-104">This document provides the steps required to manage user access to [Education Insights in Microsoft Teams](class-insights.md).</span></span>

<span data-ttu-id="be0c0-105">Вам нужно предоставить разрешения лидерам образовательных учреждений, руководителям округа, школьным директорам, старшим преподавателям, консультантам, руководителям областей обучения, директорам программ, социальным работникам и психологам.</span><span class="sxs-lookup"><span data-stu-id="be0c0-105">You need to provide permissions for education leaders, district leaders, school principals, head teachers, counselors, heads of learning areas, program directors, social workers, and psychologists.</span></span> <span data-ttu-id="be0c0-106">Преподаватели получают разрешение *автоматически*, если они владеют командой класса.</span><span class="sxs-lookup"><span data-stu-id="be0c0-106">Educators are *automatically* given permission when they own a class team.</span></span>

<span data-ttu-id="be0c0-107">Чтобы обеспечить аналитику на уровне организации, вы должны [импортировать данные из системы данных об учащихся (SDS)](education-insights-sis-data-sync.md), чтобы средство Insights правильно сопоставило иерархическую структуру системы образования.</span><span class="sxs-lookup"><span data-stu-id="be0c0-107">To provide organization-level Insights, you must [import data from the Student Information System (SIS)](education-insights-sis-data-sync.md) so that Insights has the hierarchical structure of the educational system mapped correctly.</span></span>

> [!NOTE]
> <span data-ttu-id="be0c0-108">Управлять доступом пользователей к Insights может только глобальный администратор.</span><span class="sxs-lookup"><span data-stu-id="be0c0-108">Only Global Administrator can manage user access to Insights.</span></span>

> [!TIP]
> <span data-ttu-id="be0c0-109">Рекомендуется включить Insights для всех руководителей образовательных учреждений, чтобы им были доступны данные для понимания каждого учебного заведения и возможность быстро определять проблемы и предоставлять поддержку преподавателям.</span><span class="sxs-lookup"><span data-stu-id="be0c0-109">We recommend that you enable Insights for all your education leaders so that they have the data to understand each school, and the ability to quickly identify problems and provide support to their educators.</span></span> <span data-ttu-id="be0c0-110">Даже если вы разворачиваете пилотный проект, все равно лучше включить Insights для всех руководителей образовательных учреждений, ограничив коммуникации пилотной группой пользователей.</span><span class="sxs-lookup"><span data-stu-id="be0c0-110">Even if you're running a pilot, it may still be helpful to keep Insights enabled for all education leaders, but only target communications to the pilot group of users.</span></span>



## <a name="grant-permissions"></a><span data-ttu-id="be0c0-111">Предоставление разрешений</span><span class="sxs-lookup"><span data-stu-id="be0c0-111">Grant permissions</span></span>

* <span data-ttu-id="be0c0-112">Откройте приложение Insights, нажмите **Настройки** и выберите **Разрешения пользователей**.</span><span class="sxs-lookup"><span data-stu-id="be0c0-112">Open the Insights app, click **Settings**, and select **User permissions**</span></span>

:::image type="content" source="media/insights-user-permissions.png" alt-text="Настройки":::

* <span data-ttu-id="be0c0-114">Выберите **Добавить пользователей**.</span><span class="sxs-lookup"><span data-stu-id="be0c0-114">Select **Add users**.</span></span>
* <span data-ttu-id="be0c0-115">Введите имя пользователя или адрес электронной почты каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="be0c0-115">Enter the username or email address of each user.</span></span>
* <span data-ttu-id="be0c0-116">Выберите уровень разрешений:</span><span class="sxs-lookup"><span data-stu-id="be0c0-116">Select the permission level:</span></span>
  * <span data-ttu-id="be0c0-117">**Доступ ко всей организации** означает, что пользователь видит все подразделения на всех уровнях.</span><span class="sxs-lookup"><span data-stu-id="be0c0-117">**Access to all organization** means the user sees all the org units at all levels.</span></span>
  * <span data-ttu-id="be0c0-118">**Доступ к определенным учебным заведениям** означает, что пользователь видит выбранные учебные заведения.</span><span class="sxs-lookup"><span data-stu-id="be0c0-118">**Access to specific schools** means the user sees the selected schools.</span></span> <span data-ttu-id="be0c0-119">Начните ввод текста и выберите учебное заведение из списка.</span><span class="sxs-lookup"><span data-stu-id="be0c0-119">Start typing and select the school from the list.</span></span> <span data-ttu-id="be0c0-120">Вы можете одновременно добавить несколько учебных заведений.</span><span class="sxs-lookup"><span data-stu-id="be0c0-120">You can add multiple schools together.</span></span>
* <span data-ttu-id="be0c0-121">Щелкните **Добавить новых пользователей**.</span><span class="sxs-lookup"><span data-stu-id="be0c0-121">Click **Add new users**.</span></span>

:::image type="content" source="media/insights-add-users.png" alt-text="Предоставление разрешений":::

> [!NOTE]
> <span data-ttu-id="be0c0-123">Предоставляйте разрешение только тем руководителям образовательных учреждений, которым оно требуется, и только для тех подразделений, за которые они отвечают.</span><span class="sxs-lookup"><span data-stu-id="be0c0-123">Only provide permission to those education leaders that need them and only to the organizational units they are responsible for.</span></span> <span data-ttu-id="be0c0-124">Если вы не уверены, требуется ли пользователю разрешение для конкретной организации, обратитесь к специалистам по конфиденциальности вашего учебного заведения, например к юристам или в отдел кадров.</span><span class="sxs-lookup"><span data-stu-id="be0c0-124">If you are unsure whether user permission for a specific organization is required, consult your institution's privacy subject matter experts, such as legal or HR personnel.</span></span>

## <a name="edit-permissions"></a><span data-ttu-id="be0c0-125">Изменение разрешений</span><span class="sxs-lookup"><span data-stu-id="be0c0-125">Edit permissions</span></span>
* <span data-ttu-id="be0c0-126">Выберите определенного пользователя и нажмите **Изменить разрешения**.</span><span class="sxs-lookup"><span data-stu-id="be0c0-126">Select specific user, then select **Edit permissions**.</span></span>
* <span data-ttu-id="be0c0-127">Обновите уровень разрешений или список учебных заведений и нажмите **Обновить разрешения**.</span><span class="sxs-lookup"><span data-stu-id="be0c0-127">Update the permission level or schools list, and click **Update permissions**.</span></span>

:::image type="content" source="media/insights-edit-users.png" alt-text="Изменение разрешений":::

## <a name="remove-permissions"></a><span data-ttu-id="be0c0-129">Удаление разрешений</span><span class="sxs-lookup"><span data-stu-id="be0c0-129">Remove permissions</span></span>
* <span data-ttu-id="be0c0-130">Выберите пользователей, которых нужно удалить, и нажмите **Удалить пользователей**.</span><span class="sxs-lookup"><span data-stu-id="be0c0-130">Select the users you want to remove, then select **Remove users**.</span></span>
* <span data-ttu-id="be0c0-131">У этих пользователей больше не будет доступа к данным Insights на уровне организации, но им по-прежнему будут доступны данные Insights на уровне класса, если они владеют командой класса.</span><span class="sxs-lookup"><span data-stu-id="be0c0-131">These users no longer have access to organization-level Insights, but can still access class-level Insights if they own a class team.</span></span>

:::image type="content" source="media/insights-remove-users.png" alt-text="Удаление разрешений":::
