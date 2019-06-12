---
title: Удаление базы данных SQL Server для сервера мониторинга
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the SQL Server database for a Monitoring server
ms:assetid: aed5e394-d63e-4ad4-af40-f12d3a044344
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721848(v=OCS.15)
ms:contentKeyID: 49733781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fdb2888a6c3dc7cc5dd4e3b77b70310a405f607d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>Удаление базы данных SQL Server для сервера мониторинга

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-04_

После удаления сервера мониторинга Microsoft Lync Server 2010 вы можете удалить базы данных SQL Server, на которых размещены данные сервера. Используйте описанные ниже процедуры для удаления определений из построителя топологии и удаления файлов базы данных и журнала с сервера базы данных.

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Удаление базы данных SQL Server с помощью построителя топологии

1.  На сервере переднего плана Lync Server 2013 откройте "Построитель топологии".

2.  В построителе топологии откройте раздел **Общие компоненты** , а затем — **хранилище SQL Server**, щелкните правой кнопкой мыши экземпляр SQL Server, связанный с удаленным или перенастроенным сервером мониторинга, и выберите команду **Удалить**.

3.  Опубликуйте топологию и проверьте состояние репликации.

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a>Удаление файлов базы данных из SQL Server

1.  Для удаления баз данных на сервере SQL Server необходимо быть членом группы "Администраторы SQL Server" для сервера SQL Server, на котором нужно удалить файлы базы данных.

2.  Откройте командную консоль Lync Server Management Shell.

3.  В командной строке введите следующую команду:
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Где \<FQDN\> — полное доменное имя сервера базы данных, а \<экземпляр\> — это необязательный именованный экземпляр базы данных.

4.  Когда командлет **uninstall-ксдатабасе** предложит вам подтвердить действия, прочтите информацию, а затем нажмите клавишу **Y** (или клавишу ВВОД), чтобы **** продолжить, или клавишу с, чтобы остановить командлет (то есть ошибки).

</div>

</div>

<span> </span>

</div>

</div>

</div>

