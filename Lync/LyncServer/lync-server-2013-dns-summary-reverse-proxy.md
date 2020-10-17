---
title: 'Lync Server 2013: сводка по DNS — обратный прокси-сервер'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a468e74206fdc6bad8f078267688450636b8a725
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532146"
---
# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="2ebff-102">Сводка по DNS — обратный прокси-сервер в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ebff-102">DNS summary - Reverse proxy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ebff-103">_**Последнее изменение темы:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="2ebff-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="2ebff-104">Два сетевых адаптера на обратном прокси-сервере можно настроить следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2ebff-104">You configure two network adapters in your reverse proxy as follows:</span></span>

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a><span data-ttu-id="2ebff-105">Требования к сетевым адаптерам обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="2ebff-105">Reverse Proxy Network Adapter Requirements</span></span>

  - <span data-ttu-id="2ebff-106">**Сетевой адаптер 1 (внутренний интерфейс)** (пример)</span><span class="sxs-lookup"><span data-stu-id="2ebff-106">**Network adapter 1 (Internal Interface)** example</span></span>
    
    <span data-ttu-id="2ebff-107">Назначенный внутренний интерфейс с 172.25.33.40.</span><span class="sxs-lookup"><span data-stu-id="2ebff-107">Internal interface with 172.25.33.40 assigned.</span></span>
    
    <span data-ttu-id="2ebff-108">Шлюз по умолчанию не определен.</span><span class="sxs-lookup"><span data-stu-id="2ebff-108">No default gateway is defined.</span></span>
    
    <span data-ttu-id="2ebff-109">Убедитесь, что существует маршрут от сети, содержащей внутренний интерфейс обратного прокси-сервера, в любые сети, содержащие серверы пула переднего плана Lync Server (например, из 172.25.33.0 в 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="2ebff-109">Ensure there is a route from the network containing the reverse proxy internal interface to any networks that contain Lync Server Front End pool servers (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="2ebff-110">**Сетевой адаптер 2 (внешний интерфейс)** (пример)</span><span class="sxs-lookup"><span data-stu-id="2ebff-110">**Network adapter 2 (External Interface)** example</span></span>
    
    <span data-ttu-id="2ebff-111">Как минимум один общедоступный IP-адрес назначен данному сетевому адаптеру.</span><span class="sxs-lookup"><span data-stu-id="2ebff-111">A minimum of one public IP address is assigned to this network adapter.</span></span>
    
    <span data-ttu-id="2ebff-p101">Шлюз определен так, что он указывает на маршрутизатор или интегрированный брандмауэр во внешнем периметре. (10.45.16.1 в примерах)</span><span class="sxs-lookup"><span data-stu-id="2ebff-p101">Gateway is defined to point to the router or integrated firewall in your outer perimeter. (10.45.16.1 in the scenario examples)</span></span>

### <a name="dns-records-required-for-reverse-proxy"></a><span data-ttu-id="2ebff-114">Записи DNS, необходимые для обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="2ebff-114">DNS Records Required for Reverse Proxy</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ebff-115">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="2ebff-115">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="2ebff-116">полное доменное имя;</span><span class="sxs-lookup"><span data-stu-id="2ebff-116">FQDN</span></span></th>
<th><span data-ttu-id="2ebff-117">IP-адрес</span><span class="sxs-lookup"><span data-stu-id="2ebff-117">IP address</span></span></th>
<th><span data-ttu-id="2ebff-118">Сопоставляется с/комментарии</span><span class="sxs-lookup"><span data-stu-id="2ebff-118">Maps to/comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ebff-119">Внешний DNS/A</span><span class="sxs-lookup"><span data-stu-id="2ebff-119">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2ebff-120">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2ebff-120">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2ebff-121">Назначенный прослушиватель для внешних опубликованных ресурсов</span><span class="sxs-lookup"><span data-stu-id="2ebff-121">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="2ebff-p102">Внешние веб-службы из внутреннего развертывания. Могут быть определены и созданы дополнительные записи для всех пулов и отдельных серверов для любого SIP-домена, который будет использовать это обратный прокси-сервер и на котором определены внешние веб-службы.</span><span class="sxs-lookup"><span data-stu-id="2ebff-p102">External web services from the internal deployment. Additional records can be defined and created for all pools and single servers for any SIP domain that will use this reverse proxy, and has defined external web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ebff-124">Внешний DNS/A</span><span class="sxs-lookup"><span data-stu-id="2ebff-124">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2ebff-125">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2ebff-125">webdirext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2ebff-126">Назначенный прослушиватель для внешних опубликованных ресурсов</span><span class="sxs-lookup"><span data-stu-id="2ebff-126">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="2ebff-127">Внешние веб-службы для директоров или пулов директоров в развертывании.</span><span class="sxs-lookup"><span data-stu-id="2ebff-127">External web services for the Directors or Director pools in your deployment.</span></span> <span data-ttu-id="2ebff-128">Можно определить столько директоров, где есть разные директора, которые могут быть связаны с другими доменами SIP.</span><span class="sxs-lookup"><span data-stu-id="2ebff-128">You can define as many Directors as there are distinct Directors, of which may be associated with other SIP domains.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="2ebff-129">Определение записей DNS для публикации директоров не является интерфейсным пулом или руководителем.</span><span class="sxs-lookup"><span data-stu-id="2ebff-129">Defining the DNS records for and publishing the Directors is not an either the Front End pool or the Director decision.</span></span> <span data-ttu-id="2ebff-130">При использовании директора необходимо определить и опубликовать внешние веб-службы директора и интерфейсного пула переднего плана.</span><span class="sxs-lookup"><span data-stu-id="2ebff-130">You must define and publish both the Director and the Front End pool external web services if you are using Directors.</span></span> <span data-ttu-id="2ebff-131">Конкретные типы трафика (для проверки подлинности и других применений) будут отправлены в директоре первыми, если она определена в топологии.</span><span class="sxs-lookup"><span data-stu-id="2ebff-131">Specific traffic types (for authentication and other uses) will be sent to the Director first, if it is defined in the topology.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ebff-132">Внешний DNS/A</span><span class="sxs-lookup"><span data-stu-id="2ebff-132">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2ebff-133">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2ebff-133">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2ebff-134">Назначенный прослушиватель для внешних опубликованных ресурсов</span><span class="sxs-lookup"><span data-stu-id="2ebff-134">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="2ebff-135">Ресурсы конференц-связи с телефонным подключением, опубликованные внешне</span><span class="sxs-lookup"><span data-stu-id="2ebff-135">Dial-in conferencing published externally</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ebff-136">Внешний DNS/A</span><span class="sxs-lookup"><span data-stu-id="2ebff-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2ebff-137">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2ebff-137">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2ebff-138">Назначенный прослушиватель для внешних опубликованных ресурсов</span><span class="sxs-lookup"><span data-stu-id="2ebff-138">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="2ebff-139">Конференции, опубликованные внешне</span><span class="sxs-lookup"><span data-stu-id="2ebff-139">Conferences published externally</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ebff-140">Внешний DNS/A</span><span class="sxs-lookup"><span data-stu-id="2ebff-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2ebff-141">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2ebff-141">officewebapps01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2ebff-142">Назначенный прослушиватель для сервера Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="2ebff-142">Assigned listener for Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="2ebff-143">Сервер Office Web Apps, развернутый внутри или на периметре и опубликованный для внешнего клиентского доступа</span><span class="sxs-lookup"><span data-stu-id="2ebff-143">Office Web Apps Server deployed internally or in the perimeter, and published for external client access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ebff-144">Внешний DNS/A</span><span class="sxs-lookup"><span data-stu-id="2ebff-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="2ebff-145">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="2ebff-145">lyncdiscover.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="2ebff-146">Назначенный прослушиватель для внешних опубликованных ресурсов</span><span class="sxs-lookup"><span data-stu-id="2ebff-146">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="2ebff-147">Внешняя запись Lync обнаружение для внешнего опубликованного автообнаружения и включение мобильности, Microsoft Lync Web App и веб-приложения планировщика</span><span class="sxs-lookup"><span data-stu-id="2ebff-147">Lync Discover External record for externally published AutoDiscover, and includes Mobility, Microsoft Lync Web App, and scheduler Web app</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

