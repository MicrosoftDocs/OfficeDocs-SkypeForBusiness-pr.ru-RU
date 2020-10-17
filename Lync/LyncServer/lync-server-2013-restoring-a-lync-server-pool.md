---
title: 'Lync Server 2013: восстановление пула Lync Server'
description: 'Lync Server 2013: восстановление пула Lync Server.'
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
ms.openlocfilehash: 02e92b4e7af9cf782d49c265425006e0118b9161
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543815"
---
# <a name="restoring-a-lync-server-pool-in-lync-server-2013"></a>Восстановление пула Lync Server в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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

