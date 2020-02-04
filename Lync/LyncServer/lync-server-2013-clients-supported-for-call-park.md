---
title: 'Lync Server 2013: клиенты, поддерживаемые для парковки вызовов'
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
ms.openlocfilehash: 52304a0241425a3b88c7f9419afa57f3d768fbb0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clients-supported-for-call-park-in-lync-server-2013"></a><span data-ttu-id="a465b-102">Клиенты, поддерживаемые для парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a465b-102">Clients supported for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a465b-103">_**Тема последнего изменения:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="a465b-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="a465b-104">В этом разделе указаны клиенты, которые можно использовать для приостановки звонков и клиентов, которые можно использовать для получения приостановленных звонков.</span><span class="sxs-lookup"><span data-stu-id="a465b-104">This section identifies the clients that can be used to park calls and the clients that can be used to retrieve parked calls.</span></span>

<div>

## <a name="clients-supported-for-parking-calls"></a><span data-ttu-id="a465b-105">Клиенты, поддерживаемые для приостановки звонков</span><span class="sxs-lookup"><span data-stu-id="a465b-105">Clients Supported for Parking Calls</span></span>

<span data-ttu-id="a465b-106">Приостанавливать можно звонки с любых IP-телефонов, АТС учреждения (УАТС), телефонной сети общего пользования (ТСОП) и с мобильных телефонов.</span><span class="sxs-lookup"><span data-stu-id="a465b-106">Calls from any IP, private branch exchange (PBX), public switched telephone network (PSTN), or mobile phone can be parked.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a465b-p101">Приостанавливать можно только голосовые звонки. Приостанавливать сеансы обмена мгновенными сообщениями и конференции нельзя.</span><span class="sxs-lookup"><span data-stu-id="a465b-p101">Only audio calls can be parked. Instant messages and conferences cannot be parked.</span></span>



</div>

<span data-ttu-id="a465b-109">Следующие клиенты могут использовать приостановку звонков для приема звонков:</span><span class="sxs-lookup"><span data-stu-id="a465b-109">The following clients can use Call Park to park calls:</span></span>

  - <span data-ttu-id="a465b-110">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="a465b-110">Lync 2013</span></span>

  - <span data-ttu-id="a465b-111">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="a465b-111">Lync 2010</span></span>

  - <span data-ttu-id="a465b-112">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="a465b-112">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="a465b-113">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="a465b-113">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a465b-114">Мобильные телефоны не могут использовать приостановку звонков для приема звонков.</span><span class="sxs-lookup"><span data-stu-id="a465b-114">Mobile phones cannot use Call Park to park calls.</span></span>



</div>

</div>

<div>

## <a name="clients-supported-for-retrieving-calls"></a><span data-ttu-id="a465b-115">Клиенты, поддерживаемые для приема звонков</span><span class="sxs-lookup"><span data-stu-id="a465b-115">Clients Supported for Retrieving Calls</span></span>

<span data-ttu-id="a465b-p102">Диапазоны орбит задаются в виде блоков виртуальных расширений (расширений без назначенных пользователей или телефонов). При настройке орбит в виде виртуальных расширений мобильные телефоны и телефоны ТСОП не смогут принимать приостановленные звонки.</span><span class="sxs-lookup"><span data-stu-id="a465b-p102">Orbit ranges are configured as blocks of virtual extensions (extensions without an assigned user or phone). When you configure orbits as virtual extensions, mobile phones and PSTN phones cannot retrieve parked calls.</span></span>

<span data-ttu-id="a465b-118">Федеративные пользователи не могут принимать приостановленные звонки.</span><span class="sxs-lookup"><span data-stu-id="a465b-118">Federated users cannot retrieve parked calls.</span></span>

<span data-ttu-id="a465b-119">Следующие клиенты могут получать звонки, приостановленные на приостановке звонка:</span><span class="sxs-lookup"><span data-stu-id="a465b-119">The following clients can retrieve calls that are parked on Call Park:</span></span>

  - <span data-ttu-id="a465b-120">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="a465b-120">Lync 2013</span></span>

  - <span data-ttu-id="a465b-121">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="a465b-121">Lync 2010</span></span>

  - <span data-ttu-id="a465b-122">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="a465b-122">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="a465b-123">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="a465b-123">Lync Phone Edition</span></span>

  - <span data-ttu-id="a465b-124">Региональные IP-телефоны</span><span class="sxs-lookup"><span data-stu-id="a465b-124">IP common area phones</span></span>

  - <span data-ttu-id="a465b-125">Телефоны, не поддерживающие IP, которые подключены к инфраструктуре Lync Server 2013, в том числе обычные телефоны и телефоны обмена филиалами (АТС)</span><span class="sxs-lookup"><span data-stu-id="a465b-125">Non-IP phones that are connected to the Lync Server 2013 infrastructure, including common area phones and private branch exchange (PBX) phones</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

