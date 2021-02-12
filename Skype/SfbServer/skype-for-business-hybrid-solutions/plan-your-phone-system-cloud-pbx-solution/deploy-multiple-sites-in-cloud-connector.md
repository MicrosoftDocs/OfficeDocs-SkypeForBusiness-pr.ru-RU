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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Узнайте о развертывании нескольких сайтов PSTN в Cloud Connector Edition.
ms.openlocfilehash: 3c777c54690b1eb31671f71cff915f1bb4854a0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358925"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="c1d01-103">Развертывание нескольких сайтов в Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="c1d01-103">Deploy multiple sites in Cloud Connector</span></span>

> [!Important] 
> <span data-ttu-id="c1d01-104">Выпуск Cloud Connector Edition завершится 31 июля 2021 г. вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="c1d01-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="c1d01-105">После обновления вашей организации до Teams узнайте, как подключить свою локальной телефонной сети к Teams с помощью [прямой маршрутизации.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="c1d01-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="c1d01-106">Узнайте о развертывании нескольких сайтов STN в Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="c1d01-106">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="c1d01-107">В этом разделе описывается развертывание нескольких сайтов телефонной сети общего чения (PSTN).</span><span class="sxs-lookup"><span data-stu-id="c1d01-107">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites.</span></span> <span data-ttu-id="c1d01-108">Сайты развертываются по одному, используя те же действия, что и при развертывании одного сайта.</span><span class="sxs-lookup"><span data-stu-id="c1d01-108">Sites are deployed one at a time using the same steps as deploying a single site.</span></span> <span data-ttu-id="c1d01-109">В этом разделе описываются вопросы и различия между сайтами в развертывании с несколькими сайтами.</span><span class="sxs-lookup"><span data-stu-id="c1d01-109">This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="c1d01-110">Несколько сайтов телефонной сети общего ского ского уровня (PSTN)</span><span class="sxs-lookup"><span data-stu-id="c1d01-110">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="c1d01-111">Ниже показан пример конфигурации для развертывания Skype для бизнеса Cloud Connector Edition для разных сайтов ЗВОНКОВ.</span><span class="sxs-lookup"><span data-stu-id="c1d01-111">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="c1d01-112">Перед началом развертывания убедитесь, что параметры конфигурации правильны.</span><span class="sxs-lookup"><span data-stu-id="c1d01-112">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="c1d01-113">Сайт STN 1</span><span class="sxs-lookup"><span data-stu-id="c1d01-113">PSTN Site 1</span></span>
  
```console
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

<span data-ttu-id="c1d01-114">Сайт STN 2</span><span class="sxs-lookup"><span data-stu-id="c1d01-114">PSTN Site 2</span></span>
  
```console
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

