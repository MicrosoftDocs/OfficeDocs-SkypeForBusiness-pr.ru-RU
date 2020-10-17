---
title: 'Lync Server 2013: сводка по портам — обратный прокси-сервер'
description: 'Lync Server 2013: сводка по портам — обратный прокси-сервер.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Reverse proxy
ms:assetid: 59b9ac3c-3e6f-4776-b366-174f0dd1f2eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204932(v=OCS.15)
ms:contentKeyID: 48184251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf07800c91f5a28165eb05e14e2d775758460f50
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555255"
---
# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="b027c-103">Сводка по портам — обратный прокси-сервер в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b027c-103">Port summary - Reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b027c-104">_**Последнее изменение темы:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="b027c-104">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="b027c-105">Обратный прокси-сервер предъявляет минимальные требования к брандмауэру, портам и протоколам.</span><span class="sxs-lookup"><span data-stu-id="b027c-105">The reverse proxy has minimal requirements for firewall and port/protocol.</span></span>

  - <span data-ttu-id="b027c-106">Требования к внешнему брандмауэру это HTTPS/TCP/443 и необязательный HTTP/TCP/80.</span><span class="sxs-lookup"><span data-stu-id="b027c-106">External firewall requirements are the HTTPS/TCP/443 and the optional HTTP/TCP/80.</span></span> <span data-ttu-id="b027c-107">Протокол HTTPS используется для безопасного обмена данными по протоколу SSL и TLS через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="b027c-107">HTTPS is used for SSL and TLS secure communications through the reverse proxy.</span></span> <span data-ttu-id="b027c-108">HTTP используется, если вы решили разрешить доступ к службе автообнаружения при изменении сертификатов, которые могут быть затруднительными или не выровнены по затратам.</span><span class="sxs-lookup"><span data-stu-id="b027c-108">HTTP is used if you choose to allow access to the Autodiscover Service when modifying certificates might prove difficult or not cost justified.</span></span>

  - <span data-ttu-id="b027c-109">Клиенты ожидают подключения к серверу Office Web Apps на HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b027c-109">Clients expect to contact the Office Web Apps Server on HTTPS.</span></span> <span data-ttu-id="b027c-110">Сервер Office Web Apps ожидает взаимодействия внутренних клиентов по протоколу HTTPS/TCP/443.</span><span class="sxs-lookup"><span data-stu-id="b027c-110">The Office Web Apps Server expects communication from internal clients on HTTPS/TCP/443.</span></span> <span data-ttu-id="b027c-111">Рекомендуемая конфигурация — Разрешить HTTPS/TCP/443 с обратного прокси-сервера на сервер Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="b027c-111">The recommended configuration is to allow HTTPS/TCP/443 from the reverse proxy to the Office Web Apps Server.</span></span>

  - <span data-ttu-id="b027c-112">Порт 8080 используется для маршрутизации трафика из внутреннего интерфейса обратного прокси-сервера на сервер переднего плана, виртуальный IP-адрес пула переднего плана (VIP) или дополнительный виртуальный IP-адрес пула или пула директоров.</span><span class="sxs-lookup"><span data-stu-id="b027c-112">Port 8080 is used to route traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP.</span></span> <span data-ttu-id="b027c-113">Порт TCP 8080 необходим для мобильных устройств, работающих с Lync, для обнаружения службы автообнаружения в ситуациях, когда не удается изменить сертификат правила публикации внешних веб-служб (например, при наличии большого количества доменов SIP).</span><span class="sxs-lookup"><span data-stu-id="b027c-113">Port TCP 8080 is required for mobile devices running Lync to locate the Autodiscover Service in situations where modifying the external web service publishing rule certificate is undesirable (for example, if you have a large number of SIP domains).</span></span> <span data-ttu-id="b027c-114">Если выбрать поучение новых сертификатов с указанием необходимых значений альтернативных субъектов, порт TCP 8080 становится необязательным условием.</span><span class="sxs-lookup"><span data-stu-id="b027c-114">If you choose to acquire new certificates with the necessary SAN entries, the port TCP 8080 is not needed and is optional.</span></span>

  - <span data-ttu-id="b027c-115">Порт 4443 используется для трафика от внутреннего интерфейса обратного прокси-сервера к серверу переднего плана, виртуальному IP-адресу пула переднего плана (VIP) или дополнительному пулу или виртуальному IP-адресу пула директоров.</span><span class="sxs-lookup"><span data-stu-id="b027c-115">Port 4443 is used for traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP</span></span>
    
    <span data-ttu-id="b027c-116">![13142405 — d5c9 — 45b7 — a8b7 – a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405 — d5c9 — 45b7 — a8b7 – a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="b027c-116">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>  
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="b027c-117">Не путайте 4443/TCP от обратного прокси-сервера к внутреннему развертыванию для порта 4443 через сервер Standard Edition или интерфейсного пула, управляющего ролью центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="b027c-117">Do not confuse the 4443 over TCP from the reverse proxy to the internal deployment for the port 4443 over TCP traffic from the Standard Edition server or the Front End pool that manages the Central Management store role.</span></span>

    
    </div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="b027c-118">Сведения о портах и протоколе</span><span class="sxs-lookup"><span data-stu-id="b027c-118">Port and Protocol Details</span></span>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="b027c-119">Подробные сведения о настройках брандмауэра для обратного прокси-сервера: внешний интерфейс</span><span class="sxs-lookup"><span data-stu-id="b027c-119">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b027c-120">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="b027c-120">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b027c-121">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="b027c-121">Source IP Address</span></span></th>
<th><span data-ttu-id="b027c-122">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="b027c-122">Destination IP Address</span></span></th>
<th><span data-ttu-id="b027c-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="b027c-123">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b027c-124">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="b027c-124">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="b027c-125">Любой</span><span class="sxs-lookup"><span data-stu-id="b027c-125">Any</span></span></p></td>
<td><p><span data-ttu-id="b027c-126">Слушатель обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="b027c-126">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="b027c-127">Необязательно Перенаправление на HTTPS, если пользователь вводит http:// &lt; публишедситефкдн &gt; .</span><span class="sxs-lookup"><span data-stu-id="b027c-127">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span></p>
<p><span data-ttu-id="b027c-128">Кроме того, необходимо использовать Office Web Apps для конференций и службу автообнаружения для мобильных устройств, работающих с Lync, в ситуациях, когда организациям не требуется изменять сертификат правила публикации внешних веб-служб.</span><span class="sxs-lookup"><span data-stu-id="b027c-128">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b027c-129">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b027c-129">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b027c-130">Любой</span><span class="sxs-lookup"><span data-stu-id="b027c-130">Any</span></span></p></td>
<td><p><span data-ttu-id="b027c-131">Слушатель обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="b027c-131">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="b027c-132">Загрузка адресной книги, служба веб-запросов к адресной книге, автообнаружение, обновление клиентов, содержимое собраний, обновления устройств, развертывание групп, Office Web Apps для конференций, Конференц-связь с телефонным подключением и собрания.</span><span class="sxs-lookup"><span data-stu-id="b027c-132">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="b027c-133">Подробные сведения о настройках брандмауэра для обратного прокси-сервера: внутренний интерфейс</span><span class="sxs-lookup"><span data-stu-id="b027c-133">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b027c-134">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="b027c-134">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b027c-135">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="b027c-135">Source IP Address</span></span></th>
<th><span data-ttu-id="b027c-136">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="b027c-136">Destination IP Address</span></span></th>
<th><span data-ttu-id="b027c-137">Примечания</span><span class="sxs-lookup"><span data-stu-id="b027c-137">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b027c-138">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="b027c-138">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="b027c-139">Внутренний интерфейс обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="b027c-139">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="b027c-140">Сервер переднего плана, интерфейсный пул, директор, директор пула</span><span class="sxs-lookup"><span data-stu-id="b027c-140">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="b027c-141">Требуется при использовании службы автообнаружения для мобильных устройств, работающих с Lync, в ситуациях, когда Организация не хочет изменить сертификат правила публикации внешних веб-служб.</span><span class="sxs-lookup"><span data-stu-id="b027c-141">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p>
<p><span data-ttu-id="b027c-142">Трафик, отправляемый на порт 80 внешнего интерфейса обратного прокси-сервера, перенаправляется в пул на порте 8080 из внутреннего интерфейса обратного прокси-сервера, чтобы веб-службы пула могли отличить его от внутреннего веб-трафика.</span><span class="sxs-lookup"><span data-stu-id="b027c-142">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b027c-143">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="b027c-143">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="b027c-144">Внутренний интерфейс обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="b027c-144">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="b027c-145">Сервер переднего плана, интерфейсный пул, директор, директор пула</span><span class="sxs-lookup"><span data-stu-id="b027c-145">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="b027c-146">Трафик, отправляемый на порт 443 внешнего интерфейса обратного прокси-сервера, перенаправляется в пул на порте 4443 из внутреннего интерфейса обратного прокси-сервера, чтобы веб-службы пула могли отличить его от внутреннего веб-трафика.</span><span class="sxs-lookup"><span data-stu-id="b027c-146">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b027c-147">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b027c-147">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b027c-148">Внутренний интерфейс обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="b027c-148">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="b027c-149">Office Web Apps для конференц-связи</span><span class="sxs-lookup"><span data-stu-id="b027c-149">Office Web Apps for conferencing</span></span></p></td>
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

