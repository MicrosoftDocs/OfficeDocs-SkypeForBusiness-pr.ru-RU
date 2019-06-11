---
title: 'Lync Server 2013: сводка по портам — обратный прокси-сервер'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a86b993a35210934f5ebef61464c11a153bf297
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="a816f-102">Сводка по портам — обратный прокси-сервер в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a816f-102">Port summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a816f-103">_**Тема последнего изменения:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="a816f-103">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="a816f-104">У обратного прокси-сервера минимальны требования к брандмауэру и протоколу или порту.</span><span class="sxs-lookup"><span data-stu-id="a816f-104">The reverse proxy has minimal requirements for firewall and port/protocol.</span></span>

  - <span data-ttu-id="a816f-105">Для подключения к внешним брандмауэрам используются протокол HTTPS/TCP/443 и дополнительный HTTP/TCP/80.</span><span class="sxs-lookup"><span data-stu-id="a816f-105">External firewall requirements are the HTTPS/TCP/443 and the optional HTTP/TCP/80.</span></span> <span data-ttu-id="a816f-106">Протокол HTTPS используется для безопасной связи по протоколу SSL и TLS через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="a816f-106">HTTPS is used for SSL and TLS secure communications through the reverse proxy.</span></span> <span data-ttu-id="a816f-107">HTTP используется в том случае, если вы решите разрешить доступ к службе автообнаружения при изменении сертификатов, и это может быть затруднительно или не выравниваются за счет.</span><span class="sxs-lookup"><span data-stu-id="a816f-107">HTTP is used if you choose to allow access to the Autodiscover Service when modifying certificates might prove difficult or not cost justified.</span></span>

  - <span data-ttu-id="a816f-108">Клиенты должны обратиться на сервер Office Web Apps на HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a816f-108">Clients expect to contact the Office Web Apps Server on HTTPS.</span></span> <span data-ttu-id="a816f-109">Сервер Office Web Apps ожидает передачи данных от внутренних клиентов по протоколу HTTPS/TCP/443.</span><span class="sxs-lookup"><span data-stu-id="a816f-109">The Office Web Apps Server expects communication from internal clients on HTTPS/TCP/443.</span></span> <span data-ttu-id="a816f-110">Рекомендуемая конфигурация — Разрешить HTTPS/TCP/443 из обратного прокси-сервера на сервер Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="a816f-110">The recommended configuration is to allow HTTPS/TCP/443 from the reverse proxy to the Office Web Apps Server.</span></span>

  - <span data-ttu-id="a816f-111">Порт 8080 используется для маршрутизации трафика между внутренним прокси-интерфейсом на сервер переднего плана, внешним IP-адресом пула (VIP) или дополнительным пулом (VIP) пула или режиссером.</span><span class="sxs-lookup"><span data-stu-id="a816f-111">Port 8080 is used to route traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP.</span></span> <span data-ttu-id="a816f-112">Порт TCP 8080 необходим для мобильных устройств с операционной системой Lync, чтобы найти службу автообнаружения в ситуациях, когда изменение сертификата внешнего правила публикации веб-службы не желательно (например, если у вас большое количество доменов SIP).</span><span class="sxs-lookup"><span data-stu-id="a816f-112">Port TCP 8080 is required for mobile devices running Lync to locate the Autodiscover Service in situations where modifying the external web service publishing rule certificate is undesirable (for example, if you have a large number of SIP domains).</span></span> <span data-ttu-id="a816f-113">Если вы решили получить новые сертификаты с необходимыми записями сети SAN, порт TCP 8080 не нужен и является необязательным.</span><span class="sxs-lookup"><span data-stu-id="a816f-113">If you choose to acquire new certificates with the necessary SAN entries, the port TCP 8080 is not needed and is optional.</span></span>

  - <span data-ttu-id="a816f-114">Порт 4443 используется для трафика между внутренним прокси-сервером и внешним IP-адресом пула (VIP), а также необязательным каталогом (VIP) пула или режиссера.</span><span class="sxs-lookup"><span data-stu-id="a816f-114">Port 4443 is used for traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP</span></span>
    
    <span data-ttu-id="a816f-115">![13142405-d5c9-45b7-a8b7-a8c89f09c97c] (images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="a816f-115">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>  
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="a816f-116">Не путайте 4443 по протоколу TCP от обратного прокси до внутреннего развертывания для порта 4443 на сервере Standard Edition или внешнем пуле, управляющем ролью хранилища центрального управления.</span><span class="sxs-lookup"><span data-stu-id="a816f-116">Do not confuse the 4443 over TCP from the reverse proxy to the internal deployment for the port 4443 over TCP traffic from the Standard Edition server or the Front End pool that manages the Central Management store role.</span></span>

    
    </div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="a816f-117">Сведения о портах и протоколах</span><span class="sxs-lookup"><span data-stu-id="a816f-117">Port and Protocol Details</span></span>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="a816f-118">Сведения о брандмауэре для обратного прокси-сервера: внешний интерфейс</span><span class="sxs-lookup"><span data-stu-id="a816f-118">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a816f-119">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="a816f-119">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a816f-120">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="a816f-120">Source IP Address</span></span></th>
<th><span data-ttu-id="a816f-121">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="a816f-121">Destination IP Address</span></span></th>
<th><span data-ttu-id="a816f-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="a816f-122">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a816f-123">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="a816f-123">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="a816f-124">Любой</span><span class="sxs-lookup"><span data-stu-id="a816f-124">Any</span></span></p></td>
<td><p><span data-ttu-id="a816f-125">Обратный прослушиватель прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="a816f-125">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="a816f-126">Необязательно Перенаправление на HTTPS, если пользователь вводит http://&lt;публишедситефкдн&gt;.</span><span class="sxs-lookup"><span data-stu-id="a816f-126">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span></p>
<p><span data-ttu-id="a816f-127">Кроме того, если вы используете Office Web Apps для конференций и службу автообнаружения для мобильных устройств, работающих в Lync, в ситуациях, когда Организация не может изменить сертификат правила публикации внешней веб-службы.</span><span class="sxs-lookup"><span data-stu-id="a816f-127">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a816f-128">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a816f-128">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a816f-129">Любой</span><span class="sxs-lookup"><span data-stu-id="a816f-129">Any</span></span></p></td>
<td><p><span data-ttu-id="a816f-130">Обратный прослушиватель прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="a816f-130">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="a816f-131">Загрузка записной книжки, служба веб-запросов к адресной книге, автоматическое обнаружение, обновление клиента, содержимое собрания, обновления устройства, развертывание групп, Office Web Apps для конференций, Конференц-связь с телефонным подключением и собраний.</span><span class="sxs-lookup"><span data-stu-id="a816f-131">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="a816f-132">Сведения о брандмауэре для обратного прокси-сервера: внутренний интерфейс</span><span class="sxs-lookup"><span data-stu-id="a816f-132">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a816f-133">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="a816f-133">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a816f-134">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="a816f-134">Source IP Address</span></span></th>
<th><span data-ttu-id="a816f-135">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="a816f-135">Destination IP Address</span></span></th>
<th><span data-ttu-id="a816f-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="a816f-136">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a816f-137">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="a816f-137">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="a816f-138">Внутренний обратный интерфейс прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="a816f-138">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="a816f-139">Сервер переднего плана, пул переднего плана, режиссер, директор пула</span><span class="sxs-lookup"><span data-stu-id="a816f-139">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="a816f-140">Требуется при использовании службы автообнаружения для мобильных устройств, работающих с Lync, в ситуациях, когда Организация не может изменить сертификат правила публикации внешней веб-службы.</span><span class="sxs-lookup"><span data-stu-id="a816f-140">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p>
<p><span data-ttu-id="a816f-141">Трафик, отправленный на порт 80 на внешнем прокси-сервере, перенаправляется в пул на порте 8080 из внутреннего прокси-интерфейса, чтобы они могли отличать ее от внутреннего веб-трафика.</span><span class="sxs-lookup"><span data-stu-id="a816f-141">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a816f-142">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="a816f-142">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="a816f-143">Внутренний обратный интерфейс прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="a816f-143">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="a816f-144">Сервер переднего плана, пул переднего плана, режиссер, директор пула</span><span class="sxs-lookup"><span data-stu-id="a816f-144">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="a816f-145">Трафик, отправленный на порт 443 на внешнем прокси-сервере, перенаправляется в пул на порте 4443 из внутреннего прокси-интерфейса, чтобы они могли отличать ее от внутреннего веб-трафика.</span><span class="sxs-lookup"><span data-stu-id="a816f-145">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a816f-146">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a816f-146">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a816f-147">Внутренний обратный интерфейс прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="a816f-147">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="a816f-148">Office Web Apps для конференций</span><span class="sxs-lookup"><span data-stu-id="a816f-148">Office Web Apps for conferencing</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

