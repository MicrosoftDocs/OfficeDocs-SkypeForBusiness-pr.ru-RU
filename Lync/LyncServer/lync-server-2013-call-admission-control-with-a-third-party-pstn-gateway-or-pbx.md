---
title: Контроль допуска звонков с помощью стороннего шлюза ТСОП или УАТС
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control with a third-party PSTN gateway or PBX
ms:assetid: 95dc4ceb-bcad-48ee-86ec-af911727f853
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398762(v=OCS.15)
ms:contentKeyID: 48184850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1996b56a50dbe616c8dc6e9b9b1c779c564b185
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-in-lync-server-2013-with-a-third-party-pstn-gateway-or-pbx"></a><span data-ttu-id="d9e79-102">Контроль допуска звонков с помощью стороннего шлюза ТСОП или УАТС в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9e79-102">Call admission control in Lync Server 2013 with a third-party PSTN gateway or PBX</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9e79-103">_**Тема последнего изменения:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="d9e79-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="d9e79-104">В этом разделе описываются примеры развертывания контроля допуска звонков (CAC) на канале между интерфейсом шлюза сервера-посредника и сторонним шлюзом ТСОП или УАТС.</span><span class="sxs-lookup"><span data-stu-id="d9e79-104">This topic describes examples of how call admission control (CAC) can be deployed on the link between the Mediation Server’s gateway interface and a third-party public switched telephone network (PSTN) gateway or private branch exchange (PBX).</span></span>

<div>

## <a name="case-1-cac-between-the-mediation-server-and-a-pstn-gateway"></a><span data-ttu-id="d9e79-105">Случай 1. Контроль допуска звонков между сервером-посредником и шлюзом ТСОП</span><span class="sxs-lookup"><span data-stu-id="d9e79-105">Case 1: CAC between the Mediation Server and a PSTN gateway</span></span>

<span data-ttu-id="d9e79-106">Контроль допуска звонков можно развернуть на канале глобальной сети, связывающем интерфейс шлюза сервера-посредника и сторонний шлюз ТСОП или УАТС.</span><span class="sxs-lookup"><span data-stu-id="d9e79-106">CAC can be deployed on the WAN link from the Mediation Server’s gateway interface to a third-party PBX or PSTN gateway.</span></span>

<span data-ttu-id="d9e79-107">**Случай 1. Контроль допуска звонков между сервером-посредником и шлюзом ТСОП**</span><span class="sxs-lookup"><span data-stu-id="d9e79-107">**Case 1: CAC between the Mediation Server and a PSTN gateway**</span></span>

