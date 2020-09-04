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
description: Сведения о развертывании нескольких сайтов PSTN в Cloud Connector Edition.
ms.openlocfilehash: 3c777c54690b1eb31671f71cff915f1bb4854a0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358925"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="96326-103">Развертывание нескольких сайтов в Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="96326-103">Deploy multiple sites in Cloud Connector</span></span>

> [!Important] 
> <span data-ttu-id="96326-104">Cloud Connector Edition выйдет 31 июля 2021 вместе со Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="96326-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="96326-105">После обновления вашей организации до Teams Узнайте, как подключить локальную телефонную сеть к Teams с помощью [прямой маршрутизации](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="96326-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="96326-106">Сведения о развертывании нескольких сайтов PSTN в Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="96326-106">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="96326-107">В этом разделе описывается развертывание нескольких сайтов телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="96326-107">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites.</span></span> <span data-ttu-id="96326-108">Сайты развертываются по одному, используя те же действия, что и развертывание одного сайта.</span><span class="sxs-lookup"><span data-stu-id="96326-108">Sites are deployed one at a time using the same steps as deploying a single site.</span></span> <span data-ttu-id="96326-109">В этом разделе описываются вопросы и различия между сайтами в развертывании с несколькими сайтами.</span><span class="sxs-lookup"><span data-stu-id="96326-109">This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="96326-110">Несколько сайтов телефонной сети общего пользования (PSTN)</span><span class="sxs-lookup"><span data-stu-id="96326-110">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="96326-111">Ниже показан пример конфигурации для развертывания Skype для бизнеса Cloud Connector Edition для разных сайтов PSTN.</span><span class="sxs-lookup"><span data-stu-id="96326-111">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="96326-112">Прежде чем приступать к развертыванию, убедитесь, что параметры конфигурации верны.</span><span class="sxs-lookup"><span data-stu-id="96326-112">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="96326-113">PSTN-сайт 1</span><span class="sxs-lookup"><span data-stu-id="96326-113">PSTN Site 1</span></span>
  
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

<span data-ttu-id="96326-114">PSTN-сайт 2</span><span class="sxs-lookup"><span data-stu-id="96326-114">PSTN Site 2</span></span>
  
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

