---
title: 'Lync Server 2013: обзор директора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb187711174785833716b2d14ffe7979cedcbc96
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520826"
---
# <a name="overview-of-the-director-in-lync-server-2013"></a><span data-ttu-id="918a7-102">Обзор директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="918a7-102">Overview of the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="918a7-103">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="918a7-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="918a7-104">Директор — это сервер, на котором работает Lync Server 2013, который выполняет проверку подлинности запросов пользователей, но не предоставляет никаких учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="918a7-104">A Director is a server running Lync Server 2013 that authenticates user requests, but does not home any user accounts.</span></span> <span data-ttu-id="918a7-105">Вы также можете развернуть директор в следующих двух сценариях:</span><span class="sxs-lookup"><span data-stu-id="918a7-105">You optionally can deploy a Director in the following two scenarios:</span></span>

  - <span data-ttu-id="918a7-106">Если вы включаете доступ внешних пользователей, развертывая пограничные серверы, необходимо также развернуть директор.</span><span class="sxs-lookup"><span data-stu-id="918a7-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="918a7-107">В этом сценарии режиссер выполняет проверку подлинности внешних пользователей, а затем передает трафик на внутренние серверы.</span><span class="sxs-lookup"><span data-stu-id="918a7-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="918a7-108">Если для проверки подлинности внешних пользователей используется директор, он освобождает серверы пула переднего плана от дополнительных затрат на проверку подлинности этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="918a7-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="918a7-109">Кроме того, он помогает разделяют внутренние пулы переднего плана от вредоносного трафика, например от атак типа "отказ в обслуживании".</span><span class="sxs-lookup"><span data-stu-id="918a7-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="918a7-110">Если во время такой атаки сеть заполняется неподходящим внешним трафиком, этот трафик останавливается на директоре.</span><span class="sxs-lookup"><span data-stu-id="918a7-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>

  - <span data-ttu-id="918a7-111">Если вы развертываете несколько интерфейсных пулов на центральном сайте, добавив директор на этот сайт, вы сможете упростить запросы проверки подлинности и повысить производительность.</span><span class="sxs-lookup"><span data-stu-id="918a7-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="918a7-112">В этом сценарии все запросы сначала поступают в директоре, а затем — в соответствующий пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="918a7-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

