---
title: Отключить гибрид для завершения миграции в Teams Только
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: В этой статье содержатся подробные действия по отключению гибрида в рамках консолидации облачных Teams и Skype для бизнеса.
ms.openlocfilehash: 87bd1f6e0dcabed067174972dd0f0fc51149beb0
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453648"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a><span data-ttu-id="798bf-103">Отключение гибридной конфигурации для завершения миграции в Teams Only</span><span class="sxs-lookup"><span data-stu-id="798bf-103">Disable your hybrid configuration to complete migration to Teams Only</span></span> 

<span data-ttu-id="798bf-104">В этой статье описывается отключение гибридной конфигурации перед выводом из эксплуатации локальной Skype для бизнеса среды.</span><span class="sxs-lookup"><span data-stu-id="798bf-104">This article describes how to disable your hybrid configuration before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="798bf-105">Это шаг 2 из следующих действий по выводу из эксплуатации локальной среды:</span><span class="sxs-lookup"><span data-stu-id="798bf-105">This is step 2 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="798bf-106">Этап 1.</span><span class="sxs-lookup"><span data-stu-id="798bf-106">Step 1.</span></span> <span data-ttu-id="798bf-107">[Перемещение всех необходимых пользователей из локального в интернет.](decommission-move-on-prem-users.md)</span><span class="sxs-lookup"><span data-stu-id="798bf-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="798bf-108">**Шаг 2. Отключите гибридную конфигурацию.**</span><span class="sxs-lookup"><span data-stu-id="798bf-108">**Step 2. Disable your hybrid configuration.**</span></span> <span data-ttu-id="798bf-109">(В этой статье)</span><span class="sxs-lookup"><span data-stu-id="798bf-109">(This article)</span></span>

