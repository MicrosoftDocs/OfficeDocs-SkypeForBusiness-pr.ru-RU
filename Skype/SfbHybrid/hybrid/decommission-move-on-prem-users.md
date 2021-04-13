---
title: Перемещение пользователей в облако
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Перемещение пользователей до вывода из эксплуатации локальной среды Skype для бизнеса.
ms.openlocfilehash: f04ebeec51b739faa89f907de6c363f0ef70a78e
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656675"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="3fb69-103">Перемещение необходимых пользователей до вывода из эксплуатации локальной среды</span><span class="sxs-lookup"><span data-stu-id="3fb69-103">Move required users before decommissioning your on-premises environment</span></span>

<span data-ttu-id="3fb69-104">В этой статье описывается, как переместить необходимых пользователей в облако Microsoft до вывода из эксплуатации локальной среды Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="3fb69-104">This article describes how to move required users to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="3fb69-105">Это шаг 1 из следующих действий по выводу из эксплуатации локальной среды:</span><span class="sxs-lookup"><span data-stu-id="3fb69-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="3fb69-106">**Шаг 1. Перемещение всех необходимых пользователей из локальной сети в интернет.**</span><span class="sxs-lookup"><span data-stu-id="3fb69-106">**Step 1. Move all required users from on-premises to online.**</span></span> <span data-ttu-id="3fb69-107">(В этой статье)</span><span class="sxs-lookup"><span data-stu-id="3fb69-107">(This article)</span></span>

- <span data-ttu-id="3fb69-108">Шаг 2.</span><span class="sxs-lookup"><span data-stu-id="3fb69-108">Step 2.</span></span> <span data-ttu-id="3fb69-109">[Отключите гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="3fb69-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="3fb69-110">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="3fb69-110">Step 3.</span></span> <span data-ttu-id="3fb69-111">[Перемещение конечных точек гибридного приложения из локального в интернет.](decommission-move-on-prem-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="3fb69-111">[Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="3fb69-112">Этап 4.</span><span class="sxs-lookup"><span data-stu-id="3fb69-112">Step 4.</span></span> <span data-ttu-id="3fb69-113">[Удалите локальное развертывание Skype для бизнеса.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="3fb69-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="3fb69-114">Перемещение всех необходимых пользователей из локального в облако</span><span class="sxs-lookup"><span data-stu-id="3fb69-114">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="3fb69-115">Все пользователи, которые будут продолжать использовать после завершения миграции, сначала должны быть перемещены из локального в облако.</span><span class="sxs-lookup"><span data-stu-id="3fb69-115">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="3fb69-116">Перемещение пользователей с помощью средств администрирования на месте.</span><span class="sxs-lookup"><span data-stu-id="3fb69-116">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="3fb69-117">Подробные сведения см. в [материале Перемещение пользователей между локальной и облачной.](move-users-between-on-premises-and-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="3fb69-117">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="3fb69-118">Несмотря на то, что пользователи с учетными записями Skype для бизнеса Server могут использовать Teams, эти пользователи не имеют полных функциональных возможностей Teams.</span><span class="sxs-lookup"><span data-stu-id="3fb69-118">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="3fb69-119">Эти пользователи не могут скооперироваться или федератироваться с любым другим пользователем, все еще использующим Skype для бизнеса (будь то онлайн или локально).</span><span class="sxs-lookup"><span data-stu-id="3fb69-119">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="3fb69-120">Эти пользователи также не могут принимать вызовы PSTN в клиенте Teams.</span><span class="sxs-lookup"><span data-stu-id="3fb69-120">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="3fb69-121">Поэтому необходимо переместить этих пользователей в интернет.</span><span class="sxs-lookup"><span data-stu-id="3fb69-121">Therefore, you must move these users to online.</span></span> <span data-ttu-id="3fb69-122">Этот шаг также обеспечивает перенос контактов или собраний, созданных в Skype для бизнеса Server, в Teams.</span><span class="sxs-lookup"><span data-stu-id="3fb69-122">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="3fb69-123">Чтобы проверить, есть ли в локальном развертывании оставшиеся пользователи, запустите следующий комдлет в окне Skype для бизнеса Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3fb69-123">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="3fb69-124">Если какие-либо пользователи возвращаются, просмотрите вывод, чтобы определить, следует ли какие-либо учетные записи быть перемещены в облако, и для любых таких пользователей выполните действия [здесь](move-users-between-on-premises-and-cloud.md).</span><span class="sxs-lookup"><span data-stu-id="3fb69-124">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="3fb69-125">Для учетных записей пользователей, которые больше не нужны, запустите следующий комдлет Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3fb69-125">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="3fb69-126">Запуск Disable-CsUser удаляет все атрибуты Skype для бизнеса для всех пользователей, которые соответствуют критериям фильтрации.</span><span class="sxs-lookup"><span data-stu-id="3fb69-126">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="3fb69-127">Перед началом процедуры подтвердим, что эти учетные записи больше не нужны.</span><span class="sxs-lookup"><span data-stu-id="3fb69-127">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>


<span data-ttu-id="3fb69-128">Теперь вы готовы отключить [гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="3fb69-128">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3fb69-129">См. также</span><span class="sxs-lookup"><span data-stu-id="3fb69-129">See also</span></span>

- [<span data-ttu-id="3fb69-130">Прекращение использования локальной среды Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3fb69-130">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="3fb69-131">Отключение гибридной конфигурации</span><span class="sxs-lookup"><span data-stu-id="3fb69-131">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="3fb69-132">Перемещение конечных точек гибридного приложения из локального в online</span><span class="sxs-lookup"><span data-stu-id="3fb69-132">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- [<span data-ttu-id="3fb69-133">Удаление локального развертывания Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3fb69-133">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




