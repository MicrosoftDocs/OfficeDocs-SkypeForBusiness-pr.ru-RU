---
title: 'Lync Server 2013: поддержка серверов и средств операционной системы'
description: 'Lync Server 2013: поддержка серверов и средств операционной системы.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server and tools operating system support
ms:assetid: b65a0956-f90d-48d0-ac61-558e67339084
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412883(v=OCS.15)
ms:contentKeyID: 48185214
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 67cf2e39e0c8f9e66f755b16be03af37dd9a946e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555155"
---
# <a name="server-and-tools-operating-system-support-in-lync-server-2013"></a><span data-ttu-id="a5369-103">Поддержка серверов и средств операционной системы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5369-103">Server and tools operating system support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5369-104">_**Последнее изменение темы:** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="a5369-104">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="a5369-105">Lync Server 2013 доступен только в 64-разрядной версии, требующей 64-разрядное оборудование и 64-разрядные выпуски Windows Server.</span><span class="sxs-lookup"><span data-stu-id="a5369-105">Lync Server 2013 is available only in 64-bit, which requires 64-bit hardware and 64-bit editions of Windows Server.</span></span> <span data-ttu-id="a5369-106">Это означает, что все роли сервера и компьютеры, на которых запущены административные средства Lync Server 2013, запускают операционную систему 64 (разрядная версия).</span><span class="sxs-lookup"><span data-stu-id="a5369-106">This means that all server roles and computers running Lync Server 2013 administrative tools run a 64-bit edition operating system.</span></span>

<div>

## <a name="operating-systems-for-server-roles"></a><span data-ttu-id="a5369-107">ОС для ролей сервера</span><span class="sxs-lookup"><span data-stu-id="a5369-107">Operating Systems for Server Roles</span></span>

<span data-ttu-id="a5369-108">Lync Server 2013 поддерживает 64 – разрядные выпуски следующих операционных систем для всех ролей серверов в Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="a5369-108">Lync Server 2013 supports the 64-bit editions of the following operating systems for all server roles in Lync Server 2013:</span></span>

  - <span data-ttu-id="a5369-109">Операционная система Windows Server 2008 R2 с пакетом обновления 1 (SP1) или более поздней версии (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="a5369-109">The Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="a5369-110">Операционная система Windows Server 2008 R2 с пакетом обновления 1 (SP1) (обязательно) или более поздняя версия пакета обновления (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="a5369-110">The Windows Server 2008 R2 with SP1 Enterprise operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="a5369-111">Операционная система Windows Server 2008 R2 с пакетом обновления 1 (SP1) (обязательно) или более поздней версии (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="a5369-111">The Windows Server 2008 R2 with SP1 Datacenter operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="a5369-112">Операционная система Windows Server 2012 Standard</span><span class="sxs-lookup"><span data-stu-id="a5369-112">The Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="a5369-113">Операционная система Windows Server 2012 Datacenter</span><span class="sxs-lookup"><span data-stu-id="a5369-113">The Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="a5369-114">Операционные системы Windows Server 2012 R2 поддерживаются с накопительными пакетами обновления для Lync Server 2013:2013.</span><span class="sxs-lookup"><span data-stu-id="a5369-114">The Windows Server 2012 R2 operating systems are supported with the Cumulative Updates for Lync Server 2013: October 2013.</span></span>

<span data-ttu-id="a5369-115">Lync Server 2013 не поддерживается для следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="a5369-115">Lync Server 2013 is not supported on the following:</span></span>

  - <span data-ttu-id="a5369-116">Вариант установки основных серверных компонентов Windows Server 2008 R2 или Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="a5369-116">The Server Core installation option of Windows Server 2008 R2 or Windows Server 2012</span></span>

  - <span data-ttu-id="a5369-117">В ОС Windows Web Server 2008 R2 или Windows Web Server 2012</span><span class="sxs-lookup"><span data-stu-id="a5369-117">The Windows Web Server 2008 R2 operating system or the Windows Web Server 2012 operating system</span></span>

  - <span data-ttu-id="a5369-118">Windows Server 2008 R2 HPC Edition или Windows Server 2012 HPC Edition</span><span class="sxs-lookup"><span data-stu-id="a5369-118">Windows Server 2008 R2 HPC Edition or Windows Server 2012 HPC Edition</span></span>

</div>

<div>

## <a name="additional-operating-systems-for-administrative-tools"></a><span data-ttu-id="a5369-119">Дополнительные ОС для средств администрирования</span><span class="sxs-lookup"><span data-stu-id="a5369-119">Additional Operating Systems for Administrative Tools</span></span>

<span data-ttu-id="a5369-120">Lync Server 2013 административные средства устанавливаются по умолчанию на серверах с Lync Server 2013, но вы можете установить средства администрирования отдельно на других компьютерах под управлением операционных систем Windows.</span><span class="sxs-lookup"><span data-stu-id="a5369-120">Lync Server 2013 administrative tools are installed by default on servers running Lync Server 2013, but you can install administrative tools separately on other computers running Windows operating systems.</span></span> <span data-ttu-id="a5369-121">К ним относятся следующие 64-разрядные версии следующих операционных систем, а также 64-разрядные выпуски операционных систем, поддерживаемые для развертывания ролей сервера (как описано в предыдущем разделе).</span><span class="sxs-lookup"><span data-stu-id="a5369-121">These include the following 64-bit versions of the following operating systems, in addition to the 64-bit editions of the operating systems supported for deployment of server roles (as described in the previous section).</span></span>

  - <span data-ttu-id="a5369-122">Операционная система Windows 7 с пакетом обновления 1 (SP1) или последним пакетом обновления (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="a5369-122">The Windows 7 operating system with SP1 operating system (required) or latest service pack (recommended)</span></span>

  - <span data-ttu-id="a5369-123">Операционная система Windows 8 или последний пакет обновления (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="a5369-123">The Windows 8 operating system or latest service pack (recommended)</span></span>

  - <span data-ttu-id="a5369-124">Операционная система Windows 8,1 или последний пакет обновления (рекомендуется)</span><span class="sxs-lookup"><span data-stu-id="a5369-124">The Windows 8.1 operating system or latest service pack (recommended)</span></span>

</div>

<div>

## <a name="operating-systems-for-other-servers-in-your-deployment"></a><span data-ttu-id="a5369-125">Операционные системы для других серверов в развертывании</span><span class="sxs-lookup"><span data-stu-id="a5369-125">Operating Systems for Other Servers in Your Deployment</span></span>

  - <span data-ttu-id="a5369-126">Сведения о требованиях к внутренним серверам и другим серверам баз данных можно найти [в разделе Поддержка программного обеспечения баз данных в Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="a5369-126">For details about requirements for Back End Servers and other database servers, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

  - <span data-ttu-id="a5369-127">Дополнительные сведения о требованиях для обратных прокси-серверов (для пограничного развертывания) можно найти [в статье поддержка IIS в Lync Server 2013](lync-server-2013-iis-support.md).</span><span class="sxs-lookup"><span data-stu-id="a5369-127">For details about requirements for reverse proxy servers (for Edge deployment), see [IIS support in Lync Server 2013](lync-server-2013-iis-support.md).</span></span>

  - <span data-ttu-id="a5369-128">Сведения о других требованиях к программному обеспечению, включая поддержку инфраструктуры и виртуализации, можно найти в других разделах, посвященных [серверному программному обеспечению и инфраструктуре в Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span><span class="sxs-lookup"><span data-stu-id="a5369-128">For details about other software requirements, including infrastructure and virtualization support, see the other topics in the [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

