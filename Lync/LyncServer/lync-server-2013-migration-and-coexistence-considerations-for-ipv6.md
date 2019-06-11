---
title: 'Lync Server 2013: вопросы миграции и сосуществования для IPv6'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration and coexistence considerations for IPv6
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205068(v=OCS.15)
ms:contentKeyID: 48184751
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8adf81df14d5c87eb2b54b63d9a58fc1b6f5b97e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a><span data-ttu-id="5f14c-102">Вопросы миграции и сосуществования для IPv6 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f14c-102">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f14c-103">_**Тема последнего изменения:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="5f14c-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="5f14c-104">Протокол IP версии 6 (IPv6) не поддерживается на Lync Server 2010 или Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="5f14c-104">IP version 6 (IPv6) is not supported on Lync Server 2010 or Office Communications Server.</span></span> <span data-ttu-id="5f14c-105">В целях пилотного развертывания вы можете проверить сосуществование Lync Server 2010 и Lync Server 2013 с двумя стопками.</span><span class="sxs-lookup"><span data-stu-id="5f14c-105">For piloting purposes, you can test Lync Server 2010 and Lync Server 2013 dual-stack coexistence.</span></span> <span data-ttu-id="5f14c-106">Рекомендуется, чтобы все пулы для данного центрального сайта обновлялись до Lync Server 2013 перед включением IPv6 (сеть с двумя стеками) для всех пулов.</span><span class="sxs-lookup"><span data-stu-id="5f14c-106">We recommend that all pools for a given central site are upgraded to Lync Server 2013 before you enable IPv6 (dual-stack network) for any of the pools.</span></span> <span data-ttu-id="5f14c-107">Если необходимо настроить пул только для IPv6, то для тестирования в лабораторной среде рекомендуется настроить пул только для IPv6.</span><span class="sxs-lookup"><span data-stu-id="5f14c-107">If you need to configure a pool for IPv6 only, we recommend that you set up an IPv6-only pool in your lab environment for testing.</span></span>

<span data-ttu-id="5f14c-108">Во время миграции и сосуществования поддерживаются следующие сценарии.</span><span class="sxs-lookup"><span data-stu-id="5f14c-108">The following scenarios are supported during migration and coexistence:</span></span>

  - <span data-ttu-id="5f14c-109">Пулы Lync Server 2013, Lync Server 2010 и Office Communications Server 2007 R2 в режиме IPv4, а вместе с Lync Server 2013 — в режиме двойной стопки.</span><span class="sxs-lookup"><span data-stu-id="5f14c-109">Lync Server 2013, Lync Server 2010, and Office Communications Server 2007 R2 pools in IPv4 mode, coexisting with Lync Server 2013 in dual-stack mode.</span></span>

  - <span data-ttu-id="5f14c-110">Пул Lync Server 2013 в режиме "только IPv6", если в пуле только IPv6 есть приемник.</span><span class="sxs-lookup"><span data-stu-id="5f14c-110">Lync Server 2013 pool in IPv6-only mode, if the IPv6-only pool is siloed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

