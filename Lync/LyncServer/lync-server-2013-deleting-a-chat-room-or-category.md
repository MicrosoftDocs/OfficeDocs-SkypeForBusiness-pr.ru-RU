---
title: 'Lync Server 2013: удаление комнаты или категории чата'
description: 'Lync Server 2013: удаление комнаты или категории чата.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a chat room or category
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215881(v=OCS.15)
ms:contentKeyID: 48706009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ef89802171a1eeca7de18ff0a4eb8eb3895f1b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555375"
---
# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a>Удаление комнаты или категории чата в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Можно удалить комнаты сохраняемого чата. Если комната чата больше не используется, вы можете отключить ее. Дополнительные сведения см. [в разделе Отключение или включение комнаты чата в Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).

Администратор сохраняемого чата может запрашивать отключенные комнаты чата, а также периодически очищать и удалять комнаты чата с помощью командлета Windows PowerShell **Remove – CsPersistentChatRoom**.

Можно удалять категории. Однако чтобы удалить категорию, нужно сначала удалить в ней все комнаты чата или перенести их в другую категорию, оставив удаляемую категорию пустой. Сервер сохраняемого чата не позволяет удалять категорию, которая содержит комнаты чата. Дополнительную информацию можно узнать [в статье Перемещение комнаты чата из одной категории в другую в Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).

Дополнительные сведения об удалении пустых категорий с помощью интерфейса командной строки Windows PowerShell можно найти в разделе Управление комнатой в разделе [Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Дополнительные сведения о комнатах и категориях чата приведены в статье [Настройка комнат в Lync server 2013](lync-server-2013-configure-rooms.md) и [Настройка категорий в Lync Server 2013](lync-server-2013-configure-categories.md) в документации по развертыванию.

</div>

<span> </span>

</div>

</div>

</div>

