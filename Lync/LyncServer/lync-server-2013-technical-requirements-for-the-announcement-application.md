---
title: 'Lync Server 2013: технические требования для приложения "Объявление"'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec0da862ce2032f5a659c9e9b7bd3b437349a3cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a>Технические требования для приложения "Объявление" в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-11-07_

В этом разделе описаны следующие технические требования для приложения извещения.

  - Требования к оборудованию

  - Требования к программному обеспечению 

  - Требования к портам

  - Требования к звуковым файлам

<div>

## <a name="hardware-requirements"></a>Требования к оборудованию

Приложение извещения имеет те же аппаратные требования, что и сервер переднего плана. Сведения о требованиях к оборудованию можно найти в документации [серверные платформы для Lync server 2013](lync-server-2013-server-hardware-platforms.md) .

</div>

<div>

## <a name="software-requirements"></a>Требования к программному обеспечению

Приложение извещения имеет те же требования к операционной системе и необходимые компоненты по отношению к серверам переднего плана. Подробные сведения о требованиях к программному обеспечению можно найти [в разделе Поддержка серверов и средств операционной системы в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) в документации по поддержке.

Все серверы переднего плана и стандартные серверы выпуска, на которых запущено приложение для объявления, должны установить среду выполнения формата Windows Media для серверов под управлением Windows Server 2008 R2 или Microsoft Media Foundation для серверов под управлением Windows Server 2012 или Windows Server 2012 R2. В Windows Server 2008 R2 среда выполнения формата Windows Media устанавливается как часть рабочего стола Windows. Для файлов Windows Media Audio (WMA), которые воспринимаются для объявлений и музыки, требуется приложение для работы с форматами среды предвыполнения Windows Media.

</div>

<div>

## <a name="port-requirements"></a>Требования к портам

Приложение извещения использует следующий порт:

  - **Порт 5071**   , используемый для запросов прослушивания SIP

<div>


> [!NOTE]  
> Этот порт указан в параметрах по умолчанию, которые можно изменить с помощью командлета <STRONG>Set-CsApplicationServer</STRONG>. Подробные сведения об этом командлете можно найти в документации по оболочке Lync Server Management Shell.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Требования к аудиофайлам

Приложение извещения поддерживает формат файла Wave (WAV) и формат Windows Media Audio (WMA) для музыки и объявлений. Требования к звуковым файлам для приложения для объявления совпадают с требованиями приложения группы ответа. Подробности можно найти [в разделе Технические требования для группы ответа в Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

