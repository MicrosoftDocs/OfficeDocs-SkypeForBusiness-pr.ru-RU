---
title: 'Lync Server 2013: Настройка хранилища для архивации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up storage for Archiving
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48185858
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab7e22d4ff0e34d903fa0306d971705c5455b2f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521786"
---
# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a>Настройка хранилища для архивации в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-12-17_

Хранилище архивации для Lync Server 2013 включает следующие компоненты:

  - **Хранение данных**     Хранилище данных требуется для хранения содержимого для обмена мгновенными сообщениями.

  - **Хранение файлов**     Для хранения данных и хранилища файлов контента для конференц-связи (собраний) требуется хранилище файлов.

<div>

## <a name="setting-up-data-storage"></a>Настройка хранилища данных

Требования для настройки хранения данных для архивации в Lync Server 2013 зависят от того, как будут храниться данные архивации.

  - Интеграция сервера Lync Server 2013 Архивация с развертыванием Exchange для хранения архивных данных с помощью хранилища Exchange.

  - Настройте отдельные серверы баз данных SQL Server для хранения архивных данных.

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a>Настройка хранилищ Exchange для архивации данных

Для настройки Exchange для хранения архивных данных необходимо, чтобы в развертывании Exchange выполнялся Exchange 2013. Кроме того, почтовые ящики пользователей должны размещаться на сервере Exchange 2013, а их почтовые ящики должны размещаться на In-Place хранения. Более подробную информацию о настройке Exchange 2013 вы найдете в документации по продукту Exchange.

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a>Настройка серверов баз данных SQL Server для хранения данных архивации

Для архивации в Lync Server 2013 необходимо, чтобы программное обеспечение баз данных SQL Server сохранит архивные данные, если вы не интегрируете развертывание с Exchange.

Для баз данных архивации SQL Server необходимо установить SQL Server на компьютере, на котором будет размещаться база данных архивации. Можно использовать тот же экземпляр SQL, который используется для серверной базы данных пула переднего плана. Для повышения производительности необходимо развернуть базу данных архивации на компьютере, который отделен от центрального хранилища управления. Подробнее о совместном размещении компонентов Lync Server 2013 можно узнать в статье Supported [выровненный сервер в Lync server 2013](lync-server-2013-supported-server-collocation.md) в документации по поддержке.

На каждом сервере баз данных должна работать поддерживаемая версия SQL Server. Дополнительные сведения о поддерживаемых версиях приведены в статье [технические требования для архивации в Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) в документации по планированию.

Перед развертыванием и включением архивации необходимо настроить платформы SQL Server. Если у учетной записи, которая будет использоваться для публикации топологии, есть необходимые права и разрешения администратора, вы можете создать базу данных архивации (LcsLog) при публикации топологии. Вы также можете создать базу данных потом, например во время установки. Подробные сведения о SQL Server можно найти в техническом центре SQL Server по адресу [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045) .

<div>


> [!NOTE]  
> Убедитесь, что тип запуска службы агента SQL Server является автоматическим, а служба агента SQL Server запущена для экземпляра SQL, в котором хранится база данных архивации, чтобы можно было запускать задание по умолчанию архивации SQL Server для архивации в зависимости от управления службой агента SQL Server.



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a>Настройка хранилища файлов

При архивации используется общий файловый ресурс Lync Server 2013, который вы указали при настройке пула переднего плана или сервера Standard Edition. Общую папку, используемую для архивации, нельзя изменить. Подробнее о поддерживаемых системах хранения файлов можно узнать [в статье поддержка хранения файлов в Lync Server 2013](lync-server-2013-file-storage-support.md) в документации по поддержке.

</div>

</div>

<span> </span>

</div>

</div>

</div>

