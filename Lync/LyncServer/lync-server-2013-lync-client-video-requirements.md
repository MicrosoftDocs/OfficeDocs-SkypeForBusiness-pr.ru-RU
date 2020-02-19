---
title: 'Lync Server 2013: требования к видео для клиента Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync client video requirements
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49733731
ms.date: 01/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e4a8e99c50bc62565ed597e65cef73a6aaddd08
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-client-video-requirements-for-lync-server-2013"></a>Требования к видео для клиента Lync для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2016-01-29_

В этом разделе описывается поддержка видеоустройств для видеовызовов Lync 2013 и описывается, как определить ожидаемое качество видео для различных конфигураций компьютера, планшета и мобильного устройства.

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a>Требования и возможности для настольных ПК и видео на планшете Windows

Lync 2013 содержит аппаратное ускорение для кодирования и декодирования видео в зависимости от стандарта H. 264/MPEG-4 в части 10 Advanced Video кодирования. Эта возможность позволяет компьютерам с более низкой скоростью ЦП кодировать и декодировать видео с более высоким разрешением. Требования к видеоустройствам зависят от конфигурации компьютера и необходимого разрешения видео.

<div>

## <a name="video-hardware-requirements"></a>Требования к видеоустройствам


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Функция</th>
<th>Требование</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Аппаратное ускорение декодирования H.264 с помощью DirectX Video Acceleration (DXVA)</p></td>
<td><ul>
<li><p>Графическая карта должна поддерживать DirectX 9.0 и работать в режиме декодирования DXVA2_ModeH264_VLD_NoFGT.</p></li>
<li><p>Должен быть установлен последний драйвер графической карты.</p></li>
</ul>
<div>

> [!NOTE]  
> Подробные сведения о режимах декодирования приведены <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A>в разделе.


</div></td>
</tr>
<tr class="even">
<td><p>Аппаратное ускорение кодирования H.264: требования к набору микросхем</p></td>
<td><p>Поддерживаются следующие решения для кодирования видео с аппаратным ускорением Intel:</p>
<ul>
<li><p>Наборы микросхем второго и третьего поколения Intel HD Graphics 2000, 2500, 3000 и 4000 (или более поздние версии) со встроенными аппаратными кодировщиками видео. Необходимо установить драйвер 15.28.9.2884 для графической подсистемы Intel HD или последнюю версию драйвера, включающую следующее:</p>
<ul>
<li><p>Драйвер дисплея 9.17.10.2884 или последний драйвер</p></li>
<li><p>Преобразование оборудования Media Foundation (ХМФТ) версии 3.12.10.31 или последней версии ХМФТ</p></li>
</ul></li>
</ul>
<p>Поддерживаются следующие решения для кодирования видео с аппаратным ускорением AMD (требуется обновление CU1 для Lync Server 2013):</p>
<ul>
<li><p>Модуль видеокодека AMD, доступный на нескольких отдельных графических платах и в интегрированных процессорах с ускоренной обработкой процессоров AMD серии с ускорением серии AMD. Должен быть установлен драйвер ядра видеокодека AMD 9.12.0.0 или более поздней версии.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Аппаратное ускорение кодирования H.264: требования к камере</p></td>
<td><p>Видеокамеры USB со встроенным аппаратным кодировщиком H.264, поддерживающие спецификацию USB Video Class (UVC) версии 1.5.</p>
<div>

> [!NOTE]  
> Lync 2013 поддерживает камеры UVC 1,5 с Windows 8 или Windows 8,1, в том числе поддержка UVC 1,5. Поскольку в Windows 7 не включена поддержка UVC 1.5, Lync 2013 работает с камерами UVC 1.5 как с обычными камерами без поддержки аппаратного кодирования.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>Определение возможностей кодирования и декодирования видео H.264

В общем случае максимальная производительность кодирования и декодирования для конкретной конфигурации компьютера определяется четырьмя основными факторами:

  - поддержка аппаратного ускорения декодирования с помощью DXVA;

  - поддержка аппаратного ускорения кодирования;

  - количество физических ядер;

  - индекс производительности Windows (WEI).

Средство оценки производительности WinSAT определяет индекс WEI. При запуске средства WinSAT создается формальный XML-документ с оценкой на компьютере в каталоге хранилища данных% WINDIR%\\с производительностью\\WinSAT\\. В этом XML-файле представлены два показателя, на основании которых можно определить возможности кодирования и декодирования:

  - значение VideoEncodeScore показывает производительность компьютера по программному кодированию видео;

  - значение GraphicsScore показывает производительность компьютера по кодированию видео с аппаратным ускорением.

