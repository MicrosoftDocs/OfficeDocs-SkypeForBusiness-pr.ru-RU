---
title: 'Lync Server 2013: технические требования для группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b07ddfa11f23c7e5183c243020c441db7219660
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a>Технические требования для группы ответа в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-11-07_

В этом разделе описываются следующие технические требования для приложения группы ответа.

  - Требования к оборудованию

  - Требования к программному обеспечению

  - Требования к портам

  - Требования к аудиофайлам

  - Требования к средствам настройки группы ответа

<div>

## <a name="hardware-requirements"></a>Требования к оборудованию

Приложение группы ответа имеет те же требования к оборудованию, что и серверы переднего плана. Сведения о требованиях к оборудованию приведены в статье [Server Hardware Platforms for Lync server 2013](lync-server-2013-server-hardware-platforms.md) в документации по поддержке.

</div>

<div>

## <a name="software-requirements"></a>Требования к программному обеспечению

Приложение группы ответа имеет те же требования к операционной системе и программное обеспечение, что и серверы переднего плана. Сведения о требованиях к программному обеспечению приведены в статье [Поддержка серверов и средств операционной системы в Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) в документации по поддержке.

Если вы используете файлы Windows Media Audio (WMA) для музыкальных сообщений и оповещений для группы ответа, на всех серверах переднего плана или серверах Standard Edition, на которых работает приложение группы ответа, должна быть установлена среда выполнения формата Windows Media для серверов под управлением Windows. Сервер 2008 R2 или Microsoft Media Foundation для серверов под управлением Windows Server 2012 или Windows Server 2012 R2. Для Windows Server 2008 R2 среда выполнения формата Windows Media устанавливается в составе Windows Desktop Experience.

Дополнительные сведения о требованиях к звуку см. ниже в подразделе "Требования к звуковым файлам".

</div>

<div>

## <a name="port-requirements"></a>Требования к портам

Приложение группы ответа использует следующие порты:

  - **Порт 5071**   используется для запросов прослушивания SIP

  - **Порт 8404**   используется для межсерверной связи
    
    <div>
    

    > [!NOTE]  
    > Этот порт используется для службы поиска и является обязательным при развертывании приложения группы ответа в пуле с несколькими серверами переднего плана.

    
    </div>

<div>


> [!NOTE]  
> Эти порты отражают параметры по умолчанию, которые вы можете изменить с помощью командлета <STRONG>Set-CsApplicationServer</STRONG>. Подробнее об этом командлете можно узнать в документации по командной консоли Lync Server.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Требования к аудиофайлам

Приложение группы ответа поддерживает формат WAV-файла и формат файлов Windows Media Audio (WMA) для сообщений группы ответа, музыки на удержании или ответов на интерактивные голосовые вызовы (IVR).

Для формата файлов Windows Media требуется, чтобы среда выполнения формата Windows Media была установлена на серверах переднего плана под управлением Windows Server 2008 R2 и Windows Server 2008. Дополнительные сведения см. выше в подразделе "Требования к программному обеспечению".

<div>

## <a name="supported-wave-file-formats"></a>Поддерживаемые форматы файлов WAV

Все файлы WAV должны удовлетворять следующим требованиям:

  - 8-разрядный или 16-разрядный файл

  - Формат линейной импульсно-кодовой модуляции, A-Law или mu-Law

  - Моно или стерео

  - 4 МБ или меньше

Для обеспечения наилучшей производительности файлов WAV рекомендуется использовать монофонический 16-разрядный файл WAV с частотой 16 кГц.

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a>Поддерживаемые форматы файлов WMA

Если вы используете файл WMA рекомендуется применять низкие скорости и проверить производительность системы под нагрузкой.

Преобразовать файл в формат WMA вы можете с помощью Microsoft Expression Encoder 4. Чтобы скачать Expression Encoder 4, ознакомьтесь [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843)со статьей.

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a>Требования к средствам настройки группы ответа

Средство настройки группы ответа поддерживает сочетания операционных систем и веб-браузеров, описанные в следующей таблице.

<div>


> [!NOTE]  
> Поддерживаются 32-разрядная или 64-разрядная версии операционных систем. Поддерживаются только 32-разрядные версии Internet Explorer.



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>Поддерживаемые операционные системы и веб-браузеры

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Операционная система</th>
<th>Веб-браузер</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Vista с пакетом обновления 2 (SP2)</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (основной режим)</p>
<p>Internet Explorer 9 (основной режим)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 с пакетом обновления 1 (SP1)</p></td>
<td><p>Internet Explorer 8 (основной режим)</p>
<p>Internet Explorer 9 (основной режим)</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 с пакетом обновления 2 (SP2)</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (основной режим)</p>
<p>Internet Explorer 9 (основной режим)</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 с пакетом обновления 1 (SP1)</p></td>
<td><p>Internet Explorer 8 (основной режим)</p>
<p>Internet Explorer 9 (основной режим)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a>Консоль агента группы ответа

Консоль агента поддерживает сочетания операционной системы и веб-браузера, перечисленные в следующей таблице.

<div>


> [!NOTE]  
> Поддерживаются 32-разрядная или 64-разрядная версии операционных систем. Поддерживаются только 32-разрядные версии Internet Explorer.



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>Поддерживаемые операционные системы и веб-браузеры

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Операционная система</th>
<th>Веб-браузер</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Vista с пакетом обновления 2 (SP2)</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (основной режим)</p>
<p>Internet Explorer 9 (основной режим)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 с пакетом обновления 1 (SP1)</p></td>
<td><p>Internet Explorer 8 (основной режим)</p>
<p>Internet Explorer 9 (основной режим)</p>
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 с пакетом обновления 2 (SP2)</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (основной режим)</p>
<p>Internet Explorer 9 (основной режим)</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 с пакетом обновления 1 (SP1)</p></td>
<td><p>Internet Explorer 8 (основной режим)</p>
<p>Internet Explorer 9 (основной режим)</p>
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

