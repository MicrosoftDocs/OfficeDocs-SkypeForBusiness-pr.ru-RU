---
title: 'Lync Server 2013: планирование устойчивости корпоративной голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Enterprise Voice resiliency
ms:assetid: ca116700-1055-4ca5-9b87-4c7f380c3655
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398840(v=OCS.15)
ms:contentKeyID: 48185408
ms.date: 10/17/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b8b35871b740bd6d52d741922a3dcea9b7b60b5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41754059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-enterprise-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="13078-102">Планирование устойчивости корпоративной голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13078-102">Planning for Enterprise Voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13078-103">_**Тема последнего изменения:** 2014-10-17_</span><span class="sxs-lookup"><span data-stu-id="13078-103">_**Topic Last Modified:** 2014-10-17_</span></span>

<span data-ttu-id="13078-104">Устойчивость голоса — это возможность, с помощью которой пользователи могут совершать и принимать звонки, если центральный сайт, на котором размещен Lync Server 2013, станет недоступен, независимо от того, какое из сбоев является глобальной сетью (WAN) или какой-либо другой причиной.</span><span class="sxs-lookup"><span data-stu-id="13078-104">Voice resiliency refers to the ability of users to continue making and receiving calls if a central site that hosts Lync Server 2013 becomes unavailable, whether through a wide area network (WAN) failure or another cause.</span></span> <span data-ttu-id="13078-105">При сбое центрального узла служба корпоративной голосовой связи должна без прерываний перейти на резервный узел.</span><span class="sxs-lookup"><span data-stu-id="13078-105">If a central site fails, Enterprise Voice service must continue uninterrupted through seamless failover to a backup site.</span></span> <span data-ttu-id="13078-106">При сбое глобальной сети вызовы узла филиала должны перенаправляться на локальный шлюз ТСОП.</span><span class="sxs-lookup"><span data-stu-id="13078-106">In the event of WAN failure, branch site calls must be redirected to a local PSTN gateway.</span></span> <span data-ttu-id="13078-107">В данном разделе описывается планирование устойчивости голосовой связи при сбое центрального узла или глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="13078-107">This section discusses planning for voice resiliency in the event of central-site or WAN failure.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="13078-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="13078-108">In This Section</span></span>

  - [<span data-ttu-id="13078-109">Планирование устойчивости голосовой связи для центрального сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13078-109">Planning for central site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-central-site-voice-resiliency.md)

  - [<span data-ttu-id="13078-110">Планирование устойчивости голосовой связи для сайта филиала в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13078-110">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

