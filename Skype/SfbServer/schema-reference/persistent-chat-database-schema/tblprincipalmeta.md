---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta содержит принципы, которые необходимо обновить из служб домена Active Directory.
ms.openlocfilehash: a2cc7ef5313be8abdf50c6cebc5bb8999bf153eeeba0a188cd2d34d2c4608546
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289427"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta содержит принципы, которые необходимо обновить из служб домена Active Directory.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |ИД субъекта.  <br/> |
|prinAffiliationsDirty  <br/> |bit, не равно null  <br/> |Значение true, если назначения субъектов требуется обновить.  <br/> |
|prinAttributesDirty  <br/> |bit, не равно null  <br/> |Значение true, если атрибуты субъектов требуется обновить.  <br/> |
|prinDeleted  <br/> |bit, не равно null  <br/> |Значение true, если субъект был удален.  <br/> |
|tryCount  <br/> |int  <br/> |Число попыток обновления субъекта из доменных служб Active Directory, предпринятых на данный момент.  <br/> |
|lastTry  <br/> |datetime  <br/> |Метка времени для последней попытки обновления субъекта. Может иметь значение null, если попытки обновления еще не предпринимались.  <br/> |
|nextTry  <br/> |datetime  <br/> |Метка времени для следующего запланированного обновления. Может иметь значение null, если дальнейшее обновление не запланировано.  <br/> |
   
**Keys**

|**Столбец**|**Описание**|
|:-----|:-----|
|prinID  <br/> |Первичный ключ.  <br/> |
|prinID  <br/> |Внешний ключ с поиском в таблице tblPrincipal.prinID.  <br/> |
   

