---
title: Таблица конференций в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: Каждая запись в этой таблице содержит сведения о одной конференции звонках.
ms.openlocfilehash: 3d8382316d17dfc13cd0d9cd2e98e79b3461951c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901368"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Таблица конференций в Скайп для Business Server 2015
 
Каждая запись в этой таблице содержит сведения о одной конференции звонках.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |Время запроса конференции были записаны агентом регистрации Вызовов. Используется только как первичный ключ для уникальной идентификации экземпляра конференции.  <br/> |
|**SessionIdSeq** <br/> |целое  <br/> |Primary  <br/> |Номер идентификатора для идентификации сеанса. Используется в сочетании с **SessionIdTime** для уникальной идентификации экземпляра конференции. * <br/> |
|**ConferenceUriId** <br/> |целое  <br/> |Внешний  <br/> |URI конференции. [Таблица ConferenceUris в Скайп для Business Server 2015](conferenceuris.md) для получения дополнительных сведений см. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> | <br/> |Полезен для повторяющихся конференций; Каждый экземпляр повторяющейся конференции имеет одинаковые **параметр ConferenceUri**, но будет иметь разные **ConfInstance**. <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> | <br/> |Время начала конференции.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> | <br/> |Время начала конференции.  <br/> |
|**PoolId** <br/> |целое  <br/> |Внешний  <br/> |Номер идентификатора для идентификации пула, в котором были записаны конференции. В [таблице пулы](pools.md) для получения дополнительных сведений см. <br/> |
|**OrganizerId** <br/> |Int  <br/> |Внешний  <br/> |Номер идентификатора для идентификации Организатор URI этой конференции. В [таблице пользователей](users.md) для получения дополнительных сведений см. <br/> |
|**Флаг** <br/> |smallint  <br/> || Битовая маска, которая содержит атрибуты конференции. Возможные значения <br/>  0X01 <br/>  Искусственная <br/>  Транзакций <br/> |
|**Обработки** <br/> |бит  <br/> ||Внутреннее поле, используемое службой мониторинга.  <br/> В этом поле было представлено в Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Даты и времени  <br/> ||Для внутреннего использования службой мониторинга.  <br/> В этом поле было представлено в Скайп для Business Server 2015.  <br/> |
   
\*Для большинства сеансов SessionIdSeq будут иметь значение 1. Если запустить два сеанса в точности то же время, SessionIdSeq для одного будет 1, а для другой будет иметь значение 2 и т. д.
  

