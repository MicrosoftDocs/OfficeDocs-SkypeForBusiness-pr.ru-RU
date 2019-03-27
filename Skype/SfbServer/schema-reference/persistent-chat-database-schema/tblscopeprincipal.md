---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal содержит области, назначенные узлам.
ms.openlocfilehash: e93b92280605dfe01f288435c7cb42b724c22064
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885626"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal содержит области, назначенные узлам.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**.|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int, не null  <br/> |Идентификатор узла, к которому применяется область.  <br/> |
|scopePrinID  <br/> |int, не null  <br/> |Идентификатор субъекта.  <br/> |
|scopeIsDenied  <br/> |bit, не может быть null  <br/> |Значение true, если тип области — Deny; Значение false, если разрешение.  <br/> |
|scopeUpdatedBy  <br/> |int, не null  <br/> |Идентификатор субъекта, который последним обновил эту запись.  <br/> |
   
**Ключи**

|**Столбец**|**Описание**.|
|:-----|:-----|
|\<scopeNodeID scopePrinID\>  <br/> |Первичный ключ.  <br/> |
|scopeNodeID  <br/> |Внешний ключ с подстановкой в таблице tblNode.nodeID.  <br/> |
|scopePrinID  <br/> |Внешний ключ с подстановкой в таблице tblPrincipal.prinID.  <br/> |
   

