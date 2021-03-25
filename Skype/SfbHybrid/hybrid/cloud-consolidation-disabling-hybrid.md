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
ms.openlocfilehash: 36ec3cba2d821cc8554e0fba95108756c83b7b3d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120358"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud-overview"></a><span data-ttu-id="2a9e6-103">Отключить гибрид для завершения миграции в облако: Обзор</span><span class="sxs-lookup"><span data-stu-id="2a9e6-103">Disable hybrid to complete migration to the cloud: Overview</span></span>

<span data-ttu-id="2a9e6-104">После перемещения всех пользователей из локальной среды в облако вы можете удалить локальное развертывание Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="2a9e6-105">Помимо удаления любого оборудования, важно логически отделить локальное развертывание от Microsoft 365 или Office 365 путем отключения гибрида.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Microsoft 365 or Office 365 by disabling hybrid.</span></span> <span data-ttu-id="2a9e6-106">Отключение гибридной среды состоит из трех этапов:</span><span class="sxs-lookup"><span data-stu-id="2a9e6-106">Disabling hybrid consists of three steps:</span></span>

1. <span data-ttu-id="2a9e6-107">Обновление записей DNS, чтобы указать на Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-107">Update DNS records to point to Microsoft 365 or Office 365.</span></span>

2. <span data-ttu-id="2a9e6-108">Отключить общее пространство адресов SIP (также известное как "раздельный домен") в организации Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-108">Disable shared sip address space (also known as "split domain") in the Microsoft 365 or Office 365 organization.</span></span>

3. <span data-ttu-id="2a9e6-109">Отключить возможность локального общения с Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-109">Disable the ability in on-premises to communicate with Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="2a9e6-110">Эти действия логически отделяют локальное развертывание Skype для бизнеса Server от Office 365 и должны быть сделаны вместе как подразделение.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-110">These steps logically separate your on-premise deployment of Skype for Business Server from Office 365 and should be done together as a unit.</span></span> <span data-ttu-id="2a9e6-111">Подробные сведения о каждом шаге приведены в этой статье ниже.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-111">Details for each step are provided in this article below.</span></span> <span data-ttu-id="2a9e6-112">По завершению развертывания Skype для бизнеса можно выписаться из эксплуатации с помощью одного из двух методов, на которые ссылается ниже.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-112">Once that is complete, you can decommission your on-premises Skype for Business Deployment using one of two methods referenced below.</span></span>

> [!Important] 
><span data-ttu-id="2a9e6-113">После завершения этого логического разделения атрибуты msRTCSIP из локального Active Directory по-прежнему будут иметь значения и будут синхронизироваться с помощью Azure AD Connect в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-113">Once this logical separation is complete, msRTCSIP attributes from your on-premises Active Directory still have values and will continue to sync via Azure AD Connect into Azure AD.</span></span> <span data-ttu-id="2a9e6-114">Вывод локальной среды из эксплуатации зависит от того, собираетесь ли вы оставить эти атрибуты на месте или сначала очистить их от локального Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-114">How you decommission the on-premises environment depends on whether you intend to leave these attributes in place, or first clear them from your on-premises Active Directory.</span></span> <span data-ttu-id="2a9e6-115">Следует помнить, что очистка атрибутов msRTCSIP на месте после миграции из локального помещения может привести к потере службы для пользователей!</span><span class="sxs-lookup"><span data-stu-id="2a9e6-115">Be aware that clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span> <span data-ttu-id="2a9e6-116">Подробные сведения и компромиссы двух подходов к выводу из эксплуатации описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-116">Details and tradeoffs of the two decommissioning approaches are described later below.</span></span>

## <a name="disable-hybrid-to-complete-migration-to-the-cloud-detailed-steps"></a><span data-ttu-id="2a9e6-117">Отключение гибридной системы для завершения миграции в облако: подробные действия</span><span class="sxs-lookup"><span data-stu-id="2a9e6-117">Disable hybrid to complete migration to the cloud: Detailed Steps</span></span>

