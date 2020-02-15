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
ms.openlocfilehash: 98d4d69a09ad58d4578c0636f7e6bce54497cb9d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a>Резервное копирование баз данных сохраняемого чата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-17_

Содержимое комнаты сохраняемого чата хранится в базе данных сохраняемого чата (MGC. mdf). Это критически важные для бизнеса данные, которые необходимо регулярно создавать при резервном копировании. Кроме контента комнаты чата, в базе данных сохраняемого чата также хранятся сведения об участниках (например, о пользователях и группах пользователей), ролях и доступе, которые они должны использовать для общения с комнатами и комнатами чата.

Существует два способа резервного копирования данных сохраняемого чата.

  - Резервное копирование SQL Server

  - `Export-CsPersistentChatData` Командлет, который экспортирует данные сохраняемого чата в виде файла

Для данных, созданных с помощью резервного копирования SQL Server `Export-CsPersistentChatData`, требуется значительно больше дискового пространства (возможно, 20 раз больше), чем создано, но резервное копирование SQL Server, скорее всего, является процедурой, с которой могут ознакомиться Администраторы.

</div>

<span> </span>

</div>

</div>

</div>

