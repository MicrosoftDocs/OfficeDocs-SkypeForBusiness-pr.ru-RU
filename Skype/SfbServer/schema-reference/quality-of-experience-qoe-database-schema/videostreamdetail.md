---
title: Представление VideoStreamDetail
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: Представление VideoStreamDetail хранит сведения о каждом видеопотоке в базе данных. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: 0e34791bd3081497c4c8501dbd01d2e9d39503f1
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393541"
---
# <a name="videostreamdetail-view"></a>Представление VideoStreamDetail
 
Представление VideoStreamDetail хранит сведения о каждом видеопотоке в базе данных. Это представление было представлено в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Описание**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |Ссылки из [таблицы MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Ссылки из [таблицы MediaLine](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Ссылки из [таблицы MediaLine](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |Уникальный идентификатор в линии мультимедиа.  <br/> |
|StartTime  <br/> |datetime  <br/> |Время начала сеанса.  <br/> |
|EndTime  <br/> |datetime  <br/> |Время окончания сеанса.  <br/> |
|CallPriority  <br/> |int  <br/> |Приоритет вызова.  <br/> |
|CallerPool  <br/> |nvarchar (256)  <br/> |Полное доменное имя пула вызывающего абонента.  <br/> |
|CalleePool  <br/> |nvarchar (256)  <br/> |Полное доменное имя пула вызываемого абонента.  <br/> |
|Вызывающая сторона  <br/> |nvarchar (450)  <br/> |URI вызываемой.  <br/> |
|Callee  <br/> |nvarchar (450)  <br/> |URI вызываемой.  <br/> |
|CallerUserAgent  <br/> |nvarchar (256)  <br/> |Строка агента пользователя вызываемой.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Тип агента пользователя вызываемого пользователя. Сведения см. [в таблице UserAgent](useragent.md) . <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Категория агента пользователя вызываемого пользователя. Сведения см. [в таблице UserAgentDef (QoE](useragentdef-qoe.md) ). <br/> |
|CalleeUserAgent  <br/> |nvarchar (256)  <br/> |Строка агента пользователя callee.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Тип агента пользователя вызываемого пользователя. Сведения см. [в таблице UserAgent](useragent.md) . <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Категория агента пользователя вызываемого пользователя. Сведения см. [в таблице UserAgentDef (QoE](useragentdef-qoe.md) ). <br/> |
|CallerEndpoint  <br/> |nvarchar (256)  <br/> |Имя конечной точки вызываемой точки.  <br/> |
|CalleeEndpoint  <br/> |nvarchar (256)  <br/> |Имя конечной точки вызываемой точки.  <br/> |
|CallerOS  <br/> |nvarchar (128)  <br/> |Операционная система (ОС) конечной точки вызываемого.  <br/> |
|CalleeOS  <br/> |nvarchar (128)  <br/> |Операционная система (ОС) конечной точки вызываемого.  <br/> |
|CallerCPUName  <br/> |nvarchar (128)  <br/> |Имя ЦП конечной точки вызываемого.  <br/> |
|CalleeCPUName  <br/> |nvarchar (128)  <br/> |Имя ЦП конечной точки вызываемого.  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Количество ядер ЦП конечной точки вызываемого.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Количество ядер ЦП конечной точки вызываемого.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Скорость процессора процессора конечной точки вызываемого.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Скорость процессора ЦП конечной точки вызываемого.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Указывает, запущена ли система вызываемого в виртуализированной среде. Дополнительные сведения [см. в таблице Endpoint](endpoint.md) . <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Указывает, работает ли система вызываемого в виртуализированной среде. Дополнительные сведения [см. в таблице Endpoint](endpoint.md) . <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Информация о пути к носителю, например прямой или с ретрансляцией. Дополнительные [сведения см. в таблице MediaLine](medialine-0.md) . <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Сведения о технологии ICE (Interactive Connectivity Establishment), описанные в битовых флагах, для вызывающего абонента. Дополнительные сведения см. в спецификации протокола сервера мониторинга качества взаимодействия.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Сведения о технологии ICE (Interactive Connectivity Establishment), описанные в битовых флагах, для вызываемого абонента. Дополнительные сведения см. в спецификации протокола сервера мониторинга качества взаимодействия.  <br/> |
|Transport  <br/> |int  <br/> |Вид транспорта: 0 — UDP, 1 — TCP.  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |IP-адрес вызывающего абонента. Это может быть IPv4-адрес или IPv6-адрес.  <br/> |
|CallerPort  <br/> |int  <br/> |Порт, используемый вызывающим абонентом.  <br/> |
|CallerInside  <br/> |bit  <br/> |Указывает, находится ли звонящий абонент внутри сети организации: 1 означает, что абонент внутри корпоративной сети, 0 — абонент вне сети.  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |IP-адрес вызываемого абонента. Это может быть IPv4-адрес или IPv6-адрес.  <br/> |
|CalleePort  <br/> |int  <br/> |Порт, используемый вызываемым абонентом.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Указывает, находится ли вызываемый абонент внутри сети организации: 1 означает, что абонент внутри корпоративной сети, 0 — абонент вне сети.  <br/> |
|CallerUserSite  <br/> |nvarchar (128)  <br/> |Имя сайта вызываемого.  <br/> |
|CallerRegion  <br/> |nvarchar (128)  <br/> |Имя страны или региона сайта вызываемого.  <br/> |
|CalleeUserSite  <br/> |nvarchar (128)  <br/> |Имя сайта вызываемого.  <br/> |
|CalleeRegion  <br/> |nvarchar (128)  <br/> |Имя страны или региона сайта вызываемого.  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |IP-адрес пограничной службы обработки аудио- и видеоданных, используемой вызывающим абонентом. Дополнительные [сведения см. в таблице IPAddress](ipaddress.md) . <br/> |
|CallerRelayPort  <br/> |int  <br/> |Порт пограничной службы обмена аудио-видео данными, используемой звонящим абонентом.  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |IP-адрес пограничной службы обработки аудио- и видеоданных, используемой вызываемым абонентом. Дополнительные [сведения см. в таблице IPAddress](ipaddress.md) . <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Порт пограничной службы обмена аудио-видео данными, используемой вызываемым абонентом.  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |Имя устройства захвата вызываемой.  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |Имя устройства визуализации вызываемой.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |Имя драйвера устройства захвата вызываемой.  <br/> |
|CallerRenderDevDriver  <br/> |varchar (256)  <br/> |Имя драйвера устройства визуализации вызываемой.  <br/> |
|CalleeCaptureDev  <br/> |varchar (256)  <br/> |Имя устройства захвата вызываемой.  <br/> |
|CalleeRenderDev  <br/> |varchar (256)  <br/> |Имя устройства визуализации вызываемой.  <br/> |
|CalleCaptureDevDriver  <br/> |varchar (256)  <br/> |Имя драйвера устройства захвата вызываемой.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |Имя драйвера отображения устройства callee.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Тип сетевого подключения вызываемого: 0 — проводное, 1 — беспроводное.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Указывает, подключен ли звонящий абонент через виртуальную частную сеть: 1 — виртуальная частная сеть (VPN), 0 — не VPN.  <br/> |
|CallerLinkSpeed  <br/> |десятичной (18,)  <br/> |Скорость сетевого канала для звонящего абонента в бит/с.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Тип сетевого подключения вызываемого: 0 — проводное, 1 — беспроводное.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Указывает, подключен ли вызываемый абонент через виртуальную частную сеть: 1 — виртуальная частная сеть (VPN), 0 — не VPN.  <br/> |
|CalleeLinkSpeed  <br/> |десятичной (18,0)  <br/> |Скорость сетевой ссылки для конечной точки вызываемой (в bps).  <br/> |
|ConversationalMOS  <br/> |десятичной (3,2)  <br/> |Узкополосный MOS аудиосеансов (на основе обоих аудиопотоков).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Фактическая пропускная способность, применяемая к данному потоку отправителя с различными параметрами политики (TURN, API, SDP, сервер политик и т. д.). Ее не следует путать с эффективной пропускной способностью, потому что эффективная пропускная способность может быть меньше в зависимости от оценки пропускной способности. По сути это в основном максимальная пропускная способность потока отправителя с учетом ограничений, наложенных оценкой пропускной способности.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Средний уровень дрожания в сети на основе статистики протокола RTCP.  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Максимальное "дрожание" сети во время вызова.  <br/> |
|RoundTrip  <br/> |int  <br/> |Время приема-передачи на основе статистики RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Максимальное время кругового пути для аудиопотока.  <br/> |
|PacketLossRate  <br/> |десятичных (5,4)  <br/> |Средний коэффициент потерь пакетов в течение вызова.  <br/> |
|PacketLossRateMax  <br/> |десятичных (5,4)  <br/> |Максимальная наблюдаемая частота потери пакетов во время вызова.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Количество пакетов для видеопотока (RTP).  <br/> |
|BandwidthEst  <br/> |int  <br/> |Оценка пропускной способности для аудиопотока.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Звуковой кодек, используемый для вызова, ссылается на таблицу [PayloadDescription](payloaddescription.md).  <br/> |
|VideoResolution  <br/> |char(9)  <br/> |Разрешение видео в пикселах (ширина умножается на высоту в пикселах). Указывается как строка.  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |Средняя скорость передачи видеопотока.  <br/> |
|InboundVideoFrameRateAvg  <br/> |десятичной (9,4)  <br/> |Частота кадров полученного видео.  <br/> |
|OutboundVideoFrameRateAvg  <br/> |десятичной (9,4)  <br/> |Частота кадров отправленного видео.  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |Максимальная скорость передачи видео в ходе видеосеанса.  <br/> |
|VideoPacketLossRate  <br/> |десятичной (9,4)  <br/> |Скорость потери видеопакетов.  <br/> |
|VideoFrameLossRate  <br/> |десятичной (9.4)  <br/> |Процент от общего числа потерянных видеокадров.  <br/> |
|VideoFEC  <br/> |bit  <br/> |Не используется.  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |Средний объем выделенной полосы пропускания для видео.  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |десятичной (9.4)  <br/> |Процент от общего числа потерянных видеокадров.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Направление потока для Р-утверждаемой идентификационной информации. 1 означает направление потока от звонящего абонента к вызываемому абоненту; 0 направление от вызываемого к звонящему абоненту.  <br/> |
   