<span data-ttu-id="d9e79-108">![Случай 1: CAC между сервером посредников и шлюзом PSTN] (images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Случай 1: CAC между сервером посредников и шлюзом PSTN")</span><span class="sxs-lookup"><span data-stu-id="d9e79-108">![Case 1: CAC between Mediation Server PSTN Gateway](images/Gg398762.4bebf9ee-2732-4ea6-bbe5-0269b2903d8c(OCS.15).jpg "Case 1: CAC between Mediation Server PSTN Gateway")</span></span>

<span data-ttu-id="d9e79-109">В этом примере для сервера-посредника и шлюза PSTN применяется CAC.</span><span class="sxs-lookup"><span data-stu-id="d9e79-109">In this example, CAC is applied between the Mediation Server and a PSTN gateway.</span></span> <span data-ttu-id="d9e79-110">Если пользователь клиента Lync на сетевом сайте 1 размещает КОММУТИРУЕМый Звонок через шлюз PSTN в сетевом сайте 2, мультимедиа проходит через ГЛОБАЛЬную сеть.</span><span class="sxs-lookup"><span data-stu-id="d9e79-110">If a Lync client user at Network Site 1 places a PSTN call through the PSTN gateway in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="d9e79-111">Поэтому для каждого сеанса ТСОП выполняются две проверки контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="d9e79-111">Therefore, two CAC checks are performed for each PSTN session:</span></span>

  - <span data-ttu-id="d9e79-112">Между клиентским приложением Lync и сервером обновлений</span><span class="sxs-lookup"><span data-stu-id="d9e79-112">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="d9e79-113">Между сервером исправлений и шлюзом PSTN</span><span class="sxs-lookup"><span data-stu-id="d9e79-113">Between the Mediation Server and the PSTN gateway</span></span>

<span data-ttu-id="d9e79-114">Проверки выполняются как для входящих звонков ТСОП, поступающих в клиент на сетевом сайте 1, так и для исходящих звонков ТСОП из клиентского приложения на сетевом сайте 1.</span><span class="sxs-lookup"><span data-stu-id="d9e79-114">This works for both incoming PSTN calls to a client in Network Site 1, and for outgoing PSTN calls originating from a client application in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d9e79-115">Убедитесь в том, что IP-подсеть, к которой относится шлюз ТСОП, настроена и связана с сетевым сайтом 2.</span><span class="sxs-lookup"><span data-stu-id="d9e79-115">Make sure that the IP subnet that the PSTN gateway belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="d9e79-116">Убедитесь, что IP-подсеть, к которой принадлежат оба интерфейса сервера-посредника, настроена и соответствует сетевому сайту 1.</span><span class="sxs-lookup"><span data-stu-id="d9e79-116">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="d9e79-117">Дополнительные сведения можно найти <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">в разделе Связывание подсети с сетевым сайтом в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d9e79-117">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-2-cac-between-the-mediation-server-and-a-third-party-pbx-with-media-termination-point"></a><span data-ttu-id="d9e79-118">Случай 2: CAC между сервером-посредником и сторонней АТС с точкой завершения мультимедиа</span><span class="sxs-lookup"><span data-stu-id="d9e79-118">Case 2: CAC between the Mediation Server and a third-party PBX with Media Termination Point</span></span>

<span data-ttu-id="d9e79-119">Эта конфигурация аналогична случаю 1.</span><span class="sxs-lookup"><span data-stu-id="d9e79-119">This configuration is similar to Case 1.</span></span> <span data-ttu-id="d9e79-120">В обоих случаях сервер-посредник определяет, какое устройство завершает работу с мультимедиа на противоположном конце ссылки WAN, и IP-адрес шлюза PSTN или УАТС с точкой завершения (MTP) настроен на сервере-посреднике в качестве следующего прыжка.</span><span class="sxs-lookup"><span data-stu-id="d9e79-120">In both the cases, the Mediation Server knows what device terminates media at the opposite end of the WAN link, and the IP address of the PSTN gateway or PBX with Media Termination Point (MTP) is configured on the Mediation Server as the next hop.</span></span>

<span data-ttu-id="d9e79-121">**Случай 2. Контроль допуска звонков между сервером-посредником и сторонней УАТС с точкой MTP**</span><span class="sxs-lookup"><span data-stu-id="d9e79-121">**Case 2: CAC between the Mediation Server and a third-party PBX with MTP**</span></span>

<span data-ttu-id="d9e79-122">![Случай 2: CAC между серверными АТС с помощью MTP] (images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Случай 2: CAC между серверными АТС с помощью MTP")</span><span class="sxs-lookup"><span data-stu-id="d9e79-122">![Case 2: CAC between Mediation Server PBX with MTP](images/Gg398762.1c0b5263-c053-4cca-842f-85dd670760c8(OCS.15).jpg "Case 2: CAC between Mediation Server PBX with MTP")</span></span>

<span data-ttu-id="d9e79-123">В этом примере для сервера-посредника и УАТС (MTP) применяется CAC.</span><span class="sxs-lookup"><span data-stu-id="d9e79-123">In this example, CAC is applied between the Mediation Server and the PBX/MTP.</span></span> <span data-ttu-id="d9e79-124">Если пользователь клиента Lync на сетевом сайте 1 помещает PSTN-Звонок через УАТС/MTP, расположенную на сетевом сайте 2, мультимедиа передается через ГЛОБАЛЬную сеть.</span><span class="sxs-lookup"><span data-stu-id="d9e79-124">If a Lync client user at the Network Site 1 places a PSTN call through the PBX/MTP located in Network Site 2, the media flows through the WAN link.</span></span> <span data-ttu-id="d9e79-125">Поэтому для каждого сеанса ТСОП выполняются две проверки контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="d9e79-125">Therefore, for each PSTN session two CAC checks are performed:</span></span>

  - <span data-ttu-id="d9e79-126">Между клиентским приложением Lync и сервером обновлений</span><span class="sxs-lookup"><span data-stu-id="d9e79-126">Between the Lync client application and the Mediation Server</span></span>

  - <span data-ttu-id="d9e79-127">Между сервером-посредником и УАТС/MTP</span><span class="sxs-lookup"><span data-stu-id="d9e79-127">Between the Mediation Server and the PBX/MTP</span></span>

<span data-ttu-id="d9e79-128">Проверки выполняются как для входящих звонков ТСОП, поступающих в клиент на сетевом сайте 1, так и для исходящих звонков ТСОП из клиента на сетевом сайте 1.</span><span class="sxs-lookup"><span data-stu-id="d9e79-128">This works for both incoming PSTN calls to a client in Network Site 1, and outgoing PSTN calls originating from a client in Network Site 1.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d9e79-129">Убедитесь в том, что IP-подсеть, к которой относится точка MTP, настроена и связана с сетевым сайтом 2.</span><span class="sxs-lookup"><span data-stu-id="d9e79-129">Make sure that the IP subnet that the MTP belongs to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="d9e79-130">Убедитесь, что IP-подсеть, к которой принадлежат оба интерфейса сервера-посредника, настроена и соответствует сетевому сайту 1.</span><span class="sxs-lookup"><span data-stu-id="d9e79-130">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="d9e79-131">Дополнительные сведения можно найти <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">в разделе Связывание подсети с сетевым сайтом в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d9e79-131">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="case-3-cac-between-the-mediation-server-and-a-third-party-pbx-without-a-media-termination-point"></a><span data-ttu-id="d9e79-132">Случай 3: CAC между сервером-посредником и сторонней АТС без точки завершения мультимедиа</span><span class="sxs-lookup"><span data-stu-id="d9e79-132">Case 3: CAC between the Mediation Server and a third-party PBX without a Media Termination Point</span></span>

<span data-ttu-id="d9e79-133">Случай 3 несколько отличается от первых двух.</span><span class="sxs-lookup"><span data-stu-id="d9e79-133">Case 3 is slightly different from the first two cases.</span></span> <span data-ttu-id="d9e79-134">Если в сторонней УАТС нет MTP, то для запроса исходящего сеанса на независимую АТС не удается определить, в каком месте на границах УАТС будет прерываться мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="d9e79-134">If there is no MTP on the third-party PBX, for an outgoing session request to the third-party PBX the Mediation Server does not know where media will terminate in the PBX boundary.</span></span> <span data-ttu-id="d9e79-135">В этом случае мультимедиа перетекает прямо между сервером-посредником и сторонним устройством конечной точки.</span><span class="sxs-lookup"><span data-stu-id="d9e79-135">In this case, the media flows directly between the Mediation Server and the third-party endpoint device.</span></span>

<span data-ttu-id="d9e79-136">**Случай 3. Контроль допуска звонков между сервером-посредником и сторонней УАТС без точки MTP**</span><span class="sxs-lookup"><span data-stu-id="d9e79-136">**Case 3: CAC between the Mediation Server and a third-party PBX without MTP**</span></span>

<span data-ttu-id="d9e79-137">![Дело 3: CAC между серверными АТС без MTP] (images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Дело 3: CAC между серверными АТС без MTP")</span><span class="sxs-lookup"><span data-stu-id="d9e79-137">![Case 3: CAC between Mediation Server PBX no MTP](images/Gg398762.f4bcf800-3a68-4037-bb3f-adb2fdf50d32(OCS.15).jpg "Case 3: CAC between Mediation Server PBX no MTP")</span></span>

<span data-ttu-id="d9e79-138">В этом примере, если пользователь клиента Lync на сетевом сайте 1 размещает вызов пользователя через УАТС, сервер-посредник может выполнять проверки CAC только для прокси-сервера (между клиентским приложением Lync и сервером-посредником).</span><span class="sxs-lookup"><span data-stu-id="d9e79-138">In this example, if a Lync client user at Network Site 1 places a call to a user through the PBX, the Mediation Server is able to perform CAC checks only on the proxy leg (between the Lync client application and Mediation Server).</span></span> <span data-ttu-id="d9e79-139">Поскольку сервер-посредник не имеет сведений о устройстве конечной точки во время запроса сеанса, перед установкой звонка невозможно выполнить проверки CAC на канале WAN (между сервером-посредником и сторонней конечной точкой).</span><span class="sxs-lookup"><span data-stu-id="d9e79-139">Because the Mediation Server does not have information about the endpoint device while the session is being requested, CAC checks cannot be performed on the WAN link (between the Mediation Server and the third-party endpoint) prior to call establishment.</span></span> <span data-ttu-id="d9e79-140">Однако после того, как сеанс будет установлен, сервер исправлений облегчает учет пропускной способности, используемой в канале.</span><span class="sxs-lookup"><span data-stu-id="d9e79-140">After the session is established, however, the Mediation Server facilitates in accounting for the bandwidth used on the trunk.</span></span>

<span data-ttu-id="d9e79-141">Для вызовов, инициированных из сторонней конечной точки, сведения об этом устройстве будут доступны на момент запроса сеанса, а проверка CAC может выполняться на обеих сторонах сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="d9e79-141">For calls that originate from the third-party endpoint, the information about that endpoint device is available at the time of session request and CAC check can be performed on both the sides of the Mediation Server.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="d9e79-142">Убедитесь в том, что IP-подсеть, к которой относятся устройства конечных точек, настроена и связана с сетевым сайтом 2.</span><span class="sxs-lookup"><span data-stu-id="d9e79-142">Make sure that the IP subnet that the endpoint devices belong to is configured and associated with Network Site 2.</span></span><BR><span data-ttu-id="d9e79-143">Убедитесь, что IP-подсеть, к которой принадлежат оба интерфейса сервера-посредника, настроена и соответствует сетевому сайту 1.</span><span class="sxs-lookup"><span data-stu-id="d9e79-143">Make sure that the IP subnet that both interfaces of the Mediation Server belong to is configured and associated with Network Site 1.</span></span><BR><span data-ttu-id="d9e79-144">Дополнительные сведения можно найти <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">в разделе Связывание подсети с сетевым сайтом в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d9e79-144">For details, see <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

