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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: В этом приложении содержатся подробные инструкции по отключению гибридной среды в составе облачной консолидации для Teams и Skype для бизнеса.
ms.openlocfilehash: 805010aa16ca8159b5e274847ca7ca2b296f214d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160718"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="0e38f-103">Отключение гибридной среды для завершения миграции в облако</span><span class="sxs-lookup"><span data-stu-id="0e38f-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="0e38f-104">После перемещения всех пользователей из локальной среды в облако можно списать локальное развертывание Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0e38f-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="0e38f-105">Помимо удаления какого-либо оборудования, критически важный шаг состоит в том, чтобы логически отделить локальное развертывание от Office 365, отключив гибридную среду.</span><span class="sxs-lookup"><span data-stu-id="0e38f-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="0e38f-106">Отключение гибридной среды состоит из трех этапов:</span><span class="sxs-lookup"><span data-stu-id="0e38f-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="0e38f-107">Обновление записей DNS для ссылки на Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e38f-107">Update DNS records to point to Office 365.</span></span>
2. <span data-ttu-id="0e38f-108">Отключите разделенный домен в клиенте Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e38f-108">Disable split domain in the Office 365 tenant.</span></span>
3. <span data-ttu-id="0e38f-109">Отключение возможности локального подключения к Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e38f-109">Disable ability in on-prem to communicate with Office 365.</span></span>


<span data-ttu-id="0e38f-110">Эти действия необходимо выполнить вместе как единое целое.</span><span class="sxs-lookup"><span data-stu-id="0e38f-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="0e38f-111">Подробные сведения приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="0e38f-111">Details are provided below.</span></span>

