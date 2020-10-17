---
title: 'Lync Server 2013: топологии для IP-телефонов'
description: 'Lync Server 2013: топологии для IP-телефонов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a151a83a69e1f7e14dcbed8d8ab1038157fa839
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549135"
---
# <a name="topologies-for-ip-phones-in-lync-server-2013"></a><span data-ttu-id="be8c8-103">Топологии для IP-телефонов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be8c8-103">Topologies for IP phones in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be8c8-104">_**Последнее изменение темы:** 2012-06-21_</span><span class="sxs-lookup"><span data-stu-id="be8c8-104">_**Topic Last Modified:** 2012-06-21_</span></span>

<span data-ttu-id="be8c8-105">В этом разделе приводится обзор процесса подключения и рассматриваются различия в способах подключения IP-телефона во внутренней и внешней сетях.</span><span class="sxs-lookup"><span data-stu-id="be8c8-105">This section provides an overview of the connectivity process and explains the differences between how an IP phone connects in an internal and external network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="be8c8-106">Lync Server обеспечивает поддержку для следующих IP-телефонов: Aastra 6721ip Common Area Phone, Aastra 6725ip стационарный телефон, HP 4110 IP-телефон (телефон с общим доступом), HP 4120 IP-телефон (стационарный телефон), Polycom CX600 IP Desk Phone, Polycom CX700 IP-телефон для конференц-связи Polycom CX500 IP-телефон.</span><span class="sxs-lookup"><span data-stu-id="be8c8-106">Lync Server provides support for the following IP phones: the Aastra 6721ip common area phone, Aastra 6725ip desk phone, HP 4110 IP Phone (common area phone), HP 4120 IP Phone (desk phone), Polycom CX600 IP desk phone, Polycom CX700 IP desk phone, Polycom CX500 IP common area phone, and Polycom CX3000 IP conference phone.</span></span> <span data-ttu-id="be8c8-107">Из этих телефонов все, кроме Polycom CX700, могут запускать Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="be8c8-107">Of those phones, all but the Polycom CX700 can run Lync Phone Edition.</span></span>



</div>

<span data-ttu-id="be8c8-108">На следующей схеме показаны все компоненты, используемые для связи между устройствами в корпоративной среде.</span><span class="sxs-lookup"><span data-stu-id="be8c8-108">The following diagram describes all the components involved in device connectivity within the corporate environment.</span></span>

<span data-ttu-id="be8c8-109">**Внутренняя топология**</span><span class="sxs-lookup"><span data-stu-id="be8c8-109">**Internal Topology**</span></span>

<span data-ttu-id="be8c8-110">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span><span class="sxs-lookup"><span data-stu-id="be8c8-110">![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="be8c8-111">Выше представлена логическая схема, которая не отражает особенности физического размещения.</span><span class="sxs-lookup"><span data-stu-id="be8c8-111">The previous figure is a logical representation, not a physical overview.</span></span> <span data-ttu-id="be8c8-112">Например, доменные службы Active Directory (AD DS) редко располагаются на том же компьютере, что и компоненты Lync Server.</span><span class="sxs-lookup"><span data-stu-id="be8c8-112">For example, Active Directory Domain Services (AD DS) is rarely located on the same machine as any Lync Server components.</span></span> <span data-ttu-id="be8c8-113">Хранилище пользователя может располагаться на тыловом сервере или на сервере архивации и наблюдения.</span><span class="sxs-lookup"><span data-stu-id="be8c8-113">The user store can be located on the Back End Server or on the Archiving and Monitoring Servers.</span></span> <span data-ttu-id="be8c8-114">Консоль управления Lync Server, веб-сервер и службы обновления являются частью роли сервера переднего плана.</span><span class="sxs-lookup"><span data-stu-id="be8c8-114">The Lync Server Management Shell, web server, and update services are all part of the Front End Server role.</span></span>



</div>

<span data-ttu-id="be8c8-115">На следующей схеме приводится обзор компонентов, используемых в том случае, если устройство находится за пределами корпоративной сети.</span><span class="sxs-lookup"><span data-stu-id="be8c8-115">The following diagram provides an overview of the components involved when the device is located outside the corporate network.</span></span>

<span data-ttu-id="be8c8-116">**Внешняя топология**</span><span class="sxs-lookup"><span data-stu-id="be8c8-116">**External Topology**</span></span>

<span data-ttu-id="be8c8-117">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span><span class="sxs-lookup"><span data-stu-id="be8c8-117">![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="be8c8-118">Веб-служба обновления устройств предоставляет внешний и внутренний веб-сайты, но здесь показан только внешний веб-сайт.</span><span class="sxs-lookup"><span data-stu-id="be8c8-118">The Device Update Web service provides an external and internal website, but only the external one is shown here.</span></span><BR><span data-ttu-id="be8c8-p103">Если планируется включать внешний доступ, в DNS необходимо опубликовать расположение Регистратора и URL-адрес веб-службы обновления устройств для организации. Кроме того, для обеспечения внешних подключений устройств к корпоративной среде и наоборот нужно развернуть и правильно настроить пограничный сервер. На предыдущей схеме этот компонент не показан, поскольку развертывание пограничного сервера не является необходимым для подключения устройств.</span><span class="sxs-lookup"><span data-stu-id="be8c8-p103">The location of the Registrar and the URL of the Device Update Web service for the organization must be published in DNS if external access is to be enabled. Additionally, the Edge Server must be deployed and correctly configured to allow external communications from the device to the corporate environment and back. This is omitted from the previous diagram because Edge deployment is not specific to device connectivity.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

