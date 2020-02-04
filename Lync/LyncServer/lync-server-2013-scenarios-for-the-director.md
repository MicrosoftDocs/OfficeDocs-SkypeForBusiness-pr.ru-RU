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
ms.openlocfilehash: ac7c5a262f5323f28ff089766cab1f4d65e30757
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-the-director-in-lync-server-2013"></a><span data-ttu-id="0f9cd-102">Сценарии для директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f9cd-102">Scenarios for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f9cd-103">_**Тема последнего изменения:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="0f9cd-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="0f9cd-104">Режиссер — это сервер, на котором работает программа связи Microsoft Lync Server 2013, которая может проверять подлинность запросов пользователей, но не все учетные записи пользователей.</span><span class="sxs-lookup"><span data-stu-id="0f9cd-104">A Director is a server running Microsoft Lync Server 2013 communications software that can authenticate user requests, but does not home any user accounts.</span></span> <span data-ttu-id="0f9cd-105">В службе Director также размещаются веб-службы, аналогичные интерфейсу сервера переднего плана, и поступают запросы веб-билета и предоставляются другие службы.</span><span class="sxs-lookup"><span data-stu-id="0f9cd-105">The Director also hosts web services similar to the Front End Server and will authenticate web ticket requests and provide other services.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0f9cd-106">Если вы развертываете режиссеров, вы должны опубликовать веб-службы для внешних пользователей, используя обратный прокси и веб-службы внешнего сервера.</span><span class="sxs-lookup"><span data-stu-id="0f9cd-106">If you deploy Directors, you must publish the Director web services externally through the reverse proxy as well as the web services of the Front End Server.</span></span> <span data-ttu-id="0f9cd-107">В следующих разделах описывается процесс планирования для возможных топологий режиссеров.</span><span class="sxs-lookup"><span data-stu-id="0f9cd-107">The topics following describe the planning process for the possible Director topologies.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0f9cd-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="0f9cd-108">In This Section</span></span>

  - [<span data-ttu-id="0f9cd-109">Обзор директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f9cd-109">Overview of the Director in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-director.md)

  - [<span data-ttu-id="0f9cd-110">Компоненты, необходимые для директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f9cd-110">Components required for the Director in Lync Server 2013</span></span>](lync-server-2013-components-required-for-the-director.md)

  - [<span data-ttu-id="0f9cd-111">Требования к оборудованию и программному обеспечению для директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f9cd-111">Hardware and software requirements for the Director in Lync Server 2013</span></span>](lync-server-2013-hardware-and-software-requirements-for-the-director.md)

  - [<span data-ttu-id="0f9cd-112">Единственный директор в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f9cd-112">Single Director in Lync Server 2013</span></span>](lync-server-2013-single-director.md)

  - [<span data-ttu-id="0f9cd-113">Масштабируемый пул директоров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f9cd-113">Scaled Director pool in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0f9cd-114">См. также</span><span class="sxs-lookup"><span data-stu-id="0f9cd-114">See Also</span></span>


[<span data-ttu-id="0f9cd-115">Поддерживаемые топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f9cd-115">Supported topologies in Lync Server 2013</span></span>](lync-server-2013-supported-topologies.md)  
[<span data-ttu-id="0f9cd-116">Аппаратные серверные платформы для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f9cd-116">Server hardware platforms for Lync Server 2013</span></span>](lync-server-2013-server-hardware-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