> [!Note] 
> <span data-ttu-id="0e38f-112">В редких случаях изменение DNS, направленное на Office 365 для вашей организации, может привести к прекращению работы Федерации с другими организациями, пока другая организация не обновит свою конфигурацию Федерации:</span><span class="sxs-lookup"><span data-stu-id="0e38f-112">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="0e38f-113">Для всех федеративных организаций, использующих старую прямую модель Федерации (также известное как разрешенный сервер-партнер), необходимо обновить записи разрешенных доменов для своей организации, чтобы удалить полное доменное имя прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="0e38f-113">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="0e38f-114">Эта устаревшая модель Федерации не основана на записях DNS SRV, поэтому такая конфигурация станет устаревшей после того, как ваша организация перейдет в облако.</span><span class="sxs-lookup"><span data-stu-id="0e38f-114">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="0e38f-115">Любая федеративная организация, у которой нет включенного поставщика услуг хостинга для sipfed. Online. Lync. <span>com необходимо обновить конфигурацию, чтобы она была включена.</span><span class="sxs-lookup"><span data-stu-id="0e38f-115">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="0e38f-116">Такая ситуация возможна только в том случае, если федеративная организация является исключительно локальной и никогда не участвует в гибридном или интернет-клиенте.</span><span class="sxs-lookup"><span data-stu-id="0e38f-116">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="0e38f-117">В этом случае Федерация с этими организациями не будет работать, пока не включит их поставщика услуг хостинга.</span><span class="sxs-lookup"><span data-stu-id="0e38f-117">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="0e38f-118">Если вы подозреваете, что любой из федеративных партнеров может использовать прямую федерацию или иметь федеративные связи с любой локальной или гибридной организацией, мы рекомендуем вам отправить им информацию о том, как вы готовитесь к выполнению миграции в облако.</span><span class="sxs-lookup"><span data-stu-id="0e38f-118">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="0e38f-119">*Обновите DNS, чтобы указать на Office 365.*</span><span class="sxs-lookup"><span data-stu-id="0e38f-119">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="0e38f-120">Необходимо обновить внешнюю DNS организации для локальной организации, чтобы записи Skype для бизнеса направляться на Office 365, а не в локальное развертывание.</span><span class="sxs-lookup"><span data-stu-id="0e38f-120">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="0e38f-121">Это означает следующее:</span><span class="sxs-lookup"><span data-stu-id="0e38f-121">Specifically:</span></span>

    |<span data-ttu-id="0e38f-122">Тип записи</span><span class="sxs-lookup"><span data-stu-id="0e38f-122">Record type</span></span>|<span data-ttu-id="0e38f-123">Имя</span><span class="sxs-lookup"><span data-stu-id="0e38f-123">Name</span></span>|<span data-ttu-id="0e38f-124">TTL (Срок жизни)</span><span class="sxs-lookup"><span data-stu-id="0e38f-124">TTL</span></span>|<span data-ttu-id="0e38f-125">Value (Значение)</span><span class="sxs-lookup"><span data-stu-id="0e38f-125">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="0e38f-126">SRV</span><span class="sxs-lookup"><span data-stu-id="0e38f-126">SRV</span></span>|<span data-ttu-id="0e38f-127">_сипфедератионтлс. _tcp</span><span class="sxs-lookup"><span data-stu-id="0e38f-127">_sipfederationtls._tcp</span></span>|<span data-ttu-id="0e38f-128">3600</span><span class="sxs-lookup"><span data-stu-id="0e38f-128">3600</span></span>|<span data-ttu-id="0e38f-129">100 1 5061 sipfed. Online. Lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="0e38f-129">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="0e38f-130">SRV</span><span class="sxs-lookup"><span data-stu-id="0e38f-130">SRV</span></span>|<span data-ttu-id="0e38f-131">_сип. _тлс</span><span class="sxs-lookup"><span data-stu-id="0e38f-131">_sip._tls</span></span>|<span data-ttu-id="0e38f-132">3600</span><span class="sxs-lookup"><span data-stu-id="0e38f-132">3600</span></span>|<span data-ttu-id="0e38f-133">100 1 443 sipdir. Online. Lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="0e38f-133">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="0e38f-134">CNAME</span><span class="sxs-lookup"><span data-stu-id="0e38f-134">CNAME</span></span>| <span data-ttu-id="0e38f-135">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="0e38f-135">lyncdiscover</span></span>|   <span data-ttu-id="0e38f-136">3600</span><span class="sxs-lookup"><span data-stu-id="0e38f-136">3600</span></span>|   <span data-ttu-id="0e38f-137">webdir. Online. Lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="0e38f-137">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="0e38f-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="0e38f-138">CNAME</span></span>| <span data-ttu-id="0e38f-139">sip</span><span class="sxs-lookup"><span data-stu-id="0e38f-139">sip</span></span>|    <span data-ttu-id="0e38f-140">3600</span><span class="sxs-lookup"><span data-stu-id="0e38f-140">3600</span></span>|   <span data-ttu-id="0e38f-141">sipdir. Online. Lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="0e38f-141">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="0e38f-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="0e38f-142">CNAME</span></span>| <span data-ttu-id="0e38f-143">Согласно</span><span class="sxs-lookup"><span data-stu-id="0e38f-143">meet</span></span>|   <span data-ttu-id="0e38f-144">3600</span><span class="sxs-lookup"><span data-stu-id="0e38f-144">3600</span></span>|   <span data-ttu-id="0e38f-145">webdir. Online. Lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="0e38f-145">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="0e38f-146">CNAME</span><span class="sxs-lookup"><span data-stu-id="0e38f-146">CNAME</span></span>| <span data-ttu-id="0e38f-147">Dialin</span><span class="sxs-lookup"><span data-stu-id="0e38f-147">dialin</span></span>  |<span data-ttu-id="0e38f-148">3600</span><span class="sxs-lookup"><span data-stu-id="0e38f-148">3600</span></span>|  <span data-ttu-id="0e38f-149">webdir. Online. Lync. <span>com-</span><span class="sxs-lookup"><span data-stu-id="0e38f-149">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="0e38f-150">*Отключите общее адресное пространство SIP в клиенте Office 365.*</span><span class="sxs-lookup"><span data-stu-id="0e38f-150">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="0e38f-151">Приведенная ниже команда должна быть выполнена в окне PowerShell Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="0e38f-151">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  <span data-ttu-id="0e38f-152">*Отключение возможности локального подключения к Office 365.*</span><span class="sxs-lookup"><span data-stu-id="0e38f-152">*Disable ability in on-prem to communicate with Office 365.*</span></span>  
<span data-ttu-id="0e38f-153">Приведенная ниже команда должна быть выполнена из локального окна PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0e38f-153">The command below needs to be done from an on-premises PowerShell window.</span></span>  <span data-ttu-id="0e38f-154">Если вы ранее импортировали сеанс Skype для бизнеса Online, запустите новый сеанс PowerShell для Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="0e38f-154">If you have previously imported a Skype for Business Online session, start a new Skype for Business PowerShell session.</span></span>

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a><span data-ttu-id="0e38f-155">См. также</span><span class="sxs-lookup"><span data-stu-id="0e38f-155">See also</span></span>

[<span data-ttu-id="0e38f-156">Объединение в облако для Teams и Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0e38f-156">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)