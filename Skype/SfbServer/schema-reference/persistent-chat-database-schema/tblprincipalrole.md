---
title: tblPrincipalRole
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
ms.openlocfilehash: 0e6c7f60f372bc14542567ccaa1b1b1a837c6c6d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole содержит явные роли, назначенные узлам.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int, не null  <br/> |Идентификатор узла, к которому применяется роль.  <br/> |
|prinRolePrinID  <br/> |int, не null  <br/> |Идентификатор субъекта.  <br/> |
|prinRoleTypeID  <br/> |int, не null  <br/> |ИД типа роли (из tblRoleType).  <br/> |
|prinRoleUpdatedBy  <br/> |int, не null  <br/> |Идентификатор субъекта, который последним обновил эту запись.  <br/> |
   
**Ключи**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |Первичный ключ.  <br/> |
|prinRoleNodeID  <br/> |Внешний ключ с подстановкой в таблице tblNode.nodeID.  <br/> |
|prinRolePrinID  <br/> |Внешний ключ с подстановкой в таблице tblPrincipal.prinID.  <br/> |
|prinRoleTypeID  <br/> |Внешний ключ с поиском в таблице tblRoleType.rtypeID.  <br/> |
   

