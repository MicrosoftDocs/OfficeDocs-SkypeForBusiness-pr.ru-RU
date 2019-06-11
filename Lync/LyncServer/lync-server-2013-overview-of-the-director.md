---
title: 'Lync Server 2013: обзор директора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e1c36cd556dcf641acb4571b5bb349466eb278d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-director-in-lync-server-2013"></a><span data-ttu-id="3a5d4-102">Обзор директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a5d4-102">Overview of the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a5d4-103">_**Тема последнего изменения:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="3a5d4-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="3a5d4-104">Режиссер — это сервер, на котором работает Lync Server 2013, который проверяет подлинность запросов пользователя, но не предоставляет ни одной учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="3a5d4-104">A Director is a server running Lync Server 2013 that authenticates user requests, but does not home any user accounts.</span></span> <span data-ttu-id="3a5d4-105">Вы также можете развернуть режиссер в следующих двух сценариях:</span><span class="sxs-lookup"><span data-stu-id="3a5d4-105">You optionally can deploy a Director in the following two scenarios:</span></span>

  - <span data-ttu-id="3a5d4-106">Если вы разрешите доступ внешним пользователям, развертывая пограничные серверы, необходимо также развернуть режиссер.</span><span class="sxs-lookup"><span data-stu-id="3a5d4-106">If you enable access by external users by deploying Edge Servers, you should also deploy a Director.</span></span> <span data-ttu-id="3a5d4-107">В этом сценарии режиссер проверяет подлинность внешних пользователей, а затем передает трафик на внутренние серверы.</span><span class="sxs-lookup"><span data-stu-id="3a5d4-107">In this scenario, the Director authenticates the external users, and then passes their traffic on to internal servers.</span></span> <span data-ttu-id="3a5d4-108">Если для проверки подлинности внешних пользователей используется режиссер, он сбрасывает серверы пула переднего плана из-за непроизводительной проверки подлинности этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="3a5d4-108">When a Director is used to authenticate external users, it relieves Front End pool servers from the overhead of performing authentication of these users.</span></span> <span data-ttu-id="3a5d4-109">Кроме того, она позволяет разрушить внутренние пулы интерфейсов из вредоносных сетей, например из-за атак типа "отказ от обслуживания".</span><span class="sxs-lookup"><span data-stu-id="3a5d4-109">It also helps insulate internal Front End pools from malicious traffic such as denial-of-service attacks.</span></span> <span data-ttu-id="3a5d4-110">Если при такой атаке сеть перегружается с недопустимым внешним трафиком, этот трафик завершается на начальнике.</span><span class="sxs-lookup"><span data-stu-id="3a5d4-110">If the network is flooded with invalid external traffic in such an attack, this traffic ends at the Director.</span></span>

  - <span data-ttu-id="3a5d4-111">Если вы разворачиваете несколько пулов переднего плана на центральном сайте, добавив на него директорию, вы сможете упростить запросы на проверку подлинности и повысить производительность.</span><span class="sxs-lookup"><span data-stu-id="3a5d4-111">If you deploy multiple Front End pools at a central site, by adding a Director to that site you can streamline authentication requests and improve performance.</span></span> <span data-ttu-id="3a5d4-112">В этом сценарии все запросы сначала поступают в директорию, а затем пересылает их в нужный пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="3a5d4-112">In this scenario, all requests go first to the Director, which then routes them to the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

