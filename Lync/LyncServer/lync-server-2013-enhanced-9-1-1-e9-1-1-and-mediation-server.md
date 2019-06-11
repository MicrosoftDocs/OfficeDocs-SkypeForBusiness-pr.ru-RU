---
title: 'Lync Server 2013: Enhanced 9-1-1 (E9-1-1) и сервер-посредник'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enhanced 9-1-1 (E9-1-1) and Mediation Server
ms:assetid: d231221f-5596-4a87-a463-269f5bcce65f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398903(v=OCS.15)
ms:contentKeyID: 48185448
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a4d8ba329d55c916b089437d4c63804c592c0a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enhanced-9-1-1-e9-1-1-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="bf91d-102">Enhanced 9-1-1 (E9-1-1) и сервер-посредник в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf91d-102">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf91d-103">_**Тема последнего изменения:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="bf91d-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="bf91d-104">У сервера-посредника есть расширенные возможности, которые могут правильно взаимодействовать с улучшенными поставщиками услуг 9-1-1 (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="bf91d-104">The Mediation Server has extended capabilities so that it can correctly interact with Enhanced 9-1-1 (E9-1-1) service providers.</span></span> <span data-ttu-id="bf91d-105">На сервере обновлений не требуется специальная настройка; расширения SIP, необходимые для взаимодействия "E9-1-1", по умолчанию включаются в протокол SIP сервера-посредника для взаимодействия с одноранговым элементом шлюза, IP-УАТС или SBC поставщика услуг телефонной связи через Интернет, в том числе в службе E9-1-1. Хранятся</span><span class="sxs-lookup"><span data-stu-id="bf91d-105">No special configuration is needed on the Mediation Server; the SIP extensions required for E9-1-1 interaction are, by default, included in the Mediation Server’s SIP protocol for its interactions with a gateway peer (PSTN gateway, IP-PBX, or the SBC of an Internet Telephony Service Provider, including E9-1-1 Service Providers)</span></span>

<span data-ttu-id="bf91d-106">Можно ли прекратить подключение SIP к поставщику услуг E9-1-1 на существующем серверном пуле или потребовать от него изолированных серверов, которые будут зависеть от того, может ли объект однорангового SBC E9-1-1 взаимодействовать с пулом серверов обновлений.</span><span class="sxs-lookup"><span data-stu-id="bf91d-106">Whether the SIP trunk to an E9-1-1 Service Provider can be terminated on an existing Mediation Server pool or will require stand-alone Mediation Servers will depend on whether the E9-1-1 SBC can interact with a pool of Mediation Servers.</span></span> <span data-ttu-id="bf91d-107">Подробности можно найти [в разделе м:н магистрали в Lync Server 2013](lync-server-2013-m-n-trunk.md).</span><span class="sxs-lookup"><span data-stu-id="bf91d-107">For details, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

