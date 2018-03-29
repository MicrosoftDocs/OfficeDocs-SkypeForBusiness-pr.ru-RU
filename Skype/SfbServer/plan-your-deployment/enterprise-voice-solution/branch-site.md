---
title: Транкинг SIP для сайта филиала Skype для бизнеса Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Узнайте о распределения каналов SIP на сайтах филиалов в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 92616062c12fce51e3adb816d5ebc299a5dbf3fa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server-2015"></a><span data-ttu-id="3eb61-103">Транкинг SIP для сайта филиала Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="3eb61-103">Branch site SIP trunking in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3eb61-104">Узнайте о распределения каналов SIP на сайтах филиалов в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="3eb61-104">Learn about SIP trunking at branch sites in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="3eb61-105">В некоторых случаях может потребоваться реализовать распределенные SIP-магистрали в выбранных филиалов.</span><span class="sxs-lookup"><span data-stu-id="3eb61-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="3eb61-106">Чтобы определить, является ли SIP магистрали необходима для сайта филиала, а также для получения дополнительных сведений о поддерживаемых вариантов топологии для развертывания магистралях SIP связи сайтов филиалов, см [SIP-магистрали в Скайп для Business Server 2015](sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="3eb61-106">To determine whether a SIP trunk is needed for a branch site, and for details about the supported topology options for deploying SIP trunks in branch sites, see [SIP trunking in Skype for Business Server 2015](sip-trunking.md).</span></span>
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="3eb61-107">Пример анализа требований к магистрали SIP для офиса филиала</span><span class="sxs-lookup"><span data-stu-id="3eb61-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="3eb61-108">Если принято решение развернуть магистраль SIP сайта филиала, которые необходимо выполнить анализ затрат конкретного узла.</span><span class="sxs-lookup"><span data-stu-id="3eb61-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="3eb61-109">К примеру в организации есть центральный сайт в Редмонд, штат Вашингтон и на сайте филиала в Нью-Йорк, следует выполнить анализ, чтобы определить, нужно ли для реализации SIP-магистраль с сайта Нью-Йорка к поставщику локальной службы.</span><span class="sxs-lookup"><span data-stu-id="3eb61-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>
  
<span data-ttu-id="3eb61-110">Чтобы определить, является ли экономически выгодной распределенная магистральная сеть SIP в Нью-Йорке, определите, какие номера для прямого соединения с внутренними абонентами будет использовать магистраль SIP, и проанализируйте число звонков, совершаемых из офиса в Нью-Йорке в области, не включающие Рэдмонд (425).</span><span class="sxs-lookup"><span data-stu-id="3eb61-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="3eb61-111">На центральном сайте может иметь завершение DID для сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="3eb61-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="3eb61-112">Например центрального сайта Redmond может размещаться номеров DID для сайта филиала Нью-Йорка.</span><span class="sxs-lookup"><span data-stu-id="3eb61-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="3eb61-113">Если затраты на внедрение распределенные SIP-магистраль меньше, чем затраты на вызовы, рассмотрите возможность реализации SIP-магистраль на сайте филиала Нью-Йорка.</span><span class="sxs-lookup"><span data-stu-id="3eb61-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span> 
  
## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="3eb61-114">Другие требования к магистрали SIP для офиса филиала</span><span class="sxs-lookup"><span data-stu-id="3eb61-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="3eb61-115">Выбор между развертыванием магистрали SIP вместо шлюза основан на разнице тарифов за междугородные звонки в телефонной сети общего пользования в каждом из вариантов.</span><span class="sxs-lookup"><span data-stu-id="3eb61-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="3eb61-116">Если развернуть магистраль SIP сайта филиала, необходимо также для определения требований к устойчивости и пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="3eb61-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="3eb61-117">Если связь между сайта филиала и центрального сайта устойчивое и имеет достаточные пропускной способности, вы можете развернуть магистраль SIP, либо шлюз.</span><span class="sxs-lookup"><span data-stu-id="3eb61-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="3eb61-118">Необходимо развернуть устройство для обеспечения связи в филиалах на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="3eb61-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="3eb61-119">Если связь между сайта филиала и центральный сайт является нестабильной, развертывание устройство для обеспечения связи в филиалах или развертывание сервера для обеспечения связи в филиалах с шлюза или магистраль SIP на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="3eb61-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span> 
  

