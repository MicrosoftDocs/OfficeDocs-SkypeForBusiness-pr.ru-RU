---
title: tblPrincipalMemberDifference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference содержит изменения членства в группе (как добавлять и удалять участников), которые еще не были обработаны с последующих этапах синхронизации службы домена Active Directory.
ms.openlocfilehash: 603c8345f2adc2ba7d5eb04835218fd3e83d8ed4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference содержит изменения членства в группе (как добавлять и удалять участников), которые еще не были обработаны с последующих этапах синхронизации службы домена Active Directory.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|prinGuid  <br/> |Идентификатор GUID, не может быть null  <br/> |GUID субъекта для измененной группы.  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |Различающееся имя члена.  <br/> |
|memberRemoved  <br/> |bit, не может быть null  <br/> |False, если элемент был добавлен. Значение true, если элемент был удален.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<prinGuid memberADPath\>  <br/> |Первичный ключ.  <br/> |
   

