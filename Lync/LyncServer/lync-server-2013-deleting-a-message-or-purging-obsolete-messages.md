---
title: 'Lync Server 2013: удаление сообщения или удаление устаревших сообщений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a message or purging obsolete messages
ms:assetid: 3f0c612d-6dfd-41a4-a5fe-5ff3448eb0ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215874(v=OCS.15)
ms:contentKeyID: 48706000
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91254ecffa70944f867f3df3b69290b52d041305
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-a-message-or-purging-obsolete-messages-in-lync-server-2013"></a>Удаление сообщения или удаление устаревших сообщений в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-02-05_

Администратор сохраняемого чата может удалить сообщение из комнаты сохраняемого чата (и при необходимости может заменить его другим сообщением). Кроме того, администраторы могут удалять устаревшие сообщения в рамках текущего обслуживания, чтобы свести к минимуму рост объема базы данных. Например, эта команда Windows PowerShell удаляет все сообщения из комнаты чата ITChatRoom, которые были отправлены пользователем kenmyer@litwareinc.com:

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

В этом примере все удаленные сообщения заменяются заметкой о том, что сообщение больше не доступно:

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Remove – CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) .

</div>

<span> </span>

</div>

</div>

</div>

