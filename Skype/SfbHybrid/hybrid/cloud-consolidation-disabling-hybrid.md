---
title: Отключение гибридной среды для завершения миграции в облако
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
description: В этой статье содержатся подробные действия по отключению гибрида в рамках консолидации облачных технологий для Teams и Skype для бизнеса.
ms.openlocfilehash: 5528172c6a9309a0884c9417a64da589f0f0d4a4
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593857"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-the-cloud"></a><span data-ttu-id="4e5f5-103">Отключение гибридной конфигурации для завершения миграции в облако</span><span class="sxs-lookup"><span data-stu-id="4e5f5-103">Disable your hybrid configuration to complete migration to the cloud</span></span>

<span data-ttu-id="4e5f5-104">В этой статье описывается отключение гибридной конфигурации до вывода из эксплуатации локальной среды Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-104">This article describes how to disable your hybrid configuration before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="4e5f5-105">Это шаг 2 из следующих действий по выводу из эксплуатации локальной среды:</span><span class="sxs-lookup"><span data-stu-id="4e5f5-105">This is step 2 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="4e5f5-106">Этап 1.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-106">Step 1.</span></span> <span data-ttu-id="4e5f5-107">[Перемещение всех необходимых пользователей и конечных точек приложения](decommission-move-on-prem-users.md)из локального в интернет.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-107">[Move all required users and application endpoints from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="4e5f5-108">**Шаг 2. Отключите гибридную конфигурацию.**</span><span class="sxs-lookup"><span data-stu-id="4e5f5-108">**Step 2. Disable your hybrid configuration.**</span></span> <span data-ttu-id="4e5f5-109">(В этой статье)</span><span class="sxs-lookup"><span data-stu-id="4e5f5-109">(This article)</span></span>

- <span data-ttu-id="4e5f5-110">Шаг 3.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-110">Step 3.</span></span> <span data-ttu-id="4e5f5-111">[Удалите локальное развертывание Skype для бизнеса.](decommission-remove-on-prem.md)</span><span class="sxs-lookup"><span data-stu-id="4e5f5-111">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="overview"></a><span data-ttu-id="4e5f5-112">Обзор</span><span class="sxs-lookup"><span data-stu-id="4e5f5-112">Overview</span></span>

<span data-ttu-id="4e5f5-113">После обновления всех пользователей из локального Skype для бизнеса в Teams Только в Microsoft 365 можно выкипать локальное развертывание Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-113">After you have upgraded all users from Skype for Business on-premises to Teams Only in Microsoft 365, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="4e5f5-114">Прежде чем отключать локальное развертывание Skype для бизнеса и удалять любое оборудование, необходимо логически отделить локальное развертывание от Microsoft 365, отключив гибрид.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-114">Before you decommission the on-premises Skype for Business deployment and remove any hardware, you must logically separate the on-premises deployment from Microsoft 365 by disabling hybrid.</span></span> <span data-ttu-id="4e5f5-115">Отключение гибрида состоит из следующих трех этапов:</span><span class="sxs-lookup"><span data-stu-id="4e5f5-115">Disabling hybrid consists of the following three steps:</span></span>

1. <span data-ttu-id="4e5f5-116">Изменение DNS-записей, чтобы они указывали на Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-116">Update DNS records to point to Microsoft 365.</span></span>

2. <span data-ttu-id="4e5f5-117">Отключение общего пространства адресов SIP (также известного как "раздельный домен") в организации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-117">Disable shared sip address space (also known as "split domain") in the Microsoft 365 organization.</span></span>

3. <span data-ttu-id="4e5f5-118">Отключить возможность локального общения с Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-118">Disable the ability in on-premises to communicate with Microsoft 365.</span></span>

