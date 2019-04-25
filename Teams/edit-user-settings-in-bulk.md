---
title: Массовое изменение параметров пользователей Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Сведения об управлении группами Майкрософт параметров пользователя в пакетном режиме в центре администрирования группами Майкрософт.
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.bulkoperations.edit
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c1dfba0bdaec642b0ea078d7f10ba022c8514da
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245080"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a><span data-ttu-id="736ac-103">Изменение параметров пользователя группами Майкрософт в пакетном режиме</span><span class="sxs-lookup"><span data-stu-id="736ac-103">Edit Microsoft Teams user settings in bulk</span></span>

<span data-ttu-id="736ac-104">Как администратор управлять группами параметров пользователя в центре администрирования группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="736ac-104">As an admin, you manage Teams user settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="736ac-105">На странице " **Пользователи** " можно просматривать сведения, такие как учетная запись и сведения о лицензиях и изменение политики и другие параметры.</span><span class="sxs-lookup"><span data-stu-id="736ac-105">On the **Users** page, you can view information such as account and licensing details and edit policy and other settings.</span></span> <span data-ttu-id="736ac-106">В то же время, можно изменить параметры для пользователей по отдельности или для нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="736ac-106">You can edit settings for users individually or for multiple users at the same time.</span></span>

## <a name="edit-user-settings-in-bulk"></a><span data-ttu-id="736ac-107">Изменение параметров пользователя в пакетном режиме</span><span class="sxs-lookup"><span data-stu-id="736ac-107">Edit user settings in bulk</span></span>

<span data-ttu-id="736ac-108">Использование центра администрирования группами Майкрософт для изменения параметров для нескольких пользователей за раз.</span><span class="sxs-lookup"><span data-stu-id="736ac-108">Use the Microsoft Teams admin center to edit settings for multiple users at a time.</span></span> <span data-ttu-id="736ac-109">Мы рекомендуем изменения параметров для 20 пользователей за раз.</span><span class="sxs-lookup"><span data-stu-id="736ac-109">We recommend editing settings for 20 users at a time.</span></span> <span data-ttu-id="736ac-110">Чтобы изменить параметры для большого числа пользователей, с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="736ac-110">To edit settings for a large number of users, use PowerShell.</span></span> <span data-ttu-id="736ac-111">Для получения дополнительных сведений см [Команды PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="736ac-111">For more information, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

1. <span data-ttu-id="736ac-112">В левой области переходов центра администрирования группами Майкрософт выберите **пользователей**.</span><span class="sxs-lookup"><span data-stu-id="736ac-112">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="736ac-113">Поиск пользователей, которые необходимо изменить или фильтрации представления для отображения пользователей, вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="736ac-113">Search for the users you want to edit or filter the view to show the users you want to edit.</span></span>
3. <span data-ttu-id="736ac-114">В **& #x 2713;** столбец (флажок), выбора пользователей, выполните одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="736ac-114">In the **&#x2713;** (check mark) column, select users by doing one of the following:</span></span>
    - <span data-ttu-id="736ac-115">Выберите пользователей по одному за раз.</span><span class="sxs-lookup"><span data-stu-id="736ac-115">Select users one at a time.</span></span> <span data-ttu-id="736ac-116">**_AMP_ #x 2713;** отображается рядом с пользователями, которые вы выбрали.</span><span class="sxs-lookup"><span data-stu-id="736ac-116">A **&#x2713;** is displayed next to each user you select.</span></span> <span data-ttu-id="736ac-117">Если выбран параметр более 20 пользователей, не будут блокироваться, но следует помнить, что выбрано большее количество пользователей, операция будет занимать значительно больше времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="736ac-117">If you select more than 20 users, you won't be blocked but keep in mind that the more users you select, the operation will take longer to complete.</span></span>

        ![Снимок экрана страницы пользователей, отражающая Выбор пользователя](media/bulk-edit-user-settings-select-users.png)

    - <span data-ttu-id="736ac-119">Нажмите кнопку & #x 2713; (флажок) в верхней части таблицы для выбора всех пользователей (не более 20 пользователей) и нажмите кнопку **Продолжить выберите все** , чтобы завершить выбор в диалоговом окне **Выбор ограничение** .</span><span class="sxs-lookup"><span data-stu-id="736ac-119">Click the &#x2713; (check mark) at the top of the table to select all users (up to a maximum of 20 users), and then in the **Selection limit** dialog box, click **Continue select all** to complete the selection.</span></span>

        <span data-ttu-id="736ac-120">![Снимок экрана страницы пользователей, отражающая предел выбора](media/bulk-edit-user-settings-select-all-limit.png)</span><span class="sxs-lookup"><span data-stu-id="736ac-120">![Screen shot of the Users page, showing the selection limit](media/bulk-edit-user-settings-select-all-limit.png)</span></span> <br> <span data-ttu-id="736ac-121">**_AMP_ #x 2713;** отображается рядом с элементом выбранных пользователей.</span><span class="sxs-lookup"><span data-stu-id="736ac-121">A **&#x2713;** is displayed next to the selected users.</span></span>

        ![Снимок экрана страницы пользователей, отражающая 20 выбранных пользователей](media/bulk-edit-user-settings-select-all.png)
4. <span data-ttu-id="736ac-123">Нажмите кнопку **Изменить параметры**, внесите необходимые изменения и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="736ac-123">Click **Edit settings**, make the changes that you want, and then click **Save**.</span></span>

    ![Снимок экрана изменить параметры области](media/bulk-edit-user-settings-edit-settings.png)
