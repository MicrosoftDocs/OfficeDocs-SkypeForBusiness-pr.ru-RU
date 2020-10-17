---
title: 'Lync Server 2013: резервное копирование баз данных сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up Persistent Chat databases
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945646(v=OCS.15)
ms:contentKeyID: 51541507
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5eec65c22465ee5a2198e7f7147db2d0d014cc2b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523146"
---
# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a><span data-ttu-id="6b408-102">Резервное копирование баз данных сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b408-102">Backing up Persistent Chat databases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b408-103">_**Последнее изменение темы:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="6b408-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="6b408-104">Содержимое комнаты сохраняемого чата хранится в базе данных сохраняемого чата (MGC. mdf).</span><span class="sxs-lookup"><span data-stu-id="6b408-104">Persistent Chat room content is stored in the Persistent Chat database (Mgc.mdf).</span></span> <span data-ttu-id="6b408-105">Это критически важные для бизнеса данные, которые необходимо регулярно создавать при резервном копировании.</span><span class="sxs-lookup"><span data-stu-id="6b408-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="6b408-106">Кроме контента комнаты чата, в базе данных сохраняемого чата также хранятся сведения об участниках (например, о пользователях и группах пользователей), ролях и доступе, которые они должны использовать для общения с комнатами и комнатами чата.</span><span class="sxs-lookup"><span data-stu-id="6b408-106">In addition to the chat room content, the Persistent Chat database also stores information about the principals (such as users and user groups), and the roles and access that they have to chat rooms and chat room.</span></span>

<span data-ttu-id="6b408-107">Существует два способа резервного копирования данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="6b408-107">There are two ways of backing up Persistent Chat data.</span></span>

  - <span data-ttu-id="6b408-108">Резервное копирование SQL Server</span><span class="sxs-lookup"><span data-stu-id="6b408-108">SQL Server Backup</span></span>

  - <span data-ttu-id="6b408-109">`Export-CsPersistentChatData`Командлет, который экспортирует данные сохраняемого чата в виде файла</span><span class="sxs-lookup"><span data-stu-id="6b408-109">The `Export-CsPersistentChatData` cmdlet, which exports Persistent Chat data as a file</span></span>

<span data-ttu-id="6b408-110">Для данных, созданных с помощью резервного копирования SQL Server, требуется значительно больше дискового пространства (возможно, 20 раз больше), чем создано `Export-CsPersistentChatData` , но резервное копирование SQL Server, скорее всего, является процедурой, с которой могут ознакомиться Администраторы.</span><span class="sxs-lookup"><span data-stu-id="6b408-110">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by `Export-CsPersistentChatData`, but SQL Server backup is more likely to be a procedure that administrators are familiar with.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