<span data-ttu-id="4e5f5-119">Эти действия логически отделяют локальное развертывание Skype для бизнеса Server от Microsoft 365 и должны быть сделаны вместе как подразделение.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-119">These steps logically separate your on-premises deployment of Skype for Business Server from Microsoft 365 and should be done together as a unit.</span></span> <span data-ttu-id="4e5f5-120">Сведения о каждом шаге предоставляются в этой статье.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-120">Details for each step are provided in this article.</span></span> <span data-ttu-id="4e5f5-121">По завершению развертывания Skype для бизнеса можно выписаться из эксплуатации с помощью одного из двух методов, на которые ссылается ниже.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-121">Once that is complete, you can decommission your on-premises Skype for Business deployment by using one of two methods referenced below.</span></span>

> [!Important] 
> <span data-ttu-id="4e5f5-122">После завершения этого логического разделения атрибуты msRTCSIP из локального Active Directory по-прежнему будут иметь значения и будут синхронизироваться с помощью Azure AD Connect в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-122">Once this logical separation is complete, msRTCSIP attributes from your on-premises Active Directory still have values and will continue to sync via Azure AD Connect into Azure AD.</span></span> <span data-ttu-id="4e5f5-123">Вывод локальной среды из эксплуатации зависит от того, собираетесь ли вы оставить эти атрибуты на месте или сначала очистить их от локального Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-123">How you decommission the on-premises environment depends on whether you intend to leave these attributes in place, or first clear them from your on-premises Active Directory.</span></span> <span data-ttu-id="4e5f5-124">Следует помнить, что очистка атрибутов msRTCSIP на месте после миграции из локального помещения может привести к потере службы для пользователей!</span><span class="sxs-lookup"><span data-stu-id="4e5f5-124">Be aware that clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span> <span data-ttu-id="4e5f5-125">Подробные сведения и компромиссы двух подходов к выводу из эксплуатации описаны позже.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-125">Details and tradeoffs of the two decommissioning approaches are described later.</span></span>

## <a name="detailed-steps"></a><span data-ttu-id="4e5f5-126">Подробные действия</span><span class="sxs-lookup"><span data-stu-id="4e5f5-126">Detailed Steps</span></span>

