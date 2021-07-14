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
ms.openlocfilehash: 97681f4e9306336874ba4d9428a273b1d31519db
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420844"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a><span data-ttu-id="6eb22-103">Отключение гибридной конфигурации для завершения миграции в Teams Only</span><span class="sxs-lookup"><span data-stu-id="6eb22-103">Disable your hybrid configuration to complete migration to Teams Only</span></span> 

<span data-ttu-id="6eb22-104">В этой статье описывается отключение гибридной конфигурации перед выводом из эксплуатации локальной Skype для бизнеса среды.</span><span class="sxs-lookup"><span data-stu-id="6eb22-104">This article describes how to disable your hybrid configuration before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="6eb22-105">Это шаг 2 из следующих действий по выводу из эксплуатации локальной среды:</span><span class="sxs-lookup"><span data-stu-id="6eb22-105">This is step 2 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="6eb22-106">Этап 1.</span><span class="sxs-lookup"><span data-stu-id="6eb22-106">Step 1.</span></span> <span data-ttu-id="6eb22-107">[Перемещение всех необходимых пользователей из локального в интернет.](decommission-move-on-prem-users.md)</span><span class="sxs-lookup"><span data-stu-id="6eb22-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="6eb22-108">**Шаг 2. Отключите гибридную конфигурацию.**</span><span class="sxs-lookup"><span data-stu-id="6eb22-108">**Step 2. Disable your hybrid configuration.**</span></span> <span data-ttu-id="6eb22-109">(В этой статье)</span><span class="sxs-lookup"><span data-stu-id="6eb22-109">(This article)</span></span>

