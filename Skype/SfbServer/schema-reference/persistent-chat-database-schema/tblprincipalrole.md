---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole содержит явные роли, назначенные узлам.
ms.openlocfilehash: 7c144f2f531af58c7c5693b28b224a2ee4456783
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904183"
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
   

