---
title: Связи с резервным регистратором Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup Registrar relationships
ms:assetid: 7e078271-84b9-4666-989c-c4507a0cdf4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205033(v=OCS.15)
ms:contentKeyID: 48184631
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07380cbea030f5c9219cef2654b4761f215988e2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-registrar-relationships-in-lync-server-2013"></a>Связи регистратора резервного копирования в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-06-28_

Помимо обеспечения возможности аварийного восстановления, два сопряженных пула служат как резервные регистраторы друг для друга. В Lync Server 2013 отношения регистратора резервного копирования между интерфейсными пулами всегда являются 1:1 и обратными. Это означает, что если П1 является резервным для П2, то П2 должен быть резервным для П1, и не может быть резервным ни для какого другого интерфейсного пула. Это изменение из Lync Server 2010, в котором отношения резервного копирования пула переднего плана могут иметь не более одного.

Несмотря на то, что отношения резервного копирования между двумя интерфейсными пулами должны быть 1:1 и симметричными, каждый интерфейсный пул по-прежнему также может быть резервным регистратором для любого количества устройств для обеспечения связи в филиалах, как и в Lync Server 2010.

Обратите внимание, что Lync Server 2013 не расширяет поддержку аварийного восстановления для пользователей, размещенных на устройстве для обеспечения связи в филиалах. Если интерфейсный пул, который выступает в качестве резервного устройства для обеспечения связи в филиалах, отключается, пользователи, воходящие в устройство для обеспечения связи в филиалах, переходят в режим устойчивости даже после отказа пользователей, размещенных в пуле переднего плана, на резервный пул.

</div>

<span> </span>

</div>

</div>

</div>

