---
title: Представление конференций
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: Представление конференций хранит информацию о конференциях. В этом представлении была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: 42bdbed9cceb8d50e2de8ddbe29ba406e4a0a2f5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213272"
---
# <a name="conferences-view"></a>Представление конференций
 
Представление конференций хранит информацию о конференциях. В этом представлении была введена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Время запроса сеанса. Используется совместно с SessionIdSeq для уникальной идентификации сеанса. В разделе [диалоговых окон в таблице в Скайп для Business Server 2015](dialogs.md) для получения дополнительных сведений. <br/> |
|**SessionIdSeq** <br/> |целое  <br/> |Номер идентификатора для идентификации сеанса. Используется в сочетании с SessionIdTime для уникальной идентификации сеанса. В разделе [диалоговых окон в таблице в Скайп для Business Server 2015](dialogs.md) для получения дополнительных сведений. <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI конференции.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Тип URI конференции. В [таблице UriTypes](uritypes.md) для получения дополнительных сведений см. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Используется для повторяющихся конференций. Каждый экземпляр повторяющейся конференции имеет одинаковые параметр ConferenceUri, но разные ConfInstance.  <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> |Время начала конференции.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> |Время окончания конференции.  <br/> |
|**OrganizerUri** <br/> |nvarchar(450)  <br/> |URI пользователя, организовавшего конференцию.  <br/> |
|**OrganizerType** <br/> |nvarchar(256)  <br/> |Тип URI пользователя, организовавшего конференцию. В [таблице UriTypes](uritypes.md) для получения дополнительных сведений см. <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |Клиент пользователя, организовавшего конференцию. В [таблице клиентов](tenants.md) для получения дополнительных сведений см. <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Полное доменное имя пула, в котором размещена конференция.  <br/> |
|**Флаг** <br/> |smallint  <br/> |Битовая маска, которая содержит атрибуты конференции. Возможные значения  <br/> 0X01 — искусственная транзакция  <br/> |
   

