---
title: 'Lync Server 2013: схема базы данных сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat database schema
ms:assetid: 58d7d94f-42f5-4c3e-8fe5-901fbe92152e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558653(v=OCS.15)
ms:contentKeyID: 48184228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73f3b21fe8ea7f9fc71aa5432a601e9fa3ad2425
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-database-schema-in-lync-server-2013"></a>Схема базы данных сохраняемого чата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-18_

В этом документе описана схема базы данных сохраняемого чата в программном обеспечении Lync Server 2013.

База данных сохраняемого чата указывает на базу данных, соответствующую серверным ролям Lync Server 2013 ( **персистентчатсторе** ), соответствующей базе данных mgc, и **персистентчаткомплианцесторе** (соответствующей базе данных мгккомп). Цель публикации этой схемы — предоставить вам возможность создавать запросы и подробно ознакомиться с подробными сведениями о использовании чата, активных комнатах, основных плакатов и т. д.

<div>


> [!IMPORTANT]  
> Мы резервируем это право для развития этой схемы. Корпорация Майкрософт не предоставляет никаких гарантий для обеспечения полной обратной совместимости с этой опубликованной схемой.



</div>

Следуйте этим рекомендациям.

  - Функция SELECT\* ///не поддерживается, так как список столбцов может увеличиваться.

  - Изменения схемы, созданные пользователем, не поддерживаются.

  - Операции записи не поддерживаются.

  - Протестируйте любые запросы, которые вы создаете в соответствии с конкретными размерами баз данных, чтобы обеспечить выполнение запросов на уровне в соответствии с вашими потребностями.

<div>

## <a name="in-this-section"></a>Содержание

  - [Список таблиц сервера сохраняемого чата в Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [Список таблиц соблюдения требований для сервера сохраняемого чата в Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [Данные таблицы сервера сохраняемого чата в Lync Server 2013](lync-server-2013-persistent-chat-server-table-details.md)

  - [Примеры запросов к базе данных сохраняемого чата для Lync Server 2013](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

