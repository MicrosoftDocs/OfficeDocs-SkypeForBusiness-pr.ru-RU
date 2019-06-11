---
title: 'Lync Server 2013: сценарии доступа внешних пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27e4f7410d7038971c6ddefe1af1c7b3ecd97ab9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="becf0-102">Сценарии доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="becf0-102">Scenarios for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="becf0-103">_**Тема последнего изменения:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="becf0-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="becf0-104">Для обеспечения доступа внешних пользователей для Lync Server 2013 требуется развернуть хотя бы один пограничный сервер и один обратный прокси-сервер в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="becf0-104">Providing external user access for Lync Server 2013 requires that you deploy at least one Edge Server and one reverse proxy in your perimeter network.</span></span> <span data-ttu-id="becf0-105">Кроме того, вы можете развернуть режиссер или директор пула во внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="becf0-105">Optionally, you may deploy a Director or Director pool in your internal network.</span></span>

<span data-ttu-id="becf0-106">Если вам нужна больше возможностей, чем один пограничный сервер, или если вам требуется высокая доступность при развертывании пограничного сервера, вы можете настроить балансировку нагрузки и развернуть несколько пограничных серверов в пуле с балансировкой нагрузки.</span><span class="sxs-lookup"><span data-stu-id="becf0-106">If you need greater capacity than a single Edge Server can provide, or if you need high availability for your Edge Server deployment, you can configure load balancing and deploy multiple Edge Servers in a load balanced pool.</span></span> <span data-ttu-id="becf0-107">Если в вашей организации есть несколько центров обработки данных, вы можете использовать развертывание пограничного сервера или пула EDGE в более чем одном местоположении.</span><span class="sxs-lookup"><span data-stu-id="becf0-107">If your organization has multiple data centers, you can have Edge Server or Edge pool deployments at more than one location.</span></span> <span data-ttu-id="becf0-108">Однако только одно из развертываний пограничного сервера может быть определено как маршрут Федерации.</span><span class="sxs-lookup"><span data-stu-id="becf0-108">However, only one of the Edge Server deployments can be designated as the federation route.</span></span>

<span data-ttu-id="becf0-109">В этом разделе определяются сценарии развертывания пограничного сервера и сопоставляются разделы планирования с возможными сценариями.</span><span class="sxs-lookup"><span data-stu-id="becf0-109">This section defines the scenarios for Edge Server deployments and maps the planning sections to the possible scenarios.</span></span> <span data-ttu-id="becf0-110">Например, если для развертывания требуется высокая доступность, интеграция с контактами и мобильными приложениями для обмена сообщениями (КСМПП) и Lync Mobility, вы можете выбрать соответствующие записи в следующей таблице, которые удовлетворяют этим требованиям, и использовать разделы планирования, на которые указывают ссылки, чтобы определить развертывание, как показано в следующей блок-схеме.</span><span class="sxs-lookup"><span data-stu-id="becf0-110">For example, if your deployment requires high availability, federation with extensible messaging and presence (XMPP) contacts, and Lync mobility, you would select the matching entries in the following table that would satisfy these requirements and use the referenced planning sections to define your deployment, as illustrated in the following flowchart.</span></span>

<span data-ttu-id="becf0-111">**Процесс выделения в сценарии развертывания пограничного сервера**</span><span class="sxs-lookup"><span data-stu-id="becf0-111">**Edge Server deployment scenario selection process**</span></span>

<span data-ttu-id="becf0-112">![Пример блок-схемы развертывания] (images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Пример блок-схемы развертывания")</span><span class="sxs-lookup"><span data-stu-id="becf0-112">![Sample deployment flowchart](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Sample deployment flowchart")</span></span>

