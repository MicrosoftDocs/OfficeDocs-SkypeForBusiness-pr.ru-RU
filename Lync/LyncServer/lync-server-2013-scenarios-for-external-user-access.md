---
title: 'Lync Server 2013: сценарии для доступа внешних пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e9a2f60b2273cf8d43833226ede66a2a90478a6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="fda15-102">Сценарии доступа внешних пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fda15-102">Scenarios for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fda15-103">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="fda15-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="fda15-104">Для предоставления доступа внешним пользователям для Lync Server 2013 необходимо развернуть хотя бы один пограничный сервер и один обратный прокси в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="fda15-104">Providing external user access for Lync Server 2013 requires that you deploy at least one Edge Server and one reverse proxy in your perimeter network.</span></span> <span data-ttu-id="fda15-105">При необходимости вы можете развернуть директор или пул директоров во внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="fda15-105">Optionally, you may deploy a Director or Director pool in your internal network.</span></span>

<span data-ttu-id="fda15-106">Если требуется больше ресурсов, чем один пограничный сервер, или если требуется высокая доступность для развертывания пограничного сервера, можно настроить балансировку нагрузки и развернуть несколько пограничных серверов в пуле с балансировкой нагрузки.</span><span class="sxs-lookup"><span data-stu-id="fda15-106">If you need greater capacity than a single Edge Server can provide, or if you need high availability for your Edge Server deployment, you can configure load balancing and deploy multiple Edge Servers in a load balanced pool.</span></span> <span data-ttu-id="fda15-107">Если в организации используется несколько центров обработки данных, можно использовать развертывания пограничного сервера или пограничного пула в нескольких расположениях.</span><span class="sxs-lookup"><span data-stu-id="fda15-107">If your organization has multiple data centers, you can have Edge Server or Edge pool deployments at more than one location.</span></span> <span data-ttu-id="fda15-108">Однако в качестве маршрута Федерации можно назначить только одно из развертываний пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="fda15-108">However, only one of the Edge Server deployments can be designated as the federation route.</span></span>

<span data-ttu-id="fda15-109">В этом разделе определяются сценарии для развертываний пограничных серверов и сопоставлены с возможными сценариями разделы планирования.</span><span class="sxs-lookup"><span data-stu-id="fda15-109">This section defines the scenarios for Edge Server deployments and maps the planning sections to the possible scenarios.</span></span> <span data-ttu-id="fda15-110">Например, если для развертывания требуется высокая доступность, Федерация с контактами с расширенной системой обмена сообщениями и присутствием (XMPP), а также Lync Mobility, выберите соответствующие записи в следующей таблице, которые удовлетворяют этим требованиям, и используйте разделы планирования, на которые указывают ссылки, чтобы определить развертывание, как показано в следующей блок-схеме.</span><span class="sxs-lookup"><span data-stu-id="fda15-110">For example, if your deployment requires high availability, federation with extensible messaging and presence (XMPP) contacts, and Lync mobility, you would select the matching entries in the following table that would satisfy these requirements and use the referenced planning sections to define your deployment, as illustrated in the following flowchart.</span></span>

<span data-ttu-id="fda15-111">**Процесс выбора сценария развертывания пограничного сервера**</span><span class="sxs-lookup"><span data-stu-id="fda15-111">**Edge Server deployment scenario selection process**</span></span>

<span data-ttu-id="fda15-112">![Пример блок-схемы развертывания](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Пример блок-схемы развертывания")</span><span class="sxs-lookup"><span data-stu-id="fda15-112">![Sample deployment flowchart](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Sample deployment flowchart")</span></span>

