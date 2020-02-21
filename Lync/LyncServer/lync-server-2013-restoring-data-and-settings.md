---
title: 'Lync Server 2013: восстановление данных и параметров'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring data and settings
ms:assetid: b07f5dd7-7bed-4819-8cb5-617f5acd478e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202185(v=OCS.15)
ms:contentKeyID: 51541503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d34d62aa5a27a3f59bae0893c4004ca25c2cb039
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-data-and-settings-in-lync-server-2013"></a>Восстановление данных и параметров в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-17_

Если вы реализовали топологию аварийного восстановления с подключенными пулами, а один из этих интерфейсных пулов прекратил работу и вам потребуется быстро восстановить службу для пользователей, ознакомьтесь [с разработкой отказа для пула в Lync Server 2013](lync-server-2013-failing-over-a-pool.md). В противном случае используйте сведения, приведенные в следующих разделах, вместе с листами в [таблицах резервного копирования и восстановления для Lync server 2013](lync-server-2013-backup-and-restoration-worksheets.md), чтобы восстановить Lync Server после сбоя или сбоя.

<div>


> [!NOTE]  
> Чтобы сократить время простоя и возможной потери данных, выполните процедуры восстановления, описанные в этом документе, только в том случае, если процедуры устранения неполадок неэффективны при определении и исправлении проблемы. Во время устранения неполадок попробуйте минимизировать влияние на другие серверы и компоненты при завершении работы и перезапуске серверов.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Подготовка к восстановлению Lync Server 2013](lync-server-2013-preparing-to-restore-lync-server.md)

  - [Восстановление сервера Standard Edition в Lync Server 2013](lync-server-2013-restoring-a-standard-edition-server.md)

  - [Восстановление сервера, на котором размещается центральное хранилище управления, в Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)

  - [Восстановление внутреннего сервера Enterprise Edition в Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)

  - [Восстановление рядового сервера Enterprise Edition в Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md)

  - [Восстановление пула Lync Server в Lync Server 2013](lync-server-2013-restoring-a-lync-server-pool.md)

  - [Выполнение отработки отказа для пула переднего плана ABC в Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md)

  - [Восстановление хранилища файлов в Lync Server 2013](lync-server-2013-restoring-a-file-store.md)

  - [Восстановление данных мониторинга или архивации в Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md)

  - [Восстановление данных сохраняемого чата в Lync Server 2013](lync-server-2013-restoring-persistent-chat-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

