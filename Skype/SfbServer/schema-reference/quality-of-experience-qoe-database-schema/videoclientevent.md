---
title: Таблица VideoClientEvent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: Каждая запись содержит события клиента для одной конечной точки в видеозвонок. Как правило один вызов имеет две записи, одно для вызывающего абонента, а другое для вызываемого абонента.
ms.openlocfilehash: 58179630534733985e062bbe0fafa1bbfd8499db
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906828"
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
   

