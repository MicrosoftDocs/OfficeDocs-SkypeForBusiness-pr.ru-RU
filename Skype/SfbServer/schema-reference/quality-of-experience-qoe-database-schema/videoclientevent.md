---
title: Таблица VideoClientEvent
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
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 'Каждая запись содержит событие клиента для одной конечной точки видеосвязи. Обычно один вызов имеет две записи, одну для вызываемой и одну для вызываемой.'
---

# <a name="videoclientevent-table"></a>Таблица VideoClientEvent
 
Каждая запись содержит событие клиента для одной конечной точки видеосвязи. Обычно один вызов имеет две записи, одну для вызываемой и одну для вызываемой.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Ссылки из [таблицы MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Ссылки из [таблицы MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Ссылки из [таблицы MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0. Данные вызываемой  <br/> 1. Данные вызываемой  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |Процент сеанса событие LowBandwidth было уволено за состояние "Bad". Доступная пропускная способность недостаточна для приемлемого голосового доступа.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |Процент сеанса событие ReceiveSendQuality было уволено за состояние "Bad".  <br/> Качество сети с точки зрения дрожания или потери пакета является серьезным и влияет на качество полученного звука.  <br/> |
   

