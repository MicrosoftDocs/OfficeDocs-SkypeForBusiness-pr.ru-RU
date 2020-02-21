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
ms.openlocfilehash: a148b63438710c5faf599b6053dcaf4cce7d0bad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="connecting-survivable-branch-appliance-to-lync-server-2013-front-end-pool"></a>Подключение Survivable Branch Appliance к пулу переднего плана Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-05_

Каждое устройство для обеспечения связи в филиалах (SBA) связано с пулом переднего плана, который выступает в качестве регистратора резервных копий для SBA. После обновления пула переднего плана до Lync Server 2013 SBA должен быть связан с интерфейсным пулом во время обновления пула переднего плана. После обновления пула переднего плана SBA может быть связан с пулом переднего плана. Сюда входит удаление устройства обеспечения связи в филиалах из топологии в построителе топологий и повторное добавление этого устройства в построителе. Пользователи, размещенные в SBA, должны быть перемещены в другой интерфейсный пул перед удалением SBA из топологии. После повторного добавления устройства в топологию можно переместить этих пользователей обратно на данное устройство обеспечения связи в филиалах.

Эти действия приведены ниже.

1.  Перемещение пользователей филиалов, размещенных в SBA, в другой интерфейсный пул.

2.  Удалите SBA из топологии, чтобы разорвать существующий интерфейсный пул в качестве регистратора резервных копий.

3.  Обновите интерфейсный пул до Microsoft Lync Server 2013.

4.  Добавьте устройство обеспечения связи в филиалах обратно в топологию.

5.  Свяжите новый интерфейсный пул с SBA в качестве регистратора резервных копий.

6.  Переместите пользователей филиала обратно на устройство.

<div>

## <a name="in-this-section"></a>Содержание

  - [Добавление сайта филиала Lync Server 2013 для обеспечения связи в филиалах к топологии](lync-server-2013-add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology.md)

  - [Добавление сайта филиала Lync Server 2010 для обеспечения связи в филиалах к топологии](lync-server-2013-add-lync-server-2010-survivable-branch-appliance-branch-site-to-your-topology.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

