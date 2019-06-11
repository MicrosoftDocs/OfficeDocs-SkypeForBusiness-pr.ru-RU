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

# <a name="migration-and-coexistence-considerations-for-ipv6-in-lync-server-2013"></a>Вопросы миграции и сосуществования для IPv6 в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-06-14_

Протокол IP версии 6 (IPv6) не поддерживается на Lync Server 2010 или Office Communications Server. В целях пилотного развертывания вы можете проверить сосуществование Lync Server 2010 и Lync Server 2013 с двумя стопками. Рекомендуется, чтобы все пулы для данного центрального сайта обновлялись до Lync Server 2013 перед включением IPv6 (сеть с двумя стеками) для всех пулов. Если необходимо настроить пул только для IPv6, то для тестирования в лабораторной среде рекомендуется настроить пул только для IPv6.

Во время миграции и сосуществования поддерживаются следующие сценарии.

  - Пулы Lync Server 2013, Lync Server 2010 и Office Communications Server 2007 R2 в режиме IPv4, а вместе с Lync Server 2013 — в режиме двойной стопки.

  - Пул Lync Server 2013 в режиме "только IPv6", если в пуле только IPv6 есть приемник.

</div>

<span> </span>

</div>

</div>

</div>

