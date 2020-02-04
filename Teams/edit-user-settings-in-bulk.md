---
title: Массовое изменение параметров пользователей Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Сведения о том, как управлять параметрами пользователей Microsoft Teams в центре администрирования Microsoft Teams.
localization_priority: Normal
f1.keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fec2338e1a7e518e90b2a5fbed716a01782bbb8c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41693294"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a><span data-ttu-id="28c77-103">Массовое редактирование параметров пользователей Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="28c77-103">Edit Microsoft Teams user settings in bulk</span></span>

<span data-ttu-id="28c77-104">Администраторы могут управлять параметрами пользователя Teams в центре администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="28c77-104">As an admin, you manage Teams user settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="28c77-105">На странице **Пользователи** можно просматривать такие сведения, как сведения об учетной записи и лицензировании, а также изменять политику и другие параметры.</span><span class="sxs-lookup"><span data-stu-id="28c77-105">On the **Users** page, you can view information such as account and licensing details and edit policy and other settings.</span></span> <span data-ttu-id="28c77-106">Вы можете изменять параметры для отдельных пользователей или для нескольких пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="28c77-106">You can edit settings for users individually or for multiple users at the same time.</span></span>

## <a name="edit-user-settings-in-bulk"></a><span data-ttu-id="28c77-107">Массовое редактирование параметров пользователя</span><span class="sxs-lookup"><span data-stu-id="28c77-107">Edit user settings in bulk</span></span>

<span data-ttu-id="28c77-108">Используйте центр администрирования Microsoft Teams для одновременного изменения параметров нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="28c77-108">Use the Microsoft Teams admin center to edit settings for multiple users at a time.</span></span> <span data-ttu-id="28c77-109">Мы рекомендуем использовать параметры редактирования более чем 20 пользователей за один раз.</span><span class="sxs-lookup"><span data-stu-id="28c77-109">We recommend editing settings for 20 users at a time.</span></span> <span data-ttu-id="28c77-110">Чтобы изменить параметры большого числа пользователей, используйте PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28c77-110">To edit settings for a large number of users, use PowerShell.</span></span> <span data-ttu-id="28c77-111">Дополнительные сведения можно найти в разделе [Общие сведения о Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="28c77-111">For more information, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

1. <span data-ttu-id="28c77-112">В левой области навигации центра администрирования Microsoft Teams выберите пункт **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="28c77-112">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="28c77-113">Найдите пользователей, которых вы хотите изменить, или отфильтруйте представление, чтобы просмотреть список пользователей, которых вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="28c77-113">Search for the users you want to edit or filter the view to show the users you want to edit.</span></span>
3. <span data-ttu-id="28c77-114">В столбце **&#x2713;** (флажок) выберите пункт Пользователи, выполнив одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="28c77-114">In the **&#x2713;** (check mark) column, select users by doing one of the following:</span></span>
    - <span data-ttu-id="28c77-115">Выберите пользователей по одному.</span><span class="sxs-lookup"><span data-stu-id="28c77-115">Select users one at a time.</span></span> <span data-ttu-id="28c77-116">Рядом с каждым из выбранных пользователей отображается **&#x2713;** .</span><span class="sxs-lookup"><span data-stu-id="28c77-116">A **&#x2713;** is displayed next to each user you select.</span></span> <span data-ttu-id="28c77-117">Если вы выбрали более 20 пользователей, вы не будете заблокированы, но имейте в виду, что чем больше пользователей вы выберете, тем больше времени потребуется для завершения операции.</span><span class="sxs-lookup"><span data-stu-id="28c77-117">If you select more than 20 users, you won't be blocked but keep in mind that the more users you select, the longer the operation will take to complete.</span></span>

        ![Снимок экрана со страницей "Пользователи", на которой показан пользовательский фрагмент](media/bulk-edit-user-settings-select-users.png)

    - <span data-ttu-id="28c77-119">Щелкните &#x2713; (флажок) в верхней части таблицы, чтобы выделить всех пользователей (не более 20 пользователей), а затем в диалоговом окне **предел выделения** нажмите кнопку **продолжить** , чтобы завершить выбор.</span><span class="sxs-lookup"><span data-stu-id="28c77-119">Click the &#x2713; (check mark) at the top of the table to select all users (up to a maximum of 20 users), and then in the **Selection limit** dialog box, click **Continue select all** to complete the selection.</span></span>

        <span data-ttu-id="28c77-120">![Снимок экрана со страницей "Пользователи" с ограничением выделения](media/bulk-edit-user-settings-select-all-limit.png)</span><span class="sxs-lookup"><span data-stu-id="28c77-120">![Screen shot of the Users page, showing the selection limit](media/bulk-edit-user-settings-select-all-limit.png)</span></span> <br> <span data-ttu-id="28c77-121">Рядом с выбранными пользователями отображается **&#x2713;** .</span><span class="sxs-lookup"><span data-stu-id="28c77-121">A **&#x2713;** is displayed next to the selected users.</span></span>

        ![Снимок экрана со страницей "Пользователи", на которой выделено 20 пользователей](media/bulk-edit-user-settings-select-all.png)
4. <span data-ttu-id="28c77-123">Нажмите кнопку **изменить параметры**, внесите необходимые изменения и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="28c77-123">Click **Edit settings**, make the changes that you want, and then click **Save**.</span></span>

    ![Снимок экрана с областью "Редактирование параметров"](media/bulk-edit-user-settings-edit-settings.png)
