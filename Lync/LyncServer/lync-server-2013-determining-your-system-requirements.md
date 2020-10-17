---
title: 'Lync Server 2013: определение требований к системе'
description: 'Lync Server 2013: определение требований к системе.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determining your system requirements
ms:assetid: 620e81e2-42df-4eda-8498-bd56a14aa0e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398438(v=OCS.15)
ms:contentKeyID: 48184286
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ceca8eabb234ae7fd483372ff5e611664ecc4fa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569495"
---
# <a name="determining-your-system-requirements-for-lync-server-2013"></a><span data-ttu-id="c6fab-103">Определение требований к системе для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6fab-103">Determining your system requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6fab-104">_**Последнее изменение темы:** 2014-01-02_</span><span class="sxs-lookup"><span data-stu-id="c6fab-104">_**Topic Last Modified:** 2014-01-02_</span></span>

<span data-ttu-id="c6fab-105">Все серверы, на которых работает Lync Server, должны соответствовать определенным минимальным требованиям к системе.</span><span class="sxs-lookup"><span data-stu-id="c6fab-105">All servers running Lync Server must meet certain minimum system requirements.</span></span> <span data-ttu-id="c6fab-106">Требования к системе для Lync Server включают серверное оборудование, операционную систему, устанавливаемую на каждом сервере, а также требования к связанному программному обеспечению, такие как обновления Windows и другое программное обеспечение, которое должно быть установлено на серверах.</span><span class="sxs-lookup"><span data-stu-id="c6fab-106">System requirements for Lync Server include the server hardware, the operating system to be installed on each server, and related software requirements, such as the Windows updates and other software that must be installed on the servers.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c6fab-107">Lync Server доступен только в 64-разрядном выпуске, для которого требуется 64-разрядное оборудование и Windows Server 64-bit Edition.</span><span class="sxs-lookup"><span data-stu-id="c6fab-107">Lync Server is available only in a 64-bit edition, which requires 64-bit hardware and a 64-bit edition of Windows Server.</span></span> <span data-ttu-id="c6fab-108">Исключением является Microsoft Lync Server 2013, средство планирования, которое доступно в 32-разрядном выпуске.</span><span class="sxs-lookup"><span data-stu-id="c6fab-108">The exception is the Microsoft Lync Server 2013, Planning Tool, which is available in a 32-bit edition.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c6fab-109">Для получения дополнительных сведений о поддержке Active Directory, поддерживаемых топологиях, размещении серверов и других проблемах с поддержкой, ознакомьтесь со статьей <A href="lync-server-2013-supportability.md">Поддержка для Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c6fab-109">For details about Active Directory support, supported topologies, server collocation, and other supportability issues, see <A href="lync-server-2013-supportability.md">Supportability for Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c6fab-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="c6fab-110">In This Section</span></span>

  - [<span data-ttu-id="c6fab-111">Аппаратные серверные платформы для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6fab-111">Server hardware platforms for Lync Server 2013</span></span>](lync-server-2013-server-hardware-platforms.md)

  - [<span data-ttu-id="c6fab-112">Поддержка серверов и средств операционной системы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6fab-112">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)

  - [<span data-ttu-id="c6fab-113">Поддержка программного обеспечения баз данных в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6fab-113">Database software support in Lync Server 2013</span></span>](lync-server-2013-database-software-support.md)

  - [<span data-ttu-id="c6fab-114">Дополнительные требования к программному обеспечению для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6fab-114">Additional software requirements for Lync Server 2013</span></span>](lync-server-2013-additional-software-requirements.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c6fab-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c6fab-115">See Also</span></span>


[<span data-ttu-id="c6fab-116">Поддержка оборудования клиентов и устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6fab-116">Client and device hardware support in Lync Server 2013</span></span>](lync-server-2013-client-and-device-hardware-support.md)  
[<span data-ttu-id="c6fab-117">Поддержка для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6fab-117">Supportability for Lync Server 2013</span></span>](lync-server-2013-supportability.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

