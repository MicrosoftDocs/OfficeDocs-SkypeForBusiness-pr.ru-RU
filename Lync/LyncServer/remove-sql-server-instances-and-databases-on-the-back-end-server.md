---
title: Удаление экземпляров и баз данных SQL Server на внутреннем сервере
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfd97f461486a873bcfade12fe7359c43ba5680c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Удаление экземпляров и баз данных SQL Server на внутреннем сервере

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-19_

Вы удаляете базы данных и экземпляры Microsoft SQL Server после удаления серверов, на которых работает Lync Server 2010, которые зависят от них, или после перенастройки серверов, на которых работает Lync Server 2010, использовать другую базу данных. Выполните процедуру, описанную в этом разделе, при отмене текущего сервера SQL Server или перенастройке текущего сервера, на котором работает Lync Server 2010, таким образом, чтобы они отображали устаревшие или недоступные базы данных.

Чтобы удалить базы данных или экземпляры сервера архивирования или сервера мониторинга, сначала необходимо удалить роль сервера. Аналогичным образом, чтобы удалить экземпляры или базы данных для интерфейсного пула, необходимо сначала удалить или перенастроить роль зависимого сервера. Эти процедуры одинаково подходят для баз данных с выровненным размещением и отдельных экземпляров, относящихся к серверам. Выровненное размещение баз данных не влияет на выполнение этих процедур.

<div>

## <a name="in-this-section"></a>Содержание

  - [Удаление базы данных SQL Server для пула переднего плана](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [Удаление базы данных SQL Server для сервера мониторинга](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [Удаление базы данных SQL Server для сервера архивации](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