В следующих таблицах приводится максимальная производительность кодирования и декодирования для нескольких типов ПК в зависимости от поддержки аппаратного ускорения. Для разрешения 640x360 и выше максимальная поддерживаемая частота кадров составляет 30 кадров в секунду (кадр/с). Для разрешений ниже 640x360 максимальная поддерживаемая частота кадров составляет 15 кадр/с.

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a>Компьютер без DXVA и без аппаратного ускорения кодирования

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Поддерживаемое разрешение кодировщика</th>
<th>Поддерживаемое разрешение декодера</th>
<th>Требование</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>424x240 (640x360 при 15 кадр/с только для приема)</p></td>
<td><p>1 ядро и VideoEncodeScore ≥ 4,0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>640x360</p></td>
<td><p>2 ядра и VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>640x360</p></td>
<td><p>1280X720</p></td>
<td><p>2 ядра и VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>4 ядра и VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>1280X720</p></td>
<td><p>1280X720</p></td>
<td><p>4 ядра и VideoEncodeScore ≥ 7,3</p></td>
</tr>
<tr class="even">
<td><p>1280X720</p></td>
<td><p>1920x1080</p></td>
<td><p>4 ядра и VideoEncodeScore ≥ 7,3</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>Н/Д</p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a>Компьютер с DXVA, но без аппаратного ускорения кодирования

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Поддерживаемое разрешение кодировщика</th>
<th>Поддерживаемое разрешение декодера</th>
<th>Требование</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>1920x1080</p></td>
<td><p>1 ядро и VideoEncodeScore ≥ 3,0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>2 ядра и VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>960x540</p></td>
<td><p>1920x1080</p></td>
<td><p>2 ядра и VideoEncodeScore ≥ 6,0</p></td>
</tr>
<tr class="even">
<td><p>1280X720</p></td>
<td><p>1920x1080</p></td>
<td><p>4 ядра и VideoEncodeScore ≥ 6,7</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>4 ядра и VideoEncodeScore ≥ 8,2</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Оценка WinSAT в Windows 7 ограничена до 7,9. Таким образом, возможность кодирования для компьютера без аппаратного ускорения кодировщика может быть достигнута только в Windows 8 или Windows 8,1, где максимальный показатель WinSAT равен 9,9.



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a>Компьютер с DXVA и с аппаратным ускорителем кодирования Intel HD Graphics

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Поддерживаемое разрешение кодировщика</th>
<th>Поддерживаемое разрешение декодера</th>
<th>Требование</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1280X720</p></td>
<td><p>1920x1080</p></td>
<td><p>Все графические карты Intel HD Graphics второго и третьего поколения</p></td>
</tr>
<tr class="even">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>Графические карты Intel HD Graphics второго и третьего поколения и GraphicsScore ≥ 5,0</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a>Возможности видео мобильных устройств

В следующей таблице описаны максимальные возможности видео для поддерживаемых мобильных устройств. Дополнительные сведения о поддержке мобильных устройств приведены в статье [планирование для мобильных клиентов в Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Функция</th>
<th>Windows Phone</th>
<th>iPhone</th>
<th>iPad</th>
<th>Android</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Максимальное разрешение кодирования H. 264</p></td>
<td><p>АДАПТЕР</p></td>
<td><p>КВГА: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720p: iPhone 5S и более поздних версий</p></td>
<td><p>VGA: iPad 2 и более поздних версий/iPad Mini 1 и более поздних версий</p>
<p>720p: iPad Air/iPad Mini 2/iPad Pro и более поздние версии</p></td>
<td><p>До VGA в зависимости от модели устройства</p></td>
</tr>
<tr class="even">
<td><p>Максимальное разрешение при декодировании H. 264</p></td>
<td><p>АДАПТЕР</p></td>
<td><p>КВГА: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720p: iPhone 5S и более поздних версий</p></td>
<td><p>VGA: iPad 2 и более поздних версий/iPad Mini 1 и более поздних версий</p>
<p>720p: iPad Air/iPad Mini 2/iPad Pro и более поздние версии</p></td>
<td><p>До VGA в зависимости от модели устройства</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

