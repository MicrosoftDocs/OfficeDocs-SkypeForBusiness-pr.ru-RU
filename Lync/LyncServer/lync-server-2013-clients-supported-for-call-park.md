---
title: 'Lync Server 2013: клиенты, поддерживаемые для парковки вызовов'
description: 'Lync Server 2013: клиенты, поддерживаемые для парковки вызовов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Clients supported for Call Park
ms:assetid: c236d2ba-9d83-418c-9cbc-92541f115fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412958(v=OCS.15)
ms:contentKeyID: 48185320
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a923f0e62c246a12b811628d578ab571f4f13e36
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543495"
---
# <a name="clients-supported-for-call-park-in-lync-server-2013"></a><span data-ttu-id="23d1d-103">Клиенты, поддерживаемые для парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23d1d-103">Clients supported for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23d1d-104">_**Последнее изменение темы:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="23d1d-104">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="23d1d-105">В этом разделе перечисляются клиенты, которые можно использовать для приостановки звонков и для приема приостановленных звонков.</span><span class="sxs-lookup"><span data-stu-id="23d1d-105">This section identifies the clients that can be used to park calls and the clients that can be used to retrieve parked calls.</span></span>

<div>

## <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="23d1d-106">Клиенты, поддерживаемые для приостановки звонков</span><span class="sxs-lookup"><span data-stu-id="23d1d-106">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="23d1d-107">Приостанавливать можно звонки с любых IP-телефонов, АТС учреждения (УАТС), телефонной сети общего пользования (ТСОП) и с мобильных телефонов.</span><span class="sxs-lookup"><span data-stu-id="23d1d-107">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="23d1d-p101">Приостанавливать можно только голосовые звонки. Приостанавливать сеансы обмена мгновенными сообщениями и конференции нельзя.</span><span class="sxs-lookup"><span data-stu-id="23d1d-p101">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span>



</div>

<span data-ttu-id="23d1d-110">Следующие клиенты могут использовать парковки вызовов для парковки вызовов:</span><span class="sxs-lookup"><span data-stu-id="23d1d-110">The following clients can use Call Park to park calls:</span></span>

  - <span data-ttu-id="23d1d-111">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="23d1d-111">Lync 2013</span></span>

  - <span data-ttu-id="23d1d-112">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="23d1d-112">Lync 2010</span></span>

  - <span data-ttu-id="23d1d-113">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="23d1d-113">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="23d1d-114">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="23d1d-114">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="23d1d-115">Мобильные телефоны не могут использовать парковки вызовов для парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="23d1d-115">Mobile phones cannot use Call Park to park calls.</span></span>



</div>

</div>

<div>

## <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="23d1d-116">Клиенты, поддерживаемые для приема звонков</span><span class="sxs-lookup"><span data-stu-id="23d1d-116">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="23d1d-p102">Диапазоны орбит задаются в виде блоков виртуальных расширений (расширений без назначенных пользователей или телефонов). При настройке орбит в виде виртуальных расширений мобильные телефоны и телефоны ТСОП не смогут принимать приостановленные звонки.</span><span class="sxs-lookup"><span data-stu-id="23d1d-p102">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>

<span data-ttu-id="23d1d-119">Федеративные пользователи не могут принимать приостановленные звонки.</span><span class="sxs-lookup"><span data-stu-id="23d1d-119">Federated users cannot retrieve parked calls.</span></span>

<span data-ttu-id="23d1d-120">Следующие клиенты могут получать вызовы, приостановленные на парковки вызовов:</span><span class="sxs-lookup"><span data-stu-id="23d1d-120">The following clients can retrieve calls that are parked on Call Park:</span></span>

  - <span data-ttu-id="23d1d-121">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="23d1d-121">Lync 2013</span></span>

  - <span data-ttu-id="23d1d-122">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="23d1d-122">Lync 2010</span></span>

  - <span data-ttu-id="23d1d-123">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="23d1d-123">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="23d1d-124">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="23d1d-124">Lync Phone Edition</span></span>

  - <span data-ttu-id="23d1d-125">Региональные IP-телефоны</span><span class="sxs-lookup"><span data-stu-id="23d1d-125">IP common area phones</span></span>

  - <span data-ttu-id="23d1d-126">Телефоны, не поддерживающие IP, которые подключены к инфраструктуре Lync Server 2013, включая телефонные телефоны и УАТС.</span><span class="sxs-lookup"><span data-stu-id="23d1d-126">Non-IP phones that are connected to the Lync Server 2013 infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

