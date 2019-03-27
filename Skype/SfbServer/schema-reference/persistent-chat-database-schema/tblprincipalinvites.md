---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites содержит приглашения для всех подготовленных пользователей для всех узлов с автоматическим приглашением на.
ms.openlocfilehash: fbf61265f4970b57ffa95a52c8bafa395fb3a331
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876692"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites содержит приглашения для всех подготовленных пользователей для всех узлов с автоматическим приглашением на.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**.|
|:-----|:-----|:-----|
|prinID  <br/> |int, не null  <br/> |Идентификатор субъекта.  <br/> |
|invID  <br/> |int, не null  <br/> |Уникальный порядковый номер (на код участника) созданный для таблицы tblLastInviteId.  <br/> |
|nodeID  <br/> |int, не null  <br/> |КОД узла (только комната чата).  <br/> |
|createdOn  <br/> |DateTime, не может быть null  <br/> |Время создания.  <br/> |
   
**Ключи**

|**Столбец**|**Описание**.|
|:-----|:-----|
|\<prinID nodeID\>  <br/> |Первичный ключ.  <br/> |
|prinID  <br/> |Внешний ключ с подстановкой в таблице tblPrincipal.prinID.  <br/> |
|nodeID  <br/> |Внешний ключ с подстановкой в таблице tblNode.nodeID.  <br/> |
   

