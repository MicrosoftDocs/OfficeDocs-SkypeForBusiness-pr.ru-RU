---
title: Таблица MediaLine
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: 'Каждая запись представляет одну строку мультимедиа. (Один сеанс аудио обычно содержит одну строку мультимедиа. Один сеанс аудио- и видеосвязи (A/V) обычно содержит одну аудио-медиа-линию и одну линию видеосвязи, хотя сеанс может содержать две линии видеосвязи, если используется устройство-конференция или используется Представление галереи.'
---

# <a name="medialine-table"></a>Таблица MediaLine
 
Каждая запись представляет одну строку мультимедиа. (Один сеанс аудио обычно содержит одну строку мультимедиа. Один сеанс аудио- и видеосвязи (A/V) обычно содержит одну аудио-медиа-линию и одну линию видеосвязи, хотя сеанс может содержать две линии видеосвязи, если используется устройство-конференция или используется Представление галереи.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Ссылки из [таблицы Сеанс](session.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Ссылки из [таблицы Сеанс](session.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |0 — основной звук, 1 — основное видео, а 2 — панорамное видео, 3 — совместное использование приложений и настольных компьютеров, 16 — видеообъемка экрана (VbSS). Эта метка должна быть уникальной в течение одного сеанса.  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |Этот столбец присутствует, но не используется в Microsoft Lync Server 2013. Сведения о подключении, используемом для линии мультимедиа, запечатлены в столбцах CallerConnectivityICE и CalleeConnectivityICE.  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |Сведения о процессе создания интерактивных подключений (ICE), описанные в флагах битов. Подробные сведения можно найти  *в спецификации*  протокола протокола мониторинга качества работы сервера, доступной для скачивания. <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |То же самое, что CallerIceWarningFlags, но на стороне вызываемой стороны. Подробные сведения можно найти  *в спецификации*  протокола протокола мониторинга качества работы сервера, доступной для скачивания. <br/> |
|**Безопасность** <br/> |tinyint  <br/> | <br/> |Используется профиль безопасности. 0 – это NONE, 1 – SRTP, 2 – V1.  <br/> |
|**Transport** <br/> |tinyint  <br/> | <br/> |0 соответствует протоколу UDP, 1 – протоколу TCP.  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |Foreign  <br/> |IP-адрес вызываемого. Дополнительные [сведения см. в таблице IPAddress](ipaddress.md) . <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | Порт, используемый вызывающим абонентом. <br/> |
|**CallerSubnet** <br/> |int  <br/> | Foreign <br/> |Подсеть вызываемого. Дополнительные [сведения см. в таблице IPAddress](ipaddress.md) . <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |1 означает, что вызываемая внутри корпоративной сети, 0 означает, что вызываемая находится вне сети.  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |Foreign  <br/> |Mac-адрес вызываемого, ссылаясь на [таблицу MacAddress](macaddress.md).  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |Foreign  <br/> |IP-адрес пограничной службы обработки аудио- и видеоданных, используемой вызывающим абонентом. Дополнительные [сведения см. в таблице IPAddress](ipaddress.md) . <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |Порт, используемый в службе A/V Edge вызываемой стороны.  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |Foreign  <br/> |Захват устройства, используемой вызываемой. Ссылки из [таблицы Device](device.md).  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |Foreign  <br/> |Отрисовка устройства, используемой вызываемой. Ссылки из [таблицы Device](device.md).  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |Foreign  <br/> |Драйвер устройства захвата вызываемого, ссылаясь на [таблицу DeviceDriver](devicedriver.md).  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |Foreign  <br/> |Драйвер для устройства визуализации вызываемого, ссылаясь на [таблицу DeviceDriver](devicedriver.md).  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |Foreign  <br/> |Указывает, как вызываемая связь с сетью. Значения получены из [таблицы NetworkConnectionDetail](networkconnectiondetail.md). Типичные значения: 0 для проводного подключения 1 для подключения WiFi; и 3 для подключения Ethernet.  <br/> |
|**CallerBssid** <br/> |int  <br/> |Foreign  <br/> |BSSID вызываемого оператора, если используется беспроводная связь. Ссылки из [таблицы MacAddress](macaddress.md).  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||Ссылка вызываемой. 1 – подключен к виртуальной частной сети, 0 – не подключен к виртуальной частной сети.  <br/> |
|**CallerLinkSpeed** <br/> |десятичной (18,0)  <br/> ||Скорость сетевой ссылки в bps для конечной точки вызываемой точки.  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |Foreign  <br/> |IP-адрес приемного вызова. Дополнительные [сведения см. в таблице IPAddress](ipaddress.md) . <br/> |
|**CalleePort** <br/> |bit  <br/> ||Порт, используемый приемником вызовов.  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |Foreign  <br/> |Подсеть вызываемого. Дополнительные [сведения см. в таблице IPAddress](ipaddress.md) . <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |1 означает, что приемник вызовов находится внутри корпоративной сети, 0 означает, что приемник вызова находится за пределами сети.  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |Foreign  <br/> |Callee Mac address. Ссылки из [таблицы MacAddress](macaddress.md).  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |Foreign  <br/> |IP-адрес службы A/V Edge, используемой приемником вызовов. Дополнительные [сведения см. в таблице IPAddress](ipaddress.md) . <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |Порт, используемый в краевой службе A/V приемником вызовов.  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |иностранные  <br/> |Захват устройства, используемой приемником вызовов. Ссылки из [таблицы Device](device.md).  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |Foreign  <br/> |Отрисовка устройства, используемой приемником вызовов. Ссылки из [таблицы Device](device.md).  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |Foreign  <br/> |Драйвер для устройства захвата приемщика вызовов. Ссылки из [таблицы DeviceDriver](devicedriver.md).  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar (256)  <br/> |Foreign  <br/> |Драйвер для устройства визуализации приемщика вызовов. Ссылки из [таблицы DeviceDriver](devicedriver.md).  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |Foreign  <br/> |Указывает, как вызываемая подключена к сети. Значения получены из [таблицы NetworkConnectionDetail](networkconnectiondetail.md). Типичные значения: 0 для проводного подключения 1 для подключения WiFi; и 3 для подключения Ethernet.  <br/> |
|**CalleeBssid** <br/> |int  <br/> |Foreign  <br/> |BSSID вызываемого, если используется беспроводная связь. Ссылки из [таблицы MacAddress](macaddress.md).  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |Ссылка приемного вызова; 1 — это виртуальная частная сеть (VPN), 0 — не VPN.  <br/> |
|**CalleeLinkSpeed** <br/> |десятичной (18,0)  <br/> | <br/> |Скорость сетевой ссылки в bps для конечной точки приемного вызова.  <br/> |
|**ConversationalMOS** <br/> |десятичной (3,2)  <br/> | <br/> |Узкополосный MOS аудиосеансов (на основе обоих аудиопотоков).  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||Это фактическая пропускная способность, применяемая к данному боковому потоку отправки с учетом различных параметров политики (TURN, API, SDP, Policy Server и так далее). Ее не следует путать с эффективной пропускной способностью, потому что эффективная пропускная способность может быть меньше в зависимости от оценки пропускной способности. По сути это в основном максимальная пропускная способность потока отправителя с учетом ограничений, наложенных оценкой пропускной способности.  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||Источник применяемого ограничения пропускной способности. В нем описывается, откуда приходит ограничение пропускной способности ("Сервер политики", "TURN Server", "Modality" и т. п.). Ссылки из [таблицы AppliedBandwidthSource](appliedbandwidthsource.md).  <br/> |
|**Caller** <br/> |bit  <br/> | <br/> |Указывает, получены ли метрики от вызываемой стороны; 1 — да, значение null — нет.  <br/> |
|**Callee** <br/> |bit  <br/> | <br/> |Указывает, были ли получены метрики из приемного звонка; 1 — да, значение null — нет.  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||Указывает, является ли отчет частью сеанса или полным сеансом.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Указывает, был ли вызов классифицирован как плохой вызов (значение 1) или как хороший вызов (0).  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||Указывает, подключен ли абонент к сети через протокол ICE (Internet Connectivity Establishment).  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||Указывает, подключен ли абонент к сети через протокол ICE (Internet Connectivity Establishment).  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |Foreign  <br/> |Рефлекторный IP-адрес пользователя, который разместил вызов. В организациях, которые используют NAT (перевод сетевых адресов), рефлекторный IP-адрес является IP-адресом прокси-сервера.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |Foreign  <br/> |Описание устройства для драйвера WiFi, занятого пользователем, который разместил вызов.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |Foreign  <br/> |Номер версии для драйвера WiFi, нанятого пользователем, который разместил вызов.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |Foreign  <br/> |Рефлекторный IP-адрес пользователя, который получил вызов. В организациях, которые используют NAT (перевод сетевых адресов), рефлекторный IP-адрес является IP-адресом прокси-сервера.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |Foreign  <br/> |Описание устройства для драйвера WiFi, занятого пользователем, который получил вызов.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |Foreign  <br/> |Номер версии для драйвера WiFi, нанятого пользователем, который получил вызов.  <br/> Этот столбец был представлен в Microsoft Lync Server 2013.  <br/> |
   

