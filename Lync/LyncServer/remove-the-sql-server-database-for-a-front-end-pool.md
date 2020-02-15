---
title: Удаление базы данных SQL Server для пула переднего плана
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a6aba3f084be6c40d5019af5da37f1a682f6eb8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Удаление базы данных SQL Server для пула переднего плана

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-04_

После удаления интерфейсного пула Microsoft Lync Server 2010 или повторной настройки пула для использования другой базы данных можно удалить базы данных SQL Server, на которых размещены данные пула. Используйте следующие процедуры для удаления определений из построителя топологий, а затем удалите базу данных и файлы журналов с сервера базы данных.

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Удаление базы данных SQL Server с помощью построителя топологий

1.  На сервере переднего плана Lync Server 2013 откройте построитель топологий и скачайте существующую топологию.

2.  В построителе топологий перейдите к разделу **Общие компоненты** , а затем к **хранилищу SQL Server**, щелкните правой кнопкой мыши экземпляр SQL Server, связанный с удаленным или перенастроенным интерфейсным пулом, а затем выберите команду **Удалить**.

3.  Опубликуйте топологию и проверьте состояние репликации.

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>Удаление базы данных пользователей и базы данных приложений из SQL Server

1.  Чтобы удалять базы данных на SQL Server, необходимо входить в группу системных администраторов сервера SQL Server, на котором удаляются файлы баз данных.

2.  Открытие консоли управления Lync Server

3.  Чтобы удалить базу данных для хранилища пользователей пула, введите:
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Где \<полное\> доменное имя — это полное доменное имя сервера базы данных, а \<экземпляр\> — это именованный экземпляр базы данных (то есть, если он определен).

4.  Чтобы удалить базу данных для хранилища приложений пула, введите:
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Где \<полное\> доменное имя — полное доменное имя сервера \<базы\> данных, а экземпляр — это именованный экземпляр базы данных (то есть, если он определен).

5.  Когда командлетом **Uninstall-CsDataBase** выводится приглашение подтвердить действия, прочитайте информацию и нажмите клавишу **Y** (или нажмите клавишу ВВОД), чтобы продолжить, или нажмите клавишу **N**, а затем — клавишу ВВОД, если хотите остановить выполнение командлета (т. е., в случае ошибок).

</div>

</div>

<span> </span>

</div>

</div>

</div>

