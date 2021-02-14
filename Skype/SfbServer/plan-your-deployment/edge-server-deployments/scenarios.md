---
title: Сценарии работы с edge-серверами в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: Сводка. Просмотрите эти сценарии, чтобы помочь вам спланировать топологию edge Server в Skype для бизнеса Server.
ms.openlocfilehash: cfcc1e8b34576fbec85464fb8d5e35903b47d8ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813799"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a><span data-ttu-id="93c00-103">Сценарии работы с edge-серверами в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="93c00-103">Edge Server scenarios in Skype for Business Server</span></span>
 
<span data-ttu-id="93c00-104">**Сводка:** Просмотрите эти сценарии, чтобы помочь вам спланировать топологию edge Server в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="93c00-104">**Summary:** Review these scenarios to help you plan your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="93c00-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span><span class="sxs-lookup"><span data-stu-id="93c00-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span></span> <span data-ttu-id="93c00-106">После выбора хорошего кандидата можно ознакомиться с требованиями к среде, которые необходимо решить.</span><span class="sxs-lookup"><span data-stu-id="93c00-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span></span> <span data-ttu-id="93c00-107">Ниже приводится пример, применимый к любому из сценариев, поэтому мы сначала упомянум об этом.</span><span class="sxs-lookup"><span data-stu-id="93c00-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span></span>
  
<span data-ttu-id="93c00-108">Эти рисунки, которые показаны только для примера (и поэтому содержат примеры данных IPv4 и IPv6), представляют не фактический поток связи, а высокоуровневый вид возможного трафика.</span><span class="sxs-lookup"><span data-stu-id="93c00-108">These figures, which are shown for example purposes only (and as such contains sample IPv4 and IPv6 data), don't represent the actual communication flow, but rather a high-level view of your possible traffic.</span></span> <span data-ttu-id="93c00-109">Сведения о портах также можно увидеть на схемах портов для каждого сценария ниже.</span><span class="sxs-lookup"><span data-stu-id="93c00-109">Port details can also be seen in the Port diagrams for each scenario below.</span></span>
  
<span data-ttu-id="93c00-110">На схемах покажите .com для внешнего интерфейса и .net для внутреннего, который также является образцом материала; Конечно, ваши собственные записи могут сильно меняться, если вы объединяете свой окончательный план Edge.</span><span class="sxs-lookup"><span data-stu-id="93c00-110">The diagrams show .com for the external interface and .net for the internal, which is also sample material; of course your own entries may be quite different when you're putting together your own final Edge plan.</span></span>
  
<span data-ttu-id="93c00-111">Мы не включаем директора (который является необязательным компонентом) в схемы, но вы можете прочитать об этом отдельно (это упоминается в других темах планирования).</span><span class="sxs-lookup"><span data-stu-id="93c00-111">We don't include the Director (which is an optional component) in any of the diagrams, but you can read about that separately (it's mentioned in other Planning topics).</span></span>
  
<span data-ttu-id="93c00-112">Как уже было отмечено выше, на схемах имеются примеры данных IPv6.</span><span class="sxs-lookup"><span data-stu-id="93c00-112">As noted above, there is sample IPv6 data in the diagrams.</span></span> <span data-ttu-id="93c00-113">Большая часть документации по планированию развертывания edge Server в Skype для бизнеса [Server](edge-server-deployments.md) относится к IPv4, но вы, конечно, поддерживаете, если вы хотите использовать IPv6.</span><span class="sxs-lookup"><span data-stu-id="93c00-113">Most of the documentation in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) will refer to IPv4, but you are certainly supported if you want to use IPv6.</span></span> <span data-ttu-id="93c00-114">Обратите внимание, что в назначенной адресной области вам потребуется IPv6-адреса, а также они должны работать с внутренними и внешними адресами, как и с IP-адресами IPv4.</span><span class="sxs-lookup"><span data-stu-id="93c00-114">Note that you'll need IPv6 addresses in your assigned address space, and they'll need to work with internal and external addressing, as with IPv4 IPs.</span></span> <span data-ttu-id="93c00-115">Благодаря Windows можно использовать функцию двойного стека, которая является отдельным и отдельным сетевым стеком для IPv4 и IPv6.</span><span class="sxs-lookup"><span data-stu-id="93c00-115">You can, thanks to Windows, employ the dual stack feature, which is a separate and distinct network stack for IPv4 and IPv6.</span></span> <span data-ttu-id="93c00-116">При необходимости вы сможете назначать адреса IPv4 и IPv6 одновременно.</span><span class="sxs-lookup"><span data-stu-id="93c00-116">This will, if you need, allow you to assign IPv4 and IPv6 addresses concurrently.</span></span>
  
<span data-ttu-id="93c00-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="93c00-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="93c00-118">При использовании контроля допуска вызовов (CAC) необходимо использовать IPv4 во внутреннем интерфейсе, чтобы он работал.</span><span class="sxs-lookup"><span data-stu-id="93c00-118">If you're using Call Admission Control (CAC) you do have to use IPv4 on the internal interface for it to work.</span></span> 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a><span data-ttu-id="93c00-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span><span class="sxs-lookup"><span data-stu-id="93c00-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span></span>