- <span data-ttu-id="6eb22-110">Этап 3.</span><span class="sxs-lookup"><span data-stu-id="6eb22-110">Step 3.</span></span> <span data-ttu-id="6eb22-111">[Перенос конечных точек](decommission-move-on-prem-endpoints.md)гибридных приложений из локального в онлайн.</span><span class="sxs-lookup"><span data-stu-id="6eb22-111">[Migrate hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="6eb22-112">Этап 4.</span><span class="sxs-lookup"><span data-stu-id="6eb22-112">Step 4.</span></span> <span data-ttu-id="6eb22-113">[Удалите локальное развертывание Skype для бизнеса.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="6eb22-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6eb22-114">Этапы 2 и 3 должны быть сделаны в одном окне обслуживания, так как существующие конечные точки гибридного приложения не будут обнаружены между этапами 2 и завершением шага 3.</span><span class="sxs-lookup"><span data-stu-id="6eb22-114">Steps 2 and 3 should be done in the same maintenance window because any existing hybrid application endpoints will not be discoverable between steps 2 and completion of step 3.</span></span>

## <a name="overview"></a><span data-ttu-id="6eb22-115">Обзор</span><span class="sxs-lookup"><span data-stu-id="6eb22-115">Overview</span></span>

<span data-ttu-id="6eb22-116">После обновления всех пользователей из локального Skype для бизнеса до Teams только в Microsoft 365, вы можете списание локального Skype для бизнеса развертывания.</span><span class="sxs-lookup"><span data-stu-id="6eb22-116">After you have upgraded all users from Skype for Business on-premises to Teams Only in Microsoft 365, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="6eb22-117">Прежде чем отключать локальное развертывание Skype для бизнеса и удалять оборудование, необходимо логически отделить локальное развертывание от Microsoft 365 путем отключения гибрида.</span><span class="sxs-lookup"><span data-stu-id="6eb22-117">Before you decommission the on-premises Skype for Business deployment and remove any hardware, you must logically separate the on-premises deployment from Microsoft 365 by disabling hybrid.</span></span> <span data-ttu-id="6eb22-118">Отключение гибрида состоит из следующих четырех действий:</span><span class="sxs-lookup"><span data-stu-id="6eb22-118">Disabling hybrid consists of the following four steps:</span></span>

1. <span data-ttu-id="6eb22-119">Изменение DNS-записей, чтобы они указывали на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6eb22-119">Update DNS records to point to Microsoft 365.</span></span>

2. <span data-ttu-id="6eb22-120">Измените режим сосуществования для организации на Teams Только.</span><span class="sxs-lookup"><span data-stu-id="6eb22-120">Change the coexistence mode for your organization to Teams Only.</span></span>

3. <span data-ttu-id="6eb22-121">Отключение общего пространства адресов SIP (также известного как "раздельный домен") в Microsoft 365 организации.</span><span class="sxs-lookup"><span data-stu-id="6eb22-121">Disable shared sip address space (also known as "split domain") in the Microsoft 365 organization.</span></span>

4. <span data-ttu-id="6eb22-122">Отключить возможность локального общения с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6eb22-122">Disable the ability in on-premises to communicate with Microsoft 365.</span></span>

<span data-ttu-id="6eb22-123">Эти действия логически отделяют локальное развертывание Skype для бизнеса Server от Microsoft 365 и гарантируют полную Teams только.</span><span class="sxs-lookup"><span data-stu-id="6eb22-123">These steps logically separate your on-premises deployment of Skype for Business Server from Microsoft 365 and ensure your organization is fully Teams Only.</span></span> <span data-ttu-id="6eb22-124">Сведения о каждом шаге предоставляются в этой статье.</span><span class="sxs-lookup"><span data-stu-id="6eb22-124">Details for each step are provided in this article.</span></span> <span data-ttu-id="6eb22-125">По завершению развертывания можно списание локального Skype для бизнеса с помощью одного из двух методов, на которые ссылается ниже.</span><span class="sxs-lookup"><span data-stu-id="6eb22-125">Once that is complete, you can decommission your on-premises Skype for Business deployment by using one of two methods referenced below.</span></span>

> [!Important] 
> <span data-ttu-id="6eb22-126">После завершения этого логического разделения атрибуты msRTCSIP из локального Active Directory по-прежнему будут иметь значения и будут синхронизироваться с помощью Azure AD Подключение в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6eb22-126">Once this logical separation is complete, msRTCSIP attributes from your on-premises Active Directory still have values and will continue to sync via Azure AD Connect into Azure AD.</span></span> <span data-ttu-id="6eb22-127">Вывод локальной среды из эксплуатации зависит от того, собираетесь ли вы оставить эти атрибуты на месте или сначала очистить их от локального Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6eb22-127">How you decommission the on-premises environment depends on whether you intend to leave these attributes in place, or first clear them from your on-premises Active Directory.</span></span> <span data-ttu-id="6eb22-128">Следует помнить, что очистка атрибутов msRTCSIP на месте после миграции из локального помещения может привести к потере службы для пользователей!</span><span class="sxs-lookup"><span data-stu-id="6eb22-128">Be aware that clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span> <span data-ttu-id="6eb22-129">Подробные сведения и компромиссы двух подходов к выводу из эксплуатации описаны позже.</span><span class="sxs-lookup"><span data-stu-id="6eb22-129">Details and tradeoffs of the two decommissioning approaches are described later.</span></span>

## <a name="detailed-steps"></a><span data-ttu-id="6eb22-130">Подробные действия</span><span class="sxs-lookup"><span data-stu-id="6eb22-130">Detailed Steps</span></span>

1. <span data-ttu-id="6eb22-131">*Обновление DNS, чтобы указать на Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="6eb22-131">*Update DNS to point to Microsoft 365.*</span></span> <span data-ttu-id="6eb22-132">Внешние DNS организации для локальной организации должны быть обновлены таким образом, чтобы Skype для бизнеса записи указывают на Microsoft 365 вместо локального развертывания.</span><span class="sxs-lookup"><span data-stu-id="6eb22-132">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="6eb22-133">Это означает следующее:</span><span class="sxs-lookup"><span data-stu-id="6eb22-133">Specifically:</span></span>

    |<span data-ttu-id="6eb22-134">Тип записи</span><span class="sxs-lookup"><span data-stu-id="6eb22-134">Record type</span></span>|<span data-ttu-id="6eb22-135">Имя</span><span class="sxs-lookup"><span data-stu-id="6eb22-135">Name</span></span>|<span data-ttu-id="6eb22-136">TTL</span><span class="sxs-lookup"><span data-stu-id="6eb22-136">TTL</span></span>|<span data-ttu-id="6eb22-137">Priority</span><span class="sxs-lookup"><span data-stu-id="6eb22-137">Priority</span></span>|<span data-ttu-id="6eb22-138">Насыщенность</span><span class="sxs-lookup"><span data-stu-id="6eb22-138">Weight</span></span>|<span data-ttu-id="6eb22-139">Порт</span><span class="sxs-lookup"><span data-stu-id="6eb22-139">Port</span></span>|<span data-ttu-id="6eb22-140">Value (Значение)</span><span class="sxs-lookup"><span data-stu-id="6eb22-140">Value</span></span>|
    |---|---|---|---|---|---|---|
    |<span data-ttu-id="6eb22-141">SRV</span><span class="sxs-lookup"><span data-stu-id="6eb22-141">SRV</span></span>|<span data-ttu-id="6eb22-142">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="6eb22-142">_sipfederationtls._tcp</span></span>|<span data-ttu-id="6eb22-143">3600</span><span class="sxs-lookup"><span data-stu-id="6eb22-143">3600</span></span>|<span data-ttu-id="6eb22-144">100</span><span class="sxs-lookup"><span data-stu-id="6eb22-144">100</span></span>|<span data-ttu-id="6eb22-145">1</span><span class="sxs-lookup"><span data-stu-id="6eb22-145">1</span></span>|<span data-ttu-id="6eb22-146">5061</span><span class="sxs-lookup"><span data-stu-id="6eb22-146">5061</span></span>|<span data-ttu-id="6eb22-147">sipfed.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="6eb22-147">sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="6eb22-148">SRV</span><span class="sxs-lookup"><span data-stu-id="6eb22-148">SRV</span></span>|<span data-ttu-id="6eb22-149">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="6eb22-149">_sip._tls</span></span>|<span data-ttu-id="6eb22-150">3600</span><span class="sxs-lookup"><span data-stu-id="6eb22-150">3600</span></span>|<span data-ttu-id="6eb22-151">100</span><span class="sxs-lookup"><span data-stu-id="6eb22-151">100</span></span>|<span data-ttu-id="6eb22-152">1</span><span class="sxs-lookup"><span data-stu-id="6eb22-152">1</span></span>|<span data-ttu-id="6eb22-153">443</span><span class="sxs-lookup"><span data-stu-id="6eb22-153">443</span></span>|<span data-ttu-id="6eb22-154">sipdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="6eb22-154">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="6eb22-155">CNAME</span><span class="sxs-lookup"><span data-stu-id="6eb22-155">CNAME</span></span>| <span data-ttu-id="6eb22-156">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="6eb22-156">lyncdiscover</span></span>|   <span data-ttu-id="6eb22-157">3600</span><span class="sxs-lookup"><span data-stu-id="6eb22-157">3600</span></span>| | | |<span data-ttu-id="6eb22-158">webdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="6eb22-158">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="6eb22-159">CNAME</span><span class="sxs-lookup"><span data-stu-id="6eb22-159">CNAME</span></span>| <span data-ttu-id="6eb22-160">sip</span><span class="sxs-lookup"><span data-stu-id="6eb22-160">sip</span></span>|    <span data-ttu-id="6eb22-161">3600</span><span class="sxs-lookup"><span data-stu-id="6eb22-161">3600</span></span>| | | | <span data-ttu-id="6eb22-162">sipdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="6eb22-162">sipdir.online.lync.<span>com</span></span>|

    <span data-ttu-id="6eb22-163">Кроме того, записи CNAME для встречи или диалогов (если присутствуют) могут быть удалены.</span><span class="sxs-lookup"><span data-stu-id="6eb22-163">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="6eb22-164">Наконец, все записи DNS для Skype для бизнеса во внутренней сети должны быть удалены.</span><span class="sxs-lookup"><span data-stu-id="6eb22-164">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

    > [!Note] 
    > <span data-ttu-id="6eb22-165">В редких случаях изменение DNS с указать на Microsoft 365 для организации может привести к остановке работы федерации с некоторыми другими организациями до тех пор, пока другая организация не обновит конфигурацию федерации:</span><span class="sxs-lookup"><span data-stu-id="6eb22-165">In rare cases, changing DNS from pointing on premises to Microsoft 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
    >
    > - <span data-ttu-id="6eb22-166">Всем федератным организациям, использующим старую модель Direct Federation (также известный как Разрешенный сервер партнеров), необходимо обновить разрешенные записи домена для организации, чтобы удалить прокси-сервер FQDN.</span><span class="sxs-lookup"><span data-stu-id="6eb22-166">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="6eb22-167">Эта устаревшая модель федерации не основана на записях SRV DNS, поэтому такая конфигурация станет устаревшей после перемещения организации в облако.</span><span class="sxs-lookup"><span data-stu-id="6eb22-167">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
    > 
    > - <span data-ttu-id="6eb22-168">Любая федераированная организация, у нее нет включенного поставщика хостинга для sipfed.online.lync. <span> com необходимо обновить конфигурацию, чтобы включить это.</span><span class="sxs-lookup"><span data-stu-id="6eb22-168">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="6eb22-169">Такая ситуация возможна только в том случае, если федератерная организация является чисто локальной и никогда не федератовывалась с любым гибридным или сетевым клиентом.</span><span class="sxs-lookup"><span data-stu-id="6eb22-169">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="6eb22-170">В этом случае федерация с этими организациями не будет работать до тех пор, пока они не увявят поставщика хостинга.</span><span class="sxs-lookup"><span data-stu-id="6eb22-170">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
    >
    > <span data-ttu-id="6eb22-171">Если вы подозреваете, что любой из ваших федеративных партнеров может использовать Direct Federation или не был федеративен в какой-либо сетевой или гибридной организации, мы рекомендуем отправить им сообщение об этом при подготовке к завершению миграции в облако.</span><span class="sxs-lookup"><span data-stu-id="6eb22-171">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

2.  <span data-ttu-id="6eb22-172">*Измените режим сосуществования для организации на Teams Только.*</span><span class="sxs-lookup"><span data-stu-id="6eb22-172">*Change the coexistence mode for your organization to Teams Only.*</span></span> <span data-ttu-id="6eb22-173">Это гарантирует, что любой новый пользователь в организации всегда создается как Teams только пользователь.</span><span class="sxs-lookup"><span data-stu-id="6eb22-173">This ensures that any new user in your organization is always created as a Teams Only user.</span></span> <span data-ttu-id="6eb22-174">Кроме того, попытка изменить режим клиента на Teams только автоматически проверяет наличие каких-либо локальной DNS-записей, которые могли быть пропущены на шаге 1, и определяет эти записи в выходе.</span><span class="sxs-lookup"><span data-stu-id="6eb22-174">In addition,  attempting to change the tenant mode to Teams Only will automatically check for existence of any on-premises DNS records that may have been missed in step 1 and identify these records in the output.</span></span>  <span data-ttu-id="6eb22-175">Изменение режима клиента на Teams только не удастся до тех пор, пока не будут обновлены все записи DNS для вашего organisaiton.</span><span class="sxs-lookup"><span data-stu-id="6eb22-175">Changing the tenant mode to Teams Only will not succeed until all DNS records for your organizaiton are updated.</span></span> <span data-ttu-id="6eb22-176">Чтобы изменить режим клиента на Teams выполнить только следующую команду из окна Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6eb22-176">To change the tenant mode to Teams Only run the following command from a Teams PowerShell window.</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
     ```
<span data-ttu-id="6eb22-177">Кроме того, вы можете использовать центр администрирования Teams для изменения режима сосуществования клиента на TeamsOnly в соответствии с "Настройками на всей организации" -> "Teams обновление".</span><span class="sxs-lookup"><span data-stu-id="6eb22-177">Alternatively, you can use the Teams Admin Center to change the tenant coexistence mode to TeamsOnly, under "Org-wide settings" -> "Teams Upgrade."</span></span>    
    
3.  <span data-ttu-id="6eb22-178">*Отключение общего пространства адресов sip в Microsoft 365 организации.*</span><span class="sxs-lookup"><span data-stu-id="6eb22-178">*Disable shared sip address space in Microsoft 365 organization.*</span></span> <span data-ttu-id="6eb22-179">Команда ниже должна быть сделана из окна Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6eb22-179">The command below needs to be done from a Teams PowerShell window.</span></span>

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
4.  <span data-ttu-id="6eb22-180">*Отключить возможность локального общения с Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="6eb22-180">*Disable the ability in on-premises to communicate with Microsoft 365.*</span></span> <span data-ttu-id="6eb22-181">Команда, приведенная ниже, должна быть сделана из локального окна PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6eb22-181">The command below needs to be done from an on-premises PowerShell window:</span></span>

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="6eb22-182">Управление атрибутами после перемещения пользователей из локального в облако</span><span class="sxs-lookup"><span data-stu-id="6eb22-182">Managing attributes after moving users from on-premises to the cloud</span></span>

<span data-ttu-id="6eb22-183">По умолчанию все пользователи, которые ранее были включены для Skype для бизнеса Server и впоследствии перемещены в облако, по-прежнему имеют атрибуты msRTCSIP, настроенные в локальном Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6eb22-183">By default, all users that were previously enabled for Skype for Business Server and subsequently moved to the cloud still have msRTCSIP attributes configured in your on-premises Active Directory.</span></span> <span data-ttu-id="6eb22-184">Эти атрибуты, в частности SIP-адрес (msRTCSIP-PrimaryUserAddress) и потенциально номер телефона (msRTCSIP-Line), продолжают синхронизироваться с Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6eb22-184">These attributes, in particular sip address (msRTCSIP-PrimaryUserAddress) and potentially phone number (msRTCSIP-Line), continue to sync into Azure AD.</span></span> <span data-ttu-id="6eb22-185">Если требуется изменить любой из атрибутов msRTCSIP, эти изменения необходимо внести в локальном Active Directory, а затем синхронизировать его с Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6eb22-185">If changes are required to any of the msRTCSIP attributes, these changes must be made in the on-premises Active Directory and then sync'd to Azure AD.</span></span> <span data-ttu-id="6eb22-186">Однако после удаления Skype для бизнеса Server, Skype для бизнеса Server средства управления этими атрибутами будут недоступны.</span><span class="sxs-lookup"><span data-stu-id="6eb22-186">However, once the Skype for Business Server deployment has been removed, the Skype for Business Server tools will not be available to manage these attributes.</span></span>

<span data-ttu-id="6eb22-187">Существует два варианта обработки этой ситуации:</span><span class="sxs-lookup"><span data-stu-id="6eb22-187">There are two options available for handling this situation:</span></span>

1. <span data-ttu-id="6eb22-188">Оставьте пользователей, включенных для Skype для бизнеса серверных учетных записей, как есть, и управляйте атрибутами msRTCSIP с помощью средств Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6eb22-188">Leave users that were enabled for Skype for Business server accounts as is, and manage the  msRTCSIP attributes using Active Directory tools.</span></span> <span data-ttu-id="6eb22-189">Это обеспечивает отсутствие потери службы для перенесенных пользователей и позволяет легко удалить развертывание Skype для бизнеса Server путем удаления (например, удаления) серверов без полного вывода из эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="6eb22-189">This ensures no loss of service for migrated users, and allows you to easily remove the Skype for Business Server deployment by eliminating (e.g. wiping) the servers, without a full decommissioning.</span></span> <span data-ttu-id="6eb22-190">Однако новые лицензированные пользователи не будут иметь эти атрибуты, заполняемые в локальном каталоге Active Directory, и им необходимо управлять в Интернете.</span><span class="sxs-lookup"><span data-stu-id="6eb22-190">However, newly licensed users will not have these attributes populated in your on-premises Active Directory and will need to be managed online.</span></span>

2.  <span data-ttu-id="6eb22-191">Очистить все атрибуты msRTCSIP от перенесенных пользователей в локальном Каталоге Active Directory и управлять этими атрибутами с помощью сетевых средств.</span><span class="sxs-lookup"><span data-stu-id="6eb22-191">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span></span> <span data-ttu-id="6eb22-192">Этот метод позволяет использовать последовательный подход к управлению для существующих и новых пользователей, однако он потенциально может привести к временной потере службы во время локального процесса вывода из эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="6eb22-192">This method allows for a consistent management approach for existing and new users, however it may potentially result in a temporary loss of service during the on-premises decommissioning process.</span></span>


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a><span data-ttu-id="6eb22-193">Метод 1 . Управление SIP-адресами и номерами телефонов для пользователей Active Directory</span><span class="sxs-lookup"><span data-stu-id="6eb22-193">Method 1 - Manage sip addresses and phone numbers for users in Active Directory</span></span>

<span data-ttu-id="6eb22-194">Администраторы могут управлять пользователями, которые ранее были перемещены из локального Skype для бизнеса Server в облако, даже после вывода из эксплуатации локального развертывания.</span><span class="sxs-lookup"><span data-stu-id="6eb22-194">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="6eb22-195">Если вы хотите внести изменения в SIP-адрес пользователя или номер телефона пользователя (а sip-адрес или номер телефона уже имеет значение в локальном Active Directory), необходимо сделать это в локальном Active Directory и позволить значению (s) перетекать в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6eb22-195">If you want to make changes to a user’s sip address or to a user’s phone number (and the sip address or phone number already has a value in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="6eb22-196">Для этого не требуется локальное Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6eb22-196">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="6eb22-197">Скорее, эти атрибуты можно изменить непосредственно в локальном Active Directory, используя либо оснастку MMC пользователей Active Directory и компьютеров (как показано ниже), либо с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6eb22-197">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in (as shown below), or by using PowerShell.</span></span> <span data-ttu-id="6eb22-198">Если вы используете оснастку MMC, откройте страницу свойств пользователя, нажмите кнопку Редактор атрибута и найдите соответствующие атрибуты для изменения:</span><span class="sxs-lookup"><span data-stu-id="6eb22-198">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="6eb22-199">Чтобы изменить SIP-адрес пользователя, измените `msRTCSIP-PrimaryUserAddress` .</span><span class="sxs-lookup"><span data-stu-id="6eb22-199">To modify a user’s sip address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6eb22-200">Если атрибут `ProxyAddresses` содержит SIP-адрес, также обнови это значение в качестве наилучшей практики.</span><span class="sxs-lookup"><span data-stu-id="6eb22-200">If the `ProxyAddresses` attribute contains a sip address, also update that value as a best practice.</span></span> <span data-ttu-id="6eb22-201">Несмотря на то, что адрес SIP в случае заполнения игнорируется O365, он может использоваться другими компонентами `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` локального использования.</span><span class="sxs-lookup"><span data-stu-id="6eb22-201">Although the sip address in `ProxyAddresses` is ignored by O365 if `msRTCSIP-PrimaryUserAddress` is populated, it may be used by other on-premises components.</span></span>

- <span data-ttu-id="6eb22-202">Чтобы изменить телефонный номер пользователя, `msRTCSIP-Line` *измените, если он уже имеет значение*.</span><span class="sxs-lookup"><span data-stu-id="6eb22-202">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Средство для пользователей и компьютеров Active Directory](../media/disable-hybrid-1.png)
  
-  <span data-ttu-id="6eb22-204">Если у пользователя изначально не было значения для локального перед перемещением, можно изменить номер телефона с помощью параметра `msRTCSIP-Line` в командлете `onpremLineUri` [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) в модуле Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6eb22-204">If the user did not originally have a value for `msRTCSIP-Line` on-premises before the move, you can modify the phone number using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

<span data-ttu-id="6eb22-205">Эти действия не являются необходимыми для новых пользователей, созданных после отключения гибрида, и управлять этими пользователями можно непосредственно в облаке.</span><span class="sxs-lookup"><span data-stu-id="6eb22-205">These steps are not necessary for new users created after you disable hybrid, and those users can be managed directly in the cloud.</span></span> <span data-ttu-id="6eb22-206">Если вам удобно использовать сочетание этих методов, а также оставить атрибуты msRTCSIP на месте в локальном Active Directory, вы можете просто повторно образ локального Skype для бизнеса серверов.</span><span class="sxs-lookup"><span data-stu-id="6eb22-206">If you are comfortable using the mix of these method as well as with leaving the msRTCSIP attributes in place in your on-premises Active Directory, you can simply re-image the on-premises Skype for Business servers.</span></span> <span data-ttu-id="6eb22-207">Однако если вы предпочитаете очистить все атрибуты msRTCSIP и сделать традиционный Skype для бизнеса Server, используйте Метод 2.</span><span class="sxs-lookup"><span data-stu-id="6eb22-207">However, if you prefer to clear all msRTCSIP attributes and do a traditional uninstall of Skype for Business Server, then use Method 2.</span></span>


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a><span data-ttu-id="6eb22-208">Метод 2 . Skype для бизнеса атрибуты для всех локального пользователя в Active Directory</span><span class="sxs-lookup"><span data-stu-id="6eb22-208">Method 2 - Clear Skype for Business Attributes for all on-premises users in Active Directory</span></span>

<span data-ttu-id="6eb22-209">Этот параметр требует дополнительных усилий и надлежащего планирования, так как пользователи, которые ранее были перемещены из локального Skype для бизнеса Server в облако, должны быть повторно продвинуты.</span><span class="sxs-lookup"><span data-stu-id="6eb22-209">This option requires additional effort and proper planning because users who were previously moved from an on-premises Skype for Business Server to the cloud are required to be re-provisioned.</span></span> <span data-ttu-id="6eb22-210">Эти пользователи могут быть классифицированы на две разные категории: пользователи без телефонная система и пользователи с телефонная система.</span><span class="sxs-lookup"><span data-stu-id="6eb22-210">These users can be categorized into two different categories: users without Phone System and users with Phone System.</span></span> <span data-ttu-id="6eb22-211">Пользователи с телефонная система будут испытывать временную потерю телефонной службы в рамках перехода номера телефона от управления в локальном Active Directory в облако.</span><span class="sxs-lookup"><span data-stu-id="6eb22-211">Users with Phone System will experience a temporary loss of phone service as part of transitioning the phone number from being managed in on-premises Active Directory to the cloud.</span></span> <span data-ttu-id="6eb22-212">**Перед началом массовых операций рекомендуется выполнить пилотную работу с небольшим числом пользователей с телефонная система пользователями.**</span><span class="sxs-lookup"><span data-stu-id="6eb22-212">**It's recommended to perform a pilot involving a small number of users with Phone System prior to start bulk user operations.**</span></span> <span data-ttu-id="6eb22-213">Для больших развертывания пользователи могут обрабатываться в небольших группах в разных окнах времени.</span><span class="sxs-lookup"><span data-stu-id="6eb22-213">For large deployments users can be processed in smaller groups in different time windows.</span></span> 

> [!NOTE] 
> <span data-ttu-id="6eb22-214">Этот процесс прост для пользователей, у которых есть совпадающий sip-адрес и UserPrincipalName.</span><span class="sxs-lookup"><span data-stu-id="6eb22-214">This process is simplest for users who have a matching sip address and UserPrincipalName.</span></span> <span data-ttu-id="6eb22-215">Для организаций, у пользователей с не совпадающих значений между этими двумя атрибутами, необходимо принять дополнительные меры, как отмечено ниже, для плавного перехода.</span><span class="sxs-lookup"><span data-stu-id="6eb22-215">For organizations that have users with non-matching values across these two attributes, extra care must be taken as noted below for a smooth transition.</span></span>

> [!NOTE]
> <span data-ttu-id="6eb22-216">Если вы настроили конечные точки гибридного приложения для автоспутников или очередей вызовов, не забудьте переместить эти конечные точки в Microsoft 365 до вывода из эксплуатации Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6eb22-216">If you have configured on-premises hybrid application endpoints for Auto Attendants or Call Queues, be sure to move these endpoints to Microsoft 365 before decommissioning Skype for Business Server.</span></span>


1. <span data-ttu-id="6eb22-217">Подтверждение следующего локального Skype для бизнеса PowerShell возвращает пустой результат.</span><span class="sxs-lookup"><span data-stu-id="6eb22-217">Confirm the following on-premises Skype for Business PowerShell cmdlet returns an empty result.</span></span> <span data-ttu-id="6eb22-218">Пустой результат означает, что пользователи не находятся в локальном помещении и не были перемещены в Microsoft 365 или отключены:</span><span class="sxs-lookup"><span data-stu-id="6eb22-218">An empty result means no users are homed on-premises and have either been moved to Microsoft 365 or have been disabled:</span></span>

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. <span data-ttu-id="6eb22-219">Запись текущего номера телефонов пользователей (LineUri), UserPrincipalName и связанных с ними данных, путем выполнения следующего локального Skype для бизнеса Server PowerShell для экспорта пользовательских данных:</span><span class="sxs-lookup"><span data-stu-id="6eb22-219">Record users' current phones number (LineUri), UserPrincipalName and related info, by executing the following on-premises Skype for Business Server PowerShell cmdlet to export user data:</span></span>

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="6eb22-220">Перед открытием SfbUserSettings.csv файл и подтверждение успешного экспорта всех пользовательских данных.</span><span class="sxs-lookup"><span data-stu-id="6eb22-220">Before proceeding open SfbUserSettings.csv file and confirm all user data has been successfully exported.</span></span> <span data-ttu-id="6eb22-221">Рекомендуется хранить копию этого файла.</span><span class="sxs-lookup"><span data-stu-id="6eb22-221">It's recommended to keep a copy of this file.</span></span>  <span data-ttu-id="6eb22-222">Не используйте этот файл в следующих действиях для обработки пользователей.</span><span class="sxs-lookup"><span data-stu-id="6eb22-222">Do not use this file in the following steps for processing users.</span></span> 

3. <span data-ttu-id="6eb22-223">Создайте файл с группой пользователей, который будет использоваться в следующих действиях.</span><span class="sxs-lookup"><span data-stu-id="6eb22-223">Create a file with a group of users to be used in the following steps.</span></span> <span data-ttu-id="6eb22-224">После успешного завершения работы первой группы пользователей приступим к следующей группе пользователей.</span><span class="sxs-lookup"><span data-stu-id="6eb22-224">After the first group of users has completed successfully, proceed with the next group of users.</span></span> <span data-ttu-id="6eb22-225">В приведенном ниже примере группы пользователей выбираются в алфавитном порядке, но можно фильтровать пользователей на основе критериев, которые соответствуют тому, как вы хотите обрабатывать пользователей.</span><span class="sxs-lookup"><span data-stu-id="6eb22-225">In the example below, the groups of users are selected alphabetically, but you may filter on users based on criteria that matches how you would like to process the users.</span></span>

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="6eb22-226">Перед открытием SfbUsers.csv файл и подтверждение успешного экспорта пользовательских данных.</span><span class="sxs-lookup"><span data-stu-id="6eb22-226">Before proceeding open SfbUsers.csv file and confirm user data has been successfully exported.</span></span> <span data-ttu-id="6eb22-227">На более позднем этапе вам потребуется LineUri (номер телефона), UserPrincipalName, SamAccountName и SipAddress из этого файла.</span><span class="sxs-lookup"><span data-stu-id="6eb22-227">You will need the LineUri (phone number), UserPrincipalName, SamAccountName, and SipAddress from this file in a later step.</span></span>

4. <span data-ttu-id="6eb22-228">Удаление сведений о атрибутах, связанных Skype для бизнеса Server из active Directory для набора пользователей, которые вы готовы обновить.</span><span class="sxs-lookup"><span data-stu-id="6eb22-228">Delete the attribute information related to Skype for Business Server from active Directory for the set of users you are ready to update.</span></span>  <span data-ttu-id="6eb22-229">Существует 2 шага к этому процессу, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="6eb22-229">There are 2 steps to this process, as shown below.</span></span>

   > [!Important] 
   > <span data-ttu-id="6eb22-230">После следующего цикла AAD Sync после запуска этого шага пользователи с телефонная система, которые ранее были перемещены из локального Skype для бизнеса Server в облако, потеряют возможность выполнять и принимать вызовы до тех пор, пока шаг 8 не будет успешно завершен и подтвержден на шаге 9.</span><span class="sxs-lookup"><span data-stu-id="6eb22-230">After the next AAD Sync cycle after running this step, users with Phone System who were previously moved from an on-premises Skype for Business Server to the cloud will lose the ability to make and receive calls until step 8 is successfully completed and confirmed in step 9.</span></span> <span data-ttu-id="6eb22-231">Кроме того, убедитесь, что на шаге 2 сохранены номера телефонов и связанные сведения пользователя, так как эта информация необходима для этого шага.</span><span class="sxs-lookup"><span data-stu-id="6eb22-231">In addition, make sure you have saved user's phone numbers and related information as per step 2, since that information is required for that step.</span></span>

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   <span data-ttu-id="6eb22-232">Далее, для того же набора пользователей, очистить значение msRTCSIP-DeploymentLocator с помощью локального Active Directory PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6eb22-232">Next, for the same set of users, clear the value of msRTCSIP-DeploymentLocator using on-premises Active Directory PowerShell:</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. <span data-ttu-id="6eb22-233">Запустите следующий локальном модуле Active Directory для командлета Windows PowerShell, чтобы добавить значение SIP-адреса обратно в локальное прокси-серверы Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6eb22-233">Run the following on-premise Active Directory Module for Windows PowerShell cmdlet to add sip address value back to the on-premises Active Directory proxyAddresses.</span></span> <span data-ttu-id="6eb22-234">Это позволит предотвратить проблемы с интероперабельностью, которые зависят от этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="6eb22-234">This will prevent interoperability issues that rely on this attribute.</span></span> 

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
     $userUpn=$user.UserPrincipalName
     $userSip=$user.SipAddress
     $proxies=Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" -properties * | Select-Object @{Name="proxyAddresses";Expression={$_.proxyAddresses}}
     if(($null -eq $proxies) -or ($proxies.proxyAddresses -NotContains $userSip))
     {
             Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" | Set-ADUser -Add @{"proxyAddresses"=$user.SipAddress}
     }
   }
   ```

6. <span data-ttu-id="6eb22-235">Запуск Azure AD Sync</span><span class="sxs-lookup"><span data-stu-id="6eb22-235">Run Azure AD Sync</span></span>

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. <span data-ttu-id="6eb22-236">Подождите, пока подготовка пользователей завершится.</span><span class="sxs-lookup"><span data-stu-id="6eb22-236">Wait for user provisioning to complete.</span></span> <span data-ttu-id="6eb22-237">Вы можете отслеживать ход подготовка пользователей, запуская следующую команду Skype для бизнеса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6eb22-237">You can monitor user provisioning progress by running the following Skype for Business Online PowerShell command.</span></span> <span data-ttu-id="6eb22-238">Следующая команда Skype для бизнеса PowerShell возвращает пустой результат по мере завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="6eb22-238">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. <span data-ttu-id="6eb22-239">Выполните следующую команду Skype для бизнеса PowerShell, чтобы назначить номера телефонов и включить пользователей для телефонная система:</span><span class="sxs-lookup"><span data-stu-id="6eb22-239">Execute the following Skype for Business Online PowerShell command to assign phone numbers and enable users for Phone System:</span></span>
     
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
                Set-CsUser -Identity $user.SipAddress -OnPremLineURI $user.LineUri -EnterpriseVoiceEnabled $True
        }
   }
    ```

   > [!Note]
   >  <span data-ttu-id="6eb22-240">Если у вас Skype для бизнеса конечные точки (Skype клиенты или 3-й телефон участника), вам также необходимо установить -HostedVoiceMail для $true.</span><span class="sxs-lookup"><span data-stu-id="6eb22-240">If you still have Skype for Business endpoints (either Skype clients or 3rd party phones), you will also want to set -HostedVoiceMail to $true.</span></span> <span data-ttu-id="6eb22-241">Если ваша организация использует только Teams конечные точки для пользователей с включенной голосовой поддержкой, этот параметр не применим к пользователям.</span><span class="sxs-lookup"><span data-stu-id="6eb22-241">If your organization is only using Teams endpoints for voice enabled users, this setting is not applicable to your users.</span></span> 

9. <span data-ttu-id="6eb22-242">Подтвердит правильность телефонная система пользователей с функциональными возможностями.</span><span class="sxs-lookup"><span data-stu-id="6eb22-242">Confirm users with Phone System functionality have been provisioned correctly.</span></span> <span data-ttu-id="6eb22-243">Следующая команда Skype для бизнеса PowerShell возвращает пустой результат по мере завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="6eb22-243">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled, HostedVoicemail
                }
        }
   }
   ``` 

