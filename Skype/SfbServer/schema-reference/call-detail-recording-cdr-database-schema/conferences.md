---
title: Таблица Conferences в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: Каждая запись в этой таблице содержит сведения о вызовах одной конференции.
ms.openlocfilehash: 85da16807d6f314fb4f9239601c77a7aed2842ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813219"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Таблица Conferences в Skype для бизнеса Server 2015
 
Каждая запись в этой таблице содержит сведения о вызовах одной конференции.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |Время, когда запрос на конференцию был захвачен агентом CDR. Используется только в качестве первичного ключа для уникальной идентификации экземпляра конференции.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |Идентификатор сеанса. Используется в сочетании с **SessionIdTime** для уникальной идентификации экземпляра конференции. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Внешняя  <br/> |URI конференции. Дополнительные сведения см. в таблице [ConferenceUris в Skype для бизнеса Server 2015.](conferenceuris.md) <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> | <br/> |Полезно для повторяющихся конференций; каждый экземпляр повторяющейся конференции имеет один и тот же **ConferenceUri,** но будет иметь разные **экземпляры ConfInstance.** <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> | <br/> |Время начала конференции.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> | <br/> |Время начала конференции.  <br/> |
|**PoolId** <br/> |int  <br/> |Внешняя  <br/> |Идентификация пула, в котором была захвачена конференция. Дополнительные [сведения см. в](pools.md) таблице "Пулы". <br/> |
|**OrganizerId** <br/> |Целое  <br/> |Внешняя  <br/> |Идентификация URI организатора данной конференции. Дополнительные [сведения см.](users.md) в таблице "Пользователи". <br/> |
|**Flag** <br/> |smallint  <br/> || Битовая маска, содержаная атрибуты конференции. Возможные значения: <br/>  0X01 <br/>  Искусственная <br/>  Транзакция <br/> |
|**Обработано** <br/> |bit  <br/> ||Внутреннее поле, используемное службой мониторинга.  <br/> Это поле было впервые введено в Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Для внутреннего использования службой мониторинга.  <br/> Это поле было впервые введено в Skype для бизнеса Server 2015.  <br/> |
   
\* Для большинства сеансов значение SessionIdSeq будет иметь значение 1. Если два сеанса начинаются в одно и то же время, sessionIdSeq для одного будет иметь 1, а для другого будет 2 и так далее.
  

