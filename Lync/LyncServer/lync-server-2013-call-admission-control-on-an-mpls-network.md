---
title: 'Lync Server 2013: управление допуском звонков в сети MPLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on an MPLS network
ms:assetid: 0beec6be-2431-4255-a3d2-512dd030e66a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398168(v=OCS.15)
ms:contentKeyID: 48183387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23ff730e64b7c7a63e277e73fa082f6d9d4e1ca3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-an-mpls-network-with-lync-server-2013"></a>Управление допуском звонков в сети MPLS с помощью Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-22_

В сети с многопротокольной коммутацией по меткам (MPLS) все сайты соединены в полную сетку. Это значит, что все сайты подключаются напрямую к MPLS-магистрали поставщика услуг Интернета, и каждому сайту выделяется полоса пропускания, используемая для взаимодействия по каналу глобальной сети с MPLS-облаком. Не существует ни сетевого концентратора, ни центрального сайта для управления IP-маршрутизацией. На следующем рисунке показана простая сеть, основанная на технологии MPLS.

**Пример сети MPLS**

![Контроль допуска звонков с многопротокольной коммутацией по меткам (MPLS)](images/Gg398168.54602e6e-ec11-4dae-936d-b01acda8a179(OCS.15).jpg "Контроль допуска звонков с многопротокольной коммутацией по меткам (MPLS)")

Чтобы развернуть контроль допуска звонков в сети MPLS, требуется создать область сети, представляющую облако MPLS, и создать сетевой сайт, представляющий каждый вспомогательный сайт MPLS. На следующем рисунке показано, как следует настроить область сети и сетевые сайты, чтобы они представляли пример сети MPLS на предыдущем рисунке. Ограничения для общей пропускной способности и пропускной способности сеанса основываются на емкости канала связи глобальной сети от каждого сетевого сайта к области сети, которая представляет облако MPLS.

**Область сети и сетевые сайты для сети MPLS**

![Контроль допуска звонков с многопротокольной коммутацией по меткам (MPLS) — схема](images/Gg398168.f8f76283-5c0c-4133-8a78-3fbbfd016dc4(OCS.15).jpg "Контроль допуска звонков с многопротокольной коммутацией по меткам (MPLS) — схема")

</div>

<span> </span>

</div>

</div>

</div>

