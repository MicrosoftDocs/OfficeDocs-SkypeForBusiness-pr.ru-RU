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
ms.openlocfilehash: 286ffe3450c3363b94e3ef1b0cd1905e70fd36eb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-response-groups-in-lync-server-2013"></a>Управление группами ответа в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2018-02-01_

Группы ответа — это компонент управления вызовами, который позволяет поместить в очередь вызовы, предназначенные определенной области, например службе технической поддержки, и затем перенаправить их группе назначенных людей, которых называют *агентами*.

Чтобы управлять группами ответов, следует настроить группы агентов, очереди и рабочие процессы, которые определяют, что происходит с вызовом с момента его получения до момента ответа на него агентом.

<div>


> [!NOTE]  
> Если в развертывании группы ответа более 300 рабочих процессов, лучше использовать командлеты командной консоли Lync Server для создания рабочих процессов. Если для создания рабочих процессов в пуле с более чем 300 рабочими процессами использовать средство настройки группы ответа, загрузка веб-страницы занимает слишком много времени. Количество агентов, косвенно связанных с рабочими процессами через очереди, также имеет пропорциональные эффекты загрузки страниц.



</div>

В подразделах этого раздела приводятся пошаговые процедуры для выполнения задач по настройке и обслуживанию приложения группы ответа в развертывании.

<div>

## <a name="in-this-section"></a>Содержание

  - [Управление группами агентов группы ответа в Lync Server 2013](lync-server-2013-managing-response-group-agent-groups.md)

  - [Управление очередями групп ответа в Lync Server 2013](lync-server-2013-managing-response-group-queues.md)

  - [Управление рабочими процессами группы ответа в Lync Server 2013](lync-server-2013-managing-response-group-workflows.md)

  - [Управление параметрами группы ответа уровня приложения в Lync Server 2013](lync-server-2013-managing-application-level-response-group-settings.md)

  - [Перемещение групп ответа в новый пул в Lync Server 2013](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [Управление группами ответа в Lync Server 2013 во время аварии](lync-server-2013-managing-response-groups-during-a-disaster.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

