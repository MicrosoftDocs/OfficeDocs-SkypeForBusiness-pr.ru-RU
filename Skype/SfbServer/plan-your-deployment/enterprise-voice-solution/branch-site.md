---
title: Магистральные магистрали SIP сайтов филиалов в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Узнайте о том, как звонить по протоколу SIP на сайтах филиалов в корпоративной голосовой связи в Skype для бизнеса Server.
ms.openlocfilehash: 158c1cff28ba0c21f5c995a1fe5b7dfdf2f9f150
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803259"
---
# <a name="branch-site-sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="b4cea-103">Магистральные магистрали SIP сайтов филиалов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b4cea-103">Branch site SIP trunking in Skype for Business Server</span></span>
 
<span data-ttu-id="b4cea-104">Узнайте о том, как звонить по протоколу SIP на сайтах филиалов в корпоративной голосовой связи в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="b4cea-104">Learn about SIP trunking at branch sites in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="b4cea-105">В некоторых случаях может потребоваться реализация распределенной магистрали SIP на выбранных сайтах филиалов.</span><span class="sxs-lookup"><span data-stu-id="b4cea-105">In some cases, you may need to implement distributed SIP trunking at selected branch sites.</span></span> <span data-ttu-id="b4cea-106">Чтобы определить, нужна ли магистральная линия SIP для сайта филиала, а также подробные сведения о поддерживаемых параметрах топологии для развертывания магистральных каналов SIP на сайтах филиалов, ознакомьтесь со статьей [магистральные линии SIP в Skype для бизнеса Server](sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="b4cea-106">To determine whether a SIP trunk is needed for a branch site, and for details about the supported topology options for deploying SIP trunks in branch sites, see [SIP trunking in Skype for Business Server](sip-trunking.md).</span></span>
  
## <a name="example-branch-site-sip-trunk-requirements-analysis"></a><span data-ttu-id="b4cea-107">Пример анализа требований к магистрали SIP для офиса филиала</span><span class="sxs-lookup"><span data-stu-id="b4cea-107">Example Branch Site SIP Trunk Requirements Analysis</span></span>

<span data-ttu-id="b4cea-108">При развертывании канала SIP на сайте филиала необходимо выполнить анализ затрат для определенного сайта.</span><span class="sxs-lookup"><span data-stu-id="b4cea-108">When you decide to deploy a branch site SIP trunk, you need to perform a site-specific cost analysis.</span></span> <span data-ttu-id="b4cea-109">Например, если в Нью-Йорке есть сайт, на котором установлен центральный сайт Redmond, Washington и филиал, необходимо выполнить анализ, чтобы определить, следует ли реализовать магистраль SIP из сайта Нью-Йорке для доступа к локальному поставщику услуг.</span><span class="sxs-lookup"><span data-stu-id="b4cea-109">For example, an enterprise that has a central site in Redmond, Washington, and a branch site in New York, should do an analysis to determine whether to implement a SIP trunk from the New York site to a local service provider.</span></span>
  
<span data-ttu-id="b4cea-110">Чтобы определить, является ли экономически выгодной распределенная магистральная сеть SIP в Нью-Йорке, определите, какие номера для прямого соединения с внутренними абонентами будет использовать магистраль SIP, и проанализируйте число звонков, совершаемых из офиса в Нью-Йорке в области, не включающие Рэдмонд (425).</span><span class="sxs-lookup"><span data-stu-id="b4cea-110">To determine whether a distributed SIP trunk in New York is cost-effective, identify which Direct Inward Dialing (DID) numbers will use the SIP trunk, and analyze the number of calls New York makes to areas other than Redmond (425).</span></span> <span data-ttu-id="b4cea-111">Вы можете присвоить прерывание для сайта филиала на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="b4cea-111">You can have DID termination for the branch site at the central site.</span></span> <span data-ttu-id="b4cea-112">Например, центр Redmond может размещать номера для сайта филиала Нью-Йорке.</span><span class="sxs-lookup"><span data-stu-id="b4cea-112">For example, the Redmond central site can host DID numbers for the New York branch site.</span></span> <span data-ttu-id="b4cea-113">Если стоимость реализации распределенной магистральной магистрали SIP меньше, чем стоимость этих звонков, рекомендуется реализовать магистраль SIP на сайте Нью-Йорка.</span><span class="sxs-lookup"><span data-stu-id="b4cea-113">If the cost of implementing a distributed SIP trunk is less than the cost of those calls, consider implementing a SIP trunk at the New York branch site.</span></span> 
  
## <a name="other-branch-site-sip-trunk-requirements"></a><span data-ttu-id="b4cea-114">Другие требования к магистрали SIP для офиса филиала</span><span class="sxs-lookup"><span data-stu-id="b4cea-114">Other Branch Site SIP Trunk Requirements</span></span>

<span data-ttu-id="b4cea-115">Выбор между развертыванием магистрали SIP вместо шлюза основан на разнице тарифов за междугородные звонки в телефонной сети общего пользования в каждом из вариантов.</span><span class="sxs-lookup"><span data-stu-id="b4cea-115">The choice between a deploying a SIP trunk instead of a gateway is based on the difference between the public switched telephone network (PSTN) long distance toll charges of each option.</span></span> <span data-ttu-id="b4cea-116">При развертывании канала SIP на сайте филиала необходимо также определить требования к устойчивости и пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="b4cea-116">If you deploy a branch site SIP trunk, you also need to determine your resiliency and bandwidth requirements.</span></span> <span data-ttu-id="b4cea-117">Если связь между сайтом филиала и центральным сайтом является устойчивой и достаточным объемом пропускной способности, вы можете развернуть магистраль SIP или шлюз.</span><span class="sxs-lookup"><span data-stu-id="b4cea-117">If the link between your branch site and central site is resilient and has sufficient bandwidth, you can deploy a SIP trunk or a gateway.</span></span> <span data-ttu-id="b4cea-118">Вам не нужно развертывать бесперебойно работающее устройство филиала на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="b4cea-118">You do not need to deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="b4cea-119">Если связь между сайтом ветви и центральным сайтом не является устойчивой, разверните бесперебойно работающее устройство филиала или разверните отказоустойчивый сервер филиала с шлюзом или магистральом SIP на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="b4cea-119">If the link between your branch site and central site is not resilient, deploy a Survivable Branch Appliance, or deploy a Survivable Branch Server with either a gateway or SIP trunk at the branch site.</span></span> 
  

