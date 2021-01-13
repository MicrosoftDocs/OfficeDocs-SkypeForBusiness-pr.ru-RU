---
title: tblPrincipalMemberDifference
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
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference содержит изменения членства в группах (как добавленных, так и удаленных членов), которые еще не были обработаны в последующих шагах синхронизации доменных служб Active Directory.
ms.openlocfilehash: 8fac76f1abfbd55d13d89c96bb23a6953d38edf9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809709"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference содержит изменения членства в группах (как добавленных, так и удаленных членов), которые еще не были обработаны в последующих шагах синхронизации доменных служб Active Directory.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, не NULL  <br/> |GUID субъекта для измененной группы.  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |Различающееся имя члена.  <br/> |
|memberRemoved  <br/> |bit, не NULL  <br/> |False, если член был добавлен. True, если член был удален.  <br/> |
   
**Раздел**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |Первичный ключ.  <br/> |
   