1. <span data-ttu-id="4e5f5-127">*Обновив DNS, указав на Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="4e5f5-127">*Update DNS to point to Microsoft 365.*</span></span> <span data-ttu-id="4e5f5-128">Внешний DNS организации для локальной организации необходимо обновить, чтобы записи Skype для бизнеса указывают на Microsoft 365 вместо локального развертывания.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-128">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="4e5f5-129">Это означает следующее:</span><span class="sxs-lookup"><span data-stu-id="4e5f5-129">Specifically:</span></span>

    |<span data-ttu-id="4e5f5-130">Тип записи</span><span class="sxs-lookup"><span data-stu-id="4e5f5-130">Record type</span></span>|<span data-ttu-id="4e5f5-131">Имя</span><span class="sxs-lookup"><span data-stu-id="4e5f5-131">Name</span></span>|<span data-ttu-id="4e5f5-132">TTL</span><span class="sxs-lookup"><span data-stu-id="4e5f5-132">TTL</span></span>|<span data-ttu-id="4e5f5-133">Value (Значение)</span><span class="sxs-lookup"><span data-stu-id="4e5f5-133">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="4e5f5-134">SRV</span><span class="sxs-lookup"><span data-stu-id="4e5f5-134">SRV</span></span>|<span data-ttu-id="4e5f5-135">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="4e5f5-135">_sipfederationtls._tcp</span></span>|<span data-ttu-id="4e5f5-136">3600</span><span class="sxs-lookup"><span data-stu-id="4e5f5-136">3600</span></span>|<span data-ttu-id="4e5f5-137">100 1 5061 sipfed.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="4e5f5-137">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="4e5f5-138">SRV</span><span class="sxs-lookup"><span data-stu-id="4e5f5-138">SRV</span></span>|<span data-ttu-id="4e5f5-139">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="4e5f5-139">_sip._tls</span></span>|<span data-ttu-id="4e5f5-140">3600</span><span class="sxs-lookup"><span data-stu-id="4e5f5-140">3600</span></span>|<span data-ttu-id="4e5f5-141">100 1 443 sipdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="4e5f5-141">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="4e5f5-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="4e5f5-142">CNAME</span></span>| <span data-ttu-id="4e5f5-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="4e5f5-143">lyncdiscover</span></span>|   <span data-ttu-id="4e5f5-144">3600</span><span class="sxs-lookup"><span data-stu-id="4e5f5-144">3600</span></span>|   <span data-ttu-id="4e5f5-145">webdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="4e5f5-145">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="4e5f5-146">CNAME</span><span class="sxs-lookup"><span data-stu-id="4e5f5-146">CNAME</span></span>| <span data-ttu-id="4e5f5-147">sip</span><span class="sxs-lookup"><span data-stu-id="4e5f5-147">sip</span></span>|    <span data-ttu-id="4e5f5-148">3600</span><span class="sxs-lookup"><span data-stu-id="4e5f5-148">3600</span></span>|   <span data-ttu-id="4e5f5-149">sipdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="4e5f5-149">sipdir.online.lync.<span>com</span></span>|

    <span data-ttu-id="4e5f5-150">Кроме того, записи CNAME для встречи или диалогов (если присутствуют) могут быть удалены.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-150">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="4e5f5-151">Наконец, все записи DNS для Skype для бизнеса во внутренней сети должны быть удалены.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-151">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

    > [!Note] 
    > <span data-ttu-id="4e5f5-152">В редких случаях изменение DNS с локальной указать на Microsoft 365 для вашей организации может привести к остановке работы федерации с некоторыми другими организациями до тех пор, пока другая организация не обновит конфигурацию федерации:</span><span class="sxs-lookup"><span data-stu-id="4e5f5-152">In rare cases, changing DNS from pointing on premises to Microsoft 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
    >
    > - <span data-ttu-id="4e5f5-153">Всем федератным организациям, использующим старую модель Direct Federation (также известный как Разрешенный сервер партнеров), необходимо обновить разрешенные записи домена для организации, чтобы удалить прокси-сервер FQDN.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-153">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="4e5f5-154">Эта устаревшая модель федерации не основана на записях SRV DNS, поэтому такая конфигурация станет устаревшей после перемещения организации в облако.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-154">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
    > 
    > - <span data-ttu-id="4e5f5-155">Любая федераированная организация, у нее нет включенного поставщика хостинга для sipfed.online.lync. <span> com необходимо обновить конфигурацию, чтобы включить это.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-155">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="4e5f5-156">Такая ситуация возможна только в том случае, если федератерная организация является чисто локальной и никогда не федератовывалась с любым гибридным или сетевым клиентом.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-156">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="4e5f5-157">В этом случае федерация с этими организациями не будет работать до тех пор, пока они не увявят поставщика хостинга.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-157">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
    >
    > <span data-ttu-id="4e5f5-158">Если вы подозреваете, что любой из ваших федеративных партнеров может использовать Direct Federation или не был федеративен в какой-либо сетевой или гибридной организации, мы рекомендуем отправить им сообщение об этом при подготовке к завершению миграции в облако.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-158">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>


2.  <span data-ttu-id="4e5f5-159">*Отключение общего пространства адресов SIP в организации Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="4e5f5-159">*Disable shared sip address space in Microsoft 365 organization.*</span></span> <span data-ttu-id="4e5f5-160">Команда, приведенная ниже, должна быть сделана из окна Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-160">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
3.  <span data-ttu-id="4e5f5-161">*Отключить возможность локального общения с Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="4e5f5-161">*Disable the ability in on-premises to communicate with Microsoft 365.*</span></span> <span data-ttu-id="4e5f5-162">Команда, приведенная ниже, должна быть сделана из локального окна PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4e5f5-162">The command below needs to be done from an on-premises PowerShell window:</span></span>

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="4e5f5-163">Управление атрибутами после перемещения пользователей из локального в облако</span><span class="sxs-lookup"><span data-stu-id="4e5f5-163">Managing attributes after moving users from on-premises to the cloud</span></span>

