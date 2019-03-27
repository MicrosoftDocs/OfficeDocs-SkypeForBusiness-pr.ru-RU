---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta содержит список субъектов, которых необходимо обновить из доменных служб Active Directory.
ms.openlocfilehash: 049a273f7134ecb945e62da39469bcaf0defbffb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889609"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta содержит список субъектов, которых необходимо обновить из доменных служб Active Directory.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**.|
|:-----|:-----|:-----|
|prinID  <br/> |int, не null  <br/> |Идентификатор субъекта.  <br/> |
|prinAffiliationsDirty  <br/> |bit, не может быть null  <br/> |Значение true, если назначения субъектов требуется обновить.  <br/> |
|prinAttributesDirty  <br/> |bit, не может быть null  <br/> |Значение true, если атрибуты которых необходимо обновить.  <br/> |
|prinDeleted  <br/> |bit, не может быть null  <br/> |Значение true, если субъект был удален.  <br/> |
|tryCount  <br/> |целое  <br/> |Число попыток обновления субъекта из Доменных службах Active Directory, предпринятых на данный момент.  <br/> |
|lastTry  <br/> |datetime  <br/> |Метка времени последней попытки обновления субъекта. Может иметь значение null, если обновление не предпринята попытка еще.  <br/> |
|nextTry  <br/> |datetime  <br/> |Метка времени для следующего запланированного обновления. Может иметь значение null, если дальнейшие обновления по расписанию.  <br/> |
   
**Ключи**

|**Столбец**|**Описание**.|
|:-----|:-----|
|prinID  <br/> |Первичный ключ.  <br/> |
|prinID  <br/> |Внешний ключ с подстановкой в таблице tblPrincipal.prinID.  <br/> |
   

