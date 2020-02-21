---
title: 'Lync Server 2013: Добавление пользовательского текста в мгновенные сообщения'
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
ms.openlocfilehash: 2e42c04c84d6df91b592bf4709daf36d6822aa49
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a>Добавление пользовательского текста в мгновенные сообщения в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-20_

Добавьте заявление об отказе или предупреждение в начало каждой беседы Lync 2013 для обмена мгновенными сообщениями с помощью командлетов командной консоли **New-CSClientPolicy** или **Set-CSClientPolicy** Lync Server с параметром Warning.

В приведенном ниже примере показано, как добавить напоминание о безопасности в верхней части окна беседы при начале новой беседы с IM:

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

Назначьте эту политику пользователям с помощью **Grant – CSClientPolicy** . Дополнительные сведения см. в статье **New/CSClientPolicy** и **Grant – CSClientPolicy** в документации по консоли управления Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

