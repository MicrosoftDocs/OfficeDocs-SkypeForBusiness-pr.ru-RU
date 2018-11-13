---
title: Развертывание нескольких сайтов в Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Сведения о развертывании нескольких сайтов ТСОП в Cloud Connector Edition.
ms.openlocfilehash: b6d4c489136f038a5d4dbe7188958ef60e4a5aed
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295715"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="fab73-103">Развертывание нескольких сайтов в Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="fab73-103">Deploy multiple sites in Cloud Connector</span></span>
 
<span data-ttu-id="fab73-104">Сведения о развертывании нескольких сайтов ТСОП в Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="fab73-104">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="fab73-p101">В этом разделе описывается развертывание нескольких сайтов телефонной сети общего пользования (ТСОП). Эти сайты развертываются поочередно с использованием одной и той же последовательности шагов. В этом разделе приводятся рекомендации и описываются различия между сайтами в развертывании с несколькими сайтами. </span><span class="sxs-lookup"><span data-stu-id="fab73-p101">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites. Sites are deployed one at a time using the same steps as deploying a single site. This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="fab73-108">Несколько сайтов телефонной сети общего пользования (ТСОП)</span><span class="sxs-lookup"><span data-stu-id="fab73-108">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="fab73-109">Далее приведен пример конфигурации развертывания Скайп для соединителя Cloud Business Edition для различных сайтов PSTN.</span><span class="sxs-lookup"><span data-stu-id="fab73-109">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="fab73-110">Прежде чем приступать к развертыванию, проверьте параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fab73-110">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="fab73-111">Сайт ТСОП 1</span><span class="sxs-lookup"><span data-stu-id="fab73-111">PSTN Site 1</span></span>
  
```
[Common]
SiteName=Site1
[EdgeServer]
InternalMachineName= cc-edge1
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.241

ExternalSIPPoolName=access1
ExternalSIPIPs=192.168.1.4

ExternalMRFQDNPoolName=mr1
ExternalMRIPs=192.168.1.4
ExternalMRPublicIPs=23.99.115.35
```

<span data-ttu-id="fab73-112">Сайт ТСОП 2</span><span class="sxs-lookup"><span data-stu-id="fab73-112">PSTN Site 2</span></span>
  
```
[Common]
SiteName=Site2
[EdgeServer]
InternalMachineName= cc-edge2
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.242

ExternalSIPPoolName=access2
ExternalSIPIPs=192.168.1.5

ExternalMRFQDNPoolName=mr2
ExternalMRIPs=192.168.1.5
ExternalMRPublicIPs=104.42.226.134
```

