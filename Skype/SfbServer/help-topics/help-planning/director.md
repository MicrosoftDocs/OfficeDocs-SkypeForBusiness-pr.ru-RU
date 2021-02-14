---
title: Директор (средство планирования)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.Director
- ms.lync.plan.Director
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Директор — это сервер с программным обеспечением для связи Skype для бизнеса Server 2015, который может проверить подлинность запросов пользователей, но не может использовать учетные записи пользователей.
ms.openlocfilehash: 9809a6293c212a52dd87476069125540848ee2a2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810549"
---
# <a name="director-planning-tool"></a><span data-ttu-id="fedde-103">Директор (средство планирования)</span><span class="sxs-lookup"><span data-stu-id="fedde-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="fedde-104">Директор — это сервер с программным обеспечением для связи Skype для бизнеса Server 2015, который может проверить подлинность запросов пользователей, но не может использовать учетные записи пользователей.</span><span class="sxs-lookup"><span data-stu-id="fedde-104">A Director is a server running Skype for Business Server 2015 communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="fedde-105">Эта роль необязательна. Развертывание директора возможно в следующих двух сценариях:</span><span class="sxs-lookup"><span data-stu-id="fedde-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="fedde-106">Если доступ внешних пользователей включается путем развертывания серверов, необходимо также развернуть директора.</span><span class="sxs-lookup"><span data-stu-id="fedde-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="fedde-107">В этом сценарии Директор проходит проверку подлинности внешних пользователей, а затем передает трафик на внутренние серверы.</span><span class="sxs-lookup"><span data-stu-id="fedde-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="fedde-108">Когда директор используется для проверки подлинности внешних пользователей, он освобождает серверы пула переднего сервера от расходов на проверку подлинности этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="fedde-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="fedde-109">Это также помогает изолировать внутренние пулы переднего входа от вредоносного трафика, такого как атаки типа "отказ в обслуживании".</span><span class="sxs-lookup"><span data-stu-id="fedde-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="fedde-110">Если во время такой атаки сеть заполняется неподходящим внешним трафиком, этот трафик останавливается на директоре.</span><span class="sxs-lookup"><span data-stu-id="fedde-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="fedde-111">При развертывании нескольких пулов переднего уровня на центральном сайте путем добавления директора на этот сайт можно оптимизировать запросы проверки подлинности и повысить производительность.</span><span class="sxs-lookup"><span data-stu-id="fedde-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="fedde-112">В этом сценарии все запросы сначала перенаправлять в каталог, а затем перенаправлять их в правильный пул переднего входа.</span><span class="sxs-lookup"><span data-stu-id="fedde-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