10. <span data-ttu-id="6eb22-244">Повторите действия от 3 до 9 до тех пор, пока все пользователи не будут обработаны.</span><span class="sxs-lookup"><span data-stu-id="6eb22-244">Repeat steps 3 through 9 until all users are processed.</span></span>

11. <span data-ttu-id="6eb22-245">Подтверди, что все пользователи успешно обработаны, запуская следующие две команды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6eb22-245">Confirm that all users have been processed successfully by running the following two PowerShell commands.</span></span>

    <span data-ttu-id="6eb22-246">Локальное Skype для бизнеса Server powerShell:</span><span class="sxs-lookup"><span data-stu-id="6eb22-246">On-premises Skype for Business Server on-premises PowerShell command:</span></span>

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    <span data-ttu-id="6eb22-247">Skype для бизнеса Команда Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6eb22-247">Skype for Business Online PowerShell command:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. <span data-ttu-id="6eb22-248">После завершения всех действий в методе 2 см. в рубке Перемещение [](decommission-remove-on-prem.md) конечных точек гибридного приложения из локального в интернет и удаление локального Skype для бизнеса Server дополнительных действий по удалению Skype для бизнеса Server локального развертывания. [](decommission-move-on-prem-endpoints.md)</span><span class="sxs-lookup"><span data-stu-id="6eb22-248">After you have completed all steps in Method 2, see [Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md) and [Remove your on-premises Skype for Business Server](decommission-remove-on-prem.md) for additional steps to remove your Skype for Business Server on-premises deployment.</span></span>


## <a name="see-also"></a><span data-ttu-id="6eb22-249">См. также</span><span class="sxs-lookup"><span data-stu-id="6eb22-249">See also</span></span>

- [<span data-ttu-id="6eb22-250">Консолидация облаков для Teams и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="6eb22-250">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="6eb22-251">Прекращение использования локальной среды Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="6eb22-251">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

