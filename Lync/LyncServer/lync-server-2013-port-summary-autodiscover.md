---
title: 'Lync Server 2013: сводка по портам — автообнаружение'
description: 'Lync Server 2013: сводка по портам — обнаружение службы обнаружения.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Autodiscover
ms:assetid: 8bd16363-5e18-4e4b-be99-b3e6457b4c99
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945642(v=OCS.15)
ms:contentKeyID: 51541497
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20a5ef54d4ad8419fd6e73909f97764bf1290c22
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543145"
---
# <a name="port-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="8c22c-103">Сводка по портам — автообнаружение в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c22c-103">Port summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c22c-104">_**Последнее изменение темы:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="8c22c-104">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="8c22c-105">Служба автообнаружения Lync Server 2013 выполняется на серверах директоров и интерфейсных серверах пула, а также при публикации в DNS с `lyncdiscover.<domain>` помощью `lyncdiscoverinternal.<domain>` записей узла и может использоваться клиентами для обнаружения компонентов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8c22c-105">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS using the `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` host records, can be used by clients to locate Lync Server features.</span></span> <span data-ttu-id="8c22c-106">Чтобы мобильные устройства, работающие с Lync Mobile, могли использовать службу автообнаружения, сначала необходимо изменить списки альтернативных имен субъектов сертификатов на любом директоре и сервере переднего плана, на котором запущена служба автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="8c22c-106">In order for mobile devices running Lync Mobile to use Autodiscover, you may first need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="8c22c-107">Кроме того, может потребоваться изменить списки альтернативных имен субъектов для сертификатов, используемых для правил публикации внешних веб-служб на обратных прокси-серверах.</span><span class="sxs-lookup"><span data-stu-id="8c22c-107">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="8c22c-108">Решение о том, следует ли использовать списки альтернативных имен субъектов для обратных прокси-серверов, зависит от того, публикуется ли служба автообнаружения на порте 80 или на порте 443:</span><span class="sxs-lookup"><span data-stu-id="8c22c-108">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="8c22c-109">**Опубликовано на порте 80**     Для мобильных устройств не требуется изменять сертификаты, если исходный запрос к службе автообнаружения проходит через порт 80.</span><span class="sxs-lookup"><span data-stu-id="8c22c-109">**Published on port 80**   For Mobile devices, no certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="8c22c-110">Это связано с тем, что мобильные устройства, работающие с Lync, обращаются к обратному прокси-серверу через порт 80 извне, а затем перенаправляются на директор или сервер переднего плана через внутренний порт 8080.</span><span class="sxs-lookup"><span data-stu-id="8c22c-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span>

  - <span data-ttu-id="8c22c-111">**Опубликовано на порте 443**     Список альтернативных имен субъектов в сертификатах, используемых правилом публикации внешних веб-служб, должен содержать `lyncdiscover.<sipdomain>` запись для каждого домена SIP в Организации.</span><span class="sxs-lookup"><span data-stu-id="8c22c-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a `lyncdiscover.<sipdomain>` entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8c22c-112">Для новых установок или обновлений с Lync Server 2010, где вы развернули мобильность, вы использовали порт 80 для автообнаружения службы Mobility Service или повторно выдавали сертификаты с правильным именем субъекта и альтернативным именем субъекта на месте.</span><span class="sxs-lookup"><span data-stu-id="8c22c-112">For new installations or upgrades from Lync Server 2010 where you deployed Mobility, you either used Port 80 for Autodiscover of the Mobility service, or reissued certificates with the proper subject name and subject alternative names in place.</span></span> <span data-ttu-id="8c22c-113">Просмотрите сертификаты на вашем директоре и сервере переднего плана, чтобы убедиться в том, какой путь выбран.</span><span class="sxs-lookup"><span data-stu-id="8c22c-113">Review the certificates on your Director and Front End Server to confirm which path you chose.</span></span>

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="8c22c-114">Подробные сведения о настройках брандмауэра для обратного прокси-сервера: внешний интерфейс</span><span class="sxs-lookup"><span data-stu-id="8c22c-114">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c22c-115">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="8c22c-115">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8c22c-116">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="8c22c-116">Source IP Address</span></span></th>
<th><span data-ttu-id="8c22c-117">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="8c22c-117">Destination IP Address</span></span></th>
<th><span data-ttu-id="8c22c-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="8c22c-118">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c22c-119">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="8c22c-119">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="8c22c-120">Любой</span><span class="sxs-lookup"><span data-stu-id="8c22c-120">Any</span></span></p></td>
<td><p><span data-ttu-id="8c22c-121">Слушатель обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="8c22c-121">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="8c22c-122">Необязательно Перенаправление на HTTPS, если пользователь вводит http:// &lt; публишедситефкдн &gt; .</span><span class="sxs-lookup"><span data-stu-id="8c22c-122">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span> <span data-ttu-id="8c22c-123">Кроме того, необходимо использовать Office Web Apps для конференций и службу автообнаружения для мобильных устройств, работающих с Lync, в ситуациях, когда организациям не требуется изменять сертификат правила публикации внешних веб-служб.</span><span class="sxs-lookup"><span data-stu-id="8c22c-123">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c22c-124">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8c22c-124">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8c22c-125">Любой</span><span class="sxs-lookup"><span data-stu-id="8c22c-125">Any</span></span></p></td>
<td><p><span data-ttu-id="8c22c-126">Слушатель обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="8c22c-126">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="8c22c-127">Загрузка адресной книги, служба веб-запросов к адресной книге, автообнаружение, обновление клиентов, содержимое собраний, обновления устройств, развертывание групп, Office Web Apps для конференций, Конференц-связь с телефонным подключением и собрания.</span><span class="sxs-lookup"><span data-stu-id="8c22c-127">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="8c22c-128">Подробные сведения о настройках брандмауэра для обратного прокси-сервера: внутренний интерфейс</span><span class="sxs-lookup"><span data-stu-id="8c22c-128">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c22c-129">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="8c22c-129">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8c22c-130">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="8c22c-130">Source IP Address</span></span></th>
<th><span data-ttu-id="8c22c-131">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="8c22c-131">Destination IP Address</span></span></th>
<th><span data-ttu-id="8c22c-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="8c22c-132">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c22c-133">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="8c22c-133">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="8c22c-134">Внутренний интерфейс обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="8c22c-134">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="8c22c-135">Сервер переднего плана, интерфейсный пул, директор, пул директоров, Office Web Apps для конференц-связи</span><span class="sxs-lookup"><span data-stu-id="8c22c-135">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="8c22c-136">Требуется при использовании службы автообнаружения для мобильных устройств, работающих с Lync, в ситуациях, когда Организация не хочет изменить сертификат правила публикации внешних веб-служб.</span><span class="sxs-lookup"><span data-stu-id="8c22c-136">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span> <span data-ttu-id="8c22c-137">Трафик, отправляемый на порт 80 внешнего интерфейса обратного прокси-сервера, перенаправляется в пул на порте 8080 из внутреннего интерфейса обратного прокси-сервера, чтобы веб-службы пула могли отличить его от внутреннего веб-трафика.</span><span class="sxs-lookup"><span data-stu-id="8c22c-137">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c22c-138">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="8c22c-138">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="8c22c-139">Внутренний интерфейс обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="8c22c-139">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="8c22c-140">Сервер переднего плана, интерфейсный пул, директор, пул директоров, Office Web Apps для конференц-связи</span><span class="sxs-lookup"><span data-stu-id="8c22c-140">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="8c22c-141">Трафик, отправляемый на порт 443 внешнего интерфейса обратного прокси-сервера, перенаправляется в пул на порте 4443 из внутреннего интерфейса обратного прокси-сервера, чтобы веб-службы пула могли отличить его от внутреннего веб-трафика.</span><span class="sxs-lookup"><span data-stu-id="8c22c-141">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

