---
title: 'Lync Server 2013: сводка по DNS — обратный прокси-сервер'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47606fe71b271e01cc7fbefbcf319a2efe93f478
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a><span data-ttu-id="5b3e6-102">Сводка по DNS — обратный прокси-сервер в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b3e6-102">DNS summary - Reverse proxy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b3e6-103">_**Тема последнего изменения:** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="5b3e6-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="5b3e6-104">Вы настраиваете на обратном прокси два сетевых адаптера, как описано ниже.</span><span class="sxs-lookup"><span data-stu-id="5b3e6-104">You configure two network adapters in your reverse proxy as follows:</span></span>

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a><span data-ttu-id="5b3e6-105">Требования к обратной сети прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="5b3e6-105">Reverse Proxy Network Adapter Requirements</span></span>

  - <span data-ttu-id="5b3e6-106">Пример **сетевого адаптера 1 (внутренний интерфейс)**</span><span class="sxs-lookup"><span data-stu-id="5b3e6-106">**Network adapter 1 (Internal Interface)** example</span></span>
    
    <span data-ttu-id="5b3e6-107">Внутренний интерфейс с назначенным 172.25.33.40.</span><span class="sxs-lookup"><span data-stu-id="5b3e6-107">Internal interface with 172.25.33.40 assigned.</span></span>
    
    <span data-ttu-id="5b3e6-108">Шлюз по умолчанию не определен.</span><span class="sxs-lookup"><span data-stu-id="5b3e6-108">No default gateway is defined.</span></span>
    
    <span data-ttu-id="5b3e6-109">Убедитесь в том, что в сети есть маршрут, который содержит внутренний прокси-интерфейс обратной связи в любые сети, которые содержат серверы пула переднего плана Lync Server (например, с 172.25.33.0 на 192.168.10.0).</span><span class="sxs-lookup"><span data-stu-id="5b3e6-109">Ensure there is a route from the network containing the reverse proxy internal interface to any networks that contain Lync Server Front End pool servers (for example, from 172.25.33.0 to 192.168.10.0).</span></span>

  - <span data-ttu-id="5b3e6-110">Пример **сетевого адаптера 2 (внешний интерфейс)**</span><span class="sxs-lookup"><span data-stu-id="5b3e6-110">**Network adapter 2 (External Interface)** example</span></span>
    
    <span data-ttu-id="5b3e6-111">Этому сетевому адаптеру назначен минимум один общедоступный IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="5b3e6-111">A minimum of one public IP address is assigned to this network adapter.</span></span>
    
    <span data-ttu-id="5b3e6-112">Шлюз определен так, чтобы он указывал на маршрутизатор или интегрированный брандмауэр во внешнем периметре.</span><span class="sxs-lookup"><span data-stu-id="5b3e6-112">Gateway is defined to point to the router or integrated firewall in your outer perimeter.</span></span> <span data-ttu-id="5b3e6-113">(10.45.16.1 в примерах сценария)</span><span class="sxs-lookup"><span data-stu-id="5b3e6-113">(10.45.16.1 in the scenario examples)</span></span>