<span data-ttu-id="4e5f5-164">По умолчанию все пользователи, которые ранее были включены для Skype для бизнес-сервера и впоследствии перемещены в облако, по-прежнему имеют атрибуты msRTCSIP, настроенные в локальном Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-164">By default, all users that were previously enabled for Skype for Business Server and subsequently moved to the cloud still have msRTCSIP attributes configured in your on-premises Active Directory.</span></span> <span data-ttu-id="4e5f5-165">Эти атрибуты, в частности SIP-адрес (msRTCSIP-PrimaryUserAddress) и потенциально номер телефона (msRTCSIP-Line), продолжают синхронизироваться с Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-165">These attributes, in particular sip address (msRTCSIP-PrimaryUserAddress) and potentially phone number (msRTCSIP-Line), continue to sync into Azure AD.</span></span> <span data-ttu-id="4e5f5-166">Если требуется изменить любой из атрибутов msRTCSIP, эти изменения необходимо внести в локальном Active Directory, а затем синхронизировать его с Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-166">If changes are required to any of the msRTCSIP attributes, these changes must be made in the on-premises Active Directory and then sync'd to Azure AD.</span></span> <span data-ttu-id="4e5f5-167">Однако после удаления развертывания Skype для бизнес-сервера средства Skype для бизнеса Server будут недоступны для управления этими атрибутами.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-167">However, once the Skype for Business Server deployment has been removed, the Skype for Business Server tools will not be available to manage these attributes.</span></span>

<span data-ttu-id="4e5f5-168">Существует два варианта обработки этой ситуации:</span><span class="sxs-lookup"><span data-stu-id="4e5f5-168">There are two options available for handling this situation:</span></span>

1. <span data-ttu-id="4e5f5-169">Оставьте пользователей, включенных для учетных записей серверов Skype для бизнеса, и управляйте атрибутами msRTCSIP с помощью средств Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-169">Leave users that were enabled for Skype for Business server accounts as is, and manage the  msRTCSIP attributes using Active Directory tools.</span></span> <span data-ttu-id="4e5f5-170">Это обеспечивает отсутствие потери службы для перенесенных пользователей и позволяет легко удалить развертывание Skype для бизнес-сервера, устранив (например, удаление) серверов без полного вывода из эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-170">This ensures no loss of service for migrated users, and allows you to easily remove the Skype for Business Server deployment by eliminating (e.g. wiping) the servers, without a full decommissioning.</span></span> <span data-ttu-id="4e5f5-171">Однако новые лицензированные пользователи не будут иметь эти атрибуты, заполняемые в локальном каталоге Active Directory, и им необходимо управлять в Интернете.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-171">However, newly licensed users will not have these attributes populated in your on-premises Active Directory and will need to be managed online.</span></span>

2.  <span data-ttu-id="4e5f5-172">Очистить все атрибуты msRTCSIP от перенесенных пользователей в локальном Каталоге Active Directory и управлять этими атрибутами с помощью сетевых средств.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-172">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span></span> <span data-ttu-id="4e5f5-173">Этот метод позволяет использовать последовательный подход к управлению для существующих и новых пользователей, однако он потенциально может привести к временной потере службы во время локального процесса вывода из эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-173">This method allows for a consistent management approach for existing and new users, however it may potentially result in a temporary loss of service during the on-premises decommissioning process.</span></span>


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a><span data-ttu-id="4e5f5-174">Метод 1 . Управление SIP-адресами и номерами телефонов для пользователей Active Directory</span><span class="sxs-lookup"><span data-stu-id="4e5f5-174">Method 1 - Manage sip addresses and phone numbers for users in Active Directory</span></span>

