---
title: Удаление экземпляров и баз данных SQL Server на внутреннем сервере
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f03a318e81b839d5f92dbaa4ddcc70bbbc8e2e3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>Удаление экземпляров и баз данных SQL Server на внутреннем сервере

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-19_

Вы удаляете базы данных и экземпляры Microsoft SQL Server после удаления серверов с Lync Server 2010, которые зависят от них, или после перенастройки серверов с Lync Server 2010 для использования другой базы данных. При отмене текущего SQL Server или изменении конфигурации текущего сервера, на котором работает Lync Server 2010, необходимо выполнить описанные ниже действия, чтобы сделать базы данных устаревшими или недоступными.

Чтобы удалить базы данных или экземпляры сервера архивирования или сервера мониторинга, необходимо сначала удалить роль сервера. Аналогичным образом для удаления экземпляров или баз данных в пуле переднего плана необходимо сначала удалить или перенастроить роль зависимого сервера. Эти процедуры не различаются между выровненными базами данных и отдельными экземплярами серверов. Расгруппировка баз данных не влияет на эти процедуры.

<div>

## <a name="in-this-section"></a>Содержание

  - [Удаление базы данных SQL Server для пула переднего плана](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [Удаление базы данных SQL Server для сервера мониторинга](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [Удаление базы данных SQL Server для сервера архивирования](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

