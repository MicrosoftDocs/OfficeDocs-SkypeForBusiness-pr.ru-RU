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
ms.openlocfilehash: d8040d52690628b6085727d6a1fdac9288b94d5e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-message-or-purging-obsolete-messages-in-lync-server-2013"></a><span data-ttu-id="6f7b1-102">Удаление сообщения или удаление устаревших сообщений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f7b1-102">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f7b1-103">_**Тема последнего изменения:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="6f7b1-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="6f7b1-104">Администратор сохраняемого чата может удалить сообщение из записной комнаты чата (и, при необходимости, может заменить его другим сообщением).</span><span class="sxs-lookup"><span data-stu-id="6f7b1-104">A Persistent Chat administrator can delete a message from a Persistent Chat room (and, optionally, can replace it with another message).</span></span> <span data-ttu-id="6f7b1-105">Кроме того, для минимизации роста базы данных администраторы могут удалять устаревшие сообщения в рамках текущего обслуживания.</span><span class="sxs-lookup"><span data-stu-id="6f7b1-105">Administrators can also purge obsolete messages as part of ongoing maintenance, to minimize growth of the database.</span></span> <span data-ttu-id="6f7b1-106">Например, эта команда Windows PowerShell удаляет все сообщения из комнаты чата Итчатрум, которые были опубликованы пользователем kenmyer@litwareinc.com:</span><span class="sxs-lookup"><span data-stu-id="6f7b1-106">For example, this Windows PowerShell command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@litwareinc.com:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="6f7b1-107">В этом примере все удаленные сообщения заменяются заметкой о том, что сообщение больше не доступно.</span><span class="sxs-lookup"><span data-stu-id="6f7b1-107">And this example replaces any removed messages with the note that the message is no longer available:</span></span>

    Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.litwareinc.com\ITChatRoom" -UserUri "sip:kenmyer@litwareinc.com" -ReplaceMessage "This message is no longer available."

<span data-ttu-id="6f7b1-108">Дополнительные сведения можно найти в разделе справки по командлету [Remove-ксперсистентчатмессаже](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) .</span><span class="sxs-lookup"><span data-stu-id="6f7b1-108">For more information, see the help topic for the [Remove-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Remove-CsPersistentChatMessage) cmdlet.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

