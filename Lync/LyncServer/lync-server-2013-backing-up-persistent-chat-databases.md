---
title: 'Lync Server 2013: резервное копирование сохраненных баз данных чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backing up Persistent Chat databases
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945646(v=OCS.15)
ms:contentKeyID: 51541507
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8ffb99effcf0a42bbddefd7151aa40a8d691d9c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a><span data-ttu-id="2aad7-102">Резервное копирование сохраненных баз данных чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2aad7-102">Backing up Persistent Chat databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2aad7-103">_**Тема последнего изменения:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="2aad7-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="2aad7-104">Сохраняемый контент комнаты чата хранится в базе данных сохраняемого чата (MGC. mdf).</span><span class="sxs-lookup"><span data-stu-id="2aad7-104">Persistent Chat room content is stored in the Persistent Chat database (Mgc.mdf).</span></span> <span data-ttu-id="2aad7-105">Необходимо регулярно создавать резервные копии этих критически важных для бизнеса данных.</span><span class="sxs-lookup"><span data-stu-id="2aad7-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="2aad7-106">В дополнение к содержимому комнаты чата, в ней также хранятся сведения об участниках (например, пользователи и группы пользователей), ролях и доступе, которым они необходимы для общения с комнатой и комнатой чата.</span><span class="sxs-lookup"><span data-stu-id="2aad7-106">In addition to the chat room content, the Persistent Chat database also stores information about the principals (such as users and user groups), and the roles and access that they have to chat rooms and chat room.</span></span>

<span data-ttu-id="2aad7-107">Существует два способа резервного копирования данных сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="2aad7-107">There are two ways of backing up Persistent Chat data.</span></span>

  - <span data-ttu-id="2aad7-108">Резервное копирование SQL Server</span><span class="sxs-lookup"><span data-stu-id="2aad7-108">SQL Server Backup</span></span>

  - <span data-ttu-id="2aad7-109">`Export-CsPersistentChatData` Командлет, который экспортирует сохраняемые данные чата в виде файла</span><span class="sxs-lookup"><span data-stu-id="2aad7-109">The `Export-CsPersistentChatData` cmdlet, which exports Persistent Chat data as a file</span></span>

<span data-ttu-id="2aad7-110">Для данных, созданных с помощью резервной копии SQL Server, требуется значительно больше места на диске (возможно, 20 больше) `Export-CsPersistentChatData`, чем создано, но в резервной копии SQL Server более вероятна процедура, с помощью которой администраторы знакомы.</span><span class="sxs-lookup"><span data-stu-id="2aad7-110">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by `Export-CsPersistentChatData`, but SQL Server backup is more likely to be a procedure that administrators are familiar with.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