<span data-ttu-id="becf0-113">С помощью этого процесса вы можете планировать и документировать конфигурацию всех потенциальных функций, которые планируется развертывать для пользователей.</span><span class="sxs-lookup"><span data-stu-id="becf0-113">By using this process, you can plan for and document the configuration of all potential features that you intend to deploy for your users.</span></span> <span data-ttu-id="becf0-114">Однако вы можете добавить службы федерации и Mobility Services после развертывания пограничного сервера и подтверждения правильной операции перед добавлением других функций.</span><span class="sxs-lookup"><span data-stu-id="becf0-114">However, you can add federation and mobility services after you have deployed the Edge Server and have confirmed the correct operation before adding other features.</span></span> <span data-ttu-id="becf0-115">Процесс добавления функций в существующее развертывание пограничного сервера рассматривается в разделе Развертывание.</span><span class="sxs-lookup"><span data-stu-id="becf0-115">The process of adding features to an existing Edge Server deployment is covered in the Deployment section.</span></span> <span data-ttu-id="becf0-116">Дополнительные сведения о развертывании можно найти [в статье Развертывание внешних пользователей Access в Lync Server 2013](lync-server-2013-deploying-external-user-access.md) , включая планирование этих функций в процессе первоначального планирования, вы можете подготовиться к требованиям к DNS, брандмауэру и сертификату для добавленных функций. что позволяет предварительно получить сертификаты и настроить требования к DNS и порту и протоколу.</span><span class="sxs-lookup"><span data-stu-id="becf0-116">For details on deployment, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) By including planning for these features during the initial planning process, you can prepare for the DNS, firewall, and certificate requirements for the added features, which enables you to acquire the certificates and configure DNS and port/protocol requirements in advance.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="becf0-117">Если вы планируете установить пограничные серверы и поменять прокси и затем добавить компоненты позже (например, Федерацию и мобильность), определите, какие сертификаты потребуется выполнить после развертывания.</span><span class="sxs-lookup"><span data-stu-id="becf0-117">If you are planning to install the Edge Servers and reverse proxy and then add features later (for example, federation and mobility), determine what certificates you will require for all services after deployment.</span></span> <span data-ttu-id="becf0-118">Планирование и получение сертификатов для всех функций, предварительно развернутых и не предназначенных для того, чтобы запланировать новые сертификаты, удовлетворяющие требованиям Федерации (то есть на пограничных серверах) или обратном прокси (то есть для мобильных устройств). Services (службы)).</span><span class="sxs-lookup"><span data-stu-id="becf0-118">Planning for and acquiring the certificates for all features in advance, initially deployed or not, saves you from having to order new certificates to satisfy the requirements of federation (that is, on the Edge Servers) or the reverse proxy (that is, for mobility services).</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="becf0-119">Все пограничные службы выполняются на каждом пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="becf0-119">All edge services run on each Edge Server.</span></span> <span data-ttu-id="becf0-120">Службы нельзя разделить между двумя различными серверами пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="becf0-120">Services cannot be split between two different Edge Servers.</span></span> <span data-ttu-id="becf0-121">При развертывании пограничных пулов для обеспечения масштабируемости все службы пограничного сервера развертываются на каждом пограничном сервере в пуле.</span><span class="sxs-lookup"><span data-stu-id="becf0-121">If you deploy an Edge pool for scalability, all edge services are deployed on each Edge Server in the pool.</span></span> <span data-ttu-id="becf0-122">КСМПП Federation, Office Communications Server и интеграции Lync Server, общедоступная служба обмена мгновенными сообщениями и мобильные клиенты — это дополнительные службы, которые можно развернуть после развертывания первого пограничного сервера или пула Edge.</span><span class="sxs-lookup"><span data-stu-id="becf0-122">XMPP federation, Office Communications Server, and Lync Server federation, public IM connectivity and client mobility are additional services that can be deployed after you have deployed your first Edge Server or Edge pool.</span></span> <span data-ttu-id="becf0-123">Услуги мобильной связи — это функция, использующая обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="becf0-123">Mobility services is a feature that uses the reverse proxy.</span></span> <span data-ttu-id="becf0-124">Установка служб Mobility Service не приведет к добавлению функций на пограничные серверы, но потребуется перенастроить обратный прокси.</span><span class="sxs-lookup"><span data-stu-id="becf0-124">Installation of mobility services will not add features to your Edge Servers, but will require reconfiguration of your reverse proxy.</span></span> <span data-ttu-id="becf0-125">В столбце " <STRONG>Цель установки</STRONG> ", в котором перечислены эти функции, содержатся инструкции по планированию в соответствующем <STRONG>разделе "Планирование пограничного сервера" или разделы</STRONG> для параллельного планирования этих функций, которые развертываются, когда пограничные серверы установлены и настроены.</span><span class="sxs-lookup"><span data-stu-id="becf0-125">The <STRONG>Installation goal</STRONG> column that lists these features provides planning guidance in the associated column under <STRONG>Edge Server planning section or sections</STRONG> for concurrently planning these features to be deployed when the Edge Servers are installed and configured.</span></span>



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a><span data-ttu-id="becf0-126">Определение и сопоставление целей развертывания</span><span class="sxs-lookup"><span data-stu-id="becf0-126">Identifying and Mapping Your Deployment Goals</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="becf0-127">Цель установки</span><span class="sxs-lookup"><span data-stu-id="becf0-127">Installation goal</span></span></th>
<th><span data-ttu-id="becf0-128">Документация по планированию пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="becf0-128">Edge Server planning documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="becf0-129">Вы решили, что для служб EDGE в вашей инфраструктуре достаточно одного сервера.</span><span class="sxs-lookup"><span data-stu-id="becf0-129">You have decided that a single server is sufficient for Edge services in your infrastructure.</span></span> <span data-ttu-id="becf0-130">Вы также планируете использовать частные IP-адреса для внешних интерфейсов пограничного сервера с помощью NAT в Интернете.</span><span class="sxs-lookup"><span data-stu-id="becf0-130">You also intend to use private IP addresses for the Edge server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="becf0-131">Используйте этот раздел Планирование при развертывании одного пограничного сервера в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="becf0-131">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="becf0-132">Вы развернете пограничный сервер с частными IP-адресами, назначенными на пограничном сервере, и будете использовать NAT для предоставления общедоступных IP-адресов внешним пользователям в Интернете.</span><span class="sxs-lookup"><span data-stu-id="becf0-132">You will deploy an Edge Server with private IP addresses assigned to the Edge Server and will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="becf0-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Единая консолидированная пограничная топология с закрытыми IP-адресами и трансляцией сетевых адресов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="becf0-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="becf0-134">Вы решили, что для служб EDGE в вашей инфраструктуре достаточно одного сервера.</span><span class="sxs-lookup"><span data-stu-id="becf0-134">You have decided that a single server is sufficient for Edge services in your infrastructure.</span></span> <span data-ttu-id="becf0-135">Вы также планируете использовать общедоступные IP-адреса для внешних интерфейсов пограничного сервера в Интернет.</span><span class="sxs-lookup"><span data-stu-id="becf0-135">You also intend to use public IP addresses for the Edge server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="becf0-136">Используйте этот раздел Планирование при развертывании одного пограничного сервера в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="becf0-136">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="becf0-137">Вы развернете пограничный сервер с общедоступными IP-адресами, назначенными пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="becf0-137">You will deploy an Edge Server with public IP addresses assigned to the Edge Server.</span></span> <span data-ttu-id="becf0-138">Вместо NAT вы будете использовать маршрутизацию в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="becf0-138">Instead of NAT, you will use routing in this scenario.</span></span> <span data-ttu-id="becf0-139">Фактический публичный IP-адрес пограничного сервера становится доступным для внешних подключений пользователей.</span><span class="sxs-lookup"><span data-stu-id="becf0-139">The actual public IP address of the Edge Server are made available for external user connections.</span></span></p></td>
<td><p><span data-ttu-id="becf0-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Единая консолидированная пограничная топология с общедоступными IP-адресами в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="becf0-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Single consolidated edge with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="becf0-141">Вы решили, что высокий уровень доступности служб Edge важен для ваших пользователей, и вы развернете в нем несколько пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="becf0-141">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="becf0-142">Вы также планируете использовать частные IP-адреса для внешних интерфейсов пограничного сервера с помощью NAT в Интернете.</span><span class="sxs-lookup"><span data-stu-id="becf0-142">You also intend to use private IP addresses for the Edge Server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="becf0-143">Используйте этот раздел Планирование при развертывании пула пограничных серверов в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="becf0-143">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="becf0-144">Пограничные серверы развертываются с частными IP-адресами, назначенными на пограничном сервере, с помощью балансировки нагрузки DNS для распространения связи между пулом.</span><span class="sxs-lookup"><span data-stu-id="becf0-144">You will deploy the Edge Servers with private IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="becf0-145">Вы будете использовать NAT для предоставления общедоступных IP-адресов внешним пользователям в Интернете.</span><span class="sxs-lookup"><span data-stu-id="becf0-145">You will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="becf0-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Масштабируемая консолидированная пограничная топология, балансировка нагрузки на DNS с закрытыми IP-адресами и трансляцией сетевых адресов в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="becf0-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="becf0-147">Вы решили, что высокий уровень доступности служб Edge важен для ваших пользователей, и вы развернете в нем несколько пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="becf0-147">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="becf0-148">Вы также планируете использовать общедоступные IP-адреса для внешних интерфейсов пограничного сервера в Интернет.</span><span class="sxs-lookup"><span data-stu-id="becf0-148">You also intend to use public IP addresses for the Edge Server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="becf0-149">Используйте этот раздел Планирование при развертывании пула пограничных серверов в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="becf0-149">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="becf0-150">Пограничные серверы развертываются с общедоступными IP-адресами, назначенными на пограничном сервере, с помощью балансировки нагрузки DNS для распространения связи между пулом.</span><span class="sxs-lookup"><span data-stu-id="becf0-150">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="becf0-151">Вместо NAT вы будете использовать маршрутизацию для предоставления общедоступных IP-адресов внешним пользователям в Интернете.</span><span class="sxs-lookup"><span data-stu-id="becf0-151">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="becf0-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Масштабируемая консолидированная пограничная топология, балансировка нагрузки на DNS с общедоступными IP-адресами в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="becf0-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="becf0-153">Вы решили, что у ваших пользователей важна доступность служб EDGE, и вы будете разворачивать несколько пограничных серверов в этом пуле с помощью аппаратной подсистемы балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="becf0-153">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool using a hardware load balancer.</span></span></p>
<p><span data-ttu-id="becf0-154">Используйте этот раздел Планирование при развертывании пула пограничных серверов в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="becf0-154">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="becf0-155">Пограничные серверы будут развернуты с общедоступными IP-адресами, назначенными на пограничном сервере, с помощью балансировки нагрузки аппаратных средств для распространения связи между пулом.</span><span class="sxs-lookup"><span data-stu-id="becf0-155">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using hardware load balancers to distribute communication across the pool.</span></span> <span data-ttu-id="becf0-156">Вместо NAT вы будете использовать маршрутизацию для предоставления общедоступных IP-адресов внешним пользователям в Интернете.</span><span class="sxs-lookup"><span data-stu-id="becf0-156">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="becf0-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Масштабируемая консолидированная пограничная топология с аппаратными балансировщиками нагрузки в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="becf0-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Scaled consolidated edge with hardware load balancers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="becf0-158">Сценарии Федерации позволяют планировать функцию, которая расширяет типы партнеров, с которыми пользователи смогут общаться.</span><span class="sxs-lookup"><span data-stu-id="becf0-158">The federation scenarios allow you to plan for the feature that will extend the types of partners that your users can communicate with.</span></span></p>
<ul>
<li><p><span data-ttu-id="becf0-159">Серверная Федерация Lync Server</span><span class="sxs-lookup"><span data-stu-id="becf0-159">Lync Server federation</span></span></p></li>
<li><p><span data-ttu-id="becf0-160">Серверная Федерация Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="becf0-160">Office Communications Server federation</span></span></p></li>
<li><p><span data-ttu-id="becf0-161">Подключение к общедоступным системам обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="becf0-161">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="becf0-162">КСМПП Федерация</span><span class="sxs-lookup"><span data-stu-id="becf0-162">XMPP federation</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="becf0-163">Планирование сценариев Федерации</span><span class="sxs-lookup"><span data-stu-id="becf0-163">Planning for Federation Scenarios</span></span></p>
<ul>
<li><p><span data-ttu-id="becf0-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Планирование для Lync Server 2013 и Office Communications Server Federation</a></span><span class="sxs-lookup"><span data-stu-id="becf0-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planning for Lync Server 2013 and Office Communications Server federation</a></span></span></p></li>
<li><p><span data-ttu-id="becf0-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Планирование подключения общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="becf0-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planning for public instant messaging connectivity in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="becf0-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Планирование Федерации протоколов обмена сообщениями и присутствия в КСМПП в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="becf0-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="becf0-167">Услуги мобильной связи предлагаются через обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="becf0-167">Mobility services are offered through the reverse proxy.</span></span> <span data-ttu-id="becf0-168">Службы, позволяющие внешним пользователям разворачивать мобильные пользователи на сервере переднего плана или в пуле внешних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="becf0-168">Services that enable mobility for external users are deployed on the Front End Server or Front End pool.</span></span> <span data-ttu-id="becf0-169">Вы можете создать или изменить существующие правила публикации на обратном прокси, чтобы включить службы Mobility Service для внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="becf0-169">You create or modify existing publishing rules on the reverse proxy to enable mobility services for your external users.</span></span></p></td>
<td><p><span data-ttu-id="becf0-170"><a href="lync-server-2013-planning-for-mobility.md">Планирование мобильной работы в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="becf0-170"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> <span data-ttu-id="becf0-171">В следующих разделах описаны архитектуры ссылок, примеры DNS, определения портов и протоколов и требования к сертификатам.</span><span class="sxs-lookup"><span data-stu-id="becf0-171">In the following Scenarios sections are reference architectures, example DNS, port/protocol definitions, and certificate requirements.</span></span> <span data-ttu-id="becf0-172">Кроме того, включены схемы для DNS, определения портов и протоколов и требования сертификата.</span><span class="sxs-lookup"><span data-stu-id="becf0-172">Also included are diagrams for your DNS, port/protocol definitions and certificate needs.</span></span> <span data-ttu-id="becf0-173">Схема предоставит вам шаблон для заполнения и распространения в другие команды (например, Сетевая группа Организации, группа инфраструктуры открытых ключей и группа развертывания сервера).</span><span class="sxs-lookup"><span data-stu-id="becf0-173">The diagrams will provide a template for you to fill in and distribute to other teams (for example, your organization’s Network Team, Public Key Infrastructure Team, and Server Deployment Team).</span></span> <span data-ttu-id="becf0-174">Цель схем — повысить эффективность общения и убедиться в том, что при передаче необходимых элементов конфигурации пограничного сервера для пользователей, которые будут выполнять текущую работу по настройке.</span><span class="sxs-lookup"><span data-stu-id="becf0-174">The goal of the diagrams is to enhance communication and to ensure success when communicating the required Edge Server configuration elements to the people who will do the actual configuration work.</span></span> <span data-ttu-id="becf0-175">Для планирования развертывания мы рекомендуем использовать схемы и связанные с ними эталонные архитектуры.</span><span class="sxs-lookup"><span data-stu-id="becf0-175">We recommend that you use the diagrams and associated reference architectures to plan your deployment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

