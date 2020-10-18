---
title: 'Lync Server 2013: технические требования для парковки вызовов'
description: 'Lync Server 2013: технические требования для парковки вызовов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Call Park
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48183897
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ddc17b40f78c42c090d1a87b4580ebdad0a07f6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577135"
---
# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a>Технические требования для парковки вызовов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-11-07_

В этом разделе описываются следующие технические требования для парковки вызовов:

  - Требования к оборудованию

  - Требования к программному обеспечению

  - Требования к портам

  - Требования к аудиофайлам

<div>

## <a name="hardware-requirements"></a>Требования к оборудованию

Приложение парковки вызовов имеет те же требования к оборудованию, что и серверы переднего плана. Сведения о требованиях к оборудованию приведены в статье [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) в документации по поддержке.

</div>

<div>

## <a name="software-requirements"></a>Требования к программному обеспечению

Приложение парковки вызовов имеет те же требования к операционной системе и программное обеспечение, что и серверы переднего плана. Сведения о требованиях к программному обеспечению приведены в статье [Поддержка серверов и средств операционной системы в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) в документации по поддержке.

Все серверы переднего плана и серверы Standard Edition, на которых развернуто приложение парковки вызовов, должны иметь среду выполнения формата Windows Media, установленную для серверов под управлением Windows Server 2008 R2 или Microsoft Media Foundation для серверов под управлением Windows Server 2012 или Windows Server 2012 R2. Для Windows Server 2008 R2 среда выполнения формата Windows Media устанавливается в составе Windows Desktop Experience. Windows Media Format Runtime или Microsoft Media Foundation необходим для файлов Windows Media Audio (WMA), воспроизводимых для прослушивания музыки при удержании.

</div>

<div>

## <a name="port-requirements"></a>Требования к портам

Приложение парковки вызовов использует следующий порт:

  - **Порт 5075**     Используется для запросов прослушивания SIP.

<div>


> [!NOTE]  
> Этот порт является установкой по умолчанию, которую можно изменить с помощью командлета <STRONG>Set-CsApplicationServer</STRONG>. Подробнее об этом командлете можно узнать в документации по командной консоли Lync Server.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Требования к аудиофайлам

Приложение парковки вызовов поддерживает только файлы Windows Media Audio (WMA) для музыки при удержании. Вы можете использовать Microsoft Expression Encoder 4 для настройки файлов для музыкальных файлов на удержании. Чтобы скачать Expression Encoder 4, обратитесь к разделу "Expression Encoder 4" на странице [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843) . Используйте средство, чтобы преобразовать файл в формат WMA. Рекомендуемый формат для файлов музыки для парковки на удержание вызовов — Media Audio 9, 44 кГц, 16 бит, моно, CBR, 32 кбит/с.

<div>


> [!NOTE]  
> Преобразованный файл воспроизводится на телефоне только на 16 кГц, даже если он был записан на 44 кГц.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

