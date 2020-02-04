---
title: 'Lync Server 2013: Управление группами ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing response groups
ms:assetid: 5a804d7d-3c1a-4647-a0e0-d5c4c8c23b73
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520996(v=OCS.15)
ms:contentKeyID: 48184222
ms.date: 02/01/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 210debb3c3879d6895b127b960139970bf73d020
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-groups-in-lync-server-2013"></a>Управление группами ответов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2018-02-01_

Группы ответа — это функция управления звонками, которая позволяет ставить в очередь звонки, которые выполняются в определенной области, например в службу поддержки, а затем перенаправлять звонки в определенную группу пользователей, которые называются *агентами*.

Для управления группами ответа настраиваются группы агента, очереди и рабочие процессы, которые определяют, что произойдет с вызовом с момента его появления, пока агент не ответит.

<div>


> [!NOTE]  
> Если у вас более 300 рабочих процессов в одном пуле в развертывании группы ответа, лучше использовать командлеты командной консоли Lync Server для создания рабочих процессов. Если вы используете средство настройки группы ответа для создания рабочих процессов для пула с более чем 300 рабочими процессами, веб-страница занимает много времени. Количество агентов, косвенно связанных с рабочими процессами, в очереди также имеет пропорциональный эффект для загрузки страницы.



</div>

В этой статье приведены пошаговые инструкции для задач, которые можно выполнять для настройки и обслуживания приложения группы ответа в развертывании.

<div>

## <a name="in-this-section"></a>Содержание

  - [Управление группами агентов группы ответа в Lync Server 2013](lync-server-2013-managing-response-group-agent-groups.md)

  - [Управление очередями групп ответов в Lync Server 2013](lync-server-2013-managing-response-group-queues.md)

  - [Управление рабочими процессами групп ответов в Lync Server 2013](lync-server-2013-managing-response-group-workflows.md)

  - [Управление параметрами группы ответа уровня приложения в Lync Server 2013](lync-server-2013-managing-application-level-response-group-settings.md)

  - [Перемещение групп ответа в новый пул в Lync Server 2013](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [Управление группами ответов в Lync Server 2013 в аварийном режиме](lync-server-2013-managing-response-groups-during-a-disaster.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

