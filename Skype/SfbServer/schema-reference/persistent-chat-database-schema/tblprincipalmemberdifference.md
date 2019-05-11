---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference содержит изменения членства в группе (как добавлять и удалять участников), которые еще не были обработаны с последующих этапах синхронизации службы домена Active Directory.
ms.openlocfilehash: 4445bc6a4b83053d7d9244fc20d0a7a8cbd01b26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902238"
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
   

