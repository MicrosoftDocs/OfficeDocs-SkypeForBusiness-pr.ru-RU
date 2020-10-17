---
title: 'Lync Server 2013: вопросы миграции и сосуществования для IPv6'
description: 'Lync Server 2013: вопросы миграции и сосуществования для IPv6.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration and coexistence considerations for IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48184751
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8618cc14ff3c2467ea41df34e39f5094d1206dc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560995"
---
# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="128ce-103">Вопросы миграции и сосуществования для IPv6 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="128ce-103">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="128ce-104">_**Последнее изменение темы:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="128ce-104">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="128ce-105">Протокол IP версии 6 (IPv6) не поддерживается на Lync Server 2010 или Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="128ce-105">IP version 6 (IPv6) is not supported on Lync Server 2010 or Office Communications Server.</span></span> <span data-ttu-id="128ce-106">При пилотном развертывании можно тестировать сосуществование с двумя стеками Lync Server 2010 и Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="128ce-106">For piloting purposes, you can test Lync Server 2010 and Lync Server 2013 dual-stack coexistence.</span></span> <span data-ttu-id="128ce-107">Перед включением поддержки IPv6 (сеть с двумя стеками) для любого пула рекомендуется обновить все пулы для данного центрального сайта до Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="128ce-107">We recommend that all pools for a given central site are upgraded to Lync Server 2013 before you enable IPv6 (dual-stack network) for any of the pools.</span></span> <span data-ttu-id="128ce-108">Если необходимо настроить пул только для IPv6, то для тестирования в лабораторной среде рекомендуется настроить пул только для IPv6.</span><span class="sxs-lookup"><span data-stu-id="128ce-108">If you need to configure a pool for IPv6 only, we recommend that you set up an IPv6-only pool in your lab environment for testing.</span></span>

<span data-ttu-id="128ce-109">Во время миграции и сосуществования поддерживаются следующие сценарии.</span><span class="sxs-lookup"><span data-stu-id="128ce-109">The following scenarios are supported during migration and coexistence:</span></span>

  - <span data-ttu-id="128ce-110">Пулы Lync Server 2013, Lync Server 2010 и Office Communications Server 2007 R2 в режиме IPv4, сосуществующие с Lync Server 2013 в режиме двойного стека.</span><span class="sxs-lookup"><span data-stu-id="128ce-110">Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2 pools in IPv4 mode, coexisting with Lync Server 2013 in dual-stack mode.</span></span>

  - <span data-ttu-id="128ce-111">Lync Server 2013 pool в режиме только IPv6, если пул, поддерживающий только IPv6, является приемником.</span><span class="sxs-lookup"><span data-stu-id="128ce-111">Lync Server 2013 pool in IPv6-only mode, if the IPv6-only pool is siloed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

