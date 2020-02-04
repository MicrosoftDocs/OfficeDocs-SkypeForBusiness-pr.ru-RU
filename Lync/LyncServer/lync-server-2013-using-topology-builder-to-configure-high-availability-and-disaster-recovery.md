---
title: Использование построителя топологий для настройки высокой доступности и аварийного восстановления
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Topology Builder to configure high availability and disaster recovery
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48185113
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73bcd2c2892e4e121512ae852d5920d600af91ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a>Использование построителя топологий для настройки высокой доступности и аварийного восстановления в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-06_

Выполните указанные ниже действия в построителе топологии для настройки высокой доступности и аварийного восстановления для постоянного сервера чата.

1.  Добавьте зеркальные базы данных и хранилище журналов SQL Server, которые являются получателями.

2.  Измените параметры службы сервера для сохраняемого чата следующим образом:
    
    1.  Включите зеркальное отображение для базы данных-источника.
    
    2.  Добавьте основное зеркальное хранилище SQL Server.
    
    3.  Включите базу данных доставки журналов SQL Server.
    
    4.  Добавьте хранилище журналов SQL Server с дополнительной доставкой.
    
    5.  Добавьте зеркало хранилища SQL Server для базы данных получателя.
    
    6.  Опубликуйте топологию.

</div>

<span> </span>

</div>

</div>

</div>

