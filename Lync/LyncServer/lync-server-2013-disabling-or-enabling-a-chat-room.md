---
title: 'Lync Server 2013: отключение или включение комнаты чата'
description: 'Lync Server 2013: отключение или включение комнаты чата.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling or enabling a chat room
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48706011
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b81ce2614cebcf554c0390369068d8fd8b8f932
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568155"
---
# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a>Отключение или включение комнаты чата в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-02-05_

Если тема сохраняемого чата больше не важна, вы можете сделать комнату чата недоступной для пользователей, отключив ее. Когда чат отключен, все подключенные на данный момент участники отключаются от него. Пользователи не могут снова подключиться к чату или найти его через поиск после его отключения.

Отключенная комната чата может быть включена позже администратором сохраняемого чата. Если чат отключен, список его участников и другие параметры сохраняются. При повторном включении их не потребуется создавать вручную повторно.

Если журнал чата сохраняется (сохранение журнала чата — это дополнительный параметр категории, который применяется ко всем чатам категории; по умолчанию он сохраняется, но эту функцию можно отключить путем установки для параметра **Enable Chat History** (Включить журнал чата) категории значения «false»), содержимое сохраняется, даже если чат отключен. Тем не менее, содержимое не будет отображаться в поиске, пока чат остается в отключенном состоянии. Если включить чат позднее, пользователи смогут находить сообщения, опубликованные до того, как чат был отключен.

Дополнительные сведения об отключении и активации комнат чата с помощью интерфейса командной строки Windows PowerShell можно найти в разделе Управление комнатой в разделе [Настройка сервера сохраняемого чата с помощью командлетов Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md). Чтобы отключить комнату чата, используйте команду, аналогичную следующей:

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

Чтобы включить комнату чата, установите для свойства Disabled значение false:

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

Обратите внимание, что комнаты чата невозможно включать и отключать с помощью панели управления Lync Server.

Дополнительные сведения о настройке комнат чата приведены в статье [Configure комнаты в Lync Server 2013](lync-server-2013-configure-rooms.md) в документации по развертыванию.

</div>

<span> </span>

</div>

</div>

</div>

