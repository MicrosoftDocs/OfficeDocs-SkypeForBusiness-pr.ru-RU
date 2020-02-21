---
title: Удаление базы данных SQL Server для сервера мониторинга
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Monitoring server
ms:assetid: aed5e394-d63e-4ad4-af40-f12d3a044344
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721848(v=OCS.15)
ms:contentKeyID: 49733781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f175f17b41a72c63aba77e6eb59aadce985ced82
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>Удаление базы данных SQL Server для сервера мониторинга

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-04_

После удаления сервера мониторинга Microsoft Lync Server 2010 можно удалить базы данных SQL Server, в которых размещены данные сервера. Используйте следующие процедуры для удаления определений из построителя топологий, а затем удалите базу данных и файлы журналов с сервера базы данных.

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Удаление базы данных SQL Server с помощью построителя топологий

1.  На сервере переднего плана Lync Server 2013 откройте построитель топологий.

2.  В построителе топологий перейдите к разделу **Общие компоненты** , а затем к **хранилищу SQL Server**, щелкните правой кнопкой мыши экземпляр SQL Server, связанный с удаленным или перенастроенным сервером мониторинга, а затем выберите команду **Удалить**.

3.  Опубликуйте топологию и проверьте состояние репликации.

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a>Удаление файлов базы данных из SQL Server

1.  Для удаления баз данных на сервере SQL Server вы должны быть членом группы администраторов системы SQL Server на этом сервере.

2.  Откройте командную консоль Lync Server.

3.  Введите в командной строке следующую команду:
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Где \<полное\> доменное имя — это полное доменное имя сервера базы данных, а \<экземпляр\> — это необязательный именованный экземпляр базы данных.

4.  Когда командлетом **Uninstall-CsDataBase** выводится приглашение подтвердить действия, прочитайте информацию и нажмите клавишу **Y** (или нажмите клавишу ВВОД), чтобы продолжить, или нажмите клавишу **N**, а затем — клавишу ВВОД, если хотите остановить выполнение командлета (т. е., в случае ошибок).

</div>

</div>

<span> </span>

</div>

</div>

</div>

