---
title: 'Lync Server 2013: удаление чата или категории'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting a chat room or category
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215881(v=OCS.15)
ms:contentKeyID: 48706009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f64b89abd0b3266d2be52e300458ceabf3f9b915
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a>Удаление чата или категории в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Сохраняемые комнаты чата могут быть удалены. Если у вас есть комната чата, которая больше не используется, ее можно отключить. Подробности можно найти [в разделе Отключение и включение комнаты чата в Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).

Администратор сохраняемого чата может запрашивать отключенные комнаты чата, а также периодически очищать и удалять комнаты чата с помощью командлета Windows PowerShell **Remove-ксперсистентчатрум**.

Категории можно удалить. Тем не менее, чтобы удалить категорию, необходимо сначала удалить из нее все комнаты чата или переместить комнаты чата в новую категорию, оставив пустую категорию для удаления. На сервере сохраняемого чата не разрешается удалять категории, содержащие комнаты чата. Подробности можно найти [в разделе Перемещение комнаты чата из одной категории в другую в Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).

Подробнее об удалении пустых категорий с помощью интерфейса командной строки Windows PowerShell можно узнать в разделе Управление комнатой на странице [Настройка сохраняемого сервера чата с помощью командлетов Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Дополнительные сведения о комнатах и категориях чата в разделе [Настройка комнат в Lync server 2013](lync-server-2013-configure-rooms.md) и [Настройка категорий в Lync Server 2013](lync-server-2013-configure-categories.md) в документации по развертыванию.

</div>

<span> </span>

</div>

</div>

</div>

