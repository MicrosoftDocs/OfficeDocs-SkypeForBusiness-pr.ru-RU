---
title: Director (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02795b46-21ec-4a85-9890-959c91d97df3
description: Режиссер — это сервер, на котором работает программа для связи Skype для бизнеса Server 2015, которая может проверять подлинность запросов пользователей, но не домены каких-либо учетных записей пользователей.
ms.openlocfilehash: 7ce22dadf636d4e7b5e609fc5b3fea9a1891fadd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816478"
---
# <a name="director-planning-tool"></a><span data-ttu-id="1817c-103">Director (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="1817c-103">Director (Planning Tool)</span></span>
 
<span data-ttu-id="1817c-104">Режиссер — это сервер, на котором работает программа для связи Skype для бизнеса Server 2015, которая может проверять подлинность запросов пользователей, но не домены каких-либо учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="1817c-104">A Director is a server running Skype for Business Server 2015 communications software that can authenticate user requests, but does not home any user accounts.</span></span> 
  
<span data-ttu-id="1817c-105">Эта роль необязательная, вы можете выбрать развертывание режиссера в следующих двух сценариях:</span><span class="sxs-lookup"><span data-stu-id="1817c-105">This role is optional, you would choose to deploy a Director in the following two scenarios:</span></span>
  
- <span data-ttu-id="1817c-106">Если вы разрешите доступ внешним пользователям, развертывая пограничные серверы, необходимо также развернуть режиссер.</span><span class="sxs-lookup"><span data-stu-id="1817c-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="1817c-107">В этом сценарии режиссер проверяет подлинность внешних пользователей, а затем передает трафик на внутренние серверы.</span><span class="sxs-lookup"><span data-stu-id="1817c-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="1817c-108">Если для проверки подлинности внешних пользователей используется режиссер, он сбрасывает серверы пула переднего плана из-за непроизводительной проверки подлинности этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="1817c-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="1817c-109">Кроме того, она позволяет разрушить внутренние пулы интерфейсов из вредоносных сетей, например из-за атак типа "отказ от обслуживания".</span><span class="sxs-lookup"><span data-stu-id="1817c-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="1817c-110">Если при такой атаке сеть перегружается с недопустимым внешним трафиком, этот трафик завершается на начальнике.</span><span class="sxs-lookup"><span data-stu-id="1817c-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>
    
- <span data-ttu-id="1817c-111">Если вы разворачиваете несколько пулов переднего плана на центральном сайте, добавив на него директорию, вы сможете упростить запросы на проверку подлинности и повысить производительность.</span><span class="sxs-lookup"><span data-stu-id="1817c-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="1817c-112">В этом сценарии все запросы сначала поступают в директорию, а затем пересылает их в нужный пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="1817c-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>
    

