---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole содержит явные роли, назначенные узлам.
ms.openlocfilehash: 69cfb0cb2b821064801a07510758514bb5d33128
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890771"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole содержит явные роли, назначенные узлам.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**.|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int, не null  <br/> |Идентификатор узла, к которому применяется роль.  <br/> |
|prinRolePrinID  <br/> |int, не null  <br/> |Идентификатор субъекта.  <br/> |
|prinRoleTypeID  <br/> |int, не null  <br/> |ИД типа роли (из tblRoleType).  <br/> |
|prinRoleUpdatedBy  <br/> |int, не null  <br/> |Идентификатор субъекта, который последним обновил эту запись.  <br/> |
   
**Ключи**

|**Столбец**|**Описание**.|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |Первичный ключ.  <br/> |
|prinRoleNodeID  <br/> |Внешний ключ с подстановкой в таблице tblNode.nodeID.  <br/> |
|prinRolePrinID  <br/> |Внешний ключ с подстановкой в таблице tblPrincipal.prinID.  <br/> |
|prinRoleTypeID  <br/> |Внешний ключ с поиском в таблице tblRoleType.rtypeID.  <br/> |
   