1. <span data-ttu-id="2a9e6-118">*Обновим DNS, чтобы указать на Microsoft 365 или Office 365.*</span><span class="sxs-lookup"><span data-stu-id="2a9e6-118">*Update DNS to point to Microsoft 365 or  Office 365.*</span></span> <span data-ttu-id="2a9e6-119">Внешние DNS организации для локальной организации необходимо обновить таким образом, чтобы записи Skype для бизнеса указывают на Microsoft 365 или Office 365 вместо локального развертывания.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-119">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 or Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="2a9e6-120">Это означает следующее:</span><span class="sxs-lookup"><span data-stu-id="2a9e6-120">Specifically:</span></span>

    |<span data-ttu-id="2a9e6-121">Тип записи</span><span class="sxs-lookup"><span data-stu-id="2a9e6-121">Record type</span></span>|<span data-ttu-id="2a9e6-122">Имя</span><span class="sxs-lookup"><span data-stu-id="2a9e6-122">Name</span></span>|<span data-ttu-id="2a9e6-123">TTL</span><span class="sxs-lookup"><span data-stu-id="2a9e6-123">TTL</span></span>|<span data-ttu-id="2a9e6-124">Value (Значение)</span><span class="sxs-lookup"><span data-stu-id="2a9e6-124">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="2a9e6-125">SRV</span><span class="sxs-lookup"><span data-stu-id="2a9e6-125">SRV</span></span>|<span data-ttu-id="2a9e6-126">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="2a9e6-126">_sipfederationtls._tcp</span></span>|<span data-ttu-id="2a9e6-127">3600</span><span class="sxs-lookup"><span data-stu-id="2a9e6-127">3600</span></span>|<span data-ttu-id="2a9e6-128">100 1 5061 sipfed.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="2a9e6-128">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="2a9e6-129">SRV</span><span class="sxs-lookup"><span data-stu-id="2a9e6-129">SRV</span></span>|<span data-ttu-id="2a9e6-130">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="2a9e6-130">_sip._tls</span></span>|<span data-ttu-id="2a9e6-131">3600</span><span class="sxs-lookup"><span data-stu-id="2a9e6-131">3600</span></span>|<span data-ttu-id="2a9e6-132">100 1 443 sipdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="2a9e6-132">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="2a9e6-133">CNAME</span><span class="sxs-lookup"><span data-stu-id="2a9e6-133">CNAME</span></span>| <span data-ttu-id="2a9e6-134">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="2a9e6-134">lyncdiscover</span></span>|   <span data-ttu-id="2a9e6-135">3600</span><span class="sxs-lookup"><span data-stu-id="2a9e6-135">3600</span></span>|   <span data-ttu-id="2a9e6-136">webdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="2a9e6-136">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="2a9e6-137">CNAME</span><span class="sxs-lookup"><span data-stu-id="2a9e6-137">CNAME</span></span>| <span data-ttu-id="2a9e6-138">sip</span><span class="sxs-lookup"><span data-stu-id="2a9e6-138">sip</span></span>|    <span data-ttu-id="2a9e6-139">3600</span><span class="sxs-lookup"><span data-stu-id="2a9e6-139">3600</span></span>|   <span data-ttu-id="2a9e6-140">sipdir.online.lync. <span> com</span><span class="sxs-lookup"><span data-stu-id="2a9e6-140">sipdir.online.lync.<span>com</span></span>|

    <span data-ttu-id="2a9e6-141">Кроме того, записи CNAME для встречи или диалогов (если присутствуют) могут быть удалены.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-141">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="2a9e6-142">Наконец, все записи DNS для Skype для бизнеса во внутренней сети должны быть удалены.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-142">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

    > [!Note] 
    > <span data-ttu-id="2a9e6-143">В редких случаях изменение DNS от указать на локальное на Microsoft 365 или Office 365 для вашей организации может привести к остановке работы федерации с некоторыми другими организациями до тех пор, пока другая организация не обновит конфигурацию федерации:</span><span class="sxs-lookup"><span data-stu-id="2a9e6-143">In rare cases, changing DNS from pointing on premises to Microsoft 365 or Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
    >
    > - <span data-ttu-id="2a9e6-144">Всем федератным организациям, использующим старую модель Direct Federation (также известный как Разрешенный сервер партнеров), необходимо обновить разрешенные записи домена для организации, чтобы удалить прокси-сервер FQDN.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-144">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="2a9e6-145">Эта устаревшая модель федерации не основана на записях SRV DNS, поэтому такая конфигурация станет устаревшей после перемещения организации в облако.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-145">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
    > 
    > - <span data-ttu-id="2a9e6-146">Любая федераированная организация, у нее нет включенного поставщика хостинга для sipfed.online.lync. <span> com необходимо обновить конфигурацию, чтобы включить это.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-146">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="2a9e6-147">Такая ситуация возможна только в том случае, если федератерная организация является чисто локальной и никогда не федератовывалась с любым гибридным или сетевым клиентом.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-147">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="2a9e6-148">В этом случае федерация с этими организациями не будет работать до тех пор, пока они не увявят поставщика хостинга.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-148">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
    >
    > <span data-ttu-id="2a9e6-149">Если вы подозреваете, что любой из ваших федеративных партнеров может использовать Direct Federation или не был федеративен в какой-либо сетевой или гибридной организации, мы рекомендуем отправить им сообщение об этом при подготовке к завершению миграции в облако.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-149">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>


