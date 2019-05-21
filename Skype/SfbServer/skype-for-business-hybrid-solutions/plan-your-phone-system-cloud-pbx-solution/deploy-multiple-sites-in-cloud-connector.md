---
title: Развертывание нескольких сайтов в Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Сведения о развертывании нескольких сайтов ТСОП в Cloud Connector Edition.
ms.openlocfilehash: ba6b76366b65a9febb9fab06e7cfb0fad759e5ee
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287330"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="1d344-103">Развертывание нескольких сайтов в Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="1d344-103">Deploy multiple sites in Cloud Connector</span></span>
 
<span data-ttu-id="1d344-104">Сведения о развертывании нескольких сайтов ТСОП в Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="1d344-104">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="1d344-p101">В этом разделе описывается развертывание нескольких сайтов телефонной сети общего пользования (ТСОП). Эти сайты развертываются поочередно с использованием одной и той же последовательности шагов. В этом разделе приводятся рекомендации и описываются различия между сайтами в развертывании с несколькими сайтами. </span><span class="sxs-lookup"><span data-stu-id="1d344-p101">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites. Sites are deployed one at a time using the same steps as deploying a single site. This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="1d344-108">Несколько сайтов телефонной сети общего пользования (ТСОП)</span><span class="sxs-lookup"><span data-stu-id="1d344-108">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="1d344-109">Ниже приведен пример конфигурации для развертывания облачного соединителя Skype для бизнеса для разных сайтов PSTN.</span><span class="sxs-lookup"><span data-stu-id="1d344-109">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="1d344-110">Прежде чем приступать к развертыванию, проверьте параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1d344-110">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="1d344-111">Сайт ТСОП 1</span><span class="sxs-lookup"><span data-stu-id="1d344-111">PSTN Site 1</span></span>
  
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

<span data-ttu-id="1d344-112">Сайт ТСОП 2</span><span class="sxs-lookup"><span data-stu-id="1d344-112">PSTN Site 2</span></span>
  
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