<span data-ttu-id="4e5f5-175">Администраторы могут управлять пользователями, которые ранее были перемещены из локального Skype для бизнес-сервера в облако даже после вывода из эксплуатации локального развертывания.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-175">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="4e5f5-176">Если вы хотите внести изменения в SIP-адрес пользователя или номер телефона пользователя (а sip-адрес или номер телефона уже имеет значение в локальном Active Directory), необходимо сделать это в локальном Active Directory и позволить значению (s) перетекать в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-176">If you want to make changes to a user’s sip address or to a user’s phone number (and the sip address or phone number already has a value in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="4e5f5-177">Для этого не требуется локальное skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-177">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="4e5f5-178">Скорее, эти атрибуты можно изменить непосредственно в локальном Active Directory, используя либо оснастку MMC пользователей Active Directory и компьютеров (как показано ниже), либо с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-178">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in (as shown below), or by using PowerShell.</span></span> <span data-ttu-id="4e5f5-179">Если вы используете оснастку MMC, откройте страницу свойств пользователя, нажмите кнопку Редактор атрибута и найдите соответствующие атрибуты для изменения:</span><span class="sxs-lookup"><span data-stu-id="4e5f5-179">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="4e5f5-180">Чтобы изменить SIP-адрес пользователя, измените `msRTCSIP-PrimaryUserAddress` .</span><span class="sxs-lookup"><span data-stu-id="4e5f5-180">To modify a user’s sip address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span> <span data-ttu-id="4e5f5-181">Обратите внимание, `ProxyAddresses` если атрибут содержит SIP-адрес, также обнови это значение в качестве наилучшей практики.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-181">Note, if the `ProxyAddresses` attribute contains a sip address, also update that value as a best practice.</span></span> <span data-ttu-id="4e5f5-182">Несмотря на то, что адрес SIP в случае заполнения игнорируется O365, он может использоваться другими компонентами `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` локального использования.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-182">Although the sip address in `ProxyAddresses` is ignored by O365 if `msRTCSIP-PrimaryUserAddress` is populated, it may be used by other on-premises components.</span></span>

- <span data-ttu-id="4e5f5-183">Чтобы изменить телефонный номер пользователя, `msRTCSIP-Line` *измените, если он уже имеет значение*.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-183">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Средство для пользователей и компьютеров Active Directory](../media/disable-hybrid-1.png)
  
-  <span data-ttu-id="4e5f5-185">Если у пользователя изначально не было значения для локального перед перемещением, можно изменить номер телефона с помощью параметра `msRTCSIP-Line` в командлете `onpremLineUri` [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) в модуле Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-185">If the user did not originally have a value for `msRTCSIP-Line` on-premises before the move, you can modify the phone number using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

<span data-ttu-id="4e5f5-186">Эти действия не являются необходимыми для новых пользователей, созданных после отключения гибрида, и управлять этими пользователями можно непосредственно в облаке.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-186">These steps are not necessary for new users created after you disable hybrid, and those users can be managed directly in the cloud.</span></span> <span data-ttu-id="4e5f5-187">Если вам удобно использовать сочетание этих методов, а также оставить атрибуты msRTCSIP на месте в локальном Active Directory, вы можете просто повторно образ локального Skype для бизнеса серверов.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-187">If you are comfortable using the mix of these method as well as with leaving the msRTCSIP attributes in place in your on-premises Active Directory, you can simply re-image the on-premises Skype for Business servers.</span></span> <span data-ttu-id="4e5f5-188">Однако, если вы предпочитаете очистить все атрибуты msRTCSIP и сделать традиционный удалить Skype для бизнеса Server, используйте метод 2.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-188">However, if you prefer to clear all msRTCSIP attributes and do a traditional uninstall of Skype for Business Server, then use Method 2.</span></span>


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a><span data-ttu-id="4e5f5-189">Метод 2 . Очистить атрибуты Skype для бизнеса для всех пользователей в Active Directory</span><span class="sxs-lookup"><span data-stu-id="4e5f5-189">Method 2 - Clear Skype for Business Attributes for all on-premises users in Active Directory</span></span>

<span data-ttu-id="4e5f5-190">Этот параметр требует дополнительных усилий и надлежащего планирования, так как пользователи, которые ранее были перемещены из локального Skype для бизнеса Server в облако, должны быть повторно продвинуты.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-190">This option requires additional effort and proper planning because users who were previously moved from an on-premises Skype for Business Server to the cloud are required to be re-provisioned.</span></span> <span data-ttu-id="4e5f5-191">Эти пользователи могут быть классифицированы на две разные категории: пользователи без телефонной системы и пользователи с телефонной системой.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-191">These users can be categorized into two different categories: users without Phone System and users with Phone System.</span></span> <span data-ttu-id="4e5f5-192">Пользователи с телефонной системой будут испытывать временную потерю телефонной службы в рамках перехода номера телефона из управления в локальном Active Directory в облако.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-192">Users with Phone System will experience a temporary loss of phone service as part of transitioning the phone number from being managed in on-premises Active Directory to the cloud.</span></span> <span data-ttu-id="4e5f5-193">**Перед началом массовых операций рекомендуется выполнить пилотную работу с небольшим числом пользователей с телефонной системой.**</span><span class="sxs-lookup"><span data-stu-id="4e5f5-193">**It's recommended to perform a pilot involving a small number of users with Phone System prior to start bulk user operations.**</span></span> <span data-ttu-id="4e5f5-194">Для больших развертывания пользователи могут обрабатываться в небольших группах в разных окнах времени.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-194">For large deployments users can be processed in smaller groups in different time windows.</span></span> 

> [!NOTE] 
> <span data-ttu-id="4e5f5-195">Этот процесс прост для пользователей, у которых есть совпадающий sip-адрес и UserPrincipalName.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-195">This process is simplest for users who have a matching sip address and UserPrincipalName.</span></span> <span data-ttu-id="4e5f5-196">Для организаций, у пользователей с не совпадающих значений между этими двумя атрибутами, необходимо принять дополнительные меры, как отмечено ниже, для плавного перехода.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-196">For organizations that have users with non-matching values across these two attributes, extra care must be taken as noted below for a smooth transition.</span></span>

> [!NOTE]
> <span data-ttu-id="4e5f5-197">Если вы настроили конечные точки гибридного приложения для автоспутников или очередей вызовов, не забудьте переместить эти конечные точки в Microsoft 365 перед списанием Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-197">If you have configured on-premises hybrid application endpoints for Auto Attendants or Call Queues, be sure to move these endpoints to Microsoft 365 before decommissioning Skype for Business Server.</span></span>


1. <span data-ttu-id="4e5f5-198">Подтверждение следующего локального cmdlet Skype для бизнеса PowerShell возвращает пустой результат.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-198">Confirm the following on-premises Skype for Business PowerShell cmdlet returns an empty result.</span></span> <span data-ttu-id="4e5f5-199">Пустой результат означает, что пользователи не находятся в локальном помещении и либо были перемещены в Microsoft 365, либо отключены:</span><span class="sxs-lookup"><span data-stu-id="4e5f5-199">An empty result means no users are homed on-premises and have either been moved to Microsoft 365 or have been disabled:</span></span>

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. <span data-ttu-id="4e5f5-200">Запись текущего номера телефонов пользователей (LineUri), UserPrincipalName и связанных с ними данных, выполнив для экспорта пользовательских данных следующие пользовательские данные на локальном сервере Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4e5f5-200">Record users' current phones number (LineUri), UserPrincipalName and related info, by executing the following on-premises Skype for Business Server PowerShell cmdlet to export user data:</span></span>

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="4e5f5-201">Перед открытием SfbUserSettings.csv файл и подтверждение успешного экспорта всех пользовательских данных.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-201">Before proceeding open SfbUserSettings.csv file and confirm all user data has been successfully exported.</span></span> <span data-ttu-id="4e5f5-202">Рекомендуется хранить копию этого файла.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-202">It's recommended to keep a copy of this file.</span></span>  <span data-ttu-id="4e5f5-203">Не используйте этот файл в следующих действиях для обработки пользователей.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-203">Do not use this file in the following steps for processing users.</span></span> 

3. <span data-ttu-id="4e5f5-204">Создайте файл с группой пользователей, который будет использоваться в следующих действиях.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-204">Create a file with a group of users to be used in the following steps.</span></span> <span data-ttu-id="4e5f5-205">После успешного завершения работы первой группы пользователей приступим к следующей группе пользователей.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-205">After the first group of users has completed successfully, proceed with the next group of users.</span></span> <span data-ttu-id="4e5f5-206">В приведенном ниже примере группы пользователей выбираются в алфавитном порядке, но можно фильтровать пользователей на основе критериев, которые соответствуют тому, как вы хотите обрабатывать пользователей.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-206">In the example below, the groups of users are selected alphabetically, but you may filter on users based on criteria that matches how you would like to process the users.</span></span>

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="4e5f5-207">Перед открытием SfbUsers.csv файл и подтверждение успешного экспорта пользовательских данных.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-207">Before proceeding open SfbUsers.csv file and confirm user data has been successfully exported.</span></span> <span data-ttu-id="4e5f5-208">На более позднем этапе вам потребуется LineUri (номер телефона), UserPrincipalName, SamAccountName и SipAddress из этого файла.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-208">You will need the LineUri (phone number), UserPrincipalName, SamAccountName, and SipAddress from this file in a later step.</span></span>

4. <span data-ttu-id="4e5f5-209">Удалите сведения о атрибутах, связанных со Skype для бизнеса Server, из active Directory для набора пользователей, которые вы готовы обновить.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-209">Delete the attribute information related to Skype for Business Server from active Directory for the set of users you are ready to update.</span></span>  <span data-ttu-id="4e5f5-210">Существует 2 шага к этому процессу, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-210">There are 2 steps to this process, as shown below.</span></span>

   > [!Important] 
   > <span data-ttu-id="4e5f5-211">После следующего цикла синхронизации AAD после запуска этого шага пользователи с телефонной системой, которые ранее были перемещены из локального Skype для бизнеса Server в облако, потеряют возможность выполнять и принимать вызовы до тех пор, пока этап 8 не будет успешно завершен и подтвержден на шаге 9.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-211">After the next AAD Sync cycle after running this step, users with Phone System who were previously moved from an on-premises Skype for Business Server to the cloud will lose the ability to make and receive calls until step 8 is successfully completed and confirmed in step 9.</span></span> <span data-ttu-id="4e5f5-212">Кроме того, убедитесь, что на шаге 2 сохранены номера телефонов и связанные сведения пользователя, так как эта информация необходима для этого шага.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-212">In addition, make sure you have saved user's phone numbers and related information as per step 2, since that information is required for that step.</span></span>

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   <span data-ttu-id="4e5f5-213">Далее, для того же набора пользователей, очистить значение msRTCSIP-DeploymentLocator с помощью локального Active Directory PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4e5f5-213">Next, for the same set of users, clear the value of msRTCSIP-DeploymentLocator using on-premises Active Directory PowerShell:</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. <span data-ttu-id="4e5f5-214">Запустите следующий локальном сайте Skype для бизнеса PowerShell, чтобы добавить значение SIP-адрес обратно в локальном прокси-сервере Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-214">Run the following on-premise Skype for Business PowerShell cmdlet to add sip address value back to the on-premises Active Directory proxyAddresses.</span></span> <span data-ttu-id="4e5f5-215">Это позволит предотвратить проблемы с интероперабельностью, которые зависят от этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-215">This will prevent interoperability issues that rely on this attribute.</span></span> 

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

6. <span data-ttu-id="4e5f5-216">Выполнить синхронизацию Azure AD</span><span class="sxs-lookup"><span data-stu-id="4e5f5-216">Run Azure AD Sync</span></span>

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. <span data-ttu-id="4e5f5-217">Подождите, пока подготовка пользователей завершится.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-217">Wait for user provisioning to complete.</span></span> <span data-ttu-id="4e5f5-218">Вы можете отслеживать ход подготовка пользователей, запуская следующую команду Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-218">You can monitor user provisioning progress by running the following Skype for Business Online PowerShell command.</span></span> <span data-ttu-id="4e5f5-219">Следующая команда Skype для бизнеса Online PowerShell возвращает пустой результат по мере завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-219">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. <span data-ttu-id="4e5f5-220">Выполните следующую команду Skype для бизнеса Online PowerShell, чтобы назначить номера телефонов и включить пользователей для телефонной системы:</span><span class="sxs-lookup"><span data-stu-id="4e5f5-220">Execute the following Skype for Business Online PowerShell command to assign phone numbers and enable users for Phone System:</span></span>
     
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
   >  <span data-ttu-id="4e5f5-221">Если у вас по-прежнему есть конечные точки Skype для бизнеса (клиенты Skype или телефоны 3-й стороны), вам также необходимо установить -HostedVoiceMail для $true.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-221">If you still have Skype for Business endpoints (either Skype clients or 3rd party phones), you will also want to set -HostedVoiceMail to $true.</span></span> <span data-ttu-id="4e5f5-222">Если ваша организация использует только конечные точки Teams для пользователей с включенной голосовой поддержкой, этот параметр не применим к пользователям.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-222">If your organization is only using Teams endpoints for voice enabled users, this setting is not applicable to your users.</span></span> 

9. <span data-ttu-id="4e5f5-223">Подтвердит правильность работы пользователей с функциями телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-223">Confirm users with Phone System functionality have been provisioned correctly.</span></span> <span data-ttu-id="4e5f5-224">Следующая команда Skype для бизнеса Online PowerShell возвращает пустой результат по мере завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-224">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

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

10. <span data-ttu-id="4e5f5-225">Повторите действия от 3 до 9 до тех пор, пока все пользователи не будут обработаны.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-225">Repeat steps 3 through 9 until all users are processed.</span></span>

11. <span data-ttu-id="4e5f5-226">Подтверди, что все пользователи успешно обработаны, запуская следующие две команды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-226">Confirm that all users have been processed successfully by running the following two PowerShell commands.</span></span>

    <span data-ttu-id="4e5f5-227">Локальное командное приложение Skype для бизнес-сервера PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4e5f5-227">On-premises Skype for Business Server on-premises PowerShell command:</span></span>

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    <span data-ttu-id="4e5f5-228">Команда Skype для бизнеса Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4e5f5-228">Skype for Business Online PowerShell command:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. <span data-ttu-id="4e5f5-229">После завершения всех действий в методе 2 обратитесь к удалению локального [сервера Skype для](decommission-remove-on-prem.md) бизнеса для дополнительных действий по удалению локального развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4e5f5-229">After you have completed all steps in Method 2, refer to [Remove your on-premises Skype for Business Server](decommission-remove-on-prem.md) for additional steps to remove your Skype for Business Server on-premises deployment.</span></span>


## <a name="see-also"></a><span data-ttu-id="4e5f5-230">См. также</span><span class="sxs-lookup"><span data-stu-id="4e5f5-230">See also</span></span>

- [<span data-ttu-id="4e5f5-231">Консолидация облаков для команд и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="4e5f5-231">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="4e5f5-232">Вывод из эксплуатации локальной среды Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="4e5f5-232">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)
