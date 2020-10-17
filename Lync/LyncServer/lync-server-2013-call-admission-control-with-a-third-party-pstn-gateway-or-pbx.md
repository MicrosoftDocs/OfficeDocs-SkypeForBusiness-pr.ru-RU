---
title: Контроль допуска звонков с помощью стороннего шлюза PSTN или УАТС
description: Контроль допуска звонков с помощью стороннего шлюза PSTN или УАТС.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control with a third-party PSTN gateway or PBX
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48184850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aaab42992047ecedcc00ea1ecf5cf69023e51097
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545665"
---
# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="a3324-103">Контроль допуска звонков в Lync Server 2013 со сторонним шлюзом PSTN или УАТС</span><span class="sxs-lookup"><span data-stu-id="a3324-103">Call admission control in Lync Server 2013 with a third-party PSTN gateway or PBX</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3324-104">_**Последнее изменение темы:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="a3324-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="a3324-105">В этом разделе описываются примеры развертывания контроля допуска звонков (CAC) на канале между интерфейсом шлюза сервера-посредника и сторонним шлюзом ТСОП или УАТС.</span><span class="sxs-lookup"><span data-stu-id="a3324-105">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server’s gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="a3324-106">Случай 1. Контроль допуска звонков между сервером-посредником и шлюзом ТСОП</span><span class="sxs-lookup"><span data-stu-id="a3324-106">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="a3324-107">Контроль допуска звонков можно развернуть на канале глобальной сети, связывающем интерфейс шлюза сервера-посредника и сторонний шлюз ТСОП или УАТС.</span><span class="sxs-lookup"><span data-stu-id="a3324-107">CAC can be deployed on the WAN link from the Mediation Server’s gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="a3324-108">**Случай 1. Контроль допуска звонков между сервером-посредником и шлюзом ТСОП**</span><span class="sxs-lookup"><span data-stu-id="a3324-108">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

<span data-ttu-id="a3324-109">![Вариант 1: CAC между шлюзами сервер-посредника PSTN](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Вариант 1: CAC между шлюзами сервер-посредника PSTN")</span><span class="sxs-lookup"><span data-stu-id="a3324-109">![Case 1: CAC between Mediation Server PSTN Gateway](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Case 1: CAC between Mediation Server PSTN Gateway")</span></span>

<span data-ttu-id="a3324-p101">В этом примере контроль допуска звонков реализуется между сервером-посредником и шлюзом ТСОП. Если пользователь клиента Lync в сетевом узле 1 совершает звонок ТСОП через шлюз ТСОП в сетевом узле 2, данные передаются через канал глобальной сети. Поэтому для каждого сеанса ТСОП выполняются две проверки контроля допуска звонков:</span><span class="sxs-lookup"><span data-stu-id="a3324-p101">In this example, CAC is applied between the Mediation Server and a PSTN gateway. If a Lync client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link. Therefore, two CAC checks are performed for each PSTN session:</span></span>

  - <span data-ttu-id="a3324-113">между клиентским приложением Lync и сервером-посредником;</span><span class="sxs-lookup"><span data-stu-id="a3324-113">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="a3324-114">между сервером-посредником и шлюзом ТСОП.</span><span class="sxs-lookup"><span data-stu-id="a3324-114">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="a3324-115">Проверки выполняются как для входящих звонков ТСОП, поступающих в клиент в сетевом узле 1, так и для исходящих звонков ТСОП из клиентского приложения в сетевом узле 1.</span><span class="sxs-lookup"><span data-stu-id="a3324-115">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="a3324-116">Убедитесь в том, что IP-подсеть, к которой относится шлюз ТСОП, настроена и связана с сетевым узлом 2.</span><span class="sxs-lookup"><span data-stu-id="a3324-116">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="a3324-117">Убедитесь в том, что IP-подсеть, к которой относятся оба интерфейса сервера-посредника, настроена и связана с сетевым узлом 1.</span><span class="sxs-lookup"><span data-stu-id="a3324-117">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="a3324-118">Дополнительные сведения см. <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">в разделе Связывание подсети с сетевым сайтом в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a3324-118">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="a3324-119">Случай 2. Контроль допуска звонков между сервером-посредником и сторонней УАТС с точкой Media Termination Point</span><span class="sxs-lookup"><span data-stu-id="a3324-119">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="a3324-p102">Эта конфигурация аналогична случаю 1. В обоих случаях серверу-посреднику известно, какое устройство является конечным на противоположном конце канала глобальной сети, и IP-адрес шлюза ТСОП или УАТС с точкой Media Termination Point (MTP) настраивается на сервере-посреднике как следующий прыжок.</span><span class="sxs-lookup"><span data-stu-id="a3324-p102">This configuration is similar to Case 1. In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="a3324-122">**Случай 2. Контроль допуска звонков между сервером-посредником и сторонней УАТС с точкой MTP**</span><span class="sxs-lookup"><span data-stu-id="a3324-122">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

