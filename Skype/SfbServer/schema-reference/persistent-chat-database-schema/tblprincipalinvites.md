---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites содержит приглашения для всех подготовленных пользователей для всех узлов с автоматическим приглашением на.
ms.openlocfilehash: 5008158dcb1c62c766162595d9bffe1875d56514
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924425"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites содержит приглашения для всех подготовленных пользователей для всех узлов с автоматическим приглашением на.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|prinID  <br/> |int, не null  <br/> |Идентификатор субъекта.  <br/> |
|invID  <br/> |int, не null  <br/> |Уникальный порядковый номер (на код участника) созданный для таблицы tblLastInviteId.  <br/> |
|nodeID  <br/> |int, не null  <br/> |КОД узла (только комната чата).  <br/> |
|createdOn  <br/> |DateTime, не может быть null  <br/> |Время создания.  <br/> |
   
**Ключи**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<prinID nodeID\>  <br/> |Первичный ключ.  <br/> |
|prinID  <br/> |Внешний ключ с подстановкой в таблице tblPrincipal.prinID.  <br/> |
|nodeID  <br/> |Внешний ключ с подстановкой в таблице tblNode.nodeID.  <br/> |
   

