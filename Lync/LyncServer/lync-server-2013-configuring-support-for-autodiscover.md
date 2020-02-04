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
ms.openlocfilehash: 779929d270fa4ae2f8eec59a954c2273ff61b44f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="159ac-102">Настройка поддержки автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="159ac-102">Configuring support for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="159ac-103">_**Тема последнего изменения:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="159ac-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="159ac-104">**Служба автообнаружения** веб-служб Lync Server впервые появилась в накопительном обновлении lync Server 2010: Ноябрь 2011.</span><span class="sxs-lookup"><span data-stu-id="159ac-104">The Lync Server web services **Autodiscover service** first appeared in the Lync Server 2010 Cumulative Update: November 2011.</span></span> <span data-ttu-id="159ac-105">Это обновление сопровождается первоначальным выпуском мобильных клиентов Lync.</span><span class="sxs-lookup"><span data-stu-id="159ac-105">This update was accompanied by the initial release of Lync Mobile clients.</span></span> <span data-ttu-id="159ac-106">Служба автообнаружения предоставляет службы Mobility Services, называемые службой МККС.</span><span class="sxs-lookup"><span data-stu-id="159ac-106">The autodiscover service exposed the mobility services, known as the Mcx service.</span></span>

<span data-ttu-id="159ac-107">Служба автообнаружения действует как единое место для всех клиентов, которые запрашивают сведения о доступных службах и функциях, а также о том, как связаться с севицес — либо полным доменным именем, либо ссылкой на указатель URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="159ac-107">The autodiscover service acts as a single location for all clients to request information on what services and features are available, and how to contact the sevices – either by a fully qualified domain name or a web uniform resource locator reference.</span></span> <span data-ttu-id="159ac-108">Функция автообнаружения предоставляет ряд функций, и каждый клиент будет выполнять запросы на основании функций, которые может использовать клиент.</span><span class="sxs-lookup"><span data-stu-id="159ac-108">Autodiscover exposes a number of features, and each client will make requests based on the features that the client can use.</span></span> <span data-ttu-id="159ac-109">Например, классическое приложение Lync 2013 будет использовать аутодисквоер для определения внешней веб-службы, но не будет использовать службы Mobility (МККС).</span><span class="sxs-lookup"><span data-stu-id="159ac-109">For example, a desktop Lync 2013 client will use autodiscvoer to determine the external web services, but will not use the mobility (Mcx) services.</span></span> <span data-ttu-id="159ac-110">Чтобы правильно определить и позволить клиентам использовать доступные для них функции, необходимо определить сценарии, позволяющие клиенту эффективно находить и использовать записи автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="159ac-110">To properly define and enable your clients to use the features available to them, the scenarios that allow a client to effectively find and use autodiscover entries should be defined.</span></span> <span data-ttu-id="159ac-111">Для использования аутодосковер необходимо, чтобы в развертывании на обратном прокси публикуются веб-службы Lync Server, что записи DNS настроены для разрешения запросов DNS для службы автообнаружения сервера Lync Server и веб-служб Lync Server, а также для служб сертификации. правильно настроены для конкретного сценария.</span><span class="sxs-lookup"><span data-stu-id="159ac-111">To use autodoscover, your deployment requires that a reverse proxy publishes the Lync Server web services, that DNS records are configured to resolve DNS queries for the Lync Server autodiscover service and Lync Server web services, and that certificate services are properly configured for your specific scenario.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="159ac-112">Технические сведения о том, какие элементы содержатся в запросе и ответе автообнаружения, приведены <A href="lync-server-2013-understanding-autodiscover.md">в разделе Общие сведения о автообнаружения в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="159ac-112">For technical details on what the elements within the autodiscover request/response do, see <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="159ac-113">Следующие данные и таблицы определяют, какие конфигурации (если таковые имеются) необходимо реализовать для обеспечения полного и эффективного использования службы автообнаружения.</span><span class="sxs-lookup"><span data-stu-id="159ac-113">The following information and tables define, per scenario, what configurations (if any) you need to implement to provide the full and effective use of the autodiscover service.</span></span> <span data-ttu-id="159ac-114">Сведения в указанных ниже разделах относятся к Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="159ac-114">The information in the following topics is specific to Microsoft Lync Server 2013.</span></span> <span data-ttu-id="159ac-115">Если вы ищете руководство по планированию мобильных устройств для Lync Server 2010, ознакомьтесь [http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113)с разрешениями.</span><span class="sxs-lookup"><span data-stu-id="159ac-115">If you are looking for guidance on how to plan Mobility for Lync Server 2010, see [http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113).</span></span> <span data-ttu-id="159ac-116">Развертывание мобильных устройств для Lync Server 2010 можно найти в разделе[http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)</span><span class="sxs-lookup"><span data-stu-id="159ac-116">To deploy Mobility for Lync Server 2010, see [http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="159ac-117">Содержание</span><span class="sxs-lookup"><span data-stu-id="159ac-117">In This Section</span></span>

  - [<span data-ttu-id="159ac-118">Настройка DNS для автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="159ac-118">Configuring DNS for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [<span data-ttu-id="159ac-119">Настройка сертификатов для автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="159ac-119">Configuring certificates for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [<span data-ttu-id="159ac-120">Настройка обратного прокси-сервера для автообнаружения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="159ac-120">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [<span data-ttu-id="159ac-121">Настройка автообнаружения в Lync Server 2013 для гибридных развертываний</span><span class="sxs-lookup"><span data-stu-id="159ac-121">Configuring Autodiscover in Lync Server 2013 for hybrid deployments</span></span>](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