<span data-ttu-id="c1d01-115">Для каждого сайта STN, который нужно добавить, выполните действия, которые необходимо развернуть в [Cloud Connector.](deploy-a-single-site-in-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="c1d01-115">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c1d01-116">Общая папка для подготовки высокой доступности (HA) находится на сайте STN.</span><span class="sxs-lookup"><span data-stu-id="c1d01-116">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="c1d01-117">Общая папка должна **быть** разной между сайтами STN.</span><span class="sxs-lookup"><span data-stu-id="c1d01-117">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="c1d01-118">Не используйте общую папку для нескольких сайтов.></span><span class="sxs-lookup"><span data-stu-id="c1d01-118">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="c1d01-119">Один сайт с высокой доступностью по сравнению с развертываниями с несколькими сайтами</span><span class="sxs-lookup"><span data-stu-id="c1d01-119">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="c1d01-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="c1d01-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="c1d01-121">В следующей таблице перечислены различия между одним сайтом с поддержкой ha и развертыванием нескольких сайтов.</span><span class="sxs-lookup"><span data-stu-id="c1d01-121">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="c1d01-122">**Категория**</span><span class="sxs-lookup"><span data-stu-id="c1d01-122">**Category**</span></span>|<span data-ttu-id="c1d01-123">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="c1d01-123">**Item**</span></span>|<span data-ttu-id="c1d01-124">**Один сайт с ha**</span><span class="sxs-lookup"><span data-stu-id="c1d01-124">**Single-Site with HA**</span></span>|<span data-ttu-id="c1d01-125">**Multi-Site**</span><span class="sxs-lookup"><span data-stu-id="c1d01-125">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c1d01-126">Настройка</span><span class="sxs-lookup"><span data-stu-id="c1d01-126">Configure</span></span>  <br/> |<span data-ttu-id="c1d01-127">Имя хоста устройства</span><span class="sxs-lookup"><span data-stu-id="c1d01-127">Appliance Host Name</span></span> <br/> |<span data-ttu-id="c1d01-128">**Разные устройства**</span><span class="sxs-lookup"><span data-stu-id="c1d01-128">**Different** across appliances</span></span> <br/> |<span data-ttu-id="c1d01-129">**Разные** для разных сайтов STN</span><span class="sxs-lookup"><span data-stu-id="c1d01-129">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c1d01-130">Настройка</span><span class="sxs-lookup"><span data-stu-id="c1d01-130">Setup</span></span>  <br/> |<span data-ttu-id="c1d01-131">Общая папка</span><span class="sxs-lookup"><span data-stu-id="c1d01-131">Shared folder</span></span>  <br/> |<span data-ttu-id="c1d01-132">Требуется та **же общая** папка на разных устройствах</span><span class="sxs-lookup"><span data-stu-id="c1d01-132">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="c1d01-133">Требуется другая **общая** папка на разных устройствах</span><span class="sxs-lookup"><span data-stu-id="c1d01-133">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="c1d01-134">Настройка</span><span class="sxs-lookup"><span data-stu-id="c1d01-134">Configure</span></span>  <br/> |<span data-ttu-id="c1d01-135">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="c1d01-135">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="c1d01-136">Требуется один и **тот же** домен для всех устройств</span><span class="sxs-lookup"><span data-stu-id="c1d01-136">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="c1d01-137">Требуется один и **тот же** домен на сайтах STN</span><span class="sxs-lookup"><span data-stu-id="c1d01-137">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c1d01-138">Настройка</span><span class="sxs-lookup"><span data-stu-id="c1d01-138">Configure</span></span>  <br/> |<span data-ttu-id="c1d01-139">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="c1d01-139">SIPDomains</span></span>  <br/> |<span data-ttu-id="c1d01-140">Доменные имена и порядок должны быть **одинаковыми** для всех устройств</span><span class="sxs-lookup"><span data-stu-id="c1d01-140">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="c1d01-141">Доменные имена и порядок должны быть **одинаковыми** на сайтах STN</span><span class="sxs-lookup"><span data-stu-id="c1d01-141">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c1d01-142">Настройка</span><span class="sxs-lookup"><span data-stu-id="c1d01-142">Configure</span></span>  <br/> |<span data-ttu-id="c1d01-143">имя сайта.</span><span class="sxs-lookup"><span data-stu-id="c1d01-143">Site name</span></span>  <br/> |<span data-ttu-id="c1d01-144">**То же самое** Имя сайта на разных устройствах</span><span class="sxs-lookup"><span data-stu-id="c1d01-144">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="c1d01-145">**Разные** Имя сайта на сайтах STN</span><span class="sxs-lookup"><span data-stu-id="c1d01-145">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c1d01-146">Настройка</span><span class="sxs-lookup"><span data-stu-id="c1d01-146">Configure</span></span>  <br/> |<span data-ttu-id="c1d01-147">Имена серверов</span><span class="sxs-lookup"><span data-stu-id="c1d01-147">Server names</span></span>  <br/> |<span data-ttu-id="c1d01-148">**Разные устройства**</span><span class="sxs-lookup"><span data-stu-id="c1d01-148">**Different** across appliances</span></span> <br/> |<span data-ttu-id="c1d01-149">**Разные** для разных сайтов STN</span><span class="sxs-lookup"><span data-stu-id="c1d01-149">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c1d01-150">Настройка</span><span class="sxs-lookup"><span data-stu-id="c1d01-150">Configure</span></span>  <br/> |<span data-ttu-id="c1d01-151">FQDNs внутреннего пула</span><span class="sxs-lookup"><span data-stu-id="c1d01-151">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="c1d01-152">**Одинаково для** всех устройств</span><span class="sxs-lookup"><span data-stu-id="c1d01-152">**Same** across appliances</span></span> <br/> |<span data-ttu-id="c1d01-153">**То же** самое на сайтах STN</span><span class="sxs-lookup"><span data-stu-id="c1d01-153">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c1d01-154">Настройка</span><span class="sxs-lookup"><span data-stu-id="c1d01-154">Configure</span></span>  <br/> |<span data-ttu-id="c1d01-155">Внутренние IPS</span><span class="sxs-lookup"><span data-stu-id="c1d01-155">Internal IPs</span></span>  <br/> |<span data-ttu-id="c1d01-156">**Разные устройства**</span><span class="sxs-lookup"><span data-stu-id="c1d01-156">**Different** across appliances</span></span> <br/> |<span data-ttu-id="c1d01-157">**Разные** для разных сайтов STN</span><span class="sxs-lookup"><span data-stu-id="c1d01-157">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c1d01-158">Настройка</span><span class="sxs-lookup"><span data-stu-id="c1d01-158">Configure</span></span>  <br/> |<span data-ttu-id="c1d01-159">Внешнее FQDN</span><span class="sxs-lookup"><span data-stu-id="c1d01-159">External FQDN</span></span>  <br/> |<span data-ttu-id="c1d01-160">**Одинаково для** всех устройств</span><span class="sxs-lookup"><span data-stu-id="c1d01-160">**Same** across appliances</span></span> <br/> |<span data-ttu-id="c1d01-161">**Разные** для разных сайтов STN</span><span class="sxs-lookup"><span data-stu-id="c1d01-161">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c1d01-162">Настройка</span><span class="sxs-lookup"><span data-stu-id="c1d01-162">Configure</span></span>  <br/> |<span data-ttu-id="c1d01-163">Внешние IPS</span><span class="sxs-lookup"><span data-stu-id="c1d01-163">External IPs</span></span>  <br/> |<span data-ttu-id="c1d01-164">**Разные устройства**</span><span class="sxs-lookup"><span data-stu-id="c1d01-164">**Different** across appliances</span></span> <br/> |<span data-ttu-id="c1d01-165">**Разные** для разных сайтов STN</span><span class="sxs-lookup"><span data-stu-id="c1d01-165">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c1d01-166">Настройка</span><span class="sxs-lookup"><span data-stu-id="c1d01-166">Configure</span></span>  <br/> |<span data-ttu-id="c1d01-167">Параметры PSTN GW</span><span class="sxs-lookup"><span data-stu-id="c1d01-167">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="c1d01-168">**Одинаково для** всех устройств</span><span class="sxs-lookup"><span data-stu-id="c1d01-168">**Same** across appliances</span></span> <br/> |<span data-ttu-id="c1d01-169">**Разные** для разных сайтов STN</span><span class="sxs-lookup"><span data-stu-id="c1d01-169">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="c1d01-170">Настройка</span><span class="sxs-lookup"><span data-stu-id="c1d01-170">Configure</span></span>  <br/> |<span data-ttu-id="c1d01-171">Запись DNS</span><span class="sxs-lookup"><span data-stu-id="c1d01-171">DNS record</span></span>  <br/> |<span data-ttu-id="c1d01-172">Добавление записей  с одинаковыми FQDNs внешнего доступа и **разными** IP-адресами</span><span class="sxs-lookup"><span data-stu-id="c1d01-172">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="c1d01-173">Добавление записей **с** разными FQDNs внешнего доступа и **разными** IP-адресами</span><span class="sxs-lookup"><span data-stu-id="c1d01-173">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="c1d01-174">Настройка</span><span class="sxs-lookup"><span data-stu-id="c1d01-174">Setup</span></span>  <br/> |<span data-ttu-id="c1d01-175">Гибридный клиент</span><span class="sxs-lookup"><span data-stu-id="c1d01-175">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="c1d01-176">Настройка HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="c1d01-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="c1d01-177">Настройка peerDestination для отката</span><span class="sxs-lookup"><span data-stu-id="c1d01-177">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="c1d01-178">Настройка HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="c1d01-178">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="c1d01-179">Настройка peerDestination для отката</span><span class="sxs-lookup"><span data-stu-id="c1d01-179">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="c1d01-180">Настройка</span><span class="sxs-lookup"><span data-stu-id="c1d01-180">Setup</span></span>  <br/> |<span data-ttu-id="c1d01-181">Шлюз</span><span class="sxs-lookup"><span data-stu-id="c1d01-181">Gateway</span></span>  <br/> |<span data-ttu-id="c1d01-182">Сопоставление MS GW **M:N** на этом сайте</span><span class="sxs-lookup"><span data-stu-id="c1d01-182">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="c1d01-183">Шлюзы STN на каждом сайте STN должны подключаться только к серверам-посредникам на одном сайте</span><span class="sxs-lookup"><span data-stu-id="c1d01-183">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="c1d01-184">Настройка</span><span class="sxs-lookup"><span data-stu-id="c1d01-184">Setup</span></span>  <br/> |<span data-ttu-id="c1d01-185">Пользователь</span><span class="sxs-lookup"><span data-stu-id="c1d01-185">User</span></span>  <br/> |<span data-ttu-id="c1d01-186">Set UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="c1d01-186">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="c1d01-187">Set UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="c1d01-187">Set UserPSTNSettings</span></span>  <br/> |
   

