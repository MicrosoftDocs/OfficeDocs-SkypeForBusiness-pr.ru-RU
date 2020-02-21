---
title: 'Lync Server 2013: расширенные 9-1-1 (E9-1-1) и сервер-посредник'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enhanced 9-1-1 (E9-1-1) and Mediation Server
ms:assetid: d231221f-5596-4a87-a463-269f5bcce65f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398903(v=OCS.15)
ms:contentKeyID: 48185448
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a84b9eb5579a1f0931f3363e2e4071ea7c8ac5e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enhanced-9-1-1-e9-1-1-and-mediation-server-in-lync-server-2013"></a><span data-ttu-id="d4cb1-102">Улучшенный 9-1-1 (E9-1-1) и сервер-посредник в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4cb1-102">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4cb1-103">_**Последнее изменение темы:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="d4cb1-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="d4cb1-104">Сервер-посредник имеет расширенные возможности, которые могут правильно взаимодействовать с расширенными поставщиками услуг 9-1-1 (E9-1-1).</span><span class="sxs-lookup"><span data-stu-id="d4cb1-104">The Mediation Server has extended capabilities so that it can correctly interact with Enhanced 9-1-1 (E9-1-1) service providers.</span></span> <span data-ttu-id="d4cb1-105">На сервере-посреднике не требуется никаких дополнительных настроек; расширения SIP, необходимые для взаимодействия E9-1-1, по умолчанию включены в протокол SIP сервера-посредника для взаимодействия с узлом шлюза (PSTN-шлюз, IP-УАТС или SBC поставщика услуг Интернет-телефонии, в том числе для службы E9-1-1). Доступа</span><span class="sxs-lookup"><span data-stu-id="d4cb1-105">No special configuration is needed on the Mediation Server; the SIP extensions required for E9-1-1 interaction are, by default, included in the Mediation Server’s SIP protocol for its interactions with a gateway peer (PSTN gateway, IP-PBX, or the SBC of an Internet Telephony Service Provider, including E9-1-1 Service Providers)</span></span>

<span data-ttu-id="d4cb1-106">Возможность завершения магистрали SIP к поставщику услуг E9-1-1 в существующем пуле сервера-посредника или обязательное наличие автономных серверов-посредников зависит от того, может ли SBC E9-1-1 взаимодействовать с пулом серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="d4cb1-106">Whether the SIP trunk to an E9-1-1 Service Provider can be terminated on an existing Mediation Server pool or will require stand-alone Mediation Servers will depend on whether the E9-1-1 SBC can interact with a pool of Mediation Servers.</span></span> <span data-ttu-id="d4cb1-107">Для получения дополнительных сведений см [M:N магистрали в Lync Server 2013](lync-server-2013-m-n-trunk.md).</span><span class="sxs-lookup"><span data-stu-id="d4cb1-107">For details, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

