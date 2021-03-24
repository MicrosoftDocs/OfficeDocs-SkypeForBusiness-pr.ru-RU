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
description: Узнайте о развертывании нескольких сайтов PSTN в cloud Connector Edition.
ms.openlocfilehash: 059b9a39a082e876b1dd9cd772a235c384a29107
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098405"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="42338-103">Развертывание нескольких сайтов в Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="42338-103">Deploy multiple sites in Cloud Connector</span></span>

> [!Important] 
> <span data-ttu-id="42338-104">Cloud Connector Edition завершит карьеру 31 июля 2021 г. вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="42338-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="42338-105">После обновления организации до Teams узнайте, как подключить сеть локальной телефонии к Teams с помощью прямой [маршрутизации.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="42338-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="42338-106">Узнайте о развертывании нескольких сайтов PSTN в cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="42338-106">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="42338-107">В этом разделе описывается развертывание нескольких сайтов телефонной сети с общедоступными переключениями (PSTN).</span><span class="sxs-lookup"><span data-stu-id="42338-107">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites.</span></span> <span data-ttu-id="42338-108">Сайты развертываются по одному, используя те же действия, что и развертывание одного сайта.</span><span class="sxs-lookup"><span data-stu-id="42338-108">Sites are deployed one at a time using the same steps as deploying a single site.</span></span> <span data-ttu-id="42338-109">В этом разделе описываются соображения и различия между сайтами в развертывании нескольких сайтов.</span><span class="sxs-lookup"><span data-stu-id="42338-109">This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="42338-110">Несколько сайтов с общедоступными переключениями телефонной сети (PSTN)</span><span class="sxs-lookup"><span data-stu-id="42338-110">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="42338-111">Ниже показан пример конфигурации для развертывания Skype для бизнеса Cloud Connector Edition для различных сайтов PSTN.</span><span class="sxs-lookup"><span data-stu-id="42338-111">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="42338-112">Убедитесь, что параметры конфигурации правильны перед началом развертывания.</span><span class="sxs-lookup"><span data-stu-id="42338-112">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="42338-113">PSTN Site 1</span><span class="sxs-lookup"><span data-stu-id="42338-113">PSTN Site 1</span></span>
  
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

<span data-ttu-id="42338-114">PSTN Site 2</span><span class="sxs-lookup"><span data-stu-id="42338-114">PSTN Site 2</span></span>
  
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

