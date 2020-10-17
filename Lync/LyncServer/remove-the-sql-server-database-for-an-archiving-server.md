---
title: Удаление базы данных SQL Server для сервера архивирования
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for an Archiving server
ms:assetid: 6e8a1fcd-ed09-43b0-82c9-60e7ce116a01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688087(v=OCS.15)
ms:contentKeyID: 49733686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fab9cefc3fff51267426fd26263f9e2ec20a85ee
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518106"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>Удаление базы данных SQL Server для сервера архивирования

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-04_

После удаления сервера архивации Microsoft Lync Server 2010 вы можете удалить базы данных SQL Server, на которых размещены данные пула. Используйте следующие процедуры для удаления определений из построителя топологий, а затем удалите базу данных и файлы журналов с сервера базы данных.

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Удаление базы данных SQL Server с помощью построителя топологий

1.  На сервере переднего плана Lync Server 2013 откройте построитель топологий.

2.  В построителе топологий перейдите к разделу **Общие компоненты** , а затем к **хранилищу SQL Server**, щелкните правой кнопкой мыши экземпляр SQL Server, связанный с удаленным или перенастроенным сервером архивации, а затем выберите команду **Удалить**.

3.  Опубликуйте топологию и проверьте состояние репликации.

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a>Удаление файлов базы данных из SQL Server

1.  Чтобы удалять базы данных на SQL Server, необходимо входить в группу системных администраторов сервера SQL Server, на котором удаляются файлы баз данных.

2.  Откройте командную консоль Lync Server.

3.  Введите в командной строке следующую команду:
    
        Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Где \<FQDN\> — полное доменное имя сервера базы данных, а \<instance\> — это именованный экземпляр базы данных (то есть, если он определен).

4.  Когда командлетом **Uninstall-CsDataBase** выводится приглашение подтвердить действия, прочитайте информацию и нажмите клавишу **Y** (или нажмите клавишу ВВОД), чтобы продолжить, или нажмите клавишу **N**, а затем — клавишу ВВОД, если хотите остановить выполнение командлета (т. е., в случае ошибок).

</div>

</div>

<span> </span>

</div>

</div>

</div>

