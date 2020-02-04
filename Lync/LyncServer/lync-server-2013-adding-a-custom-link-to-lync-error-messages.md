---
title: 'Lync Server 2013: добавление настраиваемой ссылки в сообщения об ошибках Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding a custom link to Lync error messages
ms:assetid: de756088-fcc3-4e47-bde8-4fa4cc852fd1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398979(v=OCS.15)
ms:contentKeyID: 48185607
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63523013d8df74a52fee307192d3f60eb5232121
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a>Добавление настраиваемой ссылки в сообщения об ошибках Lync в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-20_

Настройка сообщений об ошибках Lync 2013 путем добавления ссылки на сведения о поиске и устранении неполадок в службе поддержки. Для этого используйте командлеты командной консоли **New-CSClientPolicy** или **Set-CSClientPolicy** Lync Server с параметром кустомлинкинеррормессажес. Текст настраиваемой ссылки: "щелкните здесь, чтобы найти разделы поддержки от администратора", и его нельзя настроить.

Например, следующая команда приводит к появлению настраиваемой ссылки в области сносок каждого сообщения об ошибке Lync 2013 и задает для конечной ссылки значениеhttp://contoso.com/help/LyncHelpDesk.aspx:

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

С помощью **Grant-CSClientPolicy** можно назначить пользователям новую политику. Подробные сведения можно найти в разделе **New-CSClientPolicy** и **Grant-CSClientPolicy** в документации по среде управления Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

