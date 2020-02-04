---
title: 'Lync Server 2013: отключение или включение чата'
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
ms.openlocfilehash: a3ed23319631dd8ab51131fe9a8d7a9099e35d18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757603"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a>Отключение или включение чата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-02-05_

Если тема сохраняемой комнаты чата больше не нужна, вы можете сделать ее недоступной для пользователей, отключив ее. Если комната чата отключена, все подключенные на данный момент участники отключаются от нее. Пользователи не могут снова подключиться к комнате чата или найти ее через поиск после ее отключения.

Отключенная комната чата может быть включена позднее администратором постоянного чата. Если комната чата отключена, список ее членов и другие параметры сохраняются. Если вы снова включите комнату, вам не нужно будет повторно создавать параметры вручную.

Если история комнаты чата сохраняется (сохраняемый журнал комнаты) — необязательный параметр для категории, которая применяется ко всем комнатам в категории; по умолчанию это значение сохраняется, но его можно отключить, установив для параметра **включить ведение журнала чата** в качестве значения ложь. Если комната чата отключена, содержимое сохраняется. Но содержимое не будет отображаться в поиске, пока комната чата остается в отключенном состоянии. Если включить ее позднее, пользователи смогут находить сообщения, опубликованные до того, как комната чата была отключена.

Дополнительные сведения об отключении и включении комнат чата с помощью интерфейса командной строки Windows PowerShell можно найти в разделе Управление комнатой на странице [Настройка сохраняемого сервера чата с помощью командлетов Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md). Чтобы отключить комнату чата, используйте следующую команду:

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

Чтобы включить комнату чата, установите для свойства Disabled значение false.

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

Обратите внимание, что комнаты чата нельзя включать или отключать с помощью панели управления Lync Server.

Дополнительные сведения о настройке комнат чатов можно найти в разделе [Настройка комнат в Lync Server 2013](lync-server-2013-configure-rooms.md) в документации по развертыванию.

</div>

<span> </span>

</div>

</div>

</div>