### <a name="dns-records-required-for-reverse-proxy"></a><span data-ttu-id="5b3e6-114">DNS-записи, необходимые для обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="5b3e6-114">DNS Records Required for Reverse Proxy</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b3e6-115">Расположение/тип/порт</span><span class="sxs-lookup"><span data-stu-id="5b3e6-115">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="5b3e6-116">Полное доменное имя</span><span class="sxs-lookup"><span data-stu-id="5b3e6-116">FQDN</span></span></th>
<th><span data-ttu-id="5b3e6-117">IP-адрес</span><span class="sxs-lookup"><span data-stu-id="5b3e6-117">IP address</span></span></th>
<th><span data-ttu-id="5b3e6-118">Карты и примечания</span><span class="sxs-lookup"><span data-stu-id="5b3e6-118">Maps to/comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b3e6-119">Внешние DNS/A</span><span class="sxs-lookup"><span data-stu-id="5b3e6-119">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5b3e6-120">webext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5b3e6-120">webext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5b3e6-121">Назначенный прослушиватель для внешних опубликованных ресурсов</span><span class="sxs-lookup"><span data-stu-id="5b3e6-121">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="5b3e6-122">Внешние веб-службы из внутреннего развертывания.</span><span class="sxs-lookup"><span data-stu-id="5b3e6-122">External web services from the internal deployment.</span></span> <span data-ttu-id="5b3e6-123">Дополнительные записи можно определять и создавать для всех пулов и отдельных серверов для любого домена SIP, который будет использовать этот прокси-сервер, а также с определенными внешними веб-службами.</span><span class="sxs-lookup"><span data-stu-id="5b3e6-123">Additional records can be defined and created for all pools and single servers for any SIP domain that will use this reverse proxy, and has defined external web services.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b3e6-124">Внешние DNS/A</span><span class="sxs-lookup"><span data-stu-id="5b3e6-124">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5b3e6-125">webdirext.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5b3e6-125">webdirext.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5b3e6-126">Назначенный прослушиватель для внешних опубликованных ресурсов</span><span class="sxs-lookup"><span data-stu-id="5b3e6-126">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="5b3e6-127">Внешние веб-службы для режиссеров и пулов режиссеров в развертывании.</span><span class="sxs-lookup"><span data-stu-id="5b3e6-127">External web services for the Directors or Director pools in your deployment.</span></span> <span data-ttu-id="5b3e6-128">Вы можете определить любое количество режиссеров, для которых есть разные директора, которые могут быть связаны с другими доменами SIP.</span><span class="sxs-lookup"><span data-stu-id="5b3e6-128">You can define as many Directors as there are distinct Directors, of which may be associated with other SIP domains.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="5b3e6-129">Определение DNS-записей для и публикации режиссеров не является ни интерфейсным пулом, ни решением режиссера.</span><span class="sxs-lookup"><span data-stu-id="5b3e6-129">Defining the DNS records for and publishing the Directors is not an either the Front End pool or the Director decision.</span></span> <span data-ttu-id="5b3e6-130">Если вы используете режиссеров, вы должны определить и опубликовать внешний веб-службы "режиссер" и "пул на стороне переднего плана".</span><span class="sxs-lookup"><span data-stu-id="5b3e6-130">You must define and publish both the Director and the Front End pool external web services if you are using Directors.</span></span> <span data-ttu-id="5b3e6-131">Конкретные типы трафика (для проверки подлинности и других применений) будут отправлены в директории сначала, если она определена в топологии.</span><span class="sxs-lookup"><span data-stu-id="5b3e6-131">Specific traffic types (for authentication and other uses) will be sent to the Director first, if it is defined in the topology.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b3e6-132">Внешние DNS/A</span><span class="sxs-lookup"><span data-stu-id="5b3e6-132">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5b3e6-133">dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5b3e6-133">dialin.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5b3e6-134">Назначенный прослушиватель для внешних опубликованных ресурсов</span><span class="sxs-lookup"><span data-stu-id="5b3e6-134">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="5b3e6-135">Внешний вход в Конференц-связь с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="5b3e6-135">Dial-in conferencing published externally</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b3e6-136">Внешние DNS/A</span><span class="sxs-lookup"><span data-stu-id="5b3e6-136">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5b3e6-137">meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5b3e6-137">meet.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5b3e6-138">Назначенный прослушиватель для внешних опубликованных ресурсов</span><span class="sxs-lookup"><span data-stu-id="5b3e6-138">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="5b3e6-139">Конференции, опубликованные извне</span><span class="sxs-lookup"><span data-stu-id="5b3e6-139">Conferences published externally</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b3e6-140">Внешние DNS/A</span><span class="sxs-lookup"><span data-stu-id="5b3e6-140">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5b3e6-141">officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5b3e6-141">officewebapps01.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5b3e6-142">Назначенный прослушиватель для сервера Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="5b3e6-142">Assigned listener for Office Web Apps Server</span></span></p></td>
<td><p><span data-ttu-id="5b3e6-143">Сервер Office Web Apps, развернутый внутренне или на периметре, и опубликованный для внешнего клиентского доступа</span><span class="sxs-lookup"><span data-stu-id="5b3e6-143">Office Web Apps Server deployed internally or in the perimeter, and published for external client access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b3e6-144">Внешние DNS/A</span><span class="sxs-lookup"><span data-stu-id="5b3e6-144">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="5b3e6-145">lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5b3e6-145">lyncdiscover.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="5b3e6-146">Назначенный прослушиватель для внешних опубликованных ресурсов</span><span class="sxs-lookup"><span data-stu-id="5b3e6-146">Assigned listener for externally published resources</span></span></p></td>
<td><p><span data-ttu-id="5b3e6-147">Lync обнаружение внешней записи для внешних опубликованных автообнаружения и включает мобильные и веб-приложения Microsoft Lync Web App и планировщик</span><span class="sxs-lookup"><span data-stu-id="5b3e6-147">Lync Discover External record for externally published AutoDiscover, and includes Mobility, Microsoft Lync Web App, and scheduler Web app</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

