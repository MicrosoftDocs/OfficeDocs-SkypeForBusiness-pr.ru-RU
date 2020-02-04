---
title: 'Lync Server 2013: настройка SQL Server для Lync Server'
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
ms.openlocfilehash: efdd9d8fa7b010b420c7c532d422c9b52b6d69ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a>Настройка SQL Server для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-08-12_

В этом разделе объясняется, как развернуть и настроить SQL Server для развертывания в среде Lync Server. Серверы стандартных выпусков используют размещенную версию SQL Server Express на выровненном по размеру для рабочих нагрузок сервера Standard Edition.

Хранилище Lync Server 2013 Central Management содержит данные пользователей для всех серверов выпуска Enterprise Edition в рамках пула и предназначено для размещения на сервере SQL Server с интерфейсом. Централизованное хранилище не может быть установлено на том же компьютере, что и любая другая роль Lync Server 2013. Хранилище Центрального управления не может находиться на сервере Enterprise Edition в пуле. Хранилище Центрального управления создается автоматически при первой публикации топологии и выбирается для создания баз данных. Чтобы установка прошла успешно, на компьютере, который вы указываете как сервер заднего использования, должно быть установлено программное обеспечение SQL Server Database.

<div>

## <a name="in-this-section"></a>Содержание

  - [Размещение данных и файла журнала SQL Server для Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [Настройка SQL Server в Lync Server 2013](lync-server-2013-configure-sql-server.md)

  - [Разрешения на развертывание для SQL Server в Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [Установка базы данных с помощью командной консоли Lync Server в Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [Обзор требований к брандмауэру для SQL Server с Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [Настройка кластеризации SQL Server для Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

