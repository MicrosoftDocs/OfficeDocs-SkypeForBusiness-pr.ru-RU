---
title: 'Lync Server 2013: Настройка клиентов для использования с Office Web Apps Server'
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
ms.openlocfilehash: fb4b9b881d0f7d469c924a0ba032071092bddbbc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a>Настройка клиентов Lync Server 2013 для использования с сервером Office Web Apps

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-25_

Если вы хотите, чтобы пользователи выследовали все возможности Office Web App Server, нужно обновить эти пользователи до Microsoft Lync 2013; только пользователи Lync 2013 смогут выполнять такие действия, как прокрутка слайдов PowerPoint независимо от фактической презентации PowerPoint. (Это значит, что эти пользователи могут в любое время просматривать любой слайд в презентации, не мешая реальным презентациям.) Пользователи, которые не используют Lync 2013, смогут присоединяться к Конференции через Интернет и просматривать презентацию PowerPoint; Однако они не смогут независимо прокручивать слайды, а также не могут просматривать переходы между слайдами и просматривать внедренные видео.

Обратите внимание, что эти возможности всегда будут доступны пользователям Lync 2013; Это справедливо даже в том случае, если средство выступающего PowerPoint работает в Microsoft Lync 2010. Если презентация PowerPoint размещена пользователем, работающем под управлением Lync 2010, Lync Server 2013 будет согласовываться с сервером Office Web Apps, чтобы пользователи Lync 2013 выработали версию этой презентации на сервере Office Web Apps. Сервер Office Web Apps не предоставляет службы PowerPoint для пользователей, работающих с клиентами, отличными от Lync 2013. Вместо этого пользователи подключаются к службе сервера конференций и просматривайте презентации PowerPoint таким же образом, как и в Microsoft Lync Server 2010. Это также означает, что пользователи смогут получить доступ к более ограниченным возможностям, предлагаемым Lync Server 2010.

Несмотря на то, что для Office Web Apps Server (Кроме обновления до Lync 2013) не требуется настройка клиента, рекомендуется обновить участники Конференции до Internet Explorer 9. Несмотря на то, что Конференции можно получить с помощью Internet Explorer 8, существуют некоторые ограничения на использование этого веб-браузера. Например, пользователи Internet Explorer 8 не смогут изменить размер рабочей области PowerPoint на настраиваемый размер; Вместо этого они будут ограничены использованием одного из трех предопределенных размеров рабочей области. Кроме того, пользователи Internet Explorer 8 не смогут воспроизводить файлы мультимедиа.

</div>

<span> </span>

</div>

</div>

</div>

