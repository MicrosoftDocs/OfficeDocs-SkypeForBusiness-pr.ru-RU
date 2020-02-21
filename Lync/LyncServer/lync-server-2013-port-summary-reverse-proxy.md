---
title: 'Lync Server 2013: сводка по портам — обратный прокси-сервер'
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
ms.openlocfilehash: 6259614da322e79f69db40441125b28c95e379c9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="3f51e-102">Сводка по портам — обратный прокси-сервер в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f51e-102">Port summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f51e-103">_**Последнее изменение темы:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="3f51e-103">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="3f51e-104">Обратный прокси-сервер предъявляет минимальные требования к брандмауэру, портам и протоколам.</span><span class="sxs-lookup"><span data-stu-id="3f51e-104">The reverse proxy has minimal requirements for firewall and port/protocol.</span></span>

  - <span data-ttu-id="3f51e-105">Требования к внешнему брандмауэру это HTTPS/TCP/443 и необязательный HTTP/TCP/80.</span><span class="sxs-lookup"><span data-stu-id="3f51e-105">External firewall requirements are the HTTPS/TCP/443 and the optional HTTP/TCP/80.</span></span> <span data-ttu-id="3f51e-106">Протокол HTTPS используется для безопасного обмена данными по протоколу SSL и TLS через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="3f51e-106">HTTPS is used for SSL and TLS secure communications through the reverse proxy.</span></span> <span data-ttu-id="3f51e-107">HTTP используется, если вы решили разрешить доступ к службе автообнаружения при изменении сертификатов, которые могут быть затруднительными или не выровнены по затратам.</span><span class="sxs-lookup"><span data-stu-id="3f51e-107">HTTP is used if you choose to allow access to the Autodiscover Service when modifying certificates might prove difficult or not cost justified.</span></span>

  - <span data-ttu-id="3f51e-108">Клиенты ожидают подключения к серверу Office Web Apps на HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3f51e-108">Clients expect to contact the Office Web Apps Server on HTTPS.</span></span> <span data-ttu-id="3f51e-109">Сервер Office Web Apps ожидает взаимодействия внутренних клиентов по протоколу HTTPS/TCP/443.</span><span class="sxs-lookup"><span data-stu-id="3f51e-109">The Office Web Apps Server expects communication from internal clients on HTTPS/TCP/443.</span></span> <span data-ttu-id="3f51e-110">Рекомендуемая конфигурация — Разрешить HTTPS/TCP/443 с обратного прокси-сервера на сервер Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="3f51e-110">The recommended configuration is to allow HTTPS/TCP/443 from the reverse proxy to the Office Web Apps Server.</span></span>

  - <span data-ttu-id="3f51e-111">Порт 8080 используется для маршрутизации трафика из внутреннего интерфейса обратного прокси-сервера на сервер переднего плана, виртуальный IP-адрес пула переднего плана (VIP) или дополнительный виртуальный IP-адрес пула или пула директоров.</span><span class="sxs-lookup"><span data-stu-id="3f51e-111">Port 8080 is used to route traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP.</span></span> <span data-ttu-id="3f51e-112">Порт TCP 8080 необходим для мобильных устройств, работающих с Lync, для обнаружения службы автообнаружения в ситуациях, когда не удается изменить сертификат правила публикации внешних веб-служб (например, при наличии большого количества доменов SIP).</span><span class="sxs-lookup"><span data-stu-id="3f51e-112">Port TCP 8080 is required for mobile devices running Lync to locate the Autodiscover Service in situations where modifying the external web service publishing rule certificate is undesirable (for example, if you have a large number of SIP domains).</span></span> <span data-ttu-id="3f51e-113">Если выбрать поучение новых сертификатов с указанием необходимых значений альтернативных субъектов, порт TCP 8080 становится необязательным условием.</span><span class="sxs-lookup"><span data-stu-id="3f51e-113">If you choose to acquire new certificates with the necessary SAN entries, the port TCP 8080 is not needed and is optional.</span></span>

  - <span data-ttu-id="3f51e-114">Порт 4443 используется для трафика от внутреннего интерфейса обратного прокси-сервера к серверу переднего плана, виртуальному IP-адресу пула переднего плана (VIP) или дополнительному пулу или виртуальному IP-адресу пула директоров.</span><span class="sxs-lookup"><span data-stu-id="3f51e-114">Port 4443 is used for traffic from the reverse proxy internal interface to the Front End Server, Front End pool virtual IP (VIP) or the optional Director or Director pool VIP</span></span>
    
    <span data-ttu-id="3f51e-115">![13142405 — d5c9 — 45b7 — a8b7 – a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405 — d5c9 — 45b7 — a8b7 – a8c89f09c97c")</span><span class="sxs-lookup"><span data-stu-id="3f51e-115">![13142405-d5c9-45b7-a8b7-a8c89f09c97c](images/JJ204932.13142405-d5c9-45b7-a8b7-a8c89f09c97c(OCS.15).jpg "13142405-d5c9-45b7-a8b7-a8c89f09c97c")</span></span>  
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="3f51e-116">Не путайте 4443/TCP от обратного прокси-сервера к внутреннему развертыванию для порта 4443 через сервер Standard Edition или интерфейсного пула, управляющего ролью центрального хранилища управления.</span><span class="sxs-lookup"><span data-stu-id="3f51e-116">Do not confuse the 4443 over TCP from the reverse proxy to the internal deployment for the port 4443 over TCP traffic from the Standard Edition server or the Front End pool that manages the Central Management store role.</span></span>

    
    </div>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="3f51e-117">Сведения о портах и протоколе</span><span class="sxs-lookup"><span data-stu-id="3f51e-117">Port and Protocol Details</span></span>

### <a name="firewall-details-for-reverse-proxy-server-external-interface"></a><span data-ttu-id="3f51e-118">Подробные сведения о настройках брандмауэра для обратного прокси-сервера: внешний интерфейс</span><span class="sxs-lookup"><span data-stu-id="3f51e-118">Firewall Details for Reverse Proxy Server: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f51e-119">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="3f51e-119">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3f51e-120">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="3f51e-120">Source IP Address</span></span></th>
<th><span data-ttu-id="3f51e-121">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="3f51e-121">Destination IP Address</span></span></th>
<th><span data-ttu-id="3f51e-122">Notes</span><span class="sxs-lookup"><span data-stu-id="3f51e-122">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f51e-123">HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="3f51e-123">HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="3f51e-124">Любые</span><span class="sxs-lookup"><span data-stu-id="3f51e-124">Any</span></span></p></td>
<td><p><span data-ttu-id="3f51e-125">Слушатель обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="3f51e-125">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="3f51e-126">Необязательно Перенаправление на HTTPS, если пользователь вводит http://&lt;публишедситефкдн&gt;.</span><span class="sxs-lookup"><span data-stu-id="3f51e-126">(Optional) Redirection to HTTPS if user enters http://&lt;publishedSiteFQDN&gt;.</span></span></p>
<p><span data-ttu-id="3f51e-127">Кроме того, необходимо использовать Office Web Apps для конференций и службу автообнаружения для мобильных устройств, работающих с Lync, в ситуациях, когда организациям не требуется изменять сертификат правила публикации внешних веб-служб.</span><span class="sxs-lookup"><span data-stu-id="3f51e-127">Also required if using Office Web Apps for conferencing and the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f51e-128">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3f51e-128">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3f51e-129">Любые</span><span class="sxs-lookup"><span data-stu-id="3f51e-129">Any</span></span></p></td>
<td><p><span data-ttu-id="3f51e-130">Слушатель обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="3f51e-130">Reverse proxy listener</span></span></p></td>
<td><p><span data-ttu-id="3f51e-131">Загрузка адресной книги, служба веб-запросов к адресной книге, автообнаружение, обновление клиентов, содержимое собраний, обновления устройств, развертывание групп, Office Web Apps для конференций, Конференц-связь с телефонным подключением и собрания.</span><span class="sxs-lookup"><span data-stu-id="3f51e-131">Address book downloads, Address Book Web Query service, Autodiscover, client updates, meeting content, device updates, group expansion, Office Web Apps for conferencing, dial-in conferencing, and meetings.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-details-for-reverse-proxy-server-internal-interface"></a><span data-ttu-id="3f51e-132">Подробные сведения о настройках брандмауэра для обратного прокси-сервера: внутренний интерфейс</span><span class="sxs-lookup"><span data-stu-id="3f51e-132">Firewall Details for Reverse Proxy Server: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3f51e-133">Протокол/TCP или UDP/порт</span><span class="sxs-lookup"><span data-stu-id="3f51e-133">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="3f51e-134">IP-адрес источника</span><span class="sxs-lookup"><span data-stu-id="3f51e-134">Source IP Address</span></span></th>
<th><span data-ttu-id="3f51e-135">IP-адрес назначения</span><span class="sxs-lookup"><span data-stu-id="3f51e-135">Destination IP Address</span></span></th>
<th><span data-ttu-id="3f51e-136">Notes</span><span class="sxs-lookup"><span data-stu-id="3f51e-136">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3f51e-137">HTTP/TCP/8080</span><span class="sxs-lookup"><span data-stu-id="3f51e-137">HTTP/TCP/8080</span></span></p></td>
<td><p><span data-ttu-id="3f51e-138">Внутренний интерфейс обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="3f51e-138">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="3f51e-139">Сервер переднего плана, интерфейсный пул, директор, директор пула</span><span class="sxs-lookup"><span data-stu-id="3f51e-139">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="3f51e-140">Требуется при использовании службы автообнаружения для мобильных устройств, работающих с Lync, в ситуациях, когда Организация не хочет изменить сертификат правила публикации внешних веб-служб.</span><span class="sxs-lookup"><span data-stu-id="3f51e-140">Required if using the Autodiscover Service for mobile devices running Lync in situations where the organization does not want to modify the external web service publishing rule certificate.</span></span></p>
<p><span data-ttu-id="3f51e-141">Трафик, отправляемый на порт 80 внешнего интерфейса обратного прокси-сервера, перенаправляется в пул на порте 8080 из внутреннего интерфейса обратного прокси-сервера, чтобы веб-службы пула могли отличить его от внутреннего веб-трафика.</span><span class="sxs-lookup"><span data-stu-id="3f51e-141">Traffic sent to port 80 on the reverse proxy external interface is redirected to a pool on port 8080 from the reverse proxy internal interface so that the pool Web Services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3f51e-142">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="3f51e-142">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="3f51e-143">Внутренний интерфейс обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="3f51e-143">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="3f51e-144">Сервер переднего плана, интерфейсный пул, директор, директор пула</span><span class="sxs-lookup"><span data-stu-id="3f51e-144">Front End Server, Front End pool, Director, Director pool</span></span></p></td>
<td><p><span data-ttu-id="3f51e-145">Трафик, отправляемый на порт 443 внешнего интерфейса обратного прокси-сервера, перенаправляется в пул на порте 4443 из внутреннего интерфейса обратного прокси-сервера, чтобы веб-службы пула могли отличить его от внутреннего веб-трафика.</span><span class="sxs-lookup"><span data-stu-id="3f51e-145">Traffic sent to port 443 on the reverse proxy external interface is redirected to a pool on port 4443 from the reverse proxy internal interface so that the pool web services can distinguish it from internal web traffic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3f51e-146">HTTPS/TCP/443</span><span class="sxs-lookup"><span data-stu-id="3f51e-146">HTTPS/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="3f51e-147">Внутренний интерфейс обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="3f51e-147">Internal reverse proxy interface</span></span></p></td>
<td><p><span data-ttu-id="3f51e-148">Office Web Apps для конференц-связи</span><span class="sxs-lookup"><span data-stu-id="3f51e-148">Office Web Apps for conferencing</span></span></p></td>
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

