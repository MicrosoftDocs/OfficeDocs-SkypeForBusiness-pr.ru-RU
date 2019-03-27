---
title: Таблица VideoClientEvent
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Каждая запись содержит события клиента для одной конечной точки в видеозвонок. Как правило один вызов имеет две записи, одно для вызывающего абонента, а другое для вызываемого абонента.
ms.openlocfilehash: 314e4df9313a3d111d71b6eaa06565edcbb765d1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891241"
---
# <a name="videoclientevent-table"></a>Таблица VideoClientEvent
 
Каждая запись содержит события клиента для одной конечной точки в видеозвонок. Как правило один вызов имеет две записи, одно для вызывающего абонента, а другое для вызываемого абонента.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Ссылка из [MediaLine table](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |целое  <br/> |Primary  <br/> |Ссылка из [MediaLine table](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |Ссылка из [MediaLine table](medialine-0.md).  <br/> |
|**FromCaller** <br/> |бит  <br/> |Primary  <br/> |0: данные вызываемой стороны  <br/> 1: данные вызывающего абонента  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> || <br/> |Процент в сеансе события LowBandwidth для состояния «Bad». Пропускная способность недостаточно для обеспечения взаимодействия приемлемой голосовой связи.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> || <br/> |Процент в сеансе событие ReceiveSendQuality возникало для состояния «Bad».  <br/> Качества сети в терминах дрожания или потери пакетов, что оказывает негативное влияние на качество получаемых аудиоданных.  <br/> |
   