<span data-ttu-id="96326-115">Для каждого добавляемого сайта PSTN выполните действия, описанные в разделе [развертывание одного сайта в Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="96326-115">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="96326-116">Общая папка для подготовки высокой доступности (HA) — на сайте PSTN.</span><span class="sxs-lookup"><span data-stu-id="96326-116">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="96326-117">Общая папка **должна** быть разной между сайтами PSTN.</span><span class="sxs-lookup"><span data-stu-id="96326-117">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="96326-118">Не используйте одну и ту же общую папку для нескольких сайтов. ></span><span class="sxs-lookup"><span data-stu-id="96326-118">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="96326-119">Один сайт с высокой доступностью (HA) по сравнению с развертыванием с несколькими сайтами</span><span class="sxs-lookup"><span data-stu-id="96326-119">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="96326-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="96326-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="96326-121">В следующей таблице перечислены различия между отдельными сайтами с поддержкой высокой доступности и развертыванием нескольких сайтов.</span><span class="sxs-lookup"><span data-stu-id="96326-121">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="96326-122">**Категория**</span><span class="sxs-lookup"><span data-stu-id="96326-122">**Category**</span></span>|<span data-ttu-id="96326-123">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="96326-123">**Item**</span></span>|<span data-ttu-id="96326-124">**Один сайт с высокой доступностью**</span><span class="sxs-lookup"><span data-stu-id="96326-124">**Single-Site with HA**</span></span>|<span data-ttu-id="96326-125">**Несколько сайтов**</span><span class="sxs-lookup"><span data-stu-id="96326-125">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="96326-126">Настройка</span><span class="sxs-lookup"><span data-stu-id="96326-126">Configure</span></span>  <br/> |<span data-ttu-id="96326-127">Имя узла устройства</span><span class="sxs-lookup"><span data-stu-id="96326-127">Appliance Host Name</span></span> <br/> |<span data-ttu-id="96326-128">**Разные для разных** устройств</span><span class="sxs-lookup"><span data-stu-id="96326-128">**Different** across appliances</span></span> <br/> |<span data-ttu-id="96326-129">**Разный** для сайтов PSTN</span><span class="sxs-lookup"><span data-stu-id="96326-129">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="96326-130">Настройка</span><span class="sxs-lookup"><span data-stu-id="96326-130">Setup</span></span>  <br/> |<span data-ttu-id="96326-131">Общая папка</span><span class="sxs-lookup"><span data-stu-id="96326-131">Shared folder</span></span>  <br/> |<span data-ttu-id="96326-132">Требуется **одна и та же** общая папка для всех устройств</span><span class="sxs-lookup"><span data-stu-id="96326-132">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="96326-133">Требуется **другая** общая папка для разных устройств</span><span class="sxs-lookup"><span data-stu-id="96326-133">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="96326-134">Настройка</span><span class="sxs-lookup"><span data-stu-id="96326-134">Configure</span></span>  <br/> |<span data-ttu-id="96326-135">виртуалмачинедомаин</span><span class="sxs-lookup"><span data-stu-id="96326-135">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="96326-136">Требуется **один и тот же** домен для устройств</span><span class="sxs-lookup"><span data-stu-id="96326-136">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="96326-137">Требуется **один** домен для сайтов PSTN</span><span class="sxs-lookup"><span data-stu-id="96326-137">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="96326-138">Настройка</span><span class="sxs-lookup"><span data-stu-id="96326-138">Configure</span></span>  <br/> |<span data-ttu-id="96326-139">сипдомаинс</span><span class="sxs-lookup"><span data-stu-id="96326-139">SIPDomains</span></span>  <br/> |<span data-ttu-id="96326-140">Имена и порядок доменов должны быть **одинаковыми** для всех устройств</span><span class="sxs-lookup"><span data-stu-id="96326-140">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="96326-141">Имена и порядок доменов должны быть **одинаковы** для сайтов PSTN</span><span class="sxs-lookup"><span data-stu-id="96326-141">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="96326-142">Настройка</span><span class="sxs-lookup"><span data-stu-id="96326-142">Configure</span></span>  <br/> |<span data-ttu-id="96326-143">имя сайта.</span><span class="sxs-lookup"><span data-stu-id="96326-143">Site name</span></span>  <br/> |<span data-ttu-id="96326-144">**То же самое** Имя сайта для разных устройств</span><span class="sxs-lookup"><span data-stu-id="96326-144">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="96326-145">**Разные** Имя сайта на сайтах PSTN</span><span class="sxs-lookup"><span data-stu-id="96326-145">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="96326-146">Настройка</span><span class="sxs-lookup"><span data-stu-id="96326-146">Configure</span></span>  <br/> |<span data-ttu-id="96326-147">Имена серверов</span><span class="sxs-lookup"><span data-stu-id="96326-147">Server names</span></span>  <br/> |<span data-ttu-id="96326-148">**Разные для разных** устройств</span><span class="sxs-lookup"><span data-stu-id="96326-148">**Different** across appliances</span></span> <br/> |<span data-ttu-id="96326-149">**Разный** для сайтов PSTN</span><span class="sxs-lookup"><span data-stu-id="96326-149">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="96326-150">Настройка</span><span class="sxs-lookup"><span data-stu-id="96326-150">Configure</span></span>  <br/> |<span data-ttu-id="96326-151">Полные доменные имена внутреннего пула</span><span class="sxs-lookup"><span data-stu-id="96326-151">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="96326-152">**Одинаково** для разных устройств</span><span class="sxs-lookup"><span data-stu-id="96326-152">**Same** across appliances</span></span> <br/> |<span data-ttu-id="96326-153">**Одинаково** на сайтах PSTN</span><span class="sxs-lookup"><span data-stu-id="96326-153">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="96326-154">Настройка</span><span class="sxs-lookup"><span data-stu-id="96326-154">Configure</span></span>  <br/> |<span data-ttu-id="96326-155">Внутренние IP-адреса</span><span class="sxs-lookup"><span data-stu-id="96326-155">Internal IPs</span></span>  <br/> |<span data-ttu-id="96326-156">**Разные для разных** устройств</span><span class="sxs-lookup"><span data-stu-id="96326-156">**Different** across appliances</span></span> <br/> |<span data-ttu-id="96326-157">**Разный** для сайтов PSTN</span><span class="sxs-lookup"><span data-stu-id="96326-157">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="96326-158">Настройка</span><span class="sxs-lookup"><span data-stu-id="96326-158">Configure</span></span>  <br/> |<span data-ttu-id="96326-159">Внешнее полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="96326-159">External FQDN</span></span>  <br/> |<span data-ttu-id="96326-160">**Одинаково** для разных устройств</span><span class="sxs-lookup"><span data-stu-id="96326-160">**Same** across appliances</span></span> <br/> |<span data-ttu-id="96326-161">**Разный** для сайтов PSTN</span><span class="sxs-lookup"><span data-stu-id="96326-161">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="96326-162">Настройка</span><span class="sxs-lookup"><span data-stu-id="96326-162">Configure</span></span>  <br/> |<span data-ttu-id="96326-163">Внешние IP-адреса</span><span class="sxs-lookup"><span data-stu-id="96326-163">External IPs</span></span>  <br/> |<span data-ttu-id="96326-164">**Разные для разных** устройств</span><span class="sxs-lookup"><span data-stu-id="96326-164">**Different** across appliances</span></span> <br/> |<span data-ttu-id="96326-165">**Разный** для сайтов PSTN</span><span class="sxs-lookup"><span data-stu-id="96326-165">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="96326-166">Настройка</span><span class="sxs-lookup"><span data-stu-id="96326-166">Configure</span></span>  <br/> |<span data-ttu-id="96326-167">Параметры PSTN GW</span><span class="sxs-lookup"><span data-stu-id="96326-167">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="96326-168">**Одинаково** для разных устройств</span><span class="sxs-lookup"><span data-stu-id="96326-168">**Same** across appliances</span></span> <br/> |<span data-ttu-id="96326-169">**Разный** для сайтов PSTN</span><span class="sxs-lookup"><span data-stu-id="96326-169">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="96326-170">Настройка</span><span class="sxs-lookup"><span data-stu-id="96326-170">Configure</span></span>  <br/> |<span data-ttu-id="96326-171">Запись DNS</span><span class="sxs-lookup"><span data-stu-id="96326-171">DNS record</span></span>  <br/> |<span data-ttu-id="96326-172">Добавление записей с **одинаковыми** полными доменными именами внешнего доступа и **разными** IP-адресами</span><span class="sxs-lookup"><span data-stu-id="96326-172">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="96326-173">Добавление записей с **различными** полными доменными именами внешнего доступа и **разными** IP-адресами</span><span class="sxs-lookup"><span data-stu-id="96326-173">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="96326-174">Настройка</span><span class="sxs-lookup"><span data-stu-id="96326-174">Setup</span></span>  <br/> |<span data-ttu-id="96326-175">Гибридный клиент</span><span class="sxs-lookup"><span data-stu-id="96326-175">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="96326-176">Set задайте hybridpstnsite</span><span class="sxs-lookup"><span data-stu-id="96326-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="96326-177">Set параметр peerdestination для резервного</span><span class="sxs-lookup"><span data-stu-id="96326-177">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="96326-178">Set задайте hybridpstnsite</span><span class="sxs-lookup"><span data-stu-id="96326-178">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="96326-179">Set параметр peerdestination для резервного</span><span class="sxs-lookup"><span data-stu-id="96326-179">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="96326-180">Настройка</span><span class="sxs-lookup"><span data-stu-id="96326-180">Setup</span></span>  <br/> |<span data-ttu-id="96326-181">Шлюз</span><span class="sxs-lookup"><span data-stu-id="96326-181">Gateway</span></span>  <br/> |<span data-ttu-id="96326-182">Сопоставление **M:N** MS GW на этом сайте</span><span class="sxs-lookup"><span data-stu-id="96326-182">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="96326-183">Шлюзы PSTN на каждом сайте PSTN должны подключаться только к серверам-посредникам на том же сайте.</span><span class="sxs-lookup"><span data-stu-id="96326-183">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="96326-184">Настройка</span><span class="sxs-lookup"><span data-stu-id="96326-184">Setup</span></span>  <br/> |<span data-ttu-id="96326-185">Пользователь</span><span class="sxs-lookup"><span data-stu-id="96326-185">User</span></span>  <br/> |<span data-ttu-id="96326-186">Set Усерпстнсеттингс</span><span class="sxs-lookup"><span data-stu-id="96326-186">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="96326-187">Set Усерпстнсеттингс</span><span class="sxs-lookup"><span data-stu-id="96326-187">Set UserPSTNSettings</span></span>  <br/> |
   

