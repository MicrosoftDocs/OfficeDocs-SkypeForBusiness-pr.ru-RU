---
title: 'Lync Server 2013: Настройка клиентов для использования с сервером Office Web Apps'
description: 'Lync Server 2013: Настройка клиентов для использования с сервером Office Web Apps.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring clients for use with Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48185668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b9bd7cf1e76c481c40381234ba1a84cda5500dc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545525"
---
# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a>Настройка клиентов Lync Server 2013 для использования с сервером Office Web Apps

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-25_

Если вы хотите, чтобы пользователи выполнить все возможности сервера Office Web App, необходимо обновить эти пользователи до Microsoft Lync 2013; только пользователи Lync 2013 смогут выполнять такие задачи, как прокручивать слайды PowerPoint независимо от реальной презентации PowerPoint. (То есть эти пользователи могут просматривать любой слайд в презентации в любое время, не мешая реальным презентациям.) Пользователи, не использующие Lync 2013, по-прежнему смогут присоединяться к конференциям и просматривать презентацию PowerPoint; Однако они не смогут независимо прокручивать слайды и не могут просматривать переходы слайдов и просматривать внедренные видеозаписи.

Обратите внимание, что эти возможности всегда будут доступны пользователям Lync 2013; Это справедливо даже в том случае, если у докладчика PowerPoint работает с Microsoft Lync 2010. Если презентация PowerPoint размещается пользователем Lync 2010, Lync Server 2013 будет согласовываться с сервером Office Web Apps, чтобы пользователи Lync 2013 могли просматривать версию этой презентации на сервере Office Web Apps. Сервер Office Web Apps не предоставляет службы PowerPoint для пользователей, работающих с клиентами, отличными от Lync 2013. Вместо этого пользователи подключаются к службе сервера конференций и просматривают презентации PowerPoint так же, как и в Microsoft Lync Server 2010. Это также означает, что у этих пользователей будет доступ к более ограниченным возможностям, предоставляемым Lync Server 2010.

Несмотря на то, что для сервера Office Web Apps (Кроме обновления до Lync 2013) не требуется никакой конфигурации клиента, рекомендуется обновить участников Конференции до Internet Explorer 9. Хотя доступ к конференциям можно получить с помощью Internet Explorer 8, на использование данного браузера накладываются некоторые ограничения. Например, пользователи Internet Explorer 8 не смогут свободно изменять размер этапа PowerPoint, вместо этого им придется выбирать один из трех предварительно заданных размеров этапа. Кроме того, пользователи Internet Explorer 8 не смогут воспроизводить мультимедийные файлы.

</div>

<span> </span>

</div>

</div>

</div>

