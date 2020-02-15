---
title: 'Lync Server 2013: перемещение комнаты чата из одной категории в другую'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40077d8092f8b0b78b6e9ce78cd16c6f1e0812f0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a>Перемещение комнаты чата из одной категории в другую в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

При создании комнаты чата не рекомендуется менять категорию сохраняемого чата. Однако если менеджер комнаты чата имеет привилегии **автора** в другой категории, то технически он или могут переместить комнату из одной категорию в другую. Комната не удаляется и воссоздается. Это изменение связи с базой данных.

Изменение категории комнаты должно происходить редко. Категория определяет разрешенное членство в комнате чата, поэтому при перемещении комнаты чата в другую категорию все системные списки управления доступом (SACL), которые более не поддерживаются новой категорией, очищаются. Например, если пользователь был участником комнаты и больше не является **AllowedMember** в новой категории, членство категории будет изменено, а пользователь будет удален из комнаты.

Дополнительные сведения о перемещении комнаты чата с помощью интерфейса командной строки Windows PowerShell можно найти в разделе Управление комнатой в разделе [Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Дополнительные сведения о настройке комнат чата приведены в статье [Configure комнаты в Lync Server 2013](lync-server-2013-configure-rooms.md) в документации по развертыванию.

</div>

<span> </span>

</div>

</div>

</div>

