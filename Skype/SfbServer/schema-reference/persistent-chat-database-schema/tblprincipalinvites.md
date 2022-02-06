---
title: tblPrincipalInvites
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites содержит приглашения для всех подготовленных пользователей для всех узлов с включенным автоматическим приглашением.
---

# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites содержит приглашения для всех подготовленных пользователей для всех узлов с включенным автоматическим приглашением.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |Код участника  <br/> |
|invID  <br/> |int, не null  <br/> |Уникальный порядковый номер (на код участника), созданный для таблицы tblLastInviteId.  <br/> |
|nodeID  <br/> |int, не null  <br/> |Код узла (только комната чата).  <br/> |
|createdOn  <br/> |datetime, не null  <br/> |Время создания.  <br/> |
   
**Keys**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |Первичный ключ.  <br/> |
|prinID  <br/> |Внешний ключ с подстановкой в таблице tblPrincipal.prinID.  <br/> |
|nodeID  <br/> |Внешний ключ с подстановкой в таблице tblNode.nodeID.  <br/> |
   

