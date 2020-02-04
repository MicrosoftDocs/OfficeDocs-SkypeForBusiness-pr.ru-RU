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
ms.openlocfilehash: 51ee90020be9d23384c5ed90ca1f8095156eaf56
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-director-in-lync-server-2013"></a>Обзор директора в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-08_

Режиссер — это сервер, на котором работает Lync Server 2013, который проверяет подлинность запросов пользователя, но не предоставляет ни одной учетной записи пользователя. Вы также можете развернуть режиссер в следующих двух сценариях:

  - Если вы разрешите доступ внешним пользователям, развертывая пограничные серверы, необходимо также развернуть режиссер. В этом сценарии режиссер проверяет подлинность внешних пользователей, а затем передает трафик на внутренние серверы. Если для проверки подлинности внешних пользователей используется режиссер, он сбрасывает серверы пула переднего плана из-за непроизводительной проверки подлинности этих пользователей. Кроме того, она позволяет разрушить внутренние пулы интерфейсов из вредоносных сетей, например из-за атак типа "отказ от обслуживания". Если при такой атаке сеть перегружается с недопустимым внешним трафиком, этот трафик завершается на начальнике.

  - Если вы разворачиваете несколько пулов переднего плана на центральном сайте, добавив на него директорию, вы сможете упростить запросы на проверку подлинности и повысить производительность. В этом сценарии все запросы сначала поступают в директорию, а затем пересылает их в нужный пул переднего плана.

</div>

<span> </span>

</div>

</div>

</div>

