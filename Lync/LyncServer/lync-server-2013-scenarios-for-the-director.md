---
title: 'Lync Server 2013: сценарии для директора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for the Director
ms:assetid: d2cf384a-0860-4779-80ce-cba2543be322
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398908(v=OCS.15)
ms:contentKeyID: 48185419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00e2b91607a89756b42586c060b5950675994201
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510826"
---
# <a name="scenarios-for-the-director-in-lync-server-2013"></a><span data-ttu-id="c9712-102">Сценарии для директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9712-102">Scenarios for the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9712-103">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="c9712-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="c9712-104">Директор — это сервер, на котором работает программа связи Microsoft Lync Server 2013, который может выполнять проверку подлинности запросов пользователей, но не может работать с другими учетными записями пользователей.</span><span class="sxs-lookup"><span data-stu-id="c9712-104">A Director is a server running Microsoft Lync Server 2013 communications software that can authenticate user requests, but does not home any user accounts.</span></span> <span data-ttu-id="c9712-105">В директоре также размещаются веб-службы, похожие на сервер переднего плана и подлинность запросов веб-билетов, а также другие службы.</span><span class="sxs-lookup"><span data-stu-id="c9712-105">The Director also hosts web services similar to the Front End Server and will authenticate web ticket requests and provide other services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c9712-106">При развертывании режиссеров необходимо опубликовать веб-службы Director извне через обратный прокси-сервер, а также веб-службы сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="c9712-106">If you deploy Directors, you must publish the Director web services externally through the reverse proxy as well as the web services of the Front End Server.</span></span> <span data-ttu-id="c9712-107">В следующих разделах описывается процесс планирования для возможных топологий директоров.</span><span class="sxs-lookup"><span data-stu-id="c9712-107">The topics following describe the planning process for the possible Director topologies.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c9712-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="c9712-108">In This Section</span></span>

  - [<span data-ttu-id="c9712-109">Обзор директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9712-109">Overview of the Director in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-director.md)

  - [<span data-ttu-id="c9712-110">Компоненты, необходимые для директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9712-110">Components required for the Director in Lync Server 2013</span></span>](lync-server-2013-components-required-for-the-director.md)

  - [<span data-ttu-id="c9712-111">Требования к оборудованию и программному обеспечению для директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9712-111">Hardware and software requirements for the Director in Lync Server 2013</span></span>](lync-server-2013-hardware-and-software-requirements-for-the-director.md)

  - [<span data-ttu-id="c9712-112">Один директор в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9712-112">Single Director in Lync Server 2013</span></span>](lync-server-2013-single-director.md)

  - [<span data-ttu-id="c9712-113">Масштабируемый пул директоров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9712-113">Scaled Director pool in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c9712-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c9712-114">See Also</span></span>


[<span data-ttu-id="c9712-115">Поддерживаемые топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9712-115">Supported topologies in Lync Server 2013</span></span>](lync-server-2013-supported-topologies.md)  
[<span data-ttu-id="c9712-116">Аппаратные серверные платформы для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9712-116">Server hardware platforms for Lync Server 2013</span></span>](lync-server-2013-server-hardware-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