2.  <span data-ttu-id="2a9e6-150">*Отключение общего пространства адресов SIP в организации Microsoft 365 или Office 365.*</span><span class="sxs-lookup"><span data-stu-id="2a9e6-150">*Disable shared sip address space in Microsoft 365 or Office 365 organization.*</span></span> <span data-ttu-id="2a9e6-151">Команда, приведенная ниже, должна быть сделана из окна Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-151">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
3.  <span data-ttu-id="2a9e6-152">*Отключить возможность локального общения с Microsoft 365 или Office 365.*</span><span class="sxs-lookup"><span data-stu-id="2a9e6-152">*Disable the ability in on-premises to communicate with Microsoft 365 or Office 365.*</span></span> <span data-ttu-id="2a9e6-153">Команда, приведенная ниже, должна быть сделана из локального окна PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2a9e6-153">The command below needs to be done from an on-premises PowerShell window:</span></span>

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="2a9e6-154">Управление атрибутами после перемещения пользователей из локального в облако</span><span class="sxs-lookup"><span data-stu-id="2a9e6-154">Managing attributes after moving users from on-premises to the cloud</span></span>

<span data-ttu-id="2a9e6-155">По умолчанию все пользователи, которые ранее были включены для Skype для бизнес-сервера и впоследствии перемещены в облако, по-прежнему имеют атрибуты msRTCSIP, настроенные в локальном Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-155">By default, all users that were previously enabled for Skype for Business Server and subsequently moved to the cloud still have msRTCSIP attributes configured in your on-premises Active Directory.</span></span> <span data-ttu-id="2a9e6-156">Эти атрибуты, в частности SIP-адрес (msRTCSIP-PrimaryUserAddress) и потенциально номер телефона (msRTCSIP-Line), продолжают синхронизироваться с Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-156">These attributes, in particular sip address (msRTCSIP-PrimaryUserAddress) and potentially phone number (msRTCSIP-Line), continue to sync into Azure AD.</span></span> <span data-ttu-id="2a9e6-157">Если требуется изменить любой из атрибутов msRTCSIP, эти изменения необходимо внести в локальном Active Directory, а затем синхронизировать его с Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-157">If changes are required to any of the msRTCSIP attributes, these changes must be made in the on-premises Active Directory and then sync'd to Azure AD.</span></span> <span data-ttu-id="2a9e6-158">Однако после удаления развертывания Skype для бизнес-сервера средства Skype для бизнеса Server будут недоступны для управления этими атрибутами.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-158">However, once the Skype for Business Server deployment has been removed, the Skype for Business Server tools will not be available to manage these attributes.</span></span>

<span data-ttu-id="2a9e6-159">Существует два варианта обработки этой ситуации:</span><span class="sxs-lookup"><span data-stu-id="2a9e6-159">There are two options available for handling this situation:</span></span>

