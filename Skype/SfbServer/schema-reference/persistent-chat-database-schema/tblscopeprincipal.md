---
title: tblScopePrincipal
ms.reviewer: ''
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal содержит области, назначенные узлам.
ms.openlocfilehash: 5805356a882b659c864bf8b071198bfe695f342d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394801"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal содержит области, назначенные узлам.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int, не null  <br/> |Код узла, к которой применяется область.  <br/> |
|scopePrinID  <br/> |int, не null  <br/> |Код участника  <br/> |
|scopeIsDenied  <br/> |bit, не null  <br/> |Значение true, если тип области — Deny; значение false, если тип области — Allow.  <br/> |
|scopeUpdatedBy  <br/> |int, не null  <br/> |Код участника, который последним обновил эту запись.  <br/> |
   
**Keys**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |Первичный ключ.  <br/> |
|scopeNodeID  <br/> |Внешний ключ с подстановкой в таблице tblNode.nodeID.  <br/> |
|scopePrinID  <br/> |Внешний ключ с подстановкой в таблице tblPrincipal.prinID.  <br/> |
   

