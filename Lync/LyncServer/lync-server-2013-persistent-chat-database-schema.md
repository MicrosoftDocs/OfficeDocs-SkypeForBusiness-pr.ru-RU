---
title: 'Lync Server 2013: схема базы данных сохраняемого чата'
description: 'Lync Server 2013: схема базы данных сохраняемого чата.'
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
ms.openlocfilehash: 66151201f65310cc8e6d3f2251be4f86ce2be15d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545155"
---
# <a name="persistent-chat-database-schema-in-lync-server-2013"></a>Схема базы данных сохраняемого чата в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-18_

В этом документе приведена схема базы данных сохраняемого чата в коммуникационном программном обеспечении Lync Server 2013.

База данных сохраняемого чата относится к базе данных, соответствующей серверам ролей сервера Lync Server 2013, **PersistentChatStore** (соответствующим базам данных MGC) и **PersistentChatComplianceStore** (соответствующим базам данных mgccomp). Цель публикации этой схемы – обеспечить возможность построения запросов и получения рекомендация по успешному созданию отчетов об использовании чата, активных комнатах, лучших авторах и т. д.

<div>


> [!IMPORTANT]  
> Мы сохраняем за собой право изменять эту схему. Корпорация Майкрософт не дает никаких гарантий в отношении полной обратной совместимости с данной опубликованной схемой.



</div>

Следуйте приведенным ниже рекомендациям.

  - SELECT \* //не поддерживается, так как список столбцов может увеличиваться.

  - Изменение схемы пользователем не поддерживается.

  - Операции записи не поддерживаются.

  - Все создаваемые запросы следует тестировать с помощью баз данных соответствующего размера для проверки того, будут ли они выполняться с должной производительностью.

<div>

## <a name="in-this-section"></a>Содержание

  - [Список таблиц сервера сохраняемого чата в Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-tables.md)

  - [Список таблиц соответствия сервера сохраняемого чата в Lync Server 2013](lync-server-2013-list-of-persistent-chat-server-compliance-tables.md)

  - [Сведения о таблице сервера сохраняемого чата в Lync Server 2013](lync-server-2013-persistent-chat-server-table-details.md)

  - [Примеры запросов к базе данных сохраняемого чата для Lync Server 2013](lync-server-2013-sample-persistent-chat-database-queries.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

