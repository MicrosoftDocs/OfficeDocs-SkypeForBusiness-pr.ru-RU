---
title: 'Lync Server 2013: поддержка сервера и средств в операционной системе'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server and tools operating system support
ms:assetid: b65a0956-f90d-48d0-ac61-558e67339084
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412883(v=OCS.15)
ms:contentKeyID: 48185214
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a19ae4b69eb261a9d23d767dcd3847d8986847b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822064"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-and-tools-operating-system-support-in-lync-server-2013"></a><span data-ttu-id="6a3fb-102">Поддержка сервера и средств в операционной системе в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a3fb-102">Server and tools operating system support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a3fb-103">_**Тема последнего изменения:** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="6a3fb-103">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="6a3fb-104">Lync Server 2013 доступен только в 64-разр. для этого требуется 64-разрядное оборудование и 64-разрядные выпуски Windows Server.</span><span class="sxs-lookup"><span data-stu-id="6a3fb-104">Lync Server 2013 is available only in 64-bit, which requires 64-bit hardware and 64-bit editions of Windows Server.</span></span> <span data-ttu-id="6a3fb-105">Это означает, что все серверные роли и компьютеры, на которых запущены средства администрирования Lync Server 2013, работают под управлением операционной системы 64 (более разрядная версия).</span><span class="sxs-lookup"><span data-stu-id="6a3fb-105">This means that all server roles and computers running Lync Server 2013 administrative tools run a 64-bit edition operating system.</span></span>

<div>

## <a name="operating-systems-for-server-roles"></a><span data-ttu-id="6a3fb-106">Операционные системы для ролей сервера</span><span class="sxs-lookup"><span data-stu-id="6a3fb-106">Operating Systems for Server Roles</span></span>

<span data-ttu-id="6a3fb-107">Lync Server 2013 поддерживает 64-разрядные версии следующих операционных систем для всех ролей сервера в Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="6a3fb-107">Lync Server 2013 supports the 64-bit editions of the following operating systems for all server roles in Lync Server 2013:</span></span>

  - <span data-ttu-id="6a3fb-108">Операционная система Windows Server 2008 R2 с пакетом обновления 1 (SP1) (обязательно) или последний пакет обновления (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="6a3fb-108">The Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="6a3fb-109">Операционная система Windows Server 2008 R2 с пакетом обновления 1 (обязательно) или последний пакет обновления (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="6a3fb-109">The Windows Server 2008 R2 with SP1 Enterprise operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="6a3fb-110">Операционная система Windows Server 2008 R2 с пакетом обновления 1 (обязательно) или последний пакет обновления (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="6a3fb-110">The Windows Server 2008 R2 with SP1 Datacenter operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="6a3fb-111">Операционная система Windows Server 2012 Standard</span><span class="sxs-lookup"><span data-stu-id="6a3fb-111">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="6a3fb-112">Операционная система Windows Server 2012 Datacenter</span><span class="sxs-lookup"><span data-stu-id="6a3fb-112">The Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="6a3fb-113">Операционные системы Windows Server 2012 R2 поддерживаются в накопительных обновлениях для Lync Server 2013: Октябрь 2013.</span><span class="sxs-lookup"><span data-stu-id="6a3fb-113">The Windows Server 2012 R2 operating systems are supported with the Cumulative Updates for Lync Server 2013: October 2013.</span></span>

<span data-ttu-id="6a3fb-114">Lync Server 2013 не поддерживается в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="6a3fb-114">Lync Server 2013 is not supported on the following:</span></span>

  - <span data-ttu-id="6a3fb-115">Вариант установки "ядро сервера" в Windows Server 2008 R2 или Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="6a3fb-115">The Server Core installation option of Windows Server 2008 R2 or Windows Server 2012</span></span>

  - <span data-ttu-id="6a3fb-116">Операционная система Windows Web Server 2008 R2 или операционная система Windows Web Server 2012</span><span class="sxs-lookup"><span data-stu-id="6a3fb-116">The Windows Web Server 2008 R2 operating system or the Windows Web Server 2012 operating system</span></span>

  - <span data-ttu-id="6a3fb-117">Windows Server 2008 R2 HPC Edition или Windows Server 2012 HPC Edition</span><span class="sxs-lookup"><span data-stu-id="6a3fb-117">Windows Server 2008 R2 HPC Edition or Windows Server 2012 HPC Edition</span></span>

</div>

<div>

## <a name="additional-operating-systems-for-administrative-tools"></a><span data-ttu-id="6a3fb-118">Дополнительные операционные системы для средств администрирования</span><span class="sxs-lookup"><span data-stu-id="6a3fb-118">Additional Operating Systems for Administrative Tools</span></span>

<span data-ttu-id="6a3fb-119">Средства администрирования Lync Server 2013 по умолчанию установлены на серверах с Lync Server 2013, но вы можете установить средства администрирования отдельно на других компьютерах под управлением операционной системы Windows.</span><span class="sxs-lookup"><span data-stu-id="6a3fb-119">Lync Server 2013 administrative tools are installed by default on servers running Lync Server 2013, but you can install administrative tools separately on other computers running Windows operating systems.</span></span> <span data-ttu-id="6a3fb-120">К ним относятся следующие 64-разрядные версии следующих операционных систем, а также 64-разрядные выпуски операционных систем, которые поддерживаются при развертывании ролей сервера (как описано в предыдущем разделе).</span><span class="sxs-lookup"><span data-stu-id="6a3fb-120">These include the following 64-bit versions of the following operating systems, in addition to the 64-bit editions of the operating systems supported for deployment of server roles (as described in the previous section).</span></span>

  - <span data-ttu-id="6a3fb-121">Операционная система Windows 7 с пакетом обновления 1 (обязательно) или последним пакетом обновления (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="6a3fb-121">The Windows 7 operating system with SP1 operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="6a3fb-122">Операционная система Windows 8 или последний пакет обновления (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="6a3fb-122">The Windows 8 operating system or latest service pack (recommended)</span></span>

  - <span data-ttu-id="6a3fb-123">Операционная система Windows 8,1 или последний пакет обновления (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="6a3fb-123">The Windows 8.1 operating system or latest service pack (recommended)</span></span>

</div>

<div>

## <a name="operating-systems-for-other-servers-in-your-deployment"></a><span data-ttu-id="6a3fb-124">Операционные системы для других серверов в развертывании</span><span class="sxs-lookup"><span data-stu-id="6a3fb-124">Operating Systems for Other Servers in Your Deployment</span></span>

  - <span data-ttu-id="6a3fb-125">Подробные сведения о требованиях к серверам и другим серверам баз данных можно найти [в разделе Поддержка программного обеспечения баз данных в Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="6a3fb-125">For details about requirements for Back End Servers and other database servers, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

  - <span data-ttu-id="6a3fb-126">Дополнительные сведения о требованиях для обратного прокси-серверов (для развертывания пограничного сервера) можно найти [в разделе Поддержка IIS в Lync Server 2013](lync-server-2013-iis-support.md).</span><span class="sxs-lookup"><span data-stu-id="6a3fb-126">For details about requirements for reverse proxy servers (for Edge deployment), see [IIS support in Lync Server 2013](lync-server-2013-iis-support.md).</span></span>

  - <span data-ttu-id="6a3fb-127">Дополнительные сведения о других требованиях к программному обеспечению, в том числе о поддержке инфраструктуры и виртуализации, можно найти в статьях по [серверам и поддержке инфраструктуры в Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span><span class="sxs-lookup"><span data-stu-id="6a3fb-127">For details about other software requirements, including infrastructure and virtualization support, see the other topics in the [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

