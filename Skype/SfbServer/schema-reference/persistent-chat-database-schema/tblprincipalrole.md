---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole содержит явные роли, назначенные узлам.
ms.openlocfilehash: bedb7025605dc5cd3e5808ac265931d8623060b3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767327"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
tblPrincipalRole содержит явные роли, назначенные узлам.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|prinRoleNodeID  <br/> |int, not null  <br/> |ИД узла, к которому применяется роль.  <br/> |
|prinRolePrinID  <br/> |int, not null  <br/> |ИД субъекта.  <br/> |
|prinRoleTypeID  <br/> |int, not null  <br/> |ИД типа роли (из tblRoleType).  <br/> |
|prinRoleUpdatedBy  <br/> |int, not null  <br/> |Код участника, который последним обновил эту запись.  <br/> |
   
**Keys**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |Основной ключ.  <br/> |
|prinRoleNodeID  <br/> |Внешний ключ с поиском в таблице tblNode.nodeID.  <br/> |
|prinRolePrinID  <br/> |Внешний ключ с поиском в таблице tblPrincipal.prinID.  <br/> |
|prinRoleTypeID  <br/> |Внешний ключ с поиском в таблице tblRoleType.rtypeID.  <br/> |
   

