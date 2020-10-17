---
title: 'Lync Server 2013: создание групп агентов группы ответа'
description: 'Lync Server 2013: создание групп агентов группы ответа.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group agent groups
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520969(v=OCS.15)
ms:contentKeyID: 48183688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9420ee5f6fbd4b995c8542b848ef30f53e46fc4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548695"
---
# <a name="create-response-group-agent-groups-lync-server-2013"></a>Создание групп агентов группы ответа Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-12_

Когда вы создаете группу агентов, вы выбираете агентов, назначаемых группе, и указываете дополнительные параметры группы, такие как метод маршрутизации и возможность агента выполнять вход в группу и выход из нее.

Агент, который должен входить в группу и выходить из нее, отличается от входа или выхода из Lync Server, называется *формальным агентом*. Официальные агенты должны войти в группу, прежде чем они смогут получать направленные в нее звонки. Это может быть удобно для агентов, которые отвечают на звонки из группы неполный рабочий день. Формальные агенты входят в группы и выходят из них, щелкая элемент меню в Lync 2013, чтобы открыть браузер Windows Internet Explorer и отобразить консоль веб-страницы.

Агент, который не входит в группу и не выходит из нее, называется *неофициальным агентом*. Неформальные агенты автоматически подписываются в группу при входе в Lync Server и не могут выходить из группы.

<div>


> [!NOTE]  
> Агентами могут быть только локальные пользователи. Если агент переходит из локального режима в интерактивный, ему не будут направляться звонки группы ответа.



</div>

<div>

## <a name="in-this-section"></a>Содержание

[Создание или изменение группы агентов в Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

