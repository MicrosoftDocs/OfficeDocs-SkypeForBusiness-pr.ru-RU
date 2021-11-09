---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 84fa792a6698a474e41c0e623b826fb0b8c48d65
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844032"
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
   

