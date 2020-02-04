---
title: Подключение Survivable Branch Appliance к пулу переднего плана Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Connecting Survivable Branch Appliance to Lync Server 2013 Front End pool
ms:assetid: 3c7ca33f-5295-4d82-9152-41d8bc6f35cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688026(v=OCS.15)
ms:contentKeyID: 49733616
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d73806f481cfe7c44a5eb9507d043565765a08f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a>Подключение Survivable Branch Appliance к пулу переднего плана Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-05_

Каждое работающее устройство филиала (СБА) связано с пулом переднего плана, который выступает в качестве регистратора резервных копий для СБА. Когда пул переднего плана обновляется до Lync Server 2013, СБА должен быть связан с пулом переднего плана, пока пул переднего плана будет обновлен. После обновления пула переднего плана СБА можно связать с пулом переднего плана. Это связано с тем, что удаление СБА из топологии в построителе топологии и повторное добавление СБА для Topology Builder. Пользователи, размещенные на СБА, должны быть перемещены в другой пул переднего плана, прежде чем удалять СБА из топологии. После того как СБА снова добавится в топологию, эти пользователи могут быть возвращены в СБА.

Эти действия описаны ниже.

1.  Перемещение пользователей филиалов, размещенных на СБА, в другой пул переднего плана.

2.  Удалите СБА из топологии, чтобы разорвать существующий пул переднего плана в качестве регистратора резервных копий.

3.  Обновите пул переднего плана до Microsoft Lync Server 2013.

4.  Добавьте СБА обратно в топологию.

5.  Свяжите новый пул переднего плана с СБА в качестве регистратора резервных копий.

6.  Переместить пользователей филиалов обратно в СБА.

<div>

## <a name="in-this-section"></a>Содержание

  - [Добавление в топологию сайта филиала устройства для обеспечения связи в филиалах Lync Server 2013](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [Добавление сайта филиала Lync Server 2010 Survivable Branch Appliance в топологию](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

