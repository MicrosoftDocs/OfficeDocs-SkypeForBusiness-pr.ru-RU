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

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a>Резервное копирование сохраненных баз данных чата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-17_

Сохраняемый контент комнаты чата хранится в базе данных сохраняемого чата (MGC. mdf). Необходимо регулярно создавать резервные копии этих критически важных для бизнеса данных. В дополнение к содержимому комнаты чата, в ней также хранятся сведения об участниках (например, пользователи и группы пользователей), ролях и доступе, которым они необходимы для общения с комнатой и комнатой чата.

Существует два способа резервного копирования данных сохраняемого чата.

  - Резервное копирование SQL Server

  - `Export-CsPersistentChatData` Командлет, который экспортирует сохраняемые данные чата в виде файла

Для данных, созданных с помощью резервной копии SQL Server, требуется значительно больше места на диске (возможно, 20 больше) `Export-CsPersistentChatData`, чем создано, но в резервной копии SQL Server более вероятна процедура, с помощью которой администраторы знакомы.

</div>

<span> </span>

</div>

</div>

</div>

