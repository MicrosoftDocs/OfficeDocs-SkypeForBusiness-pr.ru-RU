---
title: 'Lync Server 2013: Настройка SQL Server для Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77f6357d38731438555b2c9e3af7ec6a22e9df7c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a>Настройка SQL Server для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-08-12_

В подразделах этого раздела обсуждается развертывание и настройка SQL Server для использования в корпоративном развертывании Lync Server. Серверы Standard Edition используют совместно размещенную версию SQL Server Express SQL Server, размер которой подходит для рабочих нагрузок сервера Standard Edition.

В центральном хранилище Lync Server 2013 хранятся пользовательские данные для всех серверов Enterprise Edition в пуле, и оно разработано на внутреннем сервере, основанном на SQL Server. Как централизованный репозиторий, центральное хранилище управления невозможно установить на том же компьютере, что и любой другой роли Lync Server 2013. Центральное хранилище управления не может находиться на сервере Enterprise Edition в пуле. Центральное хранилище управления создается автоматически при первой публикации топологии и выборе для создания баз данных. Для успешного завершения установки на компьютере, который вы указываете в качестве фонового сервера, должно быть запущено программное обеспечение базы данных SQL Server.

<div>

## <a name="in-this-section"></a>Содержание

  - [Размещение данных и файлов журналов SQL Server для Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [Настройка SQL Server в Lync Server 2013](lync-server-2013-configure-sql-server.md)

  - [Разрешения развертывания для SQL Server в Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [Установка базы данных с помощью командной консоли Lync Server в Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [Общие сведения о требованиях к брандмауэру для SQL Server с Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [Настройка кластеризации SQL Server для Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

