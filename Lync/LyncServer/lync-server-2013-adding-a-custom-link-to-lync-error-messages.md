---
title: 'Lync Server 2013: Добавление настраиваемой ссылки в сообщения об ошибках Lync'
description: 'Lync Server 2013: Добавление настраиваемой ссылки в сообщения об ошибках Lync.'
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
ms.openlocfilehash: a5d333b6f27e10e5092de23fcdf1d37fd75e75a5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560035"
---
# <a name="adding-a-custom-link-to-lync-error-messages-in-lync-server-2013"></a>Добавление настраиваемой ссылки в сообщения об ошибках Lync в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-20_

Настройка сообщений об ошибках Lync 2013 путем добавления ссылки на сведения об устранении неполадок или справочной службе службы поддержки. Для этого используйте командлеты команд **New — CSClientPolicy** или **Set CSClientPolicy**   Lync Server с параметром кустомлинкинеррормессажес. Текст настраиваемой ссылки "щелкните здесь, чтобы получить доступ к разделам поддержки от администратора", и его нельзя настроить.

Например, следующая команда приводит к отображению настраиваемой ссылки в области сносок каждого сообщения об ошибке Lync 2013 и задает для конечной ссылки значение http://contoso.com/help/LyncHelpDesk.aspx:

    New-CsClientPolicy -Identity LyncErrorLink -CustomLinkInErrorMessages "http://contoso/help/LyncHelpDesk.aspx"

Назначьте эту политику пользователям с помощью **Grant – CSClientPolicy** . Дополнительные сведения см. в статье **New/CSClientPolicy** и **Grant – CSClientPolicy** в документации по консоли управления Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

