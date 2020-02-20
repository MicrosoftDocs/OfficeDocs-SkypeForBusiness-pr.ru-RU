---
title: 'Lync Server 2013: технические требования для обхода сервера мультимедиа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for media bypass
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48184321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ad685e59616f7f2a90cc8a9d3feb5f4ea669587
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141815"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a><span data-ttu-id="b9f4a-102">Технические требования для обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9f4a-102">Technical requirements for media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9f4a-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="b9f4a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="b9f4a-104">Для каждого вызова PSTN сервер-посредник определяет, может ли носитель из исходной конечной точки Lync быть отправлен непосредственно на узел сервера-посредника без обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="b9f4a-104">For each call to the PSTN, the Mediation Server determines whether media from the Lync endpoint of origin can be sent directly to a Mediation Server peer without traversing the Mediation Server.</span></span> <span data-ttu-id="b9f4a-105">Узлом партнера может являться шлюз ТСОП, УАТС или пограничный контроллер поставщика услуг интернет-телефонии (ITSP), связанного с магистральной линией между сервером-посредником, где маршрутизируется вызов.</span><span class="sxs-lookup"><span data-stu-id="b9f4a-105">The peer can be a PSTN gateway, IP-PBX, or Session Border Controller (SBC) at an Internet telephony service provider (ITSP) that is associated with the trunk between the Mediation Server where the call is routed.</span></span>

<span data-ttu-id="b9f4a-106">Обход сервера-посредника можно использовать, если удовлетворены следующие требования:</span><span class="sxs-lookup"><span data-stu-id="b9f4a-106">Media bypass can be employed when the following requirements are met:</span></span>

  - <span data-ttu-id="b9f4a-107">Узел сервера-посредника должен поддерживать необходимые возможности для обхода сервера-посредника, наиболее важным является возможность обработки нескольких разветвленных ответов (называемых ранними диалоговыми средствами).</span><span class="sxs-lookup"><span data-stu-id="b9f4a-107">A Mediation Server peer must support the necessary capabilities for media bypass, the most important being the ability to handle multiple forked responses (known as “early dialogs”).</span></span> <span data-ttu-id="b9f4a-108">Обратитесь к производителю шлюза или ITSP, чтобы получить значение максимального количества ранних диалогов, которые могут поддерживать шлюз, PBX или SBC</span><span class="sxs-lookup"><span data-stu-id="b9f4a-108">Contact the manufacturer of your gateway or PBX, or your ITSP, to obtain the value for the maximum number of early dialogs that the gateway, PBX, or SBC can accept.</span></span>

  - <span data-ttu-id="b9f4a-109">Узел сервера-посредника должен принимать трафик мультимедиа непосредственно из конечных точек Lync.</span><span class="sxs-lookup"><span data-stu-id="b9f4a-109">The Mediation Server peer must accept media traffic directly from Lync endpoints.</span></span> <span data-ttu-id="b9f4a-110">Многие Итспс позволяют их SBC получать трафик только от сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="b9f4a-110">Many ITSPs allow their SBC to receive traffic only from the Mediation Server.</span></span> <span data-ttu-id="b9f4a-111">Обратитесь к ITSP, чтобы определить, принимает ли его SBC трафик мультимедиа непосредственно из конечных точек Lync.</span><span class="sxs-lookup"><span data-stu-id="b9f4a-111">Contact your ITSP to determine whether its SBC accepts media traffic directly from Lync endpoints.</span></span>

  - <span data-ttu-id="b9f4a-112">Клиенты Lync и одноранговые серверы-посредники должны быть хорошо подключены, то есть они размещаются в одном регионе сети или на сетевых сайтах, подключающихся к регионам по каналам глобальной сети, не имеющим ограничений пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="b9f4a-112">Lync clients and a Mediation Server peer must be well connected, meaning that they are either located in the same network region or at network sites that connect to the region over WAN links that have no bandwidth constraints</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b9f4a-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b9f4a-113">See Also</span></span>


[<span data-ttu-id="b9f4a-114">Режимы обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9f4a-114">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="b9f4a-115">Обход сервера мультимедиа и контроль допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9f4a-115">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