<span data-ttu-id="42338-115">Для каждого сайта PSTN, который необходимо добавить, выполните действия в Развертывании одного сайта [в облачном соединителю.](deploy-a-single-site-in-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="42338-115">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="42338-116">Общая папка для подготовки высокой доступности (HA) находится на сайте PSTN.</span><span class="sxs-lookup"><span data-stu-id="42338-116">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="42338-117">Общая папка должна **быть** разной между сайтами PSTN.</span><span class="sxs-lookup"><span data-stu-id="42338-117">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="42338-118">Не используйте ту же общую папку для нескольких сайтов.></span><span class="sxs-lookup"><span data-stu-id="42338-118">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="42338-119">Единый сайт с высокой доступностью (HA) по сравнению с развертыванием на нескольких узлах</span><span class="sxs-lookup"><span data-stu-id="42338-119">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="42338-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="42338-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="42338-121">В следующей таблице перечислены различия между одним сайтом с поддержкой HA и нескольким развертыванием сайта.</span><span class="sxs-lookup"><span data-stu-id="42338-121">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="42338-122">**Категория**</span><span class="sxs-lookup"><span data-stu-id="42338-122">**Category**</span></span>|<span data-ttu-id="42338-123">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="42338-123">**Item**</span></span>|<span data-ttu-id="42338-124">**Одно-сайт с ha**</span><span class="sxs-lookup"><span data-stu-id="42338-124">**Single-Site with HA**</span></span>|<span data-ttu-id="42338-125">**Multi-Site**</span><span class="sxs-lookup"><span data-stu-id="42338-125">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="42338-126">Настройка</span><span class="sxs-lookup"><span data-stu-id="42338-126">Configure</span></span>  <br/> |<span data-ttu-id="42338-127">Имя хозяина устройства</span><span class="sxs-lookup"><span data-stu-id="42338-127">Appliance Host Name</span></span> <br/> |<span data-ttu-id="42338-128">**Разные** устройства</span><span class="sxs-lookup"><span data-stu-id="42338-128">**Different** across appliances</span></span> <br/> |<span data-ttu-id="42338-129">**Разные** для сайтов PSTN</span><span class="sxs-lookup"><span data-stu-id="42338-129">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="42338-130">Установка</span><span class="sxs-lookup"><span data-stu-id="42338-130">Setup</span></span>  <br/> |<span data-ttu-id="42338-131">Общая папка</span><span class="sxs-lookup"><span data-stu-id="42338-131">Shared folder</span></span>  <br/> |<span data-ttu-id="42338-132">Требуется та **же общая** папка для устройств</span><span class="sxs-lookup"><span data-stu-id="42338-132">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="42338-133">Требуется **разная общая** папка для устройств</span><span class="sxs-lookup"><span data-stu-id="42338-133">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="42338-134">Настройка</span><span class="sxs-lookup"><span data-stu-id="42338-134">Configure</span></span>  <br/> |<span data-ttu-id="42338-135">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="42338-135">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="42338-136">Требуется один **и тот же** домен для устройств</span><span class="sxs-lookup"><span data-stu-id="42338-136">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="42338-137">Требуется один **и тот же** домен на сайтах PSTN</span><span class="sxs-lookup"><span data-stu-id="42338-137">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="42338-138">Настройка</span><span class="sxs-lookup"><span data-stu-id="42338-138">Configure</span></span>  <br/> |<span data-ttu-id="42338-139">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="42338-139">SIPDomains</span></span>  <br/> |<span data-ttu-id="42338-140">Доменные имена и порядок должны быть **одинаковыми** для всех устройств</span><span class="sxs-lookup"><span data-stu-id="42338-140">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="42338-141">Доменные имена и порядок должны быть **одинаковыми** на сайтах PSTN</span><span class="sxs-lookup"><span data-stu-id="42338-141">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="42338-142">Настройка</span><span class="sxs-lookup"><span data-stu-id="42338-142">Configure</span></span>  <br/> |<span data-ttu-id="42338-143">имя сайта.</span><span class="sxs-lookup"><span data-stu-id="42338-143">Site name</span></span>  <br/> |<span data-ttu-id="42338-144">**То же самое** Имя сайта в устройствах</span><span class="sxs-lookup"><span data-stu-id="42338-144">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="42338-145">**Разные** Имя сайта на сайтах PSTN</span><span class="sxs-lookup"><span data-stu-id="42338-145">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="42338-146">Настройка</span><span class="sxs-lookup"><span data-stu-id="42338-146">Configure</span></span>  <br/> |<span data-ttu-id="42338-147">Имена серверов</span><span class="sxs-lookup"><span data-stu-id="42338-147">Server names</span></span>  <br/> |<span data-ttu-id="42338-148">**Разные** устройства</span><span class="sxs-lookup"><span data-stu-id="42338-148">**Different** across appliances</span></span> <br/> |<span data-ttu-id="42338-149">**Разные** для сайтов PSTN</span><span class="sxs-lookup"><span data-stu-id="42338-149">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="42338-150">Настройка</span><span class="sxs-lookup"><span data-stu-id="42338-150">Configure</span></span>  <br/> |<span data-ttu-id="42338-151">Внутренние FQDNs пула</span><span class="sxs-lookup"><span data-stu-id="42338-151">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="42338-152">**То же** самое в устройствах</span><span class="sxs-lookup"><span data-stu-id="42338-152">**Same** across appliances</span></span> <br/> |<span data-ttu-id="42338-153">**То же** самое на сайтах PSTN</span><span class="sxs-lookup"><span data-stu-id="42338-153">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="42338-154">Настройка</span><span class="sxs-lookup"><span data-stu-id="42338-154">Configure</span></span>  <br/> |<span data-ttu-id="42338-155">Внутренние IPs</span><span class="sxs-lookup"><span data-stu-id="42338-155">Internal IPs</span></span>  <br/> |<span data-ttu-id="42338-156">**Разные** устройства</span><span class="sxs-lookup"><span data-stu-id="42338-156">**Different** across appliances</span></span> <br/> |<span data-ttu-id="42338-157">**Разные** для сайтов PSTN</span><span class="sxs-lookup"><span data-stu-id="42338-157">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="42338-158">Настройка</span><span class="sxs-lookup"><span data-stu-id="42338-158">Configure</span></span>  <br/> |<span data-ttu-id="42338-159">Внешний FQDN</span><span class="sxs-lookup"><span data-stu-id="42338-159">External FQDN</span></span>  <br/> |<span data-ttu-id="42338-160">**То же** самое в устройствах</span><span class="sxs-lookup"><span data-stu-id="42338-160">**Same** across appliances</span></span> <br/> |<span data-ttu-id="42338-161">**Разные** для сайтов PSTN</span><span class="sxs-lookup"><span data-stu-id="42338-161">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="42338-162">Настройка</span><span class="sxs-lookup"><span data-stu-id="42338-162">Configure</span></span>  <br/> |<span data-ttu-id="42338-163">Внешние IPs</span><span class="sxs-lookup"><span data-stu-id="42338-163">External IPs</span></span>  <br/> |<span data-ttu-id="42338-164">**Разные** устройства</span><span class="sxs-lookup"><span data-stu-id="42338-164">**Different** across appliances</span></span> <br/> |<span data-ttu-id="42338-165">**Разные** для сайтов PSTN</span><span class="sxs-lookup"><span data-stu-id="42338-165">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="42338-166">Настройка</span><span class="sxs-lookup"><span data-stu-id="42338-166">Configure</span></span>  <br/> |<span data-ttu-id="42338-167">Параметры GW PSTN</span><span class="sxs-lookup"><span data-stu-id="42338-167">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="42338-168">**То же** самое в устройствах</span><span class="sxs-lookup"><span data-stu-id="42338-168">**Same** across appliances</span></span> <br/> |<span data-ttu-id="42338-169">**Разные** для сайтов PSTN</span><span class="sxs-lookup"><span data-stu-id="42338-169">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="42338-170">Настройка</span><span class="sxs-lookup"><span data-stu-id="42338-170">Configure</span></span>  <br/> |<span data-ttu-id="42338-171">Запись DNS</span><span class="sxs-lookup"><span data-stu-id="42338-171">DNS record</span></span>  <br/> |<span data-ttu-id="42338-172">Добавление записей с **одинаковыми** FQDNs внешнего доступа и **различными** IP-адресами</span><span class="sxs-lookup"><span data-stu-id="42338-172">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="42338-173">Добавление записей с **различными** FQDNs внешнего доступа и **различными** IP-адресами</span><span class="sxs-lookup"><span data-stu-id="42338-173">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="42338-174">Установка</span><span class="sxs-lookup"><span data-stu-id="42338-174">Setup</span></span>  <br/> |<span data-ttu-id="42338-175">Гибридный клиент</span><span class="sxs-lookup"><span data-stu-id="42338-175">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="42338-176">Настройка hybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="42338-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="42338-177">Установите peerDestination для отката</span><span class="sxs-lookup"><span data-stu-id="42338-177">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="42338-178">Настройка hybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="42338-178">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="42338-179">Установите peerDestination для отката</span><span class="sxs-lookup"><span data-stu-id="42338-179">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="42338-180">Установка</span><span class="sxs-lookup"><span data-stu-id="42338-180">Setup</span></span>  <br/> |<span data-ttu-id="42338-181">Шлюз</span><span class="sxs-lookup"><span data-stu-id="42338-181">Gateway</span></span>  <br/> |<span data-ttu-id="42338-182">Сопоставление MS GW **M:N** на этом сайте</span><span class="sxs-lookup"><span data-stu-id="42338-182">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="42338-183">Шлюз PSTN на каждом сайте PSTN должен подключаться только к серверу-посреднику (s) на одном сайте.</span><span class="sxs-lookup"><span data-stu-id="42338-183">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="42338-184">Установка</span><span class="sxs-lookup"><span data-stu-id="42338-184">Setup</span></span>  <br/> |<span data-ttu-id="42338-185">User</span><span class="sxs-lookup"><span data-stu-id="42338-185">User</span></span>  <br/> |<span data-ttu-id="42338-186">Настройка userPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="42338-186">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="42338-187">Настройка userPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="42338-187">Set UserPSTNSettings</span></span>  <br/> |
