---
title: 'Lync Server 2013: восстановление сохраняемых данных чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring Persistent Chat data
ms:assetid: c251a7fa-50da-434b-b39a-17f5978ce736
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945649(v=OCS.15)
ms:contentKeyID: 51541516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ed69938186de2aebf6268168e663abcb125ad86
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a><span data-ttu-id="b217e-102">Восстановление данных из сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b217e-102">Restoring Persistent Chat data in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b217e-103">_**Тема последнего изменения:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="b217e-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="b217e-104">Сохраняемый контент комнаты чата хранится в базе данных сохраняемого чата (MGC. mdf).</span><span class="sxs-lookup"><span data-stu-id="b217e-104">Persistent Chat room content is stored in the Persistent Chat database (mgc.mdf).</span></span> <span data-ttu-id="b217e-105">Необходимо регулярно создавать резервные копии этих критически важных для бизнеса данных.</span><span class="sxs-lookup"><span data-stu-id="b217e-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="b217e-106">В дополнение к содержимому комнаты чата, участникам (например, пользователям и группам), а также ролям и Access, которые им нужно общаться с комнатами и разговаривать с содержимым комнаты чата, в базе данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="b217e-106">In addition to the chat room content, principals (such as users and groups) and the roles and access that they have to chat rooms and chat room content, is also stored in the Persistent Chat database.</span></span>

<span data-ttu-id="b217e-107">Способ восстановления сохраняемых данных чата зависит от того, какой метод вы использовали для архивации.</span><span class="sxs-lookup"><span data-stu-id="b217e-107">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span>

  - <span data-ttu-id="b217e-108">Если были использованы процедуры резервного копирования SQL Server, необходимо использовать процедуры восстановления SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b217e-108">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span>

  - <span data-ttu-id="b217e-109">Если вы использовали командлет **Export-ксперсистентчатдата** для резервного копирования сохраненных данных чата, необходимо использовать командлет **Import-ксперсистентчатдата** для восстановления данных.</span><span class="sxs-lookup"><span data-stu-id="b217e-109">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

