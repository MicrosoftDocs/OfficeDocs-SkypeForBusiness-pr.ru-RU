---
title: Пограничный сервер сценариев в Скайп для Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 'Сводка: Просмотрите эти сценарии, которые помогут вам спланировать топологию пограничного сервера в Скайп для Business Server.'
ms.openlocfilehash: 6072417fabeafe330a65887bc3f96d445c970541
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33885070"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a><span data-ttu-id="dc039-103">Пограничный сервер сценариев в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="dc039-103">Edge Server scenarios in Skype for Business Server</span></span>
 
<span data-ttu-id="dc039-104">**Сводка:** Просмотрите эти сценарии, которые помогут вам спланировать топологию пограничного сервера в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="dc039-104">**Summary:** Review these scenarios to help you plan your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="dc039-105">У нас есть некоторые сценарии схемы для облегчения визуализация и о выборе какие Скайп для пограничного сервера Business Server топологии требуется реализовать.</span><span class="sxs-lookup"><span data-stu-id="dc039-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span></span> <span data-ttu-id="dc039-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span><span class="sxs-lookup"><span data-stu-id="dc039-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span></span> <span data-ttu-id="dc039-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span><span class="sxs-lookup"><span data-stu-id="dc039-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span></span>
  
<span data-ttu-id="dc039-p102">Эти рисунки используются исключительно в целях иллюстрации (по этой причине они содержат образцы данных IPv4 и IPv6). Они не отражают действительный коммуникационный поток, но дают высокоуровневое представление о возможном трафике. Сведения о портах представлены на диаграммах портов в каждом сценарии.</span><span class="sxs-lookup"><span data-stu-id="dc039-p102">These figures, which are shown for example purposes only (and as such contains sample IPv4 and IPv6 data), don't represent the actual communication flow, but rather a high-level view of your possible traffic. Port details can also be seen in the Port diagrams for each scenario below.</span></span>
  
<span data-ttu-id="dc039-110">Диаграммы отображают домен .com для внешнего интерфейса и .net для внутреннего интерфейса в качестве образцов. Конечно, ваши собственные записи могут значительно отличаться, когда вы будете создавать собственный пограничный план.</span><span class="sxs-lookup"><span data-stu-id="dc039-110">The diagrams show .com for the external interface and .net for the internal, which is also sample material; of course your own entries may be quite different when you're putting together your own final Edge plan.</span></span>
  
<span data-ttu-id="dc039-111">Мы не добавляйте директора (который является дополнительным) в любом из схемы, но вы можете ознакомьтесь со сведениями о, отдельно (упомянутые в другие разделы, планирование).</span><span class="sxs-lookup"><span data-stu-id="dc039-111">We don't include the Director (which is an optional component) in any of the diagrams, but you can read about that separately (it's mentioned in other Planning topics).</span></span>
  
<span data-ttu-id="dc039-112">Как указано выше, в диаграммах есть образец данных IPv6.</span><span class="sxs-lookup"><span data-stu-id="dc039-112">As noted above, there is sample IPv6 data in the diagrams.</span></span> <span data-ttu-id="dc039-113">Большая часть документации в [Планирование развертывания пограничного сервера, в Скайп для Business Server](edge-server-deployments.md) будет ссылаться на IPv4, но поддерживаются Конечно, если вы хотите использовать IPv6.</span><span class="sxs-lookup"><span data-stu-id="dc039-113">Most of the documentation in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) will refer to IPv4, but you are certainly supported if you want to use IPv6.</span></span> <span data-ttu-id="dc039-114">Обратите внимание, что вам потребуются адреса IPv6 в выделенном адресном пространстве, которые будут работать с внутренними и внешними адресами, а также IP-адресами IPv4.</span><span class="sxs-lookup"><span data-stu-id="dc039-114">Note that you'll need IPv6 addresses in your assigned address space, and they'll need to work with internal and external addressing, as with IPv4 IPs.</span></span> <span data-ttu-id="dc039-115">Windows позволяет использовать двойной стек, который представляет собой отдельный сетевой стек для IPv4 и IPv6.</span><span class="sxs-lookup"><span data-stu-id="dc039-115">You can, thanks to Windows, employ the dual stack feature, which is a separate and distinct network stack for IPv4 and IPv6.</span></span> <span data-ttu-id="dc039-116">Он позволяет назначать адреса для IPv4 и IPv6 одновременно, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="dc039-116">This will, if you need, allow you to assign IPv4 and IPv6 addresses concurrently.</span></span>
  
<span data-ttu-id="dc039-117">Преобразование сетевых адресов устройств, что позволяет NAT64 (IPv6 для IPv4) и NAT66 (IPv6 в IPv6)), и это допустимо для использования с Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="dc039-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="dc039-118">При использовании контроля допуска звонков для внутреннего интерфейса необязательно использоваться IPv4.</span><span class="sxs-lookup"><span data-stu-id="dc039-118">If you're using Call Admission Control (CAC) you do have to use IPv4 on the internal interface for it to work.</span></span> 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a><span data-ttu-id="dc039-119">Отдельный консолидированный Скайп для пограничного сервера Business Server с частной IP-адресами и трансляцией сетевых адресов</span><span class="sxs-lookup"><span data-stu-id="dc039-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span></span>

