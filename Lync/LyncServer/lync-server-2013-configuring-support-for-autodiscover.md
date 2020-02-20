---
title: 'Lync Server 2013: Настройка поддержки автообнаружения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee85d984f0d60d4275972982e4ff65b380f0f9b2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145918"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="e4006-102">Настройка поддержки автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4006-102">Configuring support for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4006-103">_**Последнее изменение темы:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="e4006-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="e4006-104">**Служба автообнаружения** веб-служб Lync Server впервые появилась в накопительном обновлении lync Server 2010: Ноябрь 2011.</span><span class="sxs-lookup"><span data-stu-id="e4006-104">The Lync Server web services **Autodiscover service** first appeared in the Lync Server 2010 Cumulative Update: November 2011.</span></span> <span data-ttu-id="e4006-105">Это обновление сопровождается первоначальным выпуском мобильных клиентов Lync.</span><span class="sxs-lookup"><span data-stu-id="e4006-105">This update was accompanied by the initial release of Lync Mobile clients.</span></span> <span data-ttu-id="e4006-106">Служба автообнаружения предоставляла службы Mobility Services, называемые службой MCX.</span><span class="sxs-lookup"><span data-stu-id="e4006-106">The autodiscover service exposed the mobility services, known as the Mcx service.</span></span>

<span data-ttu-id="e4006-107">Служба автообнаружения выступает в качестве единого расположения для всех клиентов, которые запрашивают сведения о доступных службах и функциях, а также о том, как связаться с севицес — либо с полным доменным именем, либо с помощью URL-адреса URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="e4006-107">The autodiscover service acts as a single location for all clients to request information on what services and features are available, and how to contact the sevices – either by a fully qualified domain name or a web uniform resource locator reference.</span></span> <span data-ttu-id="e4006-108">Служба автообнаружения предоставляет ряд функций, и каждый клиент делает запросы на основе компонентов, которые может использовать клиент.</span><span class="sxs-lookup"><span data-stu-id="e4006-108">Autodiscover exposes a number of features, and each client will make requests based on the features that the client can use.</span></span> <span data-ttu-id="e4006-109">Например, клиент Lync 2013 для настольных компьютеров будет использовать аутодисквоер для определения внешних веб-служб, но не будет использовать службы Mobility (MCX).</span><span class="sxs-lookup"><span data-stu-id="e4006-109">For example, a desktop Lync 2013 client will use autodiscvoer to determine the external web services, but will not use the mobility (Mcx) services.</span></span> <span data-ttu-id="e4006-110">Чтобы правильно определить и разрешить клиентам использовать доступные вам функции, необходимо определить сценарии, позволяющие клиенту эффективно находить и использовать записи автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="e4006-110">To properly define and enable your clients to use the features available to them, the scenarios that allow a client to effectively find and use autodiscover entries should be defined.</span></span> <span data-ttu-id="e4006-111">Чтобы использовать аутодосковер, в развертывании требуется, чтобы обратный прокси опубликовал веб-службы Lync Server, что записи DNS настроены для разрешения DNS-запросов для службы автообнаружения Lync Server и веб-служб Lync Server, а также для этих служб сертификатов. правильно настроены для конкретного сценария.</span><span class="sxs-lookup"><span data-stu-id="e4006-111">To use autodoscover, your deployment requires that a reverse proxy publishes the Lync Server web services, that DNS records are configured to resolve DNS queries for the Lync Server autodiscover service and Lync Server web services, and that certificate services are properly configured for your specific scenario.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="e4006-112">Технические сведения о том, что делают элементы в запросе и ответе службы автообнаружения, можно узнать <A href="lync-server-2013-understanding-autodiscover.md">в статье Общие сведения о службе автообнаружения в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e4006-112">For technical details on what the elements within the autodiscover request/response do, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="e4006-113">Приведенные ниже сведения и таблицы определяют, какие конфигурации (при необходимости) необходимо реализовать для предоставления полного и эффективного использования службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="e4006-113">The following information and tables define, per scenario, what configurations (if any) you need to implement to provide the full and effective use of the autodiscover service.</span></span> <span data-ttu-id="e4006-114">Сведения, приведенные в следующих разделах, относятся к Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e4006-114">The information in the following topics is specific to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="e4006-115">Если вы ищете руководство по планированию мобильных устройств для Lync Server 2010, ознакомьтесь [https://go.microsoft.com/fwlink/?LinkId=275113](https://go.microsoft.com/fwlink/?linkid=275113)со статьей.</span><span class="sxs-lookup"><span data-stu-id="e4006-115">If you are looking for guidance on how to plan Mobility for Lync Server 2010, see [https://go.microsoft.com/fwlink/?LinkId=275113](https://go.microsoft.com/fwlink/?linkid=275113).</span></span> <span data-ttu-id="e4006-116">Чтобы развернуть Mobility for Lync Server 2010, ознакомьтесь со статьей[https://go.microsoft.com/fwlink/?LinkId=275114](https://go.microsoft.com/fwlink/?linkid=275114)</span><span class="sxs-lookup"><span data-stu-id="e4006-116">To deploy Mobility for Lync Server 2010, see [https://go.microsoft.com/fwlink/?LinkId=275114](https://go.microsoft.com/fwlink/?linkid=275114)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e4006-117">Содержание</span><span class="sxs-lookup"><span data-stu-id="e4006-117">In This Section</span></span>

  - [<span data-ttu-id="e4006-118">Настройка DNS для автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4006-118">Configuring DNS for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [<span data-ttu-id="e4006-119">Настройка сертификатов для автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4006-119">Configuring certificates for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [<span data-ttu-id="e4006-120">Настройка обратного прокси-сервера для автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4006-120">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [<span data-ttu-id="e4006-121">Настройка службы автообнаружения в Lync Server 2013 для гибридных развертываний</span><span class="sxs-lookup"><span data-stu-id="e4006-121">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

