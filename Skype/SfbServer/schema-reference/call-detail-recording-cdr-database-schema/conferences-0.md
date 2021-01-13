---
title: Представление "Конференции"
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: В представлении конференций хранятся сведения о конференциях. Это представление впервые было введено в Microsoft Lync Server 2013.
ms.openlocfilehash: b31b0baa7a33b28ab9df8d78d2b49e569dfef831
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813259"
---
# <a name="conferences-view"></a>Представление "Конференции"
 
В представлении конференций хранятся сведения о конференциях. Это представление впервые было введено в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Details**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Время запроса сеанса. Используется вместе с параметром SessionIdSeq для уникального определения сеанса. Дополнительные сведения см. в таблице [Dialogs в Skype для бизнеса Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Идентификационный номер для идентификации сеанса. Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса. Дополнительные сведения см. в таблице [Dialogs в Skype для бизнеса Server 2015.](dialogs.md) <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |URI конференции.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |Тип URI конференции. Дополнительные сведения см. в таблице [UriTypes.](uritypes.md) <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Используется для повторяющихся конференций. Все экземпляры повторяющейся конференции имеют один и тот же ConferenceUri, но разные значения ConfInstance.  <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> |Время начала конференции.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> |Время окончания конференции.  <br/> |
|**OrganizerUri** <br/> |nvarchar(450)  <br/> |URI пользователя, организовавшего конференцию.  <br/> |
|**OrganizerType** <br/> |nvarchar(256)  <br/> |Тип URI пользователя, организовавшего конференцию. Дополнительные сведения см. в таблице [UriTypes.](uritypes.md) <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |Клиент пользователя, организовавшего конференцию. Дополнительные [сведения см. в](tenants.md) таблице Tenants. <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Полное доменное имя пула, в котором размещена конференция.  <br/> |
|**Flag** <br/> |smallint  <br/> |Битовая маска, содержащая атрибуты конференции. Возможные значения:  <br/> 0X01 — искусственная транзакция  <br/> |
   

