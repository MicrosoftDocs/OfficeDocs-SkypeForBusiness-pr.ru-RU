---
title: Таблица VideoStream
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: Каждая запись представляет собой один видеопоток. Одна линия мультимедиа видео обычно содержит два видеопотока.
ms.openlocfilehash: 78bc415c7b95fd0f9b6ecb3f3242b5a29c93c0dd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756070"
---
# <a name="videostream-table"></a>Таблица VideoStream
 
Каждая запись представляет собой один видеопоток. Одна линия мультимедиа видео обычно содержит два видеопотока.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Ссылки из [таблицы MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |R Ссылки из [таблицы MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Ссылки из [таблицы MediaLine](medialine-0.md).  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |Уникальный идентификатор в линии мультимедиа.  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |Foreign, Primary  <br/> |Описание полезной нагрузки. Дополнительные сведения см. в таблице [PayloadDescription.](payloaddescription.md) <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |Средний уровень дрожания в сети на основе статистики протокола RTCP.  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |Максимальный нервный срыв сети во время сеанса видео.  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |Время приема-передачи на основе статистики RTCP.  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |Максимальное время в пути для видеопотока.  <br/> |
|**PacketLossRate** <br/> |десятичных (5,4)  <br/> | <br/> |Средний коэффициент потерь пакетов в течение вызова.  <br/> |
|**PacketLossRateMax** <br/> |десятичных (5,4)  <br/> | <br/> |Максимальная потеря пакетов, наблюдавшаяся в течение вызова.  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |Количество пакетов для видеопотока (RTP).  <br/> |
|**BandwidthEst** <br/> |int  <br/> | <br/> |Оценки пропускной способности для видеопотока.  <br/> |
|**VideoResolution** <br/> |char(9)  <br/> | <br/> |Разрешение видео в пикселах (ширина умножается на высоту в пикселах). Указывается как строка.  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |Средняя скорость передачи видеопотока.  <br/> |
|**InboundVideoFrameRateAvg** <br/> |десятичной (9,4)  <br/> | <br/> |Полученная частота кадров видео.  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |десятичной (9,4)  <br/> | <br/> |Скорость видеосъемки, отправленная.  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |Максимальная скорость бита видео во время сеанса видео.  <br/> |
|**VideoFrameLossRate** <br/> |десятичной (9,4)  <br/> | <br/> |Процент от общего числа потерянных видеорамок.  <br/> |
|**VideoFEC** <br/> |bit  <br/> | <br/> |Недоступно.  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |десятичной (9,4)  <br/> ||Процент от общего числа потерянных видеорамок.  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||Процент вызова, который был в разрешении Единого формата взаимозаменяемого обмена (CIF).  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||Процент вызова, который был в разрешении VGA.  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||Процент вызова с разрешением HD720.  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||Процент длительности вызовов без падения кадра.  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||Процент длительности вызова с падением кадров B.  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||Процент длительности вызовов с падением кадров BP.  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||Процент длительности вызовов с падением кадров BPSP.  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||Процент длительности вызовов с падением кадров BPSPI.  <br/> |
|**Входящий** <br/> |bit  <br/> | <br/> |Поток данных на стороне приемник получается.  <br/> |
|**Исходящий** <br/> |bit  <br/> | <br/> |Поток данных на стороне отправитель получает.  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 означает направление потока от вызывающего абонента вызываемому абоненту.  <br/> 0 означает направление потока от вызываемого абонента вызывающему абоненту.  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||Указывает процент времени, когда вызов был в состоянии перегрузки потери.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||Указывает процент вызова, во время которого перегрузка была вызвана задержкой прибытия сетевых пакетов.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||Указывает процент времени, когда вызов был конкурирующим для сетевых ресурсов.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||Минимальный объем оценки пропускной способности, измеряемой во время вызова.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||Максимальный объем оценки пропускной способности, измеряемой во время вызова.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||Стандартное отклонение оценки пропускной способности, измеряемой во время вызова.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||Среднее количество оценки пропускной способности, измеряемой во время вызова.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**LowBandwidthForMultiview** <br/> |float  <br/> ||Процент вызова, в котором конечная точка определила, что сетевое подключение не может поддерживать видео multiview.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||Общая величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||Средняя величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||Максимальная величина односторонней задержки. Относительная односторонняя задержка измеряет задержку между клиентом и сервером  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||Общее число повторов пакетов в одну сторону. "Взрывная" передача — это передача, в которой потоки данных в непредсказуемых очередях, а не в стабильном потоке. С помощью данной метрики измеряется поток данных между клиентом и сервером.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||Общая плотность пакетов в одну сторону. "Взрывная" передача — это передача, в которой потоки данных в непредсказуемых очередях, а не в стабильном потоке. С помощью данной метрики измеряется поток данных между клиентом и сервером.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||Общая длительность пакетов в одну сторону. "Взрывная" передача — это передача, в которой потоки данных в непредсказуемых очередях, а не в стабильном потоке. С помощью данной метрики измеряется поток данных между клиентом и сервером.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||Общее число повторов разрывов в одну сторону. "Взрывная" передача — это передача, в которой потоки данных в непредсказуемых очередях, а не в стабильном потоке; пробелы указывают на задержки между этими всплесками. С помощью данной метрики измеряется поток данных между клиентом и сервером.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||Общая плотность разрывов в одну сторону. "Взрывная" передача — это передача, в которой потоки данных в непредсказуемых очередях, а не в стабильном потоке; пробелы указывают на задержки между этими всплесками. С помощью данной метрики измеряется поток данных между клиентом и сервером.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||Общая длительность разрывов в одну сторону. "Взрывная" передача — это передача, в которой потоки данных в непредсказуемых очередях, а не в стабильном потоке; пробелы указывают на задержки между этими всплесками. С помощью данной метрики измеряется поток данных между клиентом и сервером.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**VideoPacketLossRate** <br/> |десятичной (9,4)  <br/> ||Скорость потери видеопакетов.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||Средний объем выделенной полосы пропускания для видео.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |Foreign  <br/> |Тип видео-кодеков, используемых отправителю. Дополнительные сведения см. в таблице [CodecDescription.](codecdescription.md) <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||Ширина разрешения, используемая отправителю.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||Высота разрешения, используемая отправителю.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**SendFrameRateAverage** <br/> |float  <br/> ||Средняя скорость передачи кадров видео, используемая отправителю.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||Максимальная скорость бита для отправитель.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||Средняя скорость бита для отправляемой.  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||Максимальное количество видеопотоков, используемых отправивщиком.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |Foreign  <br/> |Видео-коды, используемые приемником. Дополнительные сведения см. в таблице [CodecDescription.](codecdescription.md) <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||Ширина разрешения, используемая приемником.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||Высота разрешения, используемая приемником.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**RecvFrameRateAverage** <br/> |float  <br/> ||Средняя частота кадров видео, используемая приемником.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||Максимальная скорость бита для приемник.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||Средняя скорость бита для приемник.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||Максимальное количество видеопотоков для приемник.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||Минимальные потоки видео для приемник.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||Режим видео (например, галерея или один поток) для приемник.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**VideoPostFECPLR** <br/> |float  <br/> ||Скорость потери пакета после исправления ошибки вперед.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**DynamicCapabilityPercent** <br/> |float  <br/> ||Процент времени активности флага динамических возможностей.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**ResolutionMin** <br/> |char(9)  <br/> ||Минимальное разрешение, измеряемая во время вызова.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**LowBitRateCallPercent** <br/> |float  <br/> ||Процент вызова ниже порога низкой скорости бита (70 килобит в секунду).  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**LowFrameRateCallPercent** <br/> |float  <br/> ||Процент вызова ниже порога низкой частоты кадров (7,5 кадров в секунду, входящий).  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**LowResolutionCallPercent** <br/> |float  <br/> ||Процент вызова, который произошел с наименьшим разрешением.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**DurationSeconds** <br/> |float  <br/> ||Длина вызова в секундах.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**IsAggregatedData** <br/> |bit  <br/> ||Указывает, агрегируются ли данные из нескольких вызовов.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
   

