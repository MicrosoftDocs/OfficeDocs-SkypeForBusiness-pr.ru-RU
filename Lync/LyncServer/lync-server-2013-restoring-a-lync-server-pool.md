---
title: 'Lync Server 2013: восстановление пула Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Lync Server pool
ms:assetid: 6fe80fb3-38ad-4931-a07b-1763b61aa448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202176(v=OCS.15)
ms:contentKeyID: 51541488
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a4cfda150c1ea8fadba3adff98ab1a95255c11e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-lync-server-pool-in-lync-server-2013"></a>Восстановление пула Lync Server в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-18_

Развертывание Lync Server может включать в себя любой из следующих типов пулов:

  - Сервер переднего плана

  - Mediation Server (Сервер-посредник);

  - Сервер сохраняемого чата

  - Пограничный сервер

Если происходит сбой всего пула, выполните следующие действия для каждого из рядовых серверов в пуле.

  - Для пула переднего плана сначала восстановите сервер внутреннего сервера, а затем восстановите каждый сервер переднего плана. Дополнительные сведения приведены [в статье восстановление внутреннего сервера Enterprise Edition в Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md) и [Восстановление рядового сервера Enterprise Edition в Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

  - Для всех остальных типов пулов восстановите каждый сервер участника. Дополнительную информацию можно узнать [в статье Восстановление рядового сервера Enterprise Edition в Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

</div>

<span> </span>

</div>

</div>

</div>