<span data-ttu-id="fda15-113">С помощью этого процесса можно запланировать и задокументировать конфигурацию всех потенциальных функций, которые планируется развернуть для пользователей.</span><span class="sxs-lookup"><span data-stu-id="fda15-113">By using this process, you can plan for and document the configuration of all potential features that you intend to deploy for your users.</span></span> <span data-ttu-id="fda15-114">Однако вы можете добавить службы федерации и Mobility Services после развертывания пограничного сервера и подтверждения правильной операции перед добавлением других компонентов.</span><span class="sxs-lookup"><span data-stu-id="fda15-114">However, you can add federation and mobility services after you have deployed the Edge Server and have confirmed the correct operation before adding other features.</span></span> <span data-ttu-id="fda15-115">Процесс добавления компонентов к существующему развертыванию пограничного сервера рассматривается в разделе Deployment.</span><span class="sxs-lookup"><span data-stu-id="fda15-115">The process of adding features to an existing Edge Server deployment is covered in the Deployment section.</span></span> <span data-ttu-id="fda15-116">Подробнее о развертывании можно узнать в статье [развертывание доступа внешних пользователей в Lync Server 2013](lync-server-2013-deploying-external-user-access.md) , включив в него планирование для этих компонентов в процессе первоначального планирования, вы можете подготовиться к DNS, брандмауэру и сертификатам, предъявляемым к дополнительным функциям, которые позволяют получить сертификаты и настроить требования к DNS и порту/протоколу заранее.</span><span class="sxs-lookup"><span data-stu-id="fda15-116">For details on deployment, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) By including planning for these features during the initial planning process, you can prepare for the DNS, firewall, and certificate requirements for the added features, which enables you to acquire the certificates and configure DNS and port/protocol requirements in advance.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="fda15-117">Если вы планируете установить пограничные серверы и обратный прокси-сервер, а затем добавить компоненты позже (например, Федерацию и мобильность), определите, какие сертификаты потребуется выполнить для всех служб после развертывания.</span><span class="sxs-lookup"><span data-stu-id="fda15-117">If you are planning to install the Edge Servers and reverse proxy and then add features later (for example, federation and mobility), determine what certificates you will require for all services after deployment.</span></span> <span data-ttu-id="fda15-118">При планировании и получении сертификатов для всех функций, изначально развернутых, изначально развернутых и не следует заказывать новые сертификаты для удовлетворения требований Федерации (то есть на пограничных серверах) или обратном прокси-сервере (то есть для мобильных устройств). Services).</span><span class="sxs-lookup"><span data-stu-id="fda15-118">Planning for and acquiring the certificates for all features in advance, initially deployed or not, saves you from having to order new certificates to satisfy the requirements of federation (that is, on the Edge Servers) or the reverse proxy (that is, for mobility services).</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="fda15-119">Все пограничные службы выполняются на каждом пограничном сервере.</span><span class="sxs-lookup"><span data-stu-id="fda15-119">All edge services run on each Edge Server.</span></span> <span data-ttu-id="fda15-120">Службы не могут быть разделены между двумя разными пограничными серверами.</span><span class="sxs-lookup"><span data-stu-id="fda15-120">Services cannot be split between two different Edge Servers.</span></span> <span data-ttu-id="fda15-121">При развертывании пограничных пулов для обеспечения масштабируемости все пограничные службы развертываются на каждом пограничном сервере в пуле.</span><span class="sxs-lookup"><span data-stu-id="fda15-121">If you deploy an Edge pool for scalability, all edge services are deployed on each Edge Server in the pool.</span></span> <span data-ttu-id="fda15-122">XMPP Федерация, Office Communications Server и Федерация Lync Server, общедоступные возможности обмена мгновенными сообщениями и мобильности клиентов — это дополнительные службы, которые можно развертывать после развертывания первого пограничного сервера или пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="fda15-122">XMPP federation, Office Communications Server, and Lync Server federation, public IM connectivity and client mobility are additional services that can be deployed after you have deployed your first Edge Server or Edge pool.</span></span> <span data-ttu-id="fda15-123">Мобильные службы — это функция, использующая обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="fda15-123">Mobility services is a feature that uses the reverse proxy.</span></span> <span data-ttu-id="fda15-124">Установка служб Mobility Services не будет добавлять компоненты на пограничные серверы, но потребуется перенастроить обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="fda15-124">Installation of mobility services will not add features to your Edge Servers, but will require reconfiguration of your reverse proxy.</span></span> <span data-ttu-id="fda15-125">В столбце <STRONG>Цель установки</STRONG> , в котором перечислены эти функции, представлено руководство по планированию в связанном столбце <STRONG>раздела Планирование пограничного сервера или разделов</STRONG> для параллельного планирования этих функций при установке и настройке пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="fda15-125">The <STRONG>Installation goal</STRONG> column that lists these features provides planning guidance in the associated column under <STRONG>Edge Server planning section or sections</STRONG> for concurrently planning these features to be deployed when the Edge Servers are installed and configured.</span></span>



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a><span data-ttu-id="fda15-126">Определение целей развертывания и сопоставление с ними</span><span class="sxs-lookup"><span data-stu-id="fda15-126">Identifying and Mapping Your Deployment Goals</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fda15-127">Цель установки</span><span class="sxs-lookup"><span data-stu-id="fda15-127">Installation goal</span></span></th>
<th><span data-ttu-id="fda15-128">Документация по планированию пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="fda15-128">Edge Server planning documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fda15-p107">Вы решили, что для пограничных служб в вашей инфраструктуре достаточно одного сервера. Вы также собираетесь использовать частные IP-адреса для внешних интерфейсов с NAT для подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="fda15-p107">You have decided that a single server is sufficient for Edge services in your infrastructure. You also intend to use private IP addresses for the Edge server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="fda15-131">Используйте этот раздел планирования при развертывании одного пограничного сервера в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="fda15-131">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="fda15-132">Будет развернут пограничный сервер с частными IP-адресами, назначенными для пограничного сервера, и будет использоваться преобразование сетевых адресов для предоставления общедоступных IP-адресов для внешних пользователей в Интернете.</span><span class="sxs-lookup"><span data-stu-id="fda15-132">You will deploy an Edge Server with private IP addresses assigned to the Edge Server and will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="fda15-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Единый консолидированный край с частными IP-адресами и NAT в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fda15-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fda15-p109">Вы решили, что для пограничных служб в вашей инфраструктуре достаточно одного сервера. Вы также собираетесь использовать общедоступные IP-адреса для внешних интерфейсов для подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="fda15-p109">You have decided that a single server is sufficient for Edge services in your infrastructure. You also intend to use public IP addresses for the Edge server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="fda15-136">Используйте этот раздел планирования при развертывании одного пограничного сервера в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="fda15-136">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="fda15-137">Будет развернут пограничный сервер с общедоступными IP-адресами, назначенными пограничным сервером.</span><span class="sxs-lookup"><span data-stu-id="fda15-137">You will deploy an Edge Server with public IP addresses assigned to the Edge Server.</span></span> <span data-ttu-id="fda15-138">Вместо NAT в этим сценарии вы будете использовать маршрутизацию.</span><span class="sxs-lookup"><span data-stu-id="fda15-138">Instead of NAT, you will use routing in this scenario.</span></span> <span data-ttu-id="fda15-139">Фактический общедоступный IP-адрес пограничного сервера становится доступным для подключений внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="fda15-139">The actual public IP address of the Edge Server are made available for external user connections.</span></span></p></td>
<td><p><span data-ttu-id="fda15-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Единый консолидированный край с общедоступными IP-адресами в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fda15-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Single consolidated edge with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fda15-p111">Вы решили, что высокая доступность пограничных служб имеет большое значение для пользователей, и развернете два или более пограничных серверов в этом пуле. Вы также планируете использовать частные IP-адреса для внешних интерфейсов с NAT для подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="fda15-p111">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool. You also intend to use private IP addresses for the Edge Server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="fda15-143">Используйте этот раздел планирования при развертывании пула пограничных серверов в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="fda15-143">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="fda15-144">Пограничные серверы будут развернуты с частными IP-адресами, назначенными пограничным сервером, с помощью балансировки нагрузки на DNS для распространения связи в пуле.</span><span class="sxs-lookup"><span data-stu-id="fda15-144">You will deploy the Edge Servers with private IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="fda15-145">Вы будете использовать NAT для предоставления общедоступных IP-адресов внешним пользователям в целях доступа через Интернет.</span><span class="sxs-lookup"><span data-stu-id="fda15-145">You will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="fda15-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Масштабируемый консолидированный край, балансировка нагрузки на DNS с частными IP-адресами, использующими NAT, в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fda15-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fda15-147">Вы решили, что высокая доступность пограничных служб имеет большое значение для пользователей, и развернете два или более пограничных серверов в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="fda15-147">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="fda15-148">Кроме того, вы планируете использовать общедоступные IP-адреса для внешних интерфейсов пограничного сервера в Интернет.</span><span class="sxs-lookup"><span data-stu-id="fda15-148">You also intend to use public IP addresses for the Edge Server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="fda15-149">Используйте этот раздел планирования при развертывании пула пограничных серверов в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="fda15-149">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="fda15-150">Будут развернуты пограничные серверы с общедоступными IP-адресами, назначенными пограничным сервером, с помощью балансировки нагрузки на DNS для распространения связи в пуле.</span><span class="sxs-lookup"><span data-stu-id="fda15-150">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="fda15-151">Вместо NAT вы будете использовать маршрутизацию для предоставления общедоступных IP-адресов внешним пользователям в целях доступа через Интернет.</span><span class="sxs-lookup"><span data-stu-id="fda15-151">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="fda15-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Масштабируемый консолидированный край, балансировка нагрузки на DNS с общедоступными IP-адресами в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fda15-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fda15-153">Вы решили, что высокий уровень доступности пограничных служб важен для ваших пользователей, и вы развернете в этом пуле два или более пограничных сервера с помощью аппаратной подсистемы балансировки нагрузки.</span><span class="sxs-lookup"><span data-stu-id="fda15-153">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool using a hardware load balancer.</span></span></p>
<p><span data-ttu-id="fda15-154">Используйте этот раздел планирования при развертывании пула пограничных серверов в сети периметра.</span><span class="sxs-lookup"><span data-stu-id="fda15-154">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="fda15-155">Будут развернуты пограничные серверы с общедоступными IP-адресами, назначенными пограничным сервером, с помощью аппаратных подсистем балансировки нагрузки для распространения связи в пуле.</span><span class="sxs-lookup"><span data-stu-id="fda15-155">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using hardware load balancers to distribute communication across the pool.</span></span> <span data-ttu-id="fda15-156">Вместо NAT вы будете использовать маршрутизацию для предоставления общедоступных IP-адресов внешним пользователям в целях доступа через Интернет.</span><span class="sxs-lookup"><span data-stu-id="fda15-156">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="fda15-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Масштабируемая консолидированная пограничная система с аппаратными подсистемами балансировки нагрузки в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fda15-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Scaled consolidated edge with hardware load balancers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fda15-158">Сценарии федерации позволяют планировать включение функции, расширяющей возможные типы партнеров, с которыми могут взаимодействовать пользователи.</span><span class="sxs-lookup"><span data-stu-id="fda15-158">The federation scenarios allow you to plan for the feature that will extend the types of partners that your users can communicate with.</span></span></p>
<ul>
<li><p><span data-ttu-id="fda15-159">Федерация Lync Server</span><span class="sxs-lookup"><span data-stu-id="fda15-159">Lync Server federation</span></span></p></li>
<li><p><span data-ttu-id="fda15-160">Федерация Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="fda15-160">Office Communications Server federation</span></span></p></li>
<li><p><span data-ttu-id="fda15-161">Возможность подключения к общедоступным службам обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="fda15-161">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="fda15-162">Федерация XMPP</span><span class="sxs-lookup"><span data-stu-id="fda15-162">XMPP federation</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="fda15-163">Планирование для сценариев федерации</span><span class="sxs-lookup"><span data-stu-id="fda15-163">Planning for Federation Scenarios</span></span></p>
<ul>
<li><p><span data-ttu-id="fda15-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Планирование интеграции Lync Server 2013 и Office Communications Server</a></span><span class="sxs-lookup"><span data-stu-id="fda15-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planning for Lync Server 2013 and Office Communications Server federation</a></span></span></p></li>
<li><p><span data-ttu-id="fda15-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Планирование подключений к общедоступным службам обмена мгновенными сообщениями в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fda15-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planning for public instant messaging connectivity in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="fda15-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Планирование Федерации XMPP (Extensible Messaging and Presence Protocol) в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fda15-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fda15-167">Мобильные службы предоставляются посредством обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="fda15-167">Mobility services are offered through the reverse proxy.</span></span> <span data-ttu-id="fda15-168">Службы, обеспечивающие мобильность для внешних пользователей, развертываются на сервере переднего плана или интерфейсном пуле.</span><span class="sxs-lookup"><span data-stu-id="fda15-168">Services that enable mobility for external users are deployed on the Front End Server or Front End pool.</span></span> <span data-ttu-id="fda15-169">Вы создаете или изменяете существующие правила публикации на обратном прокси-сервере для предоставления мобильных служб внешним пользователям.</span><span class="sxs-lookup"><span data-stu-id="fda15-169">You create or modify existing publishing rules on the reverse proxy to enable mobility services for your external users.</span></span></p></td>
<td><p><span data-ttu-id="fda15-170"><a href="lync-server-2013-planning-for-mobility.md">Планирование мобильной работы в Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="fda15-170"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> <span data-ttu-id="fda15-171">С следующих разделах представлены сценарии с указанием соответствующих архитектур, примеров DNS, определений портов и протоколов, а также требований к сертификатам.</span><span class="sxs-lookup"><span data-stu-id="fda15-171">In the following Scenarios sections are reference architectures, example DNS, port/protocol definitions, and certificate requirements.</span></span> <span data-ttu-id="fda15-172">Также разделы включают схемы для конкретных потребностей в отношении DNS, определений портов/протоколов и сертификатов.</span><span class="sxs-lookup"><span data-stu-id="fda15-172">Also included are diagrams for your DNS, port/protocol definitions and certificate needs.</span></span> <span data-ttu-id="fda15-173">Эти схемы представляют собой шаблоны, которые следует заполнить и предоставить представителям других отделов (например, представителям отдела сетевого обслуживания, отдела инфраструктуры открытых ключей и отдела развертывания серверов).</span><span class="sxs-lookup"><span data-stu-id="fda15-173">The diagrams will provide a template for you to fill in and distribute to other teams (for example, your organization’s Network Team, Public Key Infrastructure Team, and Server Deployment Team).</span></span> <span data-ttu-id="fda15-174">Цель схем заключается в том, чтобы повысить эффективность обмена данными и обеспечить успешную передачу необходимых элементов конфигурации пограничного сервера для пользователей, выполняющих фактическую работу по настройке.</span><span class="sxs-lookup"><span data-stu-id="fda15-174">The goal of the diagrams is to enhance communication and to ensure success when communicating the required Edge Server configuration elements to the people who will do the actual configuration work.</span></span> <span data-ttu-id="fda15-175">Мы рекомендуем использовать схемы и соответствующие архитектуры для планирования развертывания.</span><span class="sxs-lookup"><span data-stu-id="fda15-175">We recommend that you use the diagrams and associated reference architectures to plan your deployment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

