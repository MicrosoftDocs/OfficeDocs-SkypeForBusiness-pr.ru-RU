---
title: Таблица VideoClientEvent
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
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 'Каждая запись содержит событие клиента для одной конечной точки в видеосвязи. Обычно один вызов имеет две записи: одну для вызываемой стороны и одну для вызываемой.'
ms.openlocfilehash: bb4a9feca562bed7bdb0080e7f9181003952f5d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821399"
---
# <a name="videoclientevent-table"></a>Таблица VideoClientEvent
 
Каждая запись содержит событие клиента для одной конечной точки в видеосвязи. Обычно один вызов имеет две записи: одну для вызываемой стороны и одну для вызываемой.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Ссылка из [таблицы MediaLine.](medialine-0.md)  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Ссылка из [таблицы MediaLine.](medialine-0.md)  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Ссылка из [таблицы MediaLine.](medialine-0.md)  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |0: данные вызываемой  <br/> 1: данные вызываемой  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |Процент сеанса, когда событие LowBandwidth было и выпущено для состояния "Bad". Доступной пропускной способности недостаточно для приемлемого звучания.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |Процент сеанса, когда событие ReceiveSendQuality было и выпущено для состояния "Bad".  <br/> Качество сети в условиях дрожания или потери пакетов является серьезным и влияет на качество звука, который получается.  <br/> |
   

