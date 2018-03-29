---
title: Таблица AudioClientEvent
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: Каждая запись содержит события клиента для одной конечной точки в голосовой звонок. Как правило один вызов имеет две записи, одно для вызывающего абонента, а другое для вызываемого абонента.
ms.openlocfilehash: dd910c9abf5cbd8d95a7448f72b49641148a2c64
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="audioclientevent-table"></a>Таблица AudioClientEvent
 
Каждая запись содержит события клиента для одной конечной точки в голосовой звонок. Как правило один вызов имеет две записи, одно для вызывающего абонента, а другое для вызываемого абонента.
  
|**Столбец**|**Тип данных**|**Ключ или индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Ссылка из [MediaLine table](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |целое  <br/> |Primary  <br/> |Ссылка из [MediaLine table](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Ссылка из [MediaLine table](medialine-0.md).  <br/> |
|**FromCaller** <br/> |бит  <br/> |Primary  <br/> |0: данные вызываемой стороны  <br/> 1: данные вызывающего абонента  <br/> |
|**NetworkSendQualityEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Процент в сеансе событие NetworkSendQuality для состояния «Bad».  <br/> Качества сети в терминах дрожания или потери пакетов, влияющее на качество отправляемых аудиоданных.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Процент в сеансе событие ReceiveSendQuality возникало для состояния «Bad».  <br/> Качества сети в терминах дрожания или потери пакетов, влияющее на качество получаемых аудиоданных.  <br/> |
|**NetworkDelayEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Процент в сеансе событий задержка для состояния «Bad». Что оказывает задержек в сети, влияющее на компьютерах, устраняя интерактивного взаимодействия  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Процент в сеансе события LowBandwidth для состояния «Bad». Пропускная способность недостаточно для обеспечения взаимодействия приемлемой голосовой связи.  <br/> |
|**CPUInsufficientEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Процент в сеансе недостаточно события ЦП для состояния «Bad». Существует недостаточно ЦП для обработки текущего модальностей и приложения. В результате искажений с звукового канала.  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Процент в сеансе события DeviceHalfDuplexAEC для состояния «Bad». Во избежание эхо система имеет введите полудуплекс.  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Процент в сеансе события DeviceRenderNotFunctioning для состояния «Bad». Устройства обработки, в настоящее время используется для сеанса не работает правильно. Это может привести к односторонней проблем со звуком.  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Процент в сеансе события DeviceCaptureNotFunctioning для состояния «Bad». Устройства захвата, в настоящее время используется для сеанса не работает правильно. Это может привести к односторонней проблем со звуком.  <br/> |
|**DeviceGlitchesEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Процент в сеансе события DeviceGlitches для состояния «Bad». Существует серьезной ошибки визуализации звук, который искажений. Эти ошибки могут быть вызвана драйверов, ураган звонки (DPC) отложенных процедур (драйверы) и высокая загрузка ЦП.  <br/> |
|**DeviceLowSNREventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Процент в сеансе события DeviceLowSNR для состояния «Bad». Качество записи очень низкий, либо очень помехами или слишком далеко общения пользователя из микрофон. Это приведет к искажений.  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Процент в сеансе события DeviceLowSpeechLevel для состояния «Bad». Уровень речи пользователя слишком мало, и система не может увеличить его любой дальнейшей. Это может вызвать либо искажений или считается одностороннего режима передачи звука.  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Процент в сеансе событие DeviceClipping для состояния «Bad».  <br/> Когда речь рядом с конечным клипов микрофона, далеко конечных слышит искажений из-за отсечения. Важно избежать Отсечка микрофона рядом с end.  <br/> |
|**DeviceEchoEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Процент в сеансе события DeviceEchoEvent для состояния «Bad». Устройство или программа установки вызывает эхо за пределы возможности системы компенсации.  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Процент в сеансе события DeviceNearEndToEchoRatio для состояния «Bad». Речи пользователя слишком мало по сравнению с эхо, записанных которого влияет на взаимодействие с пользователями из-за ограничения, простота является прерывать работу пользователя. Уменьшить громкость динамика, переместить микрофона ближе к talker.  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |целое  <br/> ||Сколько раз во время сеанса событие DeviceMultipleEndpoints для состояния «Bad». Несколько звуковых конечных точек в том же сеансе обнаруженных и система компенсация благодаря уменьшению числа render тома.  <br/> |
|**DeviceHowlingEventCount** <br/> |целое  <br/> | <br/> |Сколько раз во время сеанса событие DeviceHowlingEvent для состояния «Bad». Обнаружен цикл обратной связи (, возникающие при нескольких конечных точек, совместное использование аудио пути).  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |Decimal(5,2)  <br/> ||Процент от сеанса DeviceRenderZeroVolume событие, для которого в «Bad "состояние. Устройства обработки было задано значение ноль тома.  <br/> Этот столбец появился в Microsoft Lync Server 2013.  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |Decimal(5,2)  <br/> ||Процент от сеанса DeviceRenderMute событие, для которого в «Bad "состояние. Устройства обработки был отключен.  <br/> Этот столбец появился в Microsoft Lync Server 2013.  <br/> |
   

