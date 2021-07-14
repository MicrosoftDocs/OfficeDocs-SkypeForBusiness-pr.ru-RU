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
description: Перемещение пользователей до вывода из эксплуатации Skype для бизнеса локальной среды.
ms.openlocfilehash: 992f2dd479e0b8ca8a3f11f069e8ef049259ad9c
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420814"
---
# <a name="move-required-users-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="2b5dc-103">Перемещение необходимых пользователей до вывода из эксплуатации локальной среды</span><span class="sxs-lookup"><span data-stu-id="2b5dc-103">Move required users before decommissioning your on-premises environment</span></span>

<span data-ttu-id="2b5dc-104">В этой статье описывается, как переместить необходимых пользователей в облако Майкрософт до вывода из эксплуатации локальной Skype для бизнеса среды.</span><span class="sxs-lookup"><span data-stu-id="2b5dc-104">This article describes how to move required users to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="2b5dc-105">Это шаг 1 из следующих действий по выводу из эксплуатации локальной среды:</span><span class="sxs-lookup"><span data-stu-id="2b5dc-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="2b5dc-106">**Шаг 1. Перемещение всех необходимых пользователей из локальной сети в интернет.**</span><span class="sxs-lookup"><span data-stu-id="2b5dc-106">**Step 1. Move all required users from on-premises to online.**</span></span> <span data-ttu-id="2b5dc-107">(В этой статье)</span><span class="sxs-lookup"><span data-stu-id="2b5dc-107">(This article)</span></span>

- <span data-ttu-id="2b5dc-108">Этап 2.</span><span class="sxs-lookup"><span data-stu-id="2b5dc-108">Step 2.</span></span> <span data-ttu-id="2b5dc-109">[Отключите гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="2b5dc-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="2b5dc-110">Этап 3.</span><span class="sxs-lookup"><span data-stu-id="2b5dc-110">Step 3.</span></span> <span data-ttu-id="2b5dc-111">[Перенос конечных точек](decommission-move-on-prem-endpoints.md)гибридных приложений из локального в онлайн.</span><span class="sxs-lookup"><span data-stu-id="2b5dc-111">[Migrate hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span> <span data-ttu-id="2b5dc-112">Следует помнить, что существующие конечные точки гибридного приложения не будут обнаружены между временем выполнения шага 2 выше, пока вы не завершите этот шаг.</span><span class="sxs-lookup"><span data-stu-id="2b5dc-112">Be aware that any existing hybrid application endpoints will not be discoverable between the time you perform Step 2 above until you complete this step.</span></span> <span data-ttu-id="2b5dc-113">Вы должны планировать оба шага 2 и 3 в одном окне обслуживания.</span><span class="sxs-lookup"><span data-stu-id="2b5dc-113">You should plan to do both steps 2 and 3 in the same maintenance window.</span></span>

- <span data-ttu-id="2b5dc-114">Этап 4.</span><span class="sxs-lookup"><span data-stu-id="2b5dc-114">Step 4.</span></span> <span data-ttu-id="2b5dc-115">[Удалите локальное развертывание Skype для бизнеса.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="2b5dc-115">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="2b5dc-116">Перемещение всех необходимых пользователей из локального в облако</span><span class="sxs-lookup"><span data-stu-id="2b5dc-116">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="2b5dc-117">Все пользователи, которые будут продолжать использовать после завершения миграции, сначала должны быть перемещены из локального в облако.</span><span class="sxs-lookup"><span data-stu-id="2b5dc-117">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="2b5dc-118">Перемещение пользователей с помощью средств администрирования на месте.</span><span class="sxs-lookup"><span data-stu-id="2b5dc-118">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="2b5dc-119">Подробные сведения см. в [материале Перемещение пользователей между локальной и облачной.](move-users-between-on-premises-and-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="2b5dc-119">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="2b5dc-120">Хотя пользователи с локальной Skype для бизнеса Server могут использовать Teams, эти пользователи не имеют полной функциональности Teams.</span><span class="sxs-lookup"><span data-stu-id="2b5dc-120">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="2b5dc-121">Эти пользователи не могут скооперироваться или федератировать с любым другим пользователем, Skype для бизнеса (будь то онлайн или локально).</span><span class="sxs-lookup"><span data-stu-id="2b5dc-121">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="2b5dc-122">Эти пользователи также не могут принимать вызовы PSTN в Teams клиенте.</span><span class="sxs-lookup"><span data-stu-id="2b5dc-122">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="2b5dc-123">Поэтому необходимо переместить этих пользователей в интернет.</span><span class="sxs-lookup"><span data-stu-id="2b5dc-123">Therefore, you must move these users to online.</span></span> <span data-ttu-id="2b5dc-124">Этот шаг также обеспечивает перенос любых контактов или собраний, созданных в Skype для бизнеса Server, в Teams.</span><span class="sxs-lookup"><span data-stu-id="2b5dc-124">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="2b5dc-125">Чтобы проверить, есть ли остальные пользователи в локальном развертывании, запустите следующий Skype для бизнеса Server PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b5dc-125">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="2b5dc-126">Если какие-либо пользователи возвращаются, просмотрите вывод, чтобы определить, следует ли какие-либо учетные записи быть перемещены в облако, и для любых таких пользователей выполните действия [здесь](move-users-between-on-premises-and-cloud.md).</span><span class="sxs-lookup"><span data-stu-id="2b5dc-126">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="2b5dc-127">Для учетных записей пользователей, которые больше не нужны, запустите следующий Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2b5dc-127">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="2b5dc-128">Запуск Disable-CsUser удаляет все Skype для бизнеса атрибуты для всех пользователей, которые соответствуют критериям фильтрации.</span><span class="sxs-lookup"><span data-stu-id="2b5dc-128">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="2b5dc-129">Перед началом процедуры подтвердим, что эти учетные записи больше не нужны.</span><span class="sxs-lookup"><span data-stu-id="2b5dc-129">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>


<span data-ttu-id="2b5dc-130">Теперь вы готовы отключить [гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)</span><span class="sxs-lookup"><span data-stu-id="2b5dc-130">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2b5dc-131">См. также</span><span class="sxs-lookup"><span data-stu-id="2b5dc-131">See also</span></span>

- [<span data-ttu-id="2b5dc-132">Прекращение использования локальной среды Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2b5dc-132">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="2b5dc-133">Отключение гибридной конфигурации</span><span class="sxs-lookup"><span data-stu-id="2b5dc-133">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="2b5dc-134">Перемещение конечных точек гибридного приложения из локального в online</span><span class="sxs-lookup"><span data-stu-id="2b5dc-134">Move hybrid application endpoints from on-premises to online</span></span>](decommission-move-on-prem-endpoints.md)

- [<span data-ttu-id="2b5dc-135">Удаление локального развертывания Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2b5dc-135">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




