---
title: 'Lync Server 2013: вопросы миграции и сосуществования для IPv6'
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
ms.openlocfilehash: 3f4a042089c0961eb8ea8313b78bbfcafa72c999
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a>Вопросы миграции и сосуществования для IPv6 в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-06-14_

Протокол IP версии 6 (IPv6) не поддерживается на Lync Server 2010 или Office Communications Server. При пилотном развертывании можно тестировать сосуществование с двумя стеками Lync Server 2010 и Lync Server 2013. Перед включением поддержки IPv6 (сеть с двумя стеками) для любого пула рекомендуется обновить все пулы для данного центрального сайта до Lync Server 2013. Если необходимо настроить пул только для IPv6, то для тестирования в лабораторной среде рекомендуется настроить пул только для IPv6.

Во время миграции и сосуществования поддерживаются следующие сценарии.

  - Пулы Lync Server 2013, Lync Server 2010 и Office Communications Server 2007 R2 в режиме IPv4, сосуществующие с Lync Server 2013 в режиме двойного стека.

  - Lync Server 2013 pool в режиме только IPv6, если пул, поддерживающий только IPv6, является приемником.

</div>

<span> </span>

</div>

</div>

</div>

