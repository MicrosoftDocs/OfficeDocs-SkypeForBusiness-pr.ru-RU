---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole содержит явные роли, назначенные узлам.
ms.openlocfilehash: 6c9960c4eafc2d28a4710a8e4dded6bea19c841a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828532"
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
   

