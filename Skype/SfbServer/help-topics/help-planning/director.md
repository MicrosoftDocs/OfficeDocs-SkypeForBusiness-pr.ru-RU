---
title: Директор (средство планирования)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/8/2016
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Директор является сервере под управлением Скайп для программного обеспечения communications Business Server 2015, который может выполнять проверку подлинности запросов пользователей, но не номер домашнего все учетные записи пользователей.
ms.openlocfilehash: b379388b05e4beda934b13517f36bc792b6f0748
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="director-planning-tool"></a><span data-ttu-id="56ebb-103">Директор (средство планирования)</span><span class="sxs-lookup"><span data-stu-id="56ebb-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="56ebb-104">Директор является сервере под управлением Скайп для программного обеспечения communications Business Server 2015, который может выполнять проверку подлинности запросов пользователей, но не номер домашнего все учетные записи пользователей.</span><span class="sxs-lookup"><span data-stu-id="56ebb-104">A Director is a server running Skype for Business Server 2015 communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="56ebb-105">Эта роль является необязательным, нужно развернуть директора в следующие два сценария:</span><span class="sxs-lookup"><span data-stu-id="56ebb-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="56ebb-106">При включении доступа внешних пользователей, развертывание пограничных серверов, следует развертывать директор.</span><span class="sxs-lookup"><span data-stu-id="56ebb-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="56ebb-107">В этом сценарии директора метода проверки подлинности внешних пользователей и передает их трафика на внутренних серверов.</span><span class="sxs-lookup"><span data-stu-id="56ebb-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="56ebb-108">Когда директор используется для проверки подлинности внешних пользователей, уменьшает пул серверов переднего плана из затрат на выполнение проверки подлинности этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="56ebb-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="56ebb-109">Он также помогает изолировать внутренних пулов переднего плана от вредоносного трафика, такие как атак типа "отказ в обслуживании".</span><span class="sxs-lookup"><span data-stu-id="56ebb-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="56ebb-110">Если распространяются с недопустимый внешнего трафика в такой атаки сетевой трафик заканчивается на директора.</span><span class="sxs-lookup"><span data-stu-id="56ebb-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="56ebb-111">При развертывании нескольких пулов переднего плана в центральном узле, то путем добавления директор на этот сайт можно оптимизировать запросы проверки подлинности и повысить производительность.</span><span class="sxs-lookup"><span data-stu-id="56ebb-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="56ebb-112">В этом сценарии все запросы перейдите первого директора, который затем направляет их правильный пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="56ebb-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