<span data-ttu-id="a3324-123">![Вариант 2: CAC между УАТС между серверами-посредниками и MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Вариант 2: CAC между УАТС между серверами-посредниками и MTP")</span><span class="sxs-lookup"><span data-stu-id="a3324-123">![Case 2: CAC between Mediation Server PBX with MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Case 2: CAC between Mediation Server PBX with MTP")</span></span>

<span data-ttu-id="a3324-p103">В этом примере контроль допуска звонков реализуется между сервером-посредником и УАТС с точкой MTP. Если пользователь клиента Lync в сетевом узле 1 совершает звонок ТСОП через УАТС с точкой MTP в сетевом узле 2, данные передаются через канал глобальной сети. Поэтому для каждого сеанса ТСОП выполняются две проверки контроля допуска звонков:</span><span class="sxs-lookup"><span data-stu-id="a3324-p103">In this example, CAC is applied between the Mediation Server and the PBX/MTP. If a Lync client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link. Therefore, for each PSTN session two CAC checks are performed:</span></span>

  - <span data-ttu-id="a3324-127">между клиентским приложением Lync и сервером-посредником;</span><span class="sxs-lookup"><span data-stu-id="a3324-127">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="a3324-128">между сервером-посредником и УАТС с точкой MTP.</span><span class="sxs-lookup"><span data-stu-id="a3324-128">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="a3324-129">Проверки выполняются как для входящих звонков ТСОП, поступающих в клиент в сетевом узле 1, так и для исходящих звонков ТСОП из клиента в сетевом узле 1.</span><span class="sxs-lookup"><span data-stu-id="a3324-129">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="a3324-130">Убедитесь в том, что IP-подсеть, к которой относится точка MTP, настроена и связана с сетевым узлом 2.</span><span class="sxs-lookup"><span data-stu-id="a3324-130">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="a3324-131">Убедитесь в том, что IP-подсеть, к которой относятся оба интерфейса сервера-посредника, настроена и связана с сетевым узлом 1.</span><span class="sxs-lookup"><span data-stu-id="a3324-131">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="a3324-132">Дополнительные сведения см. <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">в разделе Связывание подсети с сетевым сайтом в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a3324-132">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="a3324-133">Случай 3. Контроль допуска звонков между сервером-посредником и сторонней УАТС без точки Media Termination Point</span><span class="sxs-lookup"><span data-stu-id="a3324-133">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="a3324-p104">Случай 3 немного отличается от первых двух. Если на сторонней УАТС отсутствует точка MTP, то при выполнении запроса исходящего сеанса к сторонней УАТС серверу-посреднику неизвестно, куда поступят данные в пределах УАТС. В этом случае данные передаются непосредственно между сервером-посредником и сторонним конечным устройством.</span><span class="sxs-lookup"><span data-stu-id="a3324-p104">Case 3 is slightly different from the first two cases. If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary. In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="a3324-137">**Случай 3. Контроль допуска звонков между сервером-посредником и сторонней УАТС без точки MTP**</span><span class="sxs-lookup"><span data-stu-id="a3324-137">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

<span data-ttu-id="a3324-138">![Case 3: CAC между УАТС сервера-посредника без MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Case 3: CAC между УАТС сервера-посредника без MTP")</span><span class="sxs-lookup"><span data-stu-id="a3324-138">![Case 3: CAC between Mediation Server PBX no MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Case 3: CAC between Mediation Server PBX no MTP")</span></span>

<span data-ttu-id="a3324-p105">В этом примере, если пользователь клиента Lync в сетевом узле 1 совершает звонок другому пользователю через УАТС, сервер-посредник может выполнить проверки контроля допуска звонков только на участке прокси (между клиентским приложением Lync и сервером-посредником). Поскольку сервер-посредник не имеет сведений о конечном устройстве при запросе сеанса, проверки контроля допуска звонков нельзя выполнить на канале глобальной сети (между сервером-посредником и сторонним устройством) до того, как звонок будет установлен. Однако после установки сеанса серверу-посреднику проще контролировать используемую пропускную способность магистрали.</span><span class="sxs-lookup"><span data-stu-id="a3324-p105">In this example, if a Lync client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Lync client application and Mediation Server). Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment. After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="a3324-142">Если звонки исходят со сторонней конечной точки, информация об устройстве становится доступна в момент выполнения запроса сеанса, после чего проверки контроля допуска звонков можно выполнить на обеих сторонах сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="a3324-142">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="a3324-143">Убедитесь в том, что IP-подсеть, к которой относятся устройства конечных точек, настроена и связана с сетевым узлом 2.</span><span class="sxs-lookup"><span data-stu-id="a3324-143">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="a3324-144">Убедитесь в том, что IP-подсеть, к которой относятся оба интерфейса сервера-посредника, настроена и связана с сетевым узлом 1.</span><span class="sxs-lookup"><span data-stu-id="a3324-144">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="a3324-145">Дополнительные сведения см. <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">в разделе Связывание подсети с сетевым сайтом в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a3324-145">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