1. <span data-ttu-id="2a9e6-160">Оставьте пользователей, включенных для учетных записей серверов Skype для бизнеса, и управляйте атрибутами msRTCSIP с помощью средств Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-160">Leave users that were enabled for Skype for Business server accounts as is, and manage the  msRTCSIP attributes using Active Directory tools.</span></span> <span data-ttu-id="2a9e6-161">Это обеспечивает отсутствие потери службы для перенесенных пользователей и позволяет легко удалить развертывание Skype для бизнес-сервера, устранив (например, удаление) серверов без полного вывода из эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-161">This ensures no loss of service for migrated users, and allows you to easily remove the Skype for Business Server deployment by eliminating (e.g. wiping) the servers, without a full decommissioning.</span></span> <span data-ttu-id="2a9e6-162">Однако новые лицензированные пользователи не будут иметь эти атрибуты, заполняемые в локальном каталоге Active Directory, и им необходимо управлять в Интернете.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-162">However, newly licensed users will not have these attributes populated in your on-premises Active Directory and will need to be managed online.</span></span>

2.  <span data-ttu-id="2a9e6-163">Очистить все атрибуты msRTCSIP от перенесенных пользователей в локальном Каталоге Active Directory и управлять этими атрибутами с помощью сетевых средств.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-163">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span></span> <span data-ttu-id="2a9e6-164">Этот метод позволяет использовать последовательный подход к управлению для существующих и новых пользователей, однако он потенциально может привести к временной потере службы во время локального процесса вывода из эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-164">This method allows for a consistent management approach for existing and new users, however it may potentially result in a temporary loss of service during the on-premises decommissioning process.</span></span>


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a><span data-ttu-id="2a9e6-165">Метод 1 . Управление SIP-адресами и номерами телефонов для пользователей Active Directory</span><span class="sxs-lookup"><span data-stu-id="2a9e6-165">Method 1 - Manage sip addresses and phone numbers for users in Active Directory</span></span>

