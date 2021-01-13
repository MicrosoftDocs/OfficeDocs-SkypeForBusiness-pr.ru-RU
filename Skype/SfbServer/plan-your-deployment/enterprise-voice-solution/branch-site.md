---
title: Транкинг SIP сайта филиала в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4d9dfcd-8baa-41ea-9677-48b0e429429d
description: Узнайте о магистрали SIP на сайтах филиалов в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: f8b875fca8adc1ac78c0b24cf3e53fab2ec2cd89
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813719"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="8492b-103">Транкинг SIP сайта филиала в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="8492b-103">Branch site SIP trunking in Skype for Business Server</span></span>
 
<span data-ttu-id="8492b-104">Узнайте о магистрали SIP на сайтах филиалов в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="8492b-104">Learn about SIP trunking at branch sites in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="8492b-105">В некоторых случаях может потребоваться реализовать распределенную магистраль SIP на выбранных сайтах филиалов.</span><span class="sxs-lookup"><span data-stu-id="8492b-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="8492b-106">Сведения о том, требуется ли магистраль SIP для сайта филиала, а также сведения о поддерживаемых вариантах топологии для развертывания магистрали SIP на сайтах филиалов см. в [SIP-магистрали в Skype для бизнеса Server.](sip-trunking.md)</span><span class="sxs-lookup"><span data-stu-id="8492b-106">To determine whether a SIP trunk is needed for a branch site, and for details about the supported topology options for deploying SIP trunks in branch sites, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="8492b-107">Пример анализа требований к магистрали SIP для офиса филиала</span><span class="sxs-lookup"><span data-stu-id="8492b-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="8492b-108">При развертывании магистрали SIP сайта филиала необходимо выполнить анализ затрат для конкретного сайта.</span><span class="sxs-lookup"><span data-stu-id="8492b-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="8492b-109">Например, предприятие с центральным сайтом в Редмонде,Вашингтон и сайтом филиала в Нью-Йорке должно выполнить анализ, чтобы определить, следует ли реализовать магистраль SIP от сайта Нью-Йорка к локальному поставщику услуг.</span><span class="sxs-lookup"><span data-stu-id="8492b-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>
  
<span data-ttu-id="8492b-110">Чтобы определить, является ли экономически выгодной распределенная магистраль SIP в Нью-Йорке, определите, какие номера для прямого соединения с внутренними абонентами будет использовать магистраль SIP, и проанализируйте число звонков, совершаемых из офиса в Нью-Йорке в области, не включающие Рэдмонд (425).</span><span class="sxs-lookup"><span data-stu-id="8492b-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="8492b-111">Можно использовать завершение DID для сайта филиала на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="8492b-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="8492b-112">Например, центральный сайт Редмонда может принимать номера DID для сайта филиала в Нью-Йорке.</span><span class="sxs-lookup"><span data-stu-id="8492b-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="8492b-113">Если затраты на реализацию распределенной магистрали SIP меньше, чем затраты на эти вызовы, рассмотрите возможность реализации магистрали SIP на сайте филиала в Нью-Йорке.</span><span class="sxs-lookup"><span data-stu-id="8492b-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span> 
  
## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="8492b-114">Другие требования к магистрали SIP для офиса филиала</span><span class="sxs-lookup"><span data-stu-id="8492b-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="8492b-115">Выбор между развертыванием магистрали SIP вместо шлюза основан на разнице тарифов за междугородные звонки в телефонной сети общего пользования в каждом из вариантов.</span><span class="sxs-lookup"><span data-stu-id="8492b-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="8492b-116">При развертывании магистрали SIP сайта филиала также необходимо определить требования к устойчивости и пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="8492b-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="8492b-117">Если связь между сайтом филиала и центральным сайтом является устойчивой и имеет достаточную пропускную способность, можно развернуть магистраль SIP или шлюз.</span><span class="sxs-lookup"><span data-stu-id="8492b-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="8492b-118">Развертывание устройства для survivable Branch Appliance на сайте филиала не требуется.</span><span class="sxs-lookup"><span data-stu-id="8492b-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="8492b-119">Если связь между сайтом филиала и центральным сайтом не является устойчивой, разверните устройство для связи в филиалах или разверните сервер для связи в филиалах со шлюзом или магистралью SIP на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="8492b-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span> 
  

