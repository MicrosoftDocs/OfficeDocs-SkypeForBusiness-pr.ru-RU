---
title: Таблица VideoClientEvent
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Каждая запись содержит событие клиента для одной конечной точки видеосвязи. Обычно один вызов имеет две записи, одну для вызываемой и одну для вызываемой.
ms.openlocfilehash: 8c2f9142bb187fec8ceb55c34ea28c7f62b06d23
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858936"
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
   

