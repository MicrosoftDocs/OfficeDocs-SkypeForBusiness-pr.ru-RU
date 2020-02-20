---
title: 'Lync Server 2013: сводка по портам — автообнаружение'
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
ms.openlocfilehash: 635f8fca3b267fa2366b66b990ec0621f58f58e4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152667"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="3b822-102">Сводка по портам — автообнаружение в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b822-102">Port summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b822-103">_**Последнее изменение темы:** 2013-03-05_</span><span class="sxs-lookup"><span data-stu-id="3b822-103">_**Topic Last Modified:** 2013-03-05_</span></span>

<span data-ttu-id="3b822-104">Служба автообнаружения Lync Server 2013 выполняется на серверах директоров и интерфейсных серверах пула, а также при публикации в DNS с `lyncdiscover.<domain>` помощью `lyncdiscoverinternal.<domain>` записей узла и может использоваться клиентами для обнаружения компонентов Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3b822-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS using the `lyncdiscover.<domain>` and `lyncdiscoverinternal.<domain>` host records, can be used by clients to locate Lync Server features.</span></span> <span data-ttu-id="3b822-105">Чтобы мобильные устройства, работающие с Lync Mobile, могли использовать службу автообнаружения, сначала необходимо изменить списки альтернативных имен субъектов сертификатов на любом директоре и сервере переднего плана, на котором запущена служба автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="3b822-105">In order for mobile devices running Lync Mobile to use Autodiscover, you may first need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="3b822-106">Кроме того, может потребоваться изменить списки альтернативных имен субъектов для сертификатов, используемых для правил публикации внешних веб-служб на обратных прокси-серверах.</span><span class="sxs-lookup"><span data-stu-id="3b822-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="3b822-107">Решение о том, следует ли использовать списки альтернативных имен субъектов для обратных прокси-серверов, зависит от того, публикуется ли служба автообнаружения на порте 80 или на порте 443:</span><span class="sxs-lookup"><span data-stu-id="3b822-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="3b822-108">**При публикации на порте 80**   для мобильных устройств не требуется никаких изменений сертификата, если исходный запрос к службе автообнаружения проходит через порт 80.</span><span class="sxs-lookup"><span data-stu-id="3b822-108">**Published on port 80**   For Mobile devices, no certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="3b822-109">Это связано с тем, что мобильные устройства, работающие с Lync, обращаются к обратному прокси-серверу через порт 80 извне, а затем перенаправляются на директор или сервер переднего плана через внутренний порт 8080.</span><span class="sxs-lookup"><span data-stu-id="3b822-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span>

  - <span data-ttu-id="3b822-110">**Опубликовано на порте 443**   список альтернативных имен субъектов в сертификатах, используемых правилом публикации внешних веб-служб `lyncdiscover.<sipdomain>` , должен содержать запись для каждого домена SIP в Организации.</span><span class="sxs-lookup"><span data-stu-id="3b822-110">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a `lyncdiscover.<sipdomain>` entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3b822-111">Для новых установок или обновлений с Lync Server 2010, где вы развернули мобильность, вы использовали порт 80 для автообнаружения службы Mobility Service или повторно выдавали сертификаты с правильным именем субъекта и альтернативным именем субъекта на месте.</span><span class="sxs-lookup"><span data-stu-id="3b822-111">For new installations or upgrades from Lync Server 2010 where you deployed Mobility, you either used Port 80 for Autodiscover of the Mobility service, or reissued certificates with the proper subject name and subject alternative names in place.</span></span> <span data-ttu-id="3b822-112">Просмотрите сертификаты на вашем директоре и сервере переднего плана, чтобы убедиться в том, какой путь выбран.</span><span class="sxs-lookup"><span data-stu-id="3b822-112">Review the certificates on your Director and Front End Server to confirm which path you chose.</span></span>

    
    </div>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="3b822-113">Подробные сведения о настройках брандмауэра для обратного прокси-сервера: внешний интерфейс</span><span class="sxs-lookup"><span data-stu-id="3b822-113">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b822-114">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="3b822-114">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3b822-115">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="3b822-115">Source IP Address</span></span></th>
