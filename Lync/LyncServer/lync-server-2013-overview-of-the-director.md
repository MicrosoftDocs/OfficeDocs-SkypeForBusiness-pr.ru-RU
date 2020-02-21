---
title: 'Lync Server 2013: обзор директора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cf4e40f211cb992e914be20dc9962d55f229bc2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215885"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-director-in-lync-server-2013"></a>Обзор директора в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-08_

Директор — это сервер, на котором работает Lync Server 2013, который выполняет проверку подлинности запросов пользователей, но не предоставляет никаких учетных записей пользователей. Вы также можете развернуть директор в следующих двух сценариях:

  - Если вы включаете доступ внешних пользователей, развертывая пограничные серверы, необходимо также развернуть директор. В этом сценарии режиссер выполняет проверку подлинности внешних пользователей, а затем передает трафик на внутренние серверы. Если для проверки подлинности внешних пользователей используется директор, он освобождает серверы пула переднего плана от дополнительных затрат на проверку подлинности этих пользователей. Кроме того, он помогает разделяют внутренние пулы переднего плана от вредоносного трафика, например от атак типа "отказ в обслуживании". Если во время такой атаки сеть заполняется неподходящим внешним трафиком, этот трафик останавливается на директоре.

  - Если вы развертываете несколько интерфейсных пулов на центральном сайте, добавив директор на этот сайт, вы сможете упростить запросы проверки подлинности и повысить производительность. В этом сценарии все запросы сначала поступают в директоре, а затем — в соответствующий пул переднего плана.

</div>

<span> </span>

</div>

</div>

</div>