<span data-ttu-id="2a9e6-166">Администраторы могут управлять пользователями, которые ранее были перемещены из локального Skype для бизнес-сервера в облако даже после вывода из эксплуатации локального развертывания.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-166">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="2a9e6-167">Если вы хотите внести изменения в SIP-адрес пользователя или номер телефона пользователя (а sip-адрес или номер телефона уже имеет значение в локальном Active Directory), необходимо сделать это в локальном Active Directory и позволить значению (s) перетекать в Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-167">If you want to make changes to a user’s sip address or to a user’s phone number (and the sip address or phone number already has a value in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="2a9e6-168">Для этого не требуется локальное skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-168">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="2a9e6-169">Скорее, эти атрибуты можно изменить непосредственно в локальном Active Directory, используя либо оснастку MMC пользователей Active Directory и компьютеров (как показано ниже), либо с помощью PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-169">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in (as shown below), or by using PowerShell.</span></span> <span data-ttu-id="2a9e6-170">Если вы используете оснастку MMC, откройте страницу свойств пользователя, нажмите кнопку Редактор атрибута и найдите соответствующие атрибуты для изменения:</span><span class="sxs-lookup"><span data-stu-id="2a9e6-170">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="2a9e6-171">Чтобы изменить SIP-адрес пользователя, измените `msRTCSIP-PrimaryUserAddress` .</span><span class="sxs-lookup"><span data-stu-id="2a9e6-171">To modify a user’s sip address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span> <span data-ttu-id="2a9e6-172">Обратите внимание, `ProxyAddresses` если атрибут содержит SIP-адрес, также обнови это значение в качестве наилучшей практики.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-172">Note, if the `ProxyAddresses` attribute contains a sip address, also update that value as a best practice.</span></span> <span data-ttu-id="2a9e6-173">Несмотря на то, что адрес SIP в случае заполнения игнорируется O365, он может использоваться другими компонентами `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` локального использования.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-173">Although the sip address in `ProxyAddresses` is ignored by O365 if `msRTCSIP-PrimaryUserAddress` is populated, it may be used by other on-premises components.</span></span>

- <span data-ttu-id="2a9e6-174">Чтобы изменить телефонный номер пользователя, `msRTCSIP-Line` *измените, если он уже имеет значение*.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-174">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Средство для пользователей и компьютеров Active Directory](../media/disable-hybrid-1.png)
  
-  <span data-ttu-id="2a9e6-176">Если у пользователя изначально не было значения для локального перед перемещением, можно изменить номер телефона с помощью параметра `msRTCSIP-Line` в командлете `onpremLineUri` [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) в модуле Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-176">If the user did not originally have a value for `msRTCSIP-Line` on-premises before the move, you can modify the phone number using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

<span data-ttu-id="2a9e6-177">Эти действия не являются необходимыми для новых пользователей, созданных после отключения гибрида, и управлять этими пользователями можно непосредственно в облаке.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-177">These steps are not necessary for new users created after you disable hybrid, and those users can be managed directly in the cloud.</span></span> <span data-ttu-id="2a9e6-178">Если вам удобно использовать сочетание этих методов, а также оставить атрибуты msRTCSIP на месте в локальном Active Directory, вы можете просто повторно образ локального Skype для бизнеса серверов.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-178">If you are comfortable using the mix of these method as well as with leaving the msRTCSIP attributes in place in your on-premises Active Directory, you can simply re-image the on-premises Skype for Business servers.</span></span> <span data-ttu-id="2a9e6-179">Однако, если вы предпочитаете очистить все атрибуты msRTCSIP и сделать традиционный удалить Skype для бизнеса Server, используйте метод 2.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-179">However, if you prefer to clear all msRTCSIP attributes and do a traditional uninstall of Skype for Business Server, then use Method 2.</span></span>


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a><span data-ttu-id="2a9e6-180">Метод 2 . Очистить атрибуты Skype для бизнеса для всех пользователей в Active Directory</span><span class="sxs-lookup"><span data-stu-id="2a9e6-180">Method 2 - Clear Skype for Business Attributes for all on-premises users in Active Directory</span></span>

<span data-ttu-id="2a9e6-181">Этот параметр требует дополнительных усилий и надлежащего планирования, так как пользователи, которые ранее были перемещены из локального Skype для бизнеса Server в облако, должны быть повторно продвинуты.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-181">This option requires additional effort and proper planning because users that were previously moved from an on-premises Skype for Business Server to the cloud are required to be re-provisioned.</span></span> <span data-ttu-id="2a9e6-182">Эти пользователи могут быть классифицированы на две разные категории: пользователи без телефонной системы и пользователи с телефонной системой.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-182">These users can be categorized into two different categories: users without Phone System and users with Phone System.</span></span> <span data-ttu-id="2a9e6-183">Пользователи с телефонной системой будут испытывать временную потерю телефонной службы в рамках перехода номера телефона из управления в локальном Active Directory в облако.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-183">Users with Phone System will experience a temporary loss of phone service as part of transitioning the phone number from being managed in on-premises Active Directory to the cloud.</span></span> <span data-ttu-id="2a9e6-184">**Перед началом массовых операций рекомендуется выполнить пилотную работу с небольшим числом пользователей с телефонной системой.**</span><span class="sxs-lookup"><span data-stu-id="2a9e6-184">**It's recommended to perform a pilot involving a small number of users with Phone System prior to start bulk user operations.**</span></span> <span data-ttu-id="2a9e6-185">Для больших развертывания пользователи могут обрабатываться в небольших группах в разных окнах времени.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-185">For large deployments users can be processed in smaller groups in different time windows.</span></span> 

> [!NOTE]
> <span data-ttu-id="2a9e6-186">Этот процесс прост для пользователей, у которых есть совпадающий sip-адрес и UserPrincipalName.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-186">The process is simplest for users who have a matching sip address and UserPrincipalName.</span></span> <span data-ttu-id="2a9e6-187">Для организаций, у пользователей с не совпадающих значений между этими двумя атрибутами, необходимо принять дополнительные меры, как отмечено ниже, для плавного перехода.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-187">For organizations that have users with non-matching values across these two attributes, extra care must be taken as noted below for a smooth transition.</span></span> 


1. <span data-ttu-id="2a9e6-188">Подтверждение следующего локального cmdlet Skype для бизнеса PowerShell возвращает пустой результат.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-188">Confirm the following on-premises Skype for Business PowerShell cmdlet returns an empty result.</span></span> <span data-ttu-id="2a9e6-189">Пустой результат означает, что пользователи не находятся в локальном помещении и не были перемещены в Office 365 или отключены:</span><span class="sxs-lookup"><span data-stu-id="2a9e6-189">An empty result means no users are homed on-premises and have either been moved to Office 365 or have been disabled:</span></span>

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. <span data-ttu-id="2a9e6-190">Запись текущего номера телефонов пользователей (LineUri), UserPrincipalName и связанных с ними данных, выполнив для экспорта пользовательских данных следующие пользовательские данные на локальном сервере Skype для бизнеса Server PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2a9e6-190">Record users' current phones number (LineUri), UserPrincipalName and related info, by executing the following on-premises Skype for Business Server PowerShell cmdlet to export user data:</span></span>

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="2a9e6-191">Перед открытием SfbUserSettings.csv файл и подтверждение успешного экспорта всех пользовательских данных.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-191">Before proceeding open SfbUserSettings.csv file and confirm all user data has been successfully exported.</span></span> <span data-ttu-id="2a9e6-192">Рекомендуется хранить копию этого файла.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-192">It's recommended to keep a copy of this file.</span></span>  <span data-ttu-id="2a9e6-193">Не используйте этот файл в следующих действиях для обработки пользователей.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-193">Do not use this file in the following steps for processing users.</span></span> 

3. <span data-ttu-id="2a9e6-194">Создайте файл с группой пользователей, который будет использоваться в следующих действиях.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-194">Create a file with a group of users to be used in the following steps.</span></span> <span data-ttu-id="2a9e6-195">После успешного завершения работы первой группы пользователей приступим к следующей группе пользователей.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-195">After the first group of users has completed successfully, proceed with the next group of users.</span></span> <span data-ttu-id="2a9e6-196">В приведенном ниже примере группы пользователей выбираются в алфавитном порядке, но можно фильтровать пользователей на основе критериев, которые соответствуют тому, как вы хотите обрабатывать пользователей.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-196">In the example below, the groups of users are selected alphabetically, but you may filter on users based on criteria that matches how you would like to process the users.</span></span>

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="2a9e6-197">Перед открытием SfbUsers.csv файл и подтверждение успешного экспорта пользовательских данных.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-197">Before proceeding open SfbUsers.csv file and confirm user data has been successfully exported.</span></span> <span data-ttu-id="2a9e6-198">На более позднем этапе вам потребуется LineUri (номер телефона), UserPrincipalName, SamAccountName и SipAddress из этого файла.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-198">You will need the LineUri (phone number), UserPrincipalName, SamAccountName, and SipAddress from this file in a later step.</span></span>

4. <span data-ttu-id="2a9e6-199">Удалите сведения о атрибутах, связанных со Skype для бизнеса Server, из active Directory для набора пользователей, которые вы готовы обновить.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-199">Delete the attribute information related to Skype for Business Server from active Directory for the set of users you are ready to update.</span></span>  <span data-ttu-id="2a9e6-200">Существует 2 шага к этому процессу, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-200">There are 2 steps to this process, as shown below.</span></span>

   > [!Important] 
   > <span data-ttu-id="2a9e6-201">После следующего цикла синхронизации AAD после запуска этого шага пользователи с телефонной системой, которые ранее были перемещены из локального Skype для бизнеса Server в облако, потеряют возможность выполнять и принимать вызовы до тех пор, пока этап 8 не будет успешно завершен и подтвержден на шаге 9.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-201">After the next AAD Sync cycle after running this step, users with Phone System who were previously moved from an on-premises Skype for Business Server to the cloud will lose the ability to make and receive calls until step 8 is successfully completed and confirmed in step 9.</span></span> <span data-ttu-id="2a9e6-202">Кроме того, убедитесь, что на шаге 2 сохранены номера телефонов и связанные сведения пользователя, так как эта информация необходима для этого шага.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-202">In addition, make sure you have saved user's phone numbers and related information as per step 2, since that information is required for that step.</span></span>

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   <span data-ttu-id="2a9e6-203">Далее, для того же набора пользователей, очистить значение msRTCSIP-DeploymentLocator с помощью локального Active Directory PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2a9e6-203">Next, for the same set of users, clear the value of msRTCSIP-DeploymentLocator using on-premises Active Directory PowerShell:</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. <span data-ttu-id="2a9e6-204">Запустите следующий локальном сайте Skype для бизнеса PowerShell, чтобы добавить значение SIP-адрес обратно в локальном прокси-сервере Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-204">Run the following on-premise Skype for Business PowerShell cmdlet to add sip address value back to the on-premises Active Directory proxyAddresses.</span></span> <span data-ttu-id="2a9e6-205">Это позволит предотвратить проблемы с интероперабельностью, которые зависят от этого атрибута.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-205">This will prevent interoperability issues that rely on this attribute.</span></span> 

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

6. <span data-ttu-id="2a9e6-206">Выполнить синхронизацию Azure AD</span><span class="sxs-lookup"><span data-stu-id="2a9e6-206">Run Azure AD Sync</span></span>

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. <span data-ttu-id="2a9e6-207">Подождите, пока подготовка пользователей завершится.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-207">Wait for user provisioning to complete.</span></span> <span data-ttu-id="2a9e6-208">Вы можете отслеживать ход подготовка пользователей, запуская следующую команду Skype для бизнеса Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-208">You can monitor user provisioning progress by running the following Skype for Business Online PowerShell command.</span></span> <span data-ttu-id="2a9e6-209">Следующая команда Skype для бизнеса Online PowerShell возвращает пустой результат по мере завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-209">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. <span data-ttu-id="2a9e6-210">Выполните следующую команду Skype для бизнеса Online PowerShell, чтобы назначить номера телефонов и включить пользователей для телефонной системы:</span><span class="sxs-lookup"><span data-stu-id="2a9e6-210">Execute the following Skype for Business Online PowerShell command to assign phone numbers and enable users for Phone System:</span></span>
     
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
   >  <span data-ttu-id="2a9e6-211">Если у вас по-прежнему есть конечные точки Skype для бизнеса (клиенты Skype или телефоны 3-й стороны), вам также необходимо установить -HostedVoiceMail для $true.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-211">If you still have Skype for Business endpoints (either Skype clients or 3rd party phones), you will also want to set -HostedVoiceMail to $true.</span></span> <span data-ttu-id="2a9e6-212">Если ваша организация использует только конечные точки Teams для пользователей с включенной голосовой поддержкой, этот параметр не применим к пользователям.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-212">If your organization is only using Teams endpoints for voice enabled users, this setting is not applicable to your users.</span></span> 

9. <span data-ttu-id="2a9e6-213">Подтвердит правильность работы пользователей с функциями телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-213">Confirm users with Phone System functionality have been provisioned correctly.</span></span> <span data-ttu-id="2a9e6-214">Следующая команда Skype для бизнеса Online PowerShell возвращает пустой результат по мере завершения процесса.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-214">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

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

10. <span data-ttu-id="2a9e6-215">Повторите действия от 3 до 9 до тех пор, пока все пользователи не будут обработаны.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-215">Repeat steps 3 through 9 until all users are processed.</span></span>

11. <span data-ttu-id="2a9e6-216">Подтверди, что все пользователи успешно обработаны, запуская следующие две команды PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2a9e6-216">Confirm that all users have been processed successfully by running the following two PowerShell commands.</span></span>

    <span data-ttu-id="2a9e6-217">Локальное командное приложение Skype для бизнес-сервера PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2a9e6-217">On-premises Skype for Business Server on-premises PowerShell command:</span></span>

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    <span data-ttu-id="2a9e6-218">Команда Skype для бизнеса Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2a9e6-218">Skype for Business Online PowerShell command:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 


## <a name="see-also"></a><span data-ttu-id="2a9e6-219">См. также</span><span class="sxs-lookup"><span data-stu-id="2a9e6-219">See also</span></span>

[<span data-ttu-id="2a9e6-220">Консолидация облаков для команд и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2a9e6-220">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)