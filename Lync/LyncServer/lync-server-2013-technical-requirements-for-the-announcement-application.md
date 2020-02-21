---
title: 'Lync Server 2013: технические требования для приложения "оповещение"'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8687c5b9c5f422994817910eec640cc795798d18
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a>Технические требования для приложения "объявление" в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-11-07_

В этом разделе описываются следующие технические требования для приложения "извещения".

  - Требования к оборудованию

  - Требования к программному обеспечению

  - Требования к портам

  - Требования к аудиофайлам

<div>

## <a name="hardware-requirements"></a>Требования к оборудованию

Приложение извещения имеет те же требования к оборудованию, что и серверы переднего плана. Сведения о требованиях к оборудованию приведены в статье [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) в документации по поддержке.

</div>

<div>

## <a name="software-requirements"></a>Требования к программному обеспечению

Приложение извещения имеет те же требования к операционной системе и программное обеспечение, что и серверы переднего плана. Сведения о требованиях к программному обеспечению приведены в статье [Поддержка серверов и средств операционной системы в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) в документации по поддержке.

На всех серверах переднего плана или серверах Standard Edition, на которых работает приложение оповещений, должна быть установлена среда выполнения формата Windows Media для серверов под управлением Windows Server 2008 R2 или Microsoft Media Foundation для серверов под управлением Windows Server 2012 или Windows Server 2012 R2. Для Windows Server 2008 R2 среда выполнения формата Windows Media устанавливается в составе Windows Desktop Experience. Windows Media Format Runtime или Microsoft Media Foundation необходим для файлов Windows Media Audio (WMA), которые приложение для оповещений воспроизводится для оповещений и музыки.

</div>

<div>

## <a name="port-requirements"></a>Требования к портам

Приложение извещения использует следующий порт:

  - **Порт 5071**   используется для запросов прослушивания SIP

<div>


> [!NOTE]  
> Этот порт указан в параметрах по умолчанию, которые можно изменить с помощью командлета <STRONG>Set-CsApplicationServer</STRONG>. Подробнее об этом командлете можно узнать в документации по командной консоли Lync Server.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Требования к аудиофайлам

Приложение извещения поддерживает формат файлов WAV и Windows Media Audio (WMA) для музыкальных сообщений и объявлений. Требования к звуковым файлам для приложения оповещений совпадают с требованиями приложения группы ответа. Подробные сведения см. [в статье технические требования для группы ответа в Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

