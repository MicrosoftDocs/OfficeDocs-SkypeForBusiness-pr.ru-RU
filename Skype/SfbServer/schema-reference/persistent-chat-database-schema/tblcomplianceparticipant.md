---
title: tblComplianceParticipant
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: Таблица Complianceparticipant содержит текущих участников на канал и на каждом сервере.
ms.openlocfilehash: ba488f377592b48845880acaeed61074bc31ccd2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
Таблица Complianceparticipant содержит текущих участников на канал и на каждом сервере.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar (255), отлично от null  <br/> |Канал универсальный код ресурса (URI).  <br/> |
|идентификатор пользователя  <br/> |int, не null  <br/> |Идентификатор субъекта участника (в соответствии с таблицей tblPrincipal.prinID).  <br/> |
|joinedAt  <br/> |bigint, не может быть null  <br/> |Метка времени события присоединения.  <br/> |
|partedAt  <br/> |bigint  <br/> |NULL, если по-прежнему присоединился к участника. Метка времени канала, отправляемых из события, если не может быть null.  <br/> Эти записи в конечном итоге удаляются, когда все переводчики обработают событие.  <br/> |
|userUri  <br/> |nvarchar(255), не может быть null  <br/> |URI пользователя.  <br/> |
|Который  <br/> |целое  <br/> |Удостоверение сервера (в таблице tblServerIdentity.serverID).  <br/> |
|Код сеанса  <br/> |bigint  <br/> |Сеанс сервера. Это случайное число создается каждый раз при запуске службы чата. Он используется для различать сеансы для идентификации потерянных участников.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<channelUri, идентификатор пользователя, joinedAt\>  <br/> |Первичный ключ.  <br/> |
   