<th><span data-ttu-id="3b822-116">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="3b822-116">Destination IP Address</span></span></th>
<th><span data-ttu-id="3b822-117">Notes</span><span class="sxs-lookup"><span data-stu-id="3b822-117">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b822-118">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="3b822-118">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="3b822-119">Любые</span><span class="sxs-lookup"><span data-stu-id="3b822-119">Any</span></span></p></td>
<td><p><span data-ttu-id="3b822-120">Слушатель обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="3b822-120">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="3b822-121">Необязательно Перенаправление на HTTPS, если пользователь вводит http://&lt;публишедситефкдн&gt;.</span><span class="sxs-lookup"><span data-stu-id="3b822-121">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span> <span data-ttu-id="3b822-122">Кроме того, необходимо использовать Office Web Apps для конференций и службу автообнаружения для мобильных устройств, работающих с Lync, в ситуациях, когда организациям не требуется изменять сертификат правила публикации внешних веб-служб.</span><span class="sxs-lookup"><span data-stu-id="3b822-122">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b822-123">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3b822-123">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3b822-124">Любые</span><span class="sxs-lookup"><span data-stu-id="3b822-124">Any</span></span></p></td>
<td><p><span data-ttu-id="3b822-125">Слушатель обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="3b822-125">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="3b822-126">Загрузка адресной книги, служба веб-запросов к адресной книге, автообнаружение, обновление клиентов, содержимое собраний, обновления устройств, развертывание групп, Office Web Apps для конференций, Конференц-связь с телефонным подключением и собрания.</span><span class="sxs-lookup"><span data-stu-id="3b822-126">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="3b822-127">Подробные сведения о настройках брандмауэра для обратного прокси-сервера: внутренний интерфейс</span><span class="sxs-lookup"><span data-stu-id="3b822-127">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b822-128">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="3b822-128">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3b822-129">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="3b822-129">Source IP Address</span></span></th>
<th><span data-ttu-id="3b822-130">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="3b822-130">Destination IP Address</span></span></th>
<th><span data-ttu-id="3b822-131">Notes</span><span class="sxs-lookup"><span data-stu-id="3b822-131">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b822-132">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="3b822-132">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="3b822-133">Внутренний интерфейс обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="3b822-133">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="3b822-134">Сервер переднего плана, интерфейсный пул, директор, пул директоров, Office Web Apps для конференц-связи</span><span class="sxs-lookup"><span data-stu-id="3b822-134">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="3b822-135">Требуется при использовании службы автообнаружения для мобильных устройств, работающих с Lync, в ситуациях, когда Организация не хочет изменить сертификат правила публикации внешних веб-служб.</span><span class="sxs-lookup"><span data-stu-id="3b822-135">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span> <span data-ttu-id="3b822-136">Трафик, отправляемый на порт 80 внешнего интерфейса обратного прокси-сервера, перенаправляется в пул на порте 8080 из внутреннего интерфейса обратного прокси-сервера, чтобы веб-службы пула могли отличить его от внутреннего веб-трафика.</span><span class="sxs-lookup"><span data-stu-id="3b822-136">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b822-137">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="3b822-137">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="3b822-138">Внутренний интерфейс обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="3b822-138">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="3b822-139">Сервер переднего плана, интерфейсный пул, директор, пул директоров, Office Web Apps для конференц-связи</span><span class="sxs-lookup"><span data-stu-id="3b822-139">Front End Server, Front End pool, Director, Director pool, Office Web Apps for conferencing</span></span></p></td>
<td><p><span data-ttu-id="3b822-140">Трафик, отправляемый на порт 443 внешнего интерфейса обратного прокси-сервера, перенаправляется в пул на порте 4443 из внутреннего интерфейса обратного прокси-сервера, чтобы веб-службы пула могли отличить его от внутреннего веб-трафика.</span><span class="sxs-lookup"><span data-stu-id="3b822-140">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