<span data-ttu-id="dc039-p104">В этом сценарии отсутствует способ обеспечения высокой доступности. Это означает, что вы получите упрощенное развертывание с небольшими затратами на оборудование</span><span class="sxs-lookup"><span data-stu-id="dc039-p104">With this scenario, there is no option for high availability. This will mean you spend less on hardware and have a simpler deployment. If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Сценарий пограничных серверов для отдельного консолидированного пограничного сервера с частным IP-адресом с преобразованием сетевых адресов](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="dc039-124">Схема портов</span><span class="sxs-lookup"><span data-stu-id="dc039-124">Port diagram</span></span>

<span data-ttu-id="dc039-125">У нас также есть схема для портов для одного консолидированного пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="dc039-125">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Масштабированный консолидированный пограничный сервер на периметре сети для сценария пограничных серверов](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a><span data-ttu-id="dc039-127">Отдельный консолидированный Скайп Business Server пограничного сервера с общедоступными IP-адресами</span><span class="sxs-lookup"><span data-stu-id="dc039-127">Single consolidated Skype for Business Server Edge Server with public IP addresses</span></span>

<span data-ttu-id="dc039-p105">В этом сценарии отсутствует способ обеспечения высокой доступности. Это означает, что вы получите упрощенное развертывание с небольшими затратами на оборудование</span><span class="sxs-lookup"><span data-stu-id="dc039-p105">With this scenario, there is no option for high availability. This will mean you spend less on hardware and have a simpler deployment. If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Сценарий пограничных серверов для отдельного консолидированного пограничного сервера с общедоступным IP-адресом](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="dc039-132">Схема портов</span><span class="sxs-lookup"><span data-stu-id="dc039-132">Port diagram</span></span>

<span data-ttu-id="dc039-133">У нас также есть схема для портов для одного консолидированного пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="dc039-133">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Масштабированный консолидированный пограничный сервер на периметре сети для сценария пограничных серверов](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a><span data-ttu-id="dc039-135">Масштабируемый консолидированный Скайп для пограничного сервера Business пула с DNS нагрузки Балансировка и частных IP-адресов и преобразование сетевых адресов</span><span class="sxs-lookup"><span data-stu-id="dc039-135">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing, and private IP addresses and NAT</span></span>

<span data-ttu-id="dc039-136">С этим сценарием можно обеспечить высокую доступность в пограничном развертывании, которое предлагает преимущества масштабируемости и поддержку отказоустойчивости.</span><span class="sxs-lookup"><span data-stu-id="dc039-136">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Сценарий пограничных серверов для масштабированного консолидированного пограничного сервера, DNS LB с частным IP-адресом с преобразованием сетевых адресов](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="dc039-138">Схема портов</span><span class="sxs-lookup"><span data-stu-id="dc039-138">Port diagram</span></span>

<span data-ttu-id="dc039-139">У нас также есть схема для масштабируемого консолидированного пограничного сервера пулы с балансировкой нагрузки DNS.</span><span class="sxs-lookup"><span data-stu-id="dc039-139">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Масштабированный консолидированный пограничный сервер с применением DNS LB на периметре сети для сценария пограничных серверов](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a><span data-ttu-id="dc039-141">Масштабируемый консолидированный Скайп для пограничного сервера Business пула с DNS нагрузки Балансировка и общедоступный IP-адресов</span><span class="sxs-lookup"><span data-stu-id="dc039-141">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing and public IP addresses</span></span>

<span data-ttu-id="dc039-142">С этим сценарием можно обеспечить высокую доступность в пограничном развертывании, которое предлагает преимущества масштабируемости и поддержку отказоустойчивости.</span><span class="sxs-lookup"><span data-stu-id="dc039-142">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Сценарий пограничных серверов для масштабированного консолидированного пограничного сервера, DNS LB с общедоступным IP-адресом](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="dc039-144">Схема портов</span><span class="sxs-lookup"><span data-stu-id="dc039-144">Port diagram</span></span>

<span data-ttu-id="dc039-145">У нас также есть схема для масштабируемого консолидированного пограничного сервера пулы с балансировкой нагрузки DNS.</span><span class="sxs-lookup"><span data-stu-id="dc039-145">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Масштабированный консолидированный пограничный сервер с применением DNS LB на периметре сети для сценария пограничных серверов](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a><span data-ttu-id="dc039-147">Масштабированная и консолидированная Скайп для пограничного сервера Business пула, с балансировкой нагрузки оборудования</span><span class="sxs-lookup"><span data-stu-id="dc039-147">Scaled consolidated Skype for Business Server Edge pool, with hardware load balancing</span></span>

<span data-ttu-id="dc039-148">С этим сценарием можно обеспечить высокую доступность в пограничном развертывании, которое предлагает преимущества масштабируемости и поддержку отказоустойчивости.</span><span class="sxs-lookup"><span data-stu-id="dc039-148">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Сценарий пограничных серверов для масштабированного консолидированного пограничного сервера с устройством балансировки нагрузки](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="dc039-150">Схема портов</span><span class="sxs-lookup"><span data-stu-id="dc039-150">Port diagram</span></span>

<span data-ttu-id="dc039-151">Также у нас есть схема для масштабируемого консолидированного пограничного сервера пулы с балансировкой нагрузки оборудования</span><span class="sxs-lookup"><span data-stu-id="dc039-151">We also have a diagram for scaled consolidated Edge pools with hardware load balancing</span></span>
  
![Порты и протоколы сети периметра пограничного сервера](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeHLB.jpg)
  

