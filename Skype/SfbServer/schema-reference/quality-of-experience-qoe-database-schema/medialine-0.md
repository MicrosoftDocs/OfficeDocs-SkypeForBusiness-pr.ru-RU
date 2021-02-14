---
title: Таблица MediaLine
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: Каждая запись представляет одну строку мультимедиа. (Один звуковой сеанс обычно содержит одну строку мультимедиа. Один сеанс аудио- и видеосвязи обычно содержит одну аудио- и видеомагимию, хотя сеанс может содержать две видеостройки, если используется устройство для аудио- и видеоконференций или используется представление галереи.
ms.openlocfilehash: 99a54fe7a4ee4e91506069873c98d423b9069f06
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802769"
---
# <a name="medialine-table"></a>Таблица MediaLine
 
Каждая запись представляет одну строку мультимедиа. (Один звуковой сеанс обычно содержит одну строку звукового мультимедиа. Один сеанс аудио- и видеосвязи обычно содержит одну аудио- и видеомагимию, хотя сеанс может содержать две видеостройки, если используется устройство для аудио- и видеоконференций или используется представление галереи.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Ссылка из [таблицы Session](session.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Ссылка из [таблицы Session](session.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |0 — это основной звук, 1 — основное видео, 2 — панорамное видео, 3 — общий доступ к приложениям и рабочему столу, 16 — видеосвязь с экрана (VbSS). Эта метка должна быть уникальной в рамках одного сеанса.  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |Этот столбец присутствует, но не используется в Microsoft Lync Server 2013. В столбцах CallerConnectivityICE и CalleeConnectivityICE захватывается информация о подсети, используемой для линии мультимедиа.  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |Сведения о процессе interactive Connectivity Establishment (ICE), описанные в битовых флагах. For details, refer to the  *Quality of Experience Monitoring Server Protocol Specification*  , available for download. <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |То же, что и CallerIceWarningFlags, но на стороне вызываемой стороны. For details, refer to the  *Quality of Experience Monitoring Server Protocol Specification*  , available for download. <br/> |
|**Безопасность** <br/> |tinyint  <br/> | <br/> |Профиль безопасности, который используется. 0 – это NONE, 1 – SRTP, 2 – V1.  <br/> |
|**Transport** <br/> |tinyint  <br/> | <br/> |0 соответствует протоколу UDP, 1 – протоколу TCP.  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |Внешняя  <br/> |IP-адрес вызываемого. Дополнительные сведения см. в таблице [IPAddress.](ipaddress.md) <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | Порт, используемый вызывающим абонентом. <br/> |
|**CallerSubnet** <br/> |int  <br/> | Внешняя <br/> |Подсеть вызываемого. Дополнительные сведения см. в таблице [IPAddress.](ipaddress.md) <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |1 означает, что вызываемая находится внутри корпоративной сети, 0 означает, что вызываемая находится за пределами сети.  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |Внешняя  <br/> |Mac-адрес вызываемого, на который ссылается [таблица MacAddress.](macaddress.md)  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |Внешняя  <br/> |IP-адрес пограничной службы обработки аудио- и видеоданных, используемой вызывающим абонентом. Дополнительные сведения см. в таблице [IPAddress.](ipaddress.md) <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |Порт, используемый вызываемой службой для службы A/V Edge.  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |Внешняя  <br/> |Устройство захвата, используемное вызывающее устройство. Ссылка из таблицы [устройств.](device.md)  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |Внешняя  <br/> |Устройство отрисовки, используемая вызывающее устройство. Ссылка из таблицы [устройств.](device.md)  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |Внешняя  <br/> |Драйвер для устройства захвата вызываемого, на который ссылается [таблица DeviceDriver.](devicedriver.md)  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |Внешняя  <br/> |Драйвер для устройства отрисовки вызываемого, на который ссылается [таблица DeviceDriver.](devicedriver.md)  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |Внешняя  <br/> |Указывает, как вызываемая связь подключена к сети. Значения получены из [таблицы NetworkConnectionDetail.](networkconnectiondetail.md) Типичные значения: 0 для проводного подключения' 1 для подключения Wi-Fi; и 3 для подключения Ethernet.  <br/> |
|**CallerBssid** <br/> |int  <br/> |Внешняя  <br/> |BSSID вызываемого, если используется беспроводная связь. Ссылка из [таблицы MacAddress.](macaddress.md)  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||Ссылка вызываемой. 1 – подключен к виртуальной частной сети, 0 – не подключен к виртуальной частной сети.  <br/> |
|**CallerLinkSpeed** <br/> |decimal(18,0)  <br/> ||Скорость сетевого соединения (в бит/с) для конечной точки вызываемой точки.  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |Внешняя  <br/> |IP-адрес приемник вызовов. Дополнительные сведения см. в таблице [IPAddress.](ipaddress.md) <br/> |
|**CalleePort** <br/> |bit  <br/> ||Порт, используемый приемником вызовов.  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |Внешняя  <br/> |Подсеть вызываемого. Дополнительные сведения см. в таблице [IPAddress.](ipaddress.md) <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |1 означает, что приемник вызовов находится внутри корпоративной сети, 0 означает, что приемник вызовов находится за пределами сети.  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |Внешняя  <br/> |Адрес Mac вызываемой почты. Ссылка из таблицы [MacAddress.](macaddress.md)  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |Внешняя  <br/> |IP-адрес службы A/V Edge, используемой приемником вызовов. Дополнительные сведения см. в таблице [IPAddress.](ipaddress.md) <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |Порт, используемый приемником вызовов в службе A/V Edge.  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |foreign  <br/> |Устройство захвата, используемное приемником вызовов. Ссылка из таблицы [устройств.](device.md)  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |Внешняя  <br/> |Устройство отрисовки, используемая приемником вызовов. Ссылка из таблицы [устройств.](device.md)  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |Внешняя  <br/> |Драйвер для устройства захвата приемник вызовов. Ссылка из [таблицы DeviceDriver.](devicedriver.md)  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar(256)  <br/> |Внешняя  <br/> |Драйвер для устройства отрисовки приемник вызовов. Ссылка из [таблицы DeviceDriver.](devicedriver.md)  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |Внешняя  <br/> |Указывает, как вызываемая подключена к сети. Значения получены из [таблицы NetworkConnectionDetail.](networkconnectiondetail.md) Типичные значения: 0 для проводного подключения' 1 для подключения Wi-Fi; и 3 для подключения Ethernet.  <br/> |
|**CalleeBssid** <br/> |int  <br/> |Внешняя  <br/> |BSSID вызываемого, если используется беспроводная связь. Ссылка из [таблицы MacAddress.](macaddress.md)  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |Ссылка приемник вызовов; 1 — виртуальная частная сеть (VPN), 0 — не VPN.  <br/> |
|**CalleeLinkSpeed** <br/> |decimal(18,0)  <br/> | <br/> |Скорость сетевого соединения (в бит/с) для конечной точки приемник вызовов.  <br/> |
|**ConversationalMOS** <br/> |decimal(3,2)  <br/> | <br/> |Узкополосный MOS аудиосеансов (на основе обоих аудиопотоков).  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||Это фактическая пропускная способность, применяемая к данному потоку на стороне отправки с учетом различных параметров политики (TURN, API, SDP, сервер политик и так далее). Ее не следует путать с эффективной пропускной способностью, потому что эффективная пропускная способность может быть меньше в зависимости от оценки пропускной способности. По сути это в основном максимальная пропускная способность потока отправителя с учетом ограничений, наложенных оценкой пропускной способности.  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||Источник применяемого ограничения пропускной способности. В нем описывается, откуда происходит ограничение пропускной способности ("Сервер политик", "TURN Server", "Модальность" и т. п.). Ссылка из [таблицы AppliedBandwidthSource.](appliedbandwidthsource.md)  <br/> |
|**Caller** <br/> |bit  <br/> | <br/> |Указывает, получены ли показатели от вызываемой стороны; 1 — да, значение null — нет.  <br/> |
|**Вызываемая** <br/> |bit  <br/> | <br/> |Указывает, получены ли метрики от приемник вызовов; 1 — да, значение null — нет.  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||Указывает, является ли отчет частью сеанса или полным сеансом.  <br/> Этот столбец был впервые представлен в Microsoft Lync Server 2013.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Указывает, был ли звонок классифицирован как звонок низкого качества (значение 1) или как хороший вызов (0).  <br/> Этот столбец был впервые представлен в Microsoft Lync Server 2013.  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||Указывает, подключен ли абонент к сети через протокол ICE (Internet Connectivity Establishment).  <br/> Этот столбец был впервые представлен в Microsoft Lync Server 2013.  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||Указывает, подключен ли абонент к сети через протокол ICE (Internet Connectivity Establishment).  <br/> Этот столбец был впервые представлен в Microsoft Lync Server 2013.  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |Внешняя  <br/> |Ip-адрес пользователя, выместившего вызов. В организациях, где используется NAT (перевод сетевых адресов), косвенным IP-адресом является IP-адрес прокси-сервера.  <br/> Этот столбец был впервые представлен в Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |Внешняя  <br/> |Описание устройства для драйвера Wi-Fi, использованного пользователем, который разместил вызов.  <br/> Этот столбец был впервые представлен в Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |Внешняя  <br/> |Номер версии драйвера Wi-Fi, использованного пользователем, который разместил вызов.  <br/> Этот столбец был впервые представлен в Microsoft Lync Server 2013.  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |Внешняя  <br/> |Ip-адрес пользователя, который принял вызов. В организациях, где используется NAT (перевод сетевых адресов), косвенным IP-адресом является IP-адрес прокси-сервера.  <br/> Этот столбец был впервые представлен в Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |Внешняя  <br/> |Описание устройства для драйвера Wi-Fi, использованного пользователем, который принял вызов.  <br/> Этот столбец был впервые представлен в Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |Внешняя  <br/> |Номер версии драйвера Wi-Fi, использованного пользователем, который принял вызов.  <br/> Этот столбец был впервые представлен в Microsoft Lync Server 2013.  <br/> |
   

