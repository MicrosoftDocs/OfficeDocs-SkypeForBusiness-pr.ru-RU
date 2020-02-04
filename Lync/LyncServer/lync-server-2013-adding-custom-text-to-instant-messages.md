---
title: 'Lync Server 2013: добавление пользовательского текста в мгновенные сообщения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding custom text to instant messages
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398847(v=OCS.15)
ms:contentKeyID: 48185458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b54b4724568a4f57bebc7ef6162a553cfdd9a091
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a>Добавление пользовательского текста в мгновенные сообщения в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-20_

Добавляйте заявление об отказе или предупреждение в начало каждой из мгновенных сообщений Lync 2013, используя командлеты командной консоли **New-CSClientPolicy** или **Set-CSClientPolicy** Lync Server с параметром "с предупреждением".

В приведенном ниже примере в верхней части окна беседы добавляется напоминание о безопасности при запуске новой ТЕКСТовой беседы.

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

С помощью **Grant-CSClientPolicy** можно назначить пользователям новую политику. Подробные сведения можно найти в разделе **New-CSClientPolicy** и **Grant-CSClientPolicy** в документации по среде управления Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

