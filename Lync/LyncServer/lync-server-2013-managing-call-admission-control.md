---
title: 'Lync Server 2013: управление допуском звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing call admission control
ms:assetid: b0bd4783-6f47-408d-b010-2e30f9bc1770
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721851(v=OCS.15)
ms:contentKeyID: 49733784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9663f867e38319b0105373af81c8857be3e1abe
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505956"
---
# <a name="managing-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="fe897-102">Управление допуском звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe897-102">Managing call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe897-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="fe897-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="fe897-104">Контроль допуска звонков на основе доступной пропускной способности сети определяет, следует ли разрешать создание сеансов связи в режиме реального времени, таких как голосовые или видеовызовы.</span><span class="sxs-lookup"><span data-stu-id="fe897-104">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="fe897-105">Используйте следующие процедуры для управления различными функциями CAC в среде Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fe897-105">Use the following procedures to manage different CAC features for your Lync Server 2013 environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fe897-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="fe897-106">In This Section</span></span>

  - [<span data-ttu-id="fe897-107">Включение контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe897-107">Enabling call admission control in Lync Server 2013</span></span>](lync-server-2013-enabling-call-admission-control.md)

  - [<span data-ttu-id="fe897-108">Управление профилями политики пропускной способности сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe897-108">Managing network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-managing-network-bandwidth-policy-profiles.md)

  - [<span data-ttu-id="fe897-109">Регионы сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe897-109">Network regions in Lync Server 2013</span></span>](lync-server-2013-network-regions.md)

  - [<span data-ttu-id="fe897-110">Маршруты областей сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe897-110">Network region routes in Lync Server 2013</span></span>](lync-server-2013-network-region-routes.md)

  - [<span data-ttu-id="fe897-111">Контроль допуска звонков для сайтов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe897-111">Call admission control for sites in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-for-sites.md)

  - [<span data-ttu-id="fe897-112">Включение и отключение обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe897-112">Enabling and disabling media bypass in Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-media-bypass.md)

  - [<span data-ttu-id="fe897-113">Связывание областей сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe897-113">Linking network regions in Lync Server 2013</span></span>](lync-server-2013-linking-network-regions.md)

  - [<span data-ttu-id="fe897-114">Управление сетевыми подсетями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe897-114">Managing network subnets in Lync Server 2013</span></span>](lync-server-2013-managing-network-subnets.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fe897-115">См. также</span><span class="sxs-lookup"><span data-stu-id="fe897-115">See Also</span></span>


[<span data-ttu-id="fe897-116">Обзор контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe897-116">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

