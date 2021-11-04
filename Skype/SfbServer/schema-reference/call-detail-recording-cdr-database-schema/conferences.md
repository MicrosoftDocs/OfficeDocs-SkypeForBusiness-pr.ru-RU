---
title: Таблица конференций Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: Каждая запись в этой таблице содержит сведения об одной конференции.
ms.openlocfilehash: 22d394ca447852a32d8028770d7ceefea7adbcf1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763417"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Таблица конференций Skype для бизнеса Server 2015 г.
 
Каждая запись в этой таблице содержит сведения об одной конференции.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |Время, когда запрос конференции был захвачен агентом CDR. Используется только в качестве основного ключа для уникальной идентификации экземпляра конференции.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |Идентификатор сеанса. Используется совместно с **SessionIdTime** для уникальной идентификации экземпляра конференции. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Foreign  <br/> |URI конференции. Дополнительные сведения см. в таблице [ConferenceUris Skype для бизнеса Server 2015](conferenceuris.md) г. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> | <br/> |Полезно для повторяющихся конференций; каждый экземпляр повторяющейся конференции имеет один и тот же **ConferenceUri,** но будет иметь другой **ConfInstance**. <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> | <br/> |Время начала конференции.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> | <br/> |Время начала конференции.  <br/> |
|**PoolId** <br/> |int  <br/> |Foreign  <br/> |ID-номер для определения пула, в котором была захвачена конференция. Дополнительные [сведения см. в](pools.md) таблице Пулы. <br/> |
|**OrganisId** <br/> |Целое  <br/> |Foreign  <br/> |ID-номер для идентификации организатора URI этой конференции. Дополнительные [сведения см.](users.md) в таблице Пользователи. <br/> |
|**Флаг** <br/> |smallint  <br/> || Немного маски, которая содержит атрибуты конференции. Возможные значения: <br/>  0X01 <br/>  Синтетический <br/>  Транзакция <br/> |
|**Обработано** <br/> |bit  <br/> ||Внутреннее поле, используемая службой мониторинга.  <br/> Это поле было внедрено в Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Для внутреннего использования службой мониторинга.  <br/> Это поле было введено Skype для бизнеса Server 2015 г.  <br/> |
   
\* Для большинства сеансов значение SessionIdSeq будет 1. Если два сеанса начинаются одновременно, для одного сеанса sessionIdSeq будет 1, а для другого будет 2 и так далее.
  

