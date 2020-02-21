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
ms.openlocfilehash: 56f74465ecba83ec2d4f857a504952a1ed271fb7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

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

