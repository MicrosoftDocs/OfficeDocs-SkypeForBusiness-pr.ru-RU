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
ms.openlocfilehash: fc0f47bf8e0a0aec5d2a2374decd79ce2bae77f2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a>Использование построителя топологий для настройки высокой доступности и аварийного восстановления в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-06_

Выполните указанные ниже действия в построителе топологий, чтобы настроить высокую доступность и аварийное восстановление для сервера сохраняемого чата.

1.  Добавьте зеркальные базы данных и хранилища SQL Server, которые являются вторичными хранилищами баз данных SQL Server.

2.  Измените свойства службы сервера сохраняемого чата следующим образом:
    
    1.  Включите зеркальное отображение для базы данных-источника.
    
    2.  Добавьте основное зеркальное хранилище SQL Server.
    
    3.  Включите базу данных доставки журналов SQL Server.
    
    4.  Добавьте дополнительное хранилище SQL Server для доставки журналов SQL Server.
    
    5.  Добавьте зеркало хранилища SQL Server для базы данных получателя.
    
    6.  Опубликуйте топологию.

</div>

<span> </span>

</div>

</div>

</div>

