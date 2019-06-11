---
title: 'Lync Server 2013: создание групп агента группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create Response Group agent groups
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520969(v=OCS.15)
ms:contentKeyID: 48183688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0d282c4d166702c9b329271d69ef2d59b2f77aa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834767"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-response-group-agent-groups-lync-server-2013"></a>Создание групп агента группы ответа Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-12_

Когда вы создаете группу агентов, вы выбираете агентов, назначаемых группе, и указываете дополнительные параметры группы, такие как метод маршрутизации и возможность агента выполнять вход в группу и выход из нее.

Агент, который должен входить в группу и выйти из нее, отличается от входного и выходного в Lync Server, называется *формальным агентом*. Для приема вызовов, направленных в группу, официальные агенты должны сначала войти в группу. Это может быть удобно для агентов, которые отвечают на вызовы из группы неполный рабочий день. Формальные агенты для входа и выхода из их групп щелкают элемент меню в Lync 2013, чтобы открыть веб-браузер Windows Internet Explorer и отобразить ее консоль.

Агент, который не входит в группу и не выходит из нее, называется *неофициальным агентом*. Неформальные агенты автоматически подписываются в группу при входе в Lync Server и не могут выйти из группы.

<div>


> [!NOTE]  
> Агентами могут быть только локальные пользователи. Если агент перемещается из локальной сети в Online, звонки групп ответов не будут маршрутизироваться этому агенту.



</div>

<div>

## <a name="in-this-section"></a>Содержание

[Создание или изменение группы агента в Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

