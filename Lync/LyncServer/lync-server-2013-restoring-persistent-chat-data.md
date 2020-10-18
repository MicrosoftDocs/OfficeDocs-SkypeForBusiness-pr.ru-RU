---
title: 'Lync Server 2013: восстановление данных сохраняемого чата'
description: 'Lync Server 2013: восстановление данных сохраняемого чата.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring Persistent Chat data
ms:assetid: c251a7fa-50da-434b-b39a-17f5978ce736
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945649(v=OCS.15)
ms:contentKeyID: 51541516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c75683e151daaadab8374ed5b41886da9a3aea3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575521"
---
# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a><span data-ttu-id="06ec1-103">Восстановление данных сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06ec1-103">Restoring Persistent Chat data in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06ec1-104">_**Последнее изменение темы:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="06ec1-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="06ec1-105">Содержимое комнаты сохраняемого чата хранится в базе данных сохраняемого чата (MGC. mdf).</span><span class="sxs-lookup"><span data-stu-id="06ec1-105">Persistent Chat room content is stored in the Persistent Chat database (mgc.mdf).</span></span> <span data-ttu-id="06ec1-106">Это критически важные для бизнеса данные, которые необходимо регулярно создавать при резервном копировании.</span><span class="sxs-lookup"><span data-stu-id="06ec1-106">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="06ec1-107">Кроме контента комнаты чата, субъектов (таких как пользователи и группы), а также роли и доступ для общения с комнатами и содержимым комнаты чата, также хранятся в базе данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="06ec1-107">In addition to the chat room content, principals (such as users and groups) and the roles and access that they have to chat rooms and chat room content, is also stored in the Persistent Chat database.</span></span>

<span data-ttu-id="06ec1-108">Способ восстановления данных сохраняемого чата зависит от метода, используемого для создания резервной копии.</span><span class="sxs-lookup"><span data-stu-id="06ec1-108">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span>

  - <span data-ttu-id="06ec1-109">Если вы использовали процедуры резервного копирования SQL Server, необходимо использовать процедуры восстановления SQL Server.</span><span class="sxs-lookup"><span data-stu-id="06ec1-109">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span>

  - <span data-ttu-id="06ec1-110">Если вы использовали командлет **Export – CsPersistentChatData** для резервного копирования данных сохраняемого чата, необходимо использовать командлет **Import – CsPersistentChatData** для восстановления данных.</span><span class="sxs-lookup"><span data-stu-id="06ec1-110">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

