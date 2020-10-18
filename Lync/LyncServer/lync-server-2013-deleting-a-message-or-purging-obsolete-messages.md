---
title: 'Lync Server 2013: удаление сообщения или удаление устаревших сообщений'
description: 'Lync Server 2013: удаление сообщения или удаление устаревших сообщений.'
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
ms.openlocfilehash: 928e34d2ab52b02155568c7da96e4ac1d8154b7a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575825"
---
# <a name="deleting-a-message-or-purging-obsolete-messages-in-lync-server-2013"></a><span data-ttu-id="6562a-103">Удаление сообщения или удаление устаревших сообщений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6562a-103">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6562a-104">_**Последнее изменение темы:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="6562a-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="6562a-105">Администратор сохраняемого чата может удалить сообщение из комнаты сохраняемого чата (и при необходимости может заменить его другим сообщением).</span><span class="sxs-lookup"><span data-stu-id="6562a-105">A Persistent Chat administrator can delete a message from a Persistent Chat room (and, optionally, can replace it with another message).</span></span> <span data-ttu-id="6562a-106">Кроме того, администраторы могут удалять устаревшие сообщения в рамках текущего обслуживания, чтобы свести к минимуму рост объема базы данных.</span><span class="sxs-lookup"><span data-stu-id="6562a-106">Administrators can also purge obsolete messages as part of ongoing maintenance, to minimize growth of the database.</span></span> <span data-ttu-id="6562a-107">Например, эта команда Windows PowerShell удаляет все сообщения из комнаты чата ITChatRoom, которые были отправлены пользователем kenmyer@litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="6562a-107">For example, this Windows PowerShell command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@litwareinc.com:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="6562a-108">В этом примере все удаленные сообщения заменяются заметкой о том, что сообщение больше не доступно:</span><span class="sxs-lookup"><span data-stu-id="6562a-108">And this example replaces any removed messages with the note that the message is no longer available:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

<span data-ttu-id="6562a-109">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Remove – CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) .</span><span class="sxs-lookup"><span data-stu-id="6562a-109">For more information, see the help topic for the [Remove-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