- <span data-ttu-id="798bf-110">Этап 3.</span><span class="sxs-lookup"><span data-stu-id="798bf-110">Step 3.</span></span> <span data-ttu-id="798bf-111">[Перенос конечных точек](decommission-move-on-prem-endpoints.md)гибридных приложений из локального в онлайн.</span><span class="sxs-lookup"><span data-stu-id="798bf-111">[Migrate hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="798bf-112">Этап 4.</span><span class="sxs-lookup"><span data-stu-id="798bf-112">Step 4.</span></span> <span data-ttu-id="798bf-113">[Удалите локальное развертывание Skype для бизнеса.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="798bf-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

> [!NOTE]
> <span data-ttu-id="798bf-114">Этапы 2 и 3 должны быть сделаны в одном окне обслуживания, так как существующие конечные точки гибридного приложения не будут обнаружены между этапами 2 и завершением шага 3.</span><span class="sxs-lookup"><span data-stu-id="798bf-114">Steps 2 and 3 should be done in the same maintenance window because any existing hybrid application endpoints will not be discoverable between steps 2 and completion of step 3.</span></span>


## <a name="summary"></a><span data-ttu-id="798bf-115">Аннотация</span><span class="sxs-lookup"><span data-stu-id="798bf-115">Summary</span></span>

<span data-ttu-id="798bf-116">После обновления всех пользователей из локального Skype для бизнеса до Teams только в Microsoft 365, вы можете списание локального Skype для бизнеса развертывания.</span><span class="sxs-lookup"><span data-stu-id="798bf-116">After you have upgraded all users from Skype for Business on-premises to Teams Only in Microsoft 365, you can decommission the on-premises Skype for Business deployment.</span></span>

<span data-ttu-id="798bf-117">Прежде чем отключать локальное развертывание Skype для бизнеса и удалять оборудование, необходимо логически отделить локальное развертывание от Microsoft 365 путем отключения гибрида.</span><span class="sxs-lookup"><span data-stu-id="798bf-117">Before you decommission the on-premises Skype for Business deployment and remove any hardware, you must logically separate the on-premises deployment from Microsoft 365 by disabling hybrid.</span></span> <span data-ttu-id="798bf-118">Отключение гибрида состоит из следующих четырех действий:</span><span class="sxs-lookup"><span data-stu-id="798bf-118">Disabling hybrid consists of the following four steps:</span></span>

1. <span data-ttu-id="798bf-119">[Обновление записей DNS, чтобы указать на Microsoft 365](#update-dns-to-point-to-microsoft-365).</span><span class="sxs-lookup"><span data-stu-id="798bf-119">[Update DNS records to point to Microsoft 365](#update-dns-to-point-to-microsoft-365).</span></span>

2. <span data-ttu-id="798bf-120">[Измените режим сосуществования для организации](#change-the-coexistence-mode-for-your-organization-to-teams-only)на Teams только .</span><span class="sxs-lookup"><span data-stu-id="798bf-120">[Change the coexistence mode for your organization to Teams Only](#change-the-coexistence-mode-for-your-organization-to-teams-only).</span></span>

3. <span data-ttu-id="798bf-121">Отключение общего пространства адресов SIP (также известного как ["раздельный домен")](#disable-shared-sip-address-space-in-microsoft-365-organization)в Microsoft 365 организации.</span><span class="sxs-lookup"><span data-stu-id="798bf-121">[Disable shared sip address space (also known as "split domain") in the Microsoft 365 organization](#disable-shared-sip-address-space-in-microsoft-365-organization).</span></span>

4. [<span data-ttu-id="798bf-122">Отключение связи между локальной и Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="798bf-122">Disable communication between on-premises and Microsoft 365</span></span>](#disable-communication-between-on-premises-and-microsoft-365)

<span data-ttu-id="798bf-123">Эти действия логически отделяют локальное развертывание Skype для бизнеса Server от Microsoft 365 и гарантируют полную Teams только.</span><span class="sxs-lookup"><span data-stu-id="798bf-123">These steps logically separate your on-premises deployment of Skype for Business Server from Microsoft 365 and ensure your organization is fully Teams Only.</span></span> <span data-ttu-id="798bf-124">После завершения этих действий можно списать локальное развертывание Skype для бизнеса с помощью одного из двух [](cloud-consolidation-managing-attributes.md)методов, на которые ссылается в "Решение об управлении атрибутами после вывода из эксплуатации".</span><span class="sxs-lookup"><span data-stu-id="798bf-124">After you've completed these steps, you can decommission your on-premises Skype for Business deployment by using one of two methods referenced in [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).</span></span>

> [!Important] 
> <span data-ttu-id="798bf-125">После завершения этого логического разделения атрибуты msRTCSIP из локального Active Directory по-прежнему будут иметь значения и будут синхронизироваться с помощью Azure AD Подключение в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="798bf-125">Once this logical separation is complete, msRTCSIP attributes from your on-premises Active Directory still have values and will continue to sync via Azure AD Connect into Azure AD.</span></span> <span data-ttu-id="798bf-126">Вывод локальной среды из эксплуатации зависит от того, собираетесь ли вы оставить эти атрибуты на месте или сначала очистить их от локального Active Directory.</span><span class="sxs-lookup"><span data-stu-id="798bf-126">How you decommission the on-premises environment depends on whether you intend to leave these attributes in place, or first clear them from your on-premises Active Directory.</span></span> <span data-ttu-id="798bf-127">Следует помнить, что очистка атрибутов msRTCSIP на месте после миграции из локального помещения может привести к потере службы для пользователей!</span><span class="sxs-lookup"><span data-stu-id="798bf-127">Be aware that clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span> <span data-ttu-id="798bf-128">Подробные сведения и компромиссы двух подходов к выводу из эксплуатации описаны в "Решение об управлении атрибутами после вывода [из эксплуатации".](cloud-consolidation-managing-attributes.md)</span><span class="sxs-lookup"><span data-stu-id="798bf-128">Details and tradeoffs of the two decommissioning approaches are described in [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).</span></span>

## <a name="update-dns-to-point-to-microsoft-365"></a><span data-ttu-id="798bf-129">Обновление DNS, чтобы указать на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="798bf-129">Update DNS to point to Microsoft 365</span></span>

<span data-ttu-id="798bf-130">Внешние DNS организации для локальной организации должны быть обновлены таким образом, чтобы Skype для бизнеса записи указывают на Microsoft 365 вместо локального развертывания.</span><span class="sxs-lookup"><span data-stu-id="798bf-130">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 instead of the on-premises deployment.</span></span> 

<span data-ttu-id="798bf-131">Кроме того, записи CNAME для встречи или диалогов (если присутствуют) могут быть удалены.</span><span class="sxs-lookup"><span data-stu-id="798bf-131">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="798bf-132">Наконец, все записи DNS для Skype для бизнеса во внутренней сети должны быть удалены.</span><span class="sxs-lookup"><span data-stu-id="798bf-132">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

<span data-ttu-id="798bf-133">Сведения об обновлении записей DNS см. в [статьях Обновление записей DNS,](decommission-manage-dns-entries.md)чтобы позволить организации быть Teams только .</span><span class="sxs-lookup"><span data-stu-id="798bf-133">For details about updating DNS records, see [Update DNS entries to enable your organization to be all Teams Only](decommission-manage-dns-entries.md).</span></span>

## <a name="change-the-coexistence-mode-for-your-organization-to-teams-only"></a><span data-ttu-id="798bf-134">Измените режим сосуществования для организации на Teams Только</span><span class="sxs-lookup"><span data-stu-id="798bf-134">Change the coexistence mode for your organization to Teams Only</span></span>

<span data-ttu-id="798bf-135">Этот шаг гарантирует, что любой новый пользователь в организации всегда создается как Teams только пользователь.</span><span class="sxs-lookup"><span data-stu-id="798bf-135">This step ensures that any new user in your organization is always created as a Teams Only user.</span></span> 

<span data-ttu-id="798bf-136">Попытка изменить режим клиента на Teams только автоматически проверит наличие каких-либо локальной DNS-записей, которые могли быть пропущены на шаге 1, и определит эти записи в выходе.</span><span class="sxs-lookup"><span data-stu-id="798bf-136">Attempting to change the tenant mode to Teams Only will automatically check for existence of any on-premises DNS records that may have been missed in step 1 and identify these records in the output.</span></span> <span data-ttu-id="798bf-137">Изменение режима клиента на Teams только не удастся до тех пор, пока не будут обновлены все записи DNS для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="798bf-137">Changing the tenant mode to Teams Only will not succeed until all DNS records for your organization are updated.</span></span> 

<span data-ttu-id="798bf-138">Чтобы изменить режим клиента на Teams выполнить только следующую команду из окна Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="798bf-138">To change the tenant mode to Teams Only run the following command from a Teams PowerShell window.</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
```

<span data-ttu-id="798bf-139">Кроме того, вы можете использовать центр администрирования Teams для изменения режима сосуществования клиента на TeamsOnly в соответствии с "Настройками на всей организации" -> "Teams обновление".</span><span class="sxs-lookup"><span data-stu-id="798bf-139">Alternatively, you can use the Teams Admin Center to change the tenant coexistence mode to TeamsOnly, under "Org-wide settings" -> "Teams Upgrade."</span></span>    

## <a name="disable-shared-sip-address-space-in-microsoft-365-organization"></a><span data-ttu-id="798bf-140">Отключение общего пространства адресов sip в Microsoft 365 организации</span><span class="sxs-lookup"><span data-stu-id="798bf-140">Disable shared sip address space in Microsoft 365 organization</span></span>
    
<span data-ttu-id="798bf-141">Чтобы отключить общее пространство адресов sip, запустите следующую команду из окна Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="798bf-141">To disable shared sip address space, run the following command from a Teams PowerShell window.</span></span>

```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
```
 
## <a name="disable-communication-between-on-premises-and-microsoft-365"></a><span data-ttu-id="798bf-142">Отключение связи между локальной и Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="798bf-142">Disable communication between on-premises and Microsoft 365</span></span>

<span data-ttu-id="798bf-143">Чтобы отключить связь между локальной средой и Microsoft 365, запустите следующую команду из локального окна PowerShell:</span><span class="sxs-lookup"><span data-stu-id="798bf-143">To disable communication between the on-premises environment and Microsoft 365, run the following command from an on-premises PowerShell window:</span></span>

```PowerShell
Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```


## <a name="see-also"></a><span data-ttu-id="798bf-144">См. также</span><span class="sxs-lookup"><span data-stu-id="798bf-144">See also</span></span>

- [<span data-ttu-id="798bf-145">Консолидация облаков для Teams и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="798bf-145">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="798bf-146">Прекращение использования локальной среды Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="798bf-146">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