<span data-ttu-id="93c00-120">В этом сценарии нет возможности для высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="93c00-120">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="93c00-121">Это означает, что вы будете тратить меньше на оборудование и упротите развертывание.</span><span class="sxs-lookup"><span data-stu-id="93c00-121">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="93c00-122">Если высокая доступность является обязательной, ознакомьтесь с масштабированными консолидированными сценариями ниже.</span><span class="sxs-lookup"><span data-stu-id="93c00-122">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Сценарий edge для единой консолидированной границы с закрытым IP-адресом с использованием NAT](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="93c00-124">Схема порта</span><span class="sxs-lookup"><span data-stu-id="93c00-124">Port diagram</span></span>

<span data-ttu-id="93c00-125">У нас также есть схема портов для одного консолидированного сервера.</span><span class="sxs-lookup"><span data-stu-id="93c00-125">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Сетевой периметр для сценария с одним консолидированным периметром](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a><span data-ttu-id="93c00-127">Один консолидированный сервер Skype для бизнеса Server с общедоступными IP-адресами</span><span class="sxs-lookup"><span data-stu-id="93c00-127">Single consolidated Skype for Business Server Edge Server with public IP addresses</span></span>

<span data-ttu-id="93c00-128">В этом сценарии нет возможности для высокой доступности.</span><span class="sxs-lookup"><span data-stu-id="93c00-128">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="93c00-129">Это означает, что вы будете тратить меньше на оборудование и упротите развертывание.</span><span class="sxs-lookup"><span data-stu-id="93c00-129">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="93c00-130">Если высокая доступность является обязательной, ознакомьтесь с масштабированными консолидированными сценариями ниже.</span><span class="sxs-lookup"><span data-stu-id="93c00-130">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Сценарий edge для единой консолидированной границы с общедоступным IP-адресом](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="93c00-132">Схема порта</span><span class="sxs-lookup"><span data-stu-id="93c00-132">Port diagram</span></span>

<span data-ttu-id="93c00-133">У нас также есть схема портов для одного консолидированного сервера.</span><span class="sxs-lookup"><span data-stu-id="93c00-133">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Сетевой периметр для сценария с одним консолидированным периметром](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a><span data-ttu-id="93c00-135">Масштабированный консолидированный пул Skype для бизнеса Server Edge, балансировка нагрузки на DNS, частные IP-адреса и NAT</span><span class="sxs-lookup"><span data-stu-id="93c00-135">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing, and private IP addresses and NAT</span></span>

<span data-ttu-id="93c00-136">В этом сценарии обеспечивается высокая доступность в развертывании Edge, что дает преимущества масштабируемости и поддержки от сбойов.</span><span class="sxs-lookup"><span data-stu-id="93c00-136">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Сценарий edge для масштабированной консолидированной границы, DNS LB с закрытым IP-адресом с использованием NAT](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="93c00-138">Схема порта</span><span class="sxs-lookup"><span data-stu-id="93c00-138">Port diagram</span></span>

<span data-ttu-id="93c00-139">Также имеется схема масштабированных консолидированных пулов с балансировка нагрузки на DNS.</span><span class="sxs-lookup"><span data-stu-id="93c00-139">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Сетевой периметр для масштабированного консолидированного периметра по периметру с помощью DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a><span data-ttu-id="93c00-141">Масштабированный консолидированный пул Skype для бизнеса Server Edge с балансировка нагрузки на DNS и общедоступными IP-адресами</span><span class="sxs-lookup"><span data-stu-id="93c00-141">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing and public IP addresses</span></span>

<span data-ttu-id="93c00-142">В этом сценарии обеспечивается высокая доступность в развертывании Edge, что дает преимущества масштабируемости и поддержки от сбойов.</span><span class="sxs-lookup"><span data-stu-id="93c00-142">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Сценарий edge для масштабированной консолидированной границы, DNS LB с общедоступным IP-адресом](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="93c00-144">Схема порта</span><span class="sxs-lookup"><span data-stu-id="93c00-144">Port diagram</span></span>

<span data-ttu-id="93c00-145">Также имеется схема масштабированных консолидированных пулов с балансировка нагрузки на DNS.</span><span class="sxs-lookup"><span data-stu-id="93c00-145">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Сетевой периметр для масштабированного консолидированного периметра по периметру с помощью DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a><span data-ttu-id="93c00-147">Масштабированный консолидированный пул Skype для бизнеса Server Edge с аппаратной балансировка нагрузки</span><span class="sxs-lookup"><span data-stu-id="93c00-147">Scaled consolidated Skype for Business Server Edge pool, with hardware load balancing</span></span>

<span data-ttu-id="93c00-148">В этом сценарии обеспечивается высокая доступность в развертывании Edge, что дает преимущества масштабируемости и поддержки от сбойов.</span><span class="sxs-lookup"><span data-stu-id="93c00-148">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Сценарий edge для масштабированной консолидированной границы с HLB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