<span data-ttu-id="fab73-113">Для каждого сайта ТСОП, который вы хотите добавить следуйте указаниям в [Развернуть один сайт в облаке соединителя](deploy-a-single-site-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="fab73-113">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fab73-114">Общая папка для подготовки среды высокой доступности выделяется на каждый сайт ТСОП.</span><span class="sxs-lookup"><span data-stu-id="fab73-114">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="fab73-115">Каждый сайт ТСОП **должен** использовать разные общие папки.</span><span class="sxs-lookup"><span data-stu-id="fab73-115">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="fab73-116">Не используйте ту же папку общей для нескольких сайтов. ></span><span class="sxs-lookup"><span data-stu-id="fab73-116">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="fab73-117">Сравнение развертывания отдельного сайта с высокой доступностью и развертывания с несколькими сайтами</span><span class="sxs-lookup"><span data-stu-id="fab73-117">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="fab73-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="fab73-118"></span></span>

<span data-ttu-id="fab73-119">В следующей таблице приводятся различия между конфигурацией с одним сайтом с поддержкой высокой доступности и развертыванием с несколькими сайтами.</span><span class="sxs-lookup"><span data-stu-id="fab73-119">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="fab73-120">**Категория**</span><span class="sxs-lookup"><span data-stu-id="fab73-120">**Category**</span></span>|<span data-ttu-id="fab73-121">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="fab73-121">**Item**</span></span>|<span data-ttu-id="fab73-122">**Один сайт с высокой доступностью**</span><span class="sxs-lookup"><span data-stu-id="fab73-122">**Single-Site with HA**</span></span>|<span data-ttu-id="fab73-123">**Несколько сайтов**</span><span class="sxs-lookup"><span data-stu-id="fab73-123">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fab73-124">Установка</span><span class="sxs-lookup"><span data-stu-id="fab73-124">Setup</span></span>  <br/> |<span data-ttu-id="fab73-125">Общая папка</span><span class="sxs-lookup"><span data-stu-id="fab73-125">Shared folder</span></span>  <br/> |<span data-ttu-id="fab73-126">Требует **же** общую папку для устройств</span><span class="sxs-lookup"><span data-stu-id="fab73-126">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="fab73-127">Требуются **разные** общие папки для каждого устройства</span><span class="sxs-lookup"><span data-stu-id="fab73-127">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="fab73-128">Настройка</span><span class="sxs-lookup"><span data-stu-id="fab73-128">Configure</span></span>  <br/> |<span data-ttu-id="fab73-129">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="fab73-129">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="fab73-130">Требуется **один** домен для всех устройств</span><span class="sxs-lookup"><span data-stu-id="fab73-130">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="fab73-131">Требуется **один** домен для разных сайтов ТСОП</span><span class="sxs-lookup"><span data-stu-id="fab73-131">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fab73-132">Настройка</span><span class="sxs-lookup"><span data-stu-id="fab73-132">Configure</span></span>  <br/> |<span data-ttu-id="fab73-133">Домены SIP</span><span class="sxs-lookup"><span data-stu-id="fab73-133">SIPDomains</span></span>  <br/> |<span data-ttu-id="fab73-134">Доменные имена и порядок должны быть **же** между устройствами</span><span class="sxs-lookup"><span data-stu-id="fab73-134">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="fab73-135">Доменные имена и порядок должны быть **же** между сайтами ТСОП</span><span class="sxs-lookup"><span data-stu-id="fab73-135">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fab73-136">Настройка</span><span class="sxs-lookup"><span data-stu-id="fab73-136">Configure</span></span>  <br/> |<span data-ttu-id="fab73-137">Имя сайта</span><span class="sxs-lookup"><span data-stu-id="fab73-137">Site name</span></span>  <br/> |<span data-ttu-id="fab73-138">**Одно** имя сайта для всех устройств</span><span class="sxs-lookup"><span data-stu-id="fab73-138">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="fab73-139">**Разные** имена сайтов для разных сайтов ТСОП</span><span class="sxs-lookup"><span data-stu-id="fab73-139">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fab73-140">Настройка</span><span class="sxs-lookup"><span data-stu-id="fab73-140">Configure</span></span>  <br/> |<span data-ttu-id="fab73-141">Имена серверов</span><span class="sxs-lookup"><span data-stu-id="fab73-141">Server names</span></span>  <br/> |<span data-ttu-id="fab73-142">**Разные** для всех устройств</span><span class="sxs-lookup"><span data-stu-id="fab73-142">**Different** across appliances</span></span> <br/> |<span data-ttu-id="fab73-143">**Разные** для разных сайтов ТСОП</span><span class="sxs-lookup"><span data-stu-id="fab73-143">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fab73-144">Настройка</span><span class="sxs-lookup"><span data-stu-id="fab73-144">Configure</span></span>  <br/> |<span data-ttu-id="fab73-145">Полные доменные имена внутренних пулов</span><span class="sxs-lookup"><span data-stu-id="fab73-145">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="fab73-146">**Одинаковые** для всех устройств</span><span class="sxs-lookup"><span data-stu-id="fab73-146">**Same** across appliances</span></span> <br/> |<span data-ttu-id="fab73-147">**Одинаковое** для разных сайтов ТСОП</span><span class="sxs-lookup"><span data-stu-id="fab73-147">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fab73-148">Настройка</span><span class="sxs-lookup"><span data-stu-id="fab73-148">Configure</span></span>  <br/> |<span data-ttu-id="fab73-149">Внутренние IP-адреса</span><span class="sxs-lookup"><span data-stu-id="fab73-149">Internal IPs</span></span>  <br/> |<span data-ttu-id="fab73-150">**Разные** для всех устройств</span><span class="sxs-lookup"><span data-stu-id="fab73-150">**Different** across appliances</span></span> <br/> |<span data-ttu-id="fab73-151">**Разные** для разных сайтов ТСОП</span><span class="sxs-lookup"><span data-stu-id="fab73-151">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fab73-152">Настройка</span><span class="sxs-lookup"><span data-stu-id="fab73-152">Configure</span></span>  <br/> |<span data-ttu-id="fab73-153">Внешнее полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="fab73-153">External FQDN</span></span>  <br/> |<span data-ttu-id="fab73-154">**Одинаковые** для всех устройств</span><span class="sxs-lookup"><span data-stu-id="fab73-154">**Same** across appliances</span></span> <br/> |<span data-ttu-id="fab73-155">**Разные** для разных сайтов ТСОП</span><span class="sxs-lookup"><span data-stu-id="fab73-155">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fab73-156">Настройка</span><span class="sxs-lookup"><span data-stu-id="fab73-156">Configure</span></span>  <br/> |<span data-ttu-id="fab73-157">Внешние IP-адреса</span><span class="sxs-lookup"><span data-stu-id="fab73-157">External IPs</span></span>  <br/> |<span data-ttu-id="fab73-158">**Разные** для всех устройств</span><span class="sxs-lookup"><span data-stu-id="fab73-158">**Different** across appliances</span></span> <br/> |<span data-ttu-id="fab73-159">**Разные** для разных сайтов ТСОП</span><span class="sxs-lookup"><span data-stu-id="fab73-159">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fab73-160">Настройка</span><span class="sxs-lookup"><span data-stu-id="fab73-160">Configure</span></span>  <br/> |<span data-ttu-id="fab73-161">Параметры шлюза ТСОП</span><span class="sxs-lookup"><span data-stu-id="fab73-161">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="fab73-162">**Одинаковые** для всех устройств</span><span class="sxs-lookup"><span data-stu-id="fab73-162">**Same** across appliances</span></span> <br/> |<span data-ttu-id="fab73-163">**Разные** для разных сайтов ТСОП</span><span class="sxs-lookup"><span data-stu-id="fab73-163">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="fab73-164">Настройка</span><span class="sxs-lookup"><span data-stu-id="fab73-164">Configure</span></span>  <br/> |<span data-ttu-id="fab73-165">Запись DNS</span><span class="sxs-lookup"><span data-stu-id="fab73-165">DNS record</span></span>  <br/> |<span data-ttu-id="fab73-166">Добавление записей с **одной** внешние полные доменные имена доступа и **различных** IP-адресов</span><span class="sxs-lookup"><span data-stu-id="fab73-166">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="fab73-167">Добавьте записи с **разными** полными доменными именами внешнего доступа и **разными** IP-адресами.</span><span class="sxs-lookup"><span data-stu-id="fab73-167">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="fab73-168">Установка</span><span class="sxs-lookup"><span data-stu-id="fab73-168">Setup</span></span>  <br/> |<span data-ttu-id="fab73-169">Гибридные клиента</span><span class="sxs-lookup"><span data-stu-id="fab73-169">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="fab73-170">Задайте параметр HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="fab73-170">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="fab73-171">Задайте параметр PeerDestination для выполнения отката</span><span class="sxs-lookup"><span data-stu-id="fab73-171">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="fab73-172">Задайте параметр HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="fab73-172">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="fab73-173">Задайте параметр PeerDestination для выполнения отката</span><span class="sxs-lookup"><span data-stu-id="fab73-173">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="fab73-174">Установка</span><span class="sxs-lookup"><span data-stu-id="fab73-174">Setup</span></span>  <br/> |<span data-ttu-id="fab73-175">Шлюз</span><span class="sxs-lookup"><span data-stu-id="fab73-175">Gateway</span></span>  <br/> |<span data-ttu-id="fab73-176">Сопоставление шлюзов сервера-посредника **M:N** на этом сайте</span><span class="sxs-lookup"><span data-stu-id="fab73-176">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="fab73-177">Шлюзы ТСОП на каждом сайте ТСОП должны подключаться только к серверам-посредникам на том же сайте</span><span class="sxs-lookup"><span data-stu-id="fab73-177">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="fab73-178">Установка</span><span class="sxs-lookup"><span data-stu-id="fab73-178">Setup</span></span>  <br/> |<span data-ttu-id="fab73-179">Пользователь</span><span class="sxs-lookup"><span data-stu-id="fab73-179">User</span></span>  <br/> |<span data-ttu-id="fab73-180">Настройте параметр UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="fab73-180">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="fab73-181">Настройте параметр UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="fab73-181">Set UserPSTNSettings</span></span>  <br/> |
   

