---
title: Просмотр конференций
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
description: В представлении конференций хранятся сведения о конференциях. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: b7cf9300ca574773b4ffb08a8c32108155a18786d8fec3ae80ddc77398d41ccc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351309"
---
# <a name="conferences-view"></a>Просмотр конференций
 
В представлении конференций хранятся сведения о конференциях. Это представление было представлено в Microsoft Lync Server 2013.
  
|**Column**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Время запроса сеанса. Используется вместе с параметром SessionIdSeq для уникального определения сеанса. Дополнительные сведения см. в таблице [Диалоги Skype для бизнеса Server 2015](dialogs.md) г. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Идентификационный номер для идентификации сеанса. Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса. Дополнительные сведения см. в таблице [Диалоги Skype для бизнеса Server 2015](dialogs.md) г. <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |URI конференции.  <br/> |
|**ConferenceUriType** <br/> |nvarchar (256)  <br/> |Тип URI конференции. Дополнительные сведения см. в таблице [UriTypes.](uritypes.md) <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |Используется для повторяющихся конференций. Все экземпляры повторяющейся конференции имеют один и тот же ConferenceUri, но разные значения ConfInstance.  <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> |Время начала конференции.  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> |Время окончания конференции.  <br/> |
|**OrganisUri** <br/> |nvarchar (450)  <br/> |URI пользователя, организовавшего конференцию.  <br/> |
|**OrganisType** <br/> |nvarchar (256)  <br/> |Тип URI пользователя, организовавшего конференцию. Дополнительные сведения см. в таблице [UriTypes.](uritypes.md) <br/> |
|**OrganisTenant** <br/> |nvarchar (256)  <br/> |Клиент пользователя, организовавшего конференцию. Дополнительные сведения см. в таблице [Tenants.](tenants.md) <br/> |
|**Pool** <br/> |nvarchar (256)  <br/> |Полное доменное имя пула, в котором размещена конференция.  <br/> |
|**Флаг** <br/> |smallint  <br/> |Битовая маска, содержащая атрибуты конференции. Возможные значения:  <br/> 0X01 — синтетическая транзакция  <br/> |
   

