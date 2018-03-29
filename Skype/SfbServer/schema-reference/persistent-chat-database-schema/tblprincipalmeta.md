---
title: tblPrincipalMeta
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
ms.openlocfilehash: cfbff018167a3cde68061c3e04eb65d2742e51e9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta содержит список субъектов, которых необходимо обновить из доменных служб Active Directory.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|prinID  <br/> |int, не null  <br/> |Идентификатор субъекта.  <br/> |
|prinAffiliationsDirty  <br/> |bit, не может быть null  <br/> |Значение true, если назначения субъектов требуется обновить.  <br/> |
|prinAttributesDirty  <br/> |bit, не может быть null  <br/> |Значение true, если атрибуты которых необходимо обновить.  <br/> |
|prinDeleted  <br/> |bit, не может быть null  <br/> |Значение true, если субъект был удален.  <br/> |
|tryCount  <br/> |целое  <br/> |Число попыток обновления субъекта из Доменных службах Active Directory, предпринятых на данный момент.  <br/> |
|lastTry  <br/> |datetime  <br/> |Метка времени последней попытки обновления субъекта. Может иметь значение null, если обновление не предпринята попытка еще.  <br/> |
|nextTry  <br/> |datetime  <br/> |Метка времени для следующего запланированного обновления. Может иметь значение null, если дальнейшие обновления по расписанию.  <br/> |
   
**Ключи**

|**Столбец**|**Описание**|
|:-----|:-----|
|prinID  <br/> |Первичный ключ.  <br/> |
|prinID  <br/> |Внешний ключ с подстановкой в таблице tblPrincipal.prinID.  <br/> |
   

