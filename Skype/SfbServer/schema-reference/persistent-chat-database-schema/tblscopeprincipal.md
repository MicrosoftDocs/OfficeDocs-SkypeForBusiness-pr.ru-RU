---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal содержит области, назначенные узлам.
ms.openlocfilehash: e86b259126ee58c26246e78e1afd44a5e5122cbdbaaabb7f0967bb2bba7e5d39
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337597"
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
   

