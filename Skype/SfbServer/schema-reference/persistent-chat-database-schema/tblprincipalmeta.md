---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta содержит принципы, которые необходимо обновить из служб домена Active Directory.
ms.openlocfilehash: 77c260f56fe2f3e5b61956808b26bef1c7cf8827
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398623"
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
   