<span data-ttu-id="1d344-113">Для каждого сайта PSTN, который вы хотите добавить, выполните действия, описанные в разделе [развертывание одного сайта в облачном соединителе](deploy-a-single-site-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="1d344-113">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1d344-114">Общая папка для подготовки среды высокой доступности выделяется на каждый сайт ТСОП.</span><span class="sxs-lookup"><span data-stu-id="1d344-114">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="1d344-115">Каждый сайт ТСОП **должен** использовать разные общие папки.</span><span class="sxs-lookup"><span data-stu-id="1d344-115">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="1d344-116">Не используйте одну и ту же общую папку для нескольких сайтов. _Гт_</span><span class="sxs-lookup"><span data-stu-id="1d344-116">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="1d344-117">Сравнение развертывания отдельного сайта с высокой доступностью и развертывания с несколькими сайтами</span><span class="sxs-lookup"><span data-stu-id="1d344-117">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="1d344-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="1d344-118"></span></span>

<span data-ttu-id="1d344-119">В следующей таблице приводятся различия между конфигурацией с одним сайтом с поддержкой высокой доступности и развертыванием с несколькими сайтами.</span><span class="sxs-lookup"><span data-stu-id="1d344-119">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="1d344-120">**Категория**</span><span class="sxs-lookup"><span data-stu-id="1d344-120">**Category**</span></span>|<span data-ttu-id="1d344-121">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="1d344-121">**Item**</span></span>|<span data-ttu-id="1d344-122">**Один сайт с высокой доступностью**</span><span class="sxs-lookup"><span data-stu-id="1d344-122">**Single-Site with HA**</span></span>|<span data-ttu-id="1d344-123">**Несколько сайтов**</span><span class="sxs-lookup"><span data-stu-id="1d344-123">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1d344-124">Настройка</span><span class="sxs-lookup"><span data-stu-id="1d344-124">Configure</span></span>  <br/> |<span data-ttu-id="1d344-125">Имя узла управляющего устройства</span><span class="sxs-lookup"><span data-stu-id="1d344-125">Appliance Host Name</span></span> <br/> |<span data-ttu-id="1d344-126">**Разные** для всех устройств</span><span class="sxs-lookup"><span data-stu-id="1d344-126">**Different** across appliances</span></span> <br/> |<span data-ttu-id="1d344-127">**Разные** для разных сайтов ТСОП</span><span class="sxs-lookup"><span data-stu-id="1d344-127">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1d344-128">Установка</span><span class="sxs-lookup"><span data-stu-id="1d344-128">Setup</span></span>  <br/> |<span data-ttu-id="1d344-129">Общая папка</span><span class="sxs-lookup"><span data-stu-id="1d344-129">Shared folder</span></span>  <br/> |<span data-ttu-id="1d344-130">Требуется **одна и та же** общая папка для разных устройств</span><span class="sxs-lookup"><span data-stu-id="1d344-130">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="1d344-131">Требуются **разные** общие папки для каждого устройства</span><span class="sxs-lookup"><span data-stu-id="1d344-131">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="1d344-132">Настройка</span><span class="sxs-lookup"><span data-stu-id="1d344-132">Configure</span></span>  <br/> |<span data-ttu-id="1d344-133">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="1d344-133">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="1d344-134">Требуется **один** домен для всех устройств</span><span class="sxs-lookup"><span data-stu-id="1d344-134">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="1d344-135">Требуется **один** домен для разных сайтов ТСОП</span><span class="sxs-lookup"><span data-stu-id="1d344-135">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1d344-136">Настройка</span><span class="sxs-lookup"><span data-stu-id="1d344-136">Configure</span></span>  <br/> |<span data-ttu-id="1d344-137">Домены SIP</span><span class="sxs-lookup"><span data-stu-id="1d344-137">SIPDomains</span></span>  <br/> |<span data-ttu-id="1d344-138">Доменные имена и порядок должны быть **одинаковыми** на разных устройствах</span><span class="sxs-lookup"><span data-stu-id="1d344-138">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="1d344-139">Доменные имена и порядок должны быть **одинаковыми** на сайтах PSTN</span><span class="sxs-lookup"><span data-stu-id="1d344-139">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1d344-140">Настройка</span><span class="sxs-lookup"><span data-stu-id="1d344-140">Configure</span></span>  <br/> |<span data-ttu-id="1d344-141">Имя сайта</span><span class="sxs-lookup"><span data-stu-id="1d344-141">Site name</span></span>  <br/> |<span data-ttu-id="1d344-142">**Одно** имя сайта для всех устройств</span><span class="sxs-lookup"><span data-stu-id="1d344-142">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="1d344-143">**Разные** имена сайтов для разных сайтов ТСОП</span><span class="sxs-lookup"><span data-stu-id="1d344-143">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1d344-144">Настройка</span><span class="sxs-lookup"><span data-stu-id="1d344-144">Configure</span></span>  <br/> |<span data-ttu-id="1d344-145">Имена серверов</span><span class="sxs-lookup"><span data-stu-id="1d344-145">Server names</span></span>  <br/> |<span data-ttu-id="1d344-146">**Разные** для всех устройств</span><span class="sxs-lookup"><span data-stu-id="1d344-146">**Different** across appliances</span></span> <br/> |<span data-ttu-id="1d344-147">**Разные** для разных сайтов ТСОП</span><span class="sxs-lookup"><span data-stu-id="1d344-147">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1d344-148">Настройка</span><span class="sxs-lookup"><span data-stu-id="1d344-148">Configure</span></span>  <br/> |<span data-ttu-id="1d344-149">Полные доменные имена внутренних пулов</span><span class="sxs-lookup"><span data-stu-id="1d344-149">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="1d344-150">**Одинаковые** для всех устройств</span><span class="sxs-lookup"><span data-stu-id="1d344-150">**Same** across appliances</span></span> <br/> |<span data-ttu-id="1d344-151">**Одинаковое** для разных сайтов ТСОП</span><span class="sxs-lookup"><span data-stu-id="1d344-151">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1d344-152">Настройка</span><span class="sxs-lookup"><span data-stu-id="1d344-152">Configure</span></span>  <br/> |<span data-ttu-id="1d344-153">Внутренние IP-адреса</span><span class="sxs-lookup"><span data-stu-id="1d344-153">Internal IPs</span></span>  <br/> |<span data-ttu-id="1d344-154">**Разные** для всех устройств</span><span class="sxs-lookup"><span data-stu-id="1d344-154">**Different** across appliances</span></span> <br/> |<span data-ttu-id="1d344-155">**Разные** для разных сайтов ТСОП</span><span class="sxs-lookup"><span data-stu-id="1d344-155">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1d344-156">Настройка</span><span class="sxs-lookup"><span data-stu-id="1d344-156">Configure</span></span>  <br/> |<span data-ttu-id="1d344-157">Внешнее полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="1d344-157">External FQDN</span></span>  <br/> |<span data-ttu-id="1d344-158">**Одинаковые** для всех устройств</span><span class="sxs-lookup"><span data-stu-id="1d344-158">**Same** across appliances</span></span> <br/> |<span data-ttu-id="1d344-159">**Разные** для разных сайтов ТСОП</span><span class="sxs-lookup"><span data-stu-id="1d344-159">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1d344-160">Настройка</span><span class="sxs-lookup"><span data-stu-id="1d344-160">Configure</span></span>  <br/> |<span data-ttu-id="1d344-161">Внешние IP-адреса</span><span class="sxs-lookup"><span data-stu-id="1d344-161">External IPs</span></span>  <br/> |<span data-ttu-id="1d344-162">**Разные** для всех устройств</span><span class="sxs-lookup"><span data-stu-id="1d344-162">**Different** across appliances</span></span> <br/> |<span data-ttu-id="1d344-163">**Разные** для разных сайтов ТСОП</span><span class="sxs-lookup"><span data-stu-id="1d344-163">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1d344-164">Настройка</span><span class="sxs-lookup"><span data-stu-id="1d344-164">Configure</span></span>  <br/> |<span data-ttu-id="1d344-165">Параметры шлюза ТСОП</span><span class="sxs-lookup"><span data-stu-id="1d344-165">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="1d344-166">**Одинаковые** для всех устройств</span><span class="sxs-lookup"><span data-stu-id="1d344-166">**Same** across appliances</span></span> <br/> |<span data-ttu-id="1d344-167">**Разные** для разных сайтов ТСОП</span><span class="sxs-lookup"><span data-stu-id="1d344-167">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="1d344-168">Настройка</span><span class="sxs-lookup"><span data-stu-id="1d344-168">Configure</span></span>  <br/> |<span data-ttu-id="1d344-169">Запись DNS</span><span class="sxs-lookup"><span data-stu-id="1d344-169">DNS record</span></span>  <br/> |<span data-ttu-id="1d344-170">Добавление записей с **одинаковыми** полными доменными данными внешнего доступа и **разными** IP-адресами</span><span class="sxs-lookup"><span data-stu-id="1d344-170">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="1d344-171">Добавьте записи с **разными** полными доменными именами внешнего доступа и **разными** IP-адресами.</span><span class="sxs-lookup"><span data-stu-id="1d344-171">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="1d344-172">Установка</span><span class="sxs-lookup"><span data-stu-id="1d344-172">Setup</span></span>  <br/> |<span data-ttu-id="1d344-173">Гибридный клиент</span><span class="sxs-lookup"><span data-stu-id="1d344-173">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="1d344-174">Задайте параметр HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="1d344-174">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="1d344-175">Задайте параметр PeerDestination для выполнения отката</span><span class="sxs-lookup"><span data-stu-id="1d344-175">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="1d344-176">Задайте параметр HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="1d344-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="1d344-177">Задайте параметр PeerDestination для выполнения отката</span><span class="sxs-lookup"><span data-stu-id="1d344-177">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="1d344-178">Установка</span><span class="sxs-lookup"><span data-stu-id="1d344-178">Setup</span></span>  <br/> |<span data-ttu-id="1d344-179">Шлюз</span><span class="sxs-lookup"><span data-stu-id="1d344-179">Gateway</span></span>  <br/> |<span data-ttu-id="1d344-180">Сопоставление шлюзов сервера-посредника **M:N** на этом сайте</span><span class="sxs-lookup"><span data-stu-id="1d344-180">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="1d344-181">Шлюзы ТСОП на каждом сайте ТСОП должны подключаться только к серверам-посредникам на том же сайте</span><span class="sxs-lookup"><span data-stu-id="1d344-181">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="1d344-182">Установка</span><span class="sxs-lookup"><span data-stu-id="1d344-182">Setup</span></span>  <br/> |<span data-ttu-id="1d344-183">Пользователь</span><span class="sxs-lookup"><span data-stu-id="1d344-183">User</span></span>  <br/> |<span data-ttu-id="1d344-184">Настройте параметр UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="1d344-184">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="1d344-185">Настройте параметр UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="1d344-185">Set UserPSTNSettings</span></span>  <br/> |
   

