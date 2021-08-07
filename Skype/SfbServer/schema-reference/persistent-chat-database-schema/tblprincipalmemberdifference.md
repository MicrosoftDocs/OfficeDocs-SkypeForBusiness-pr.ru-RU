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
description: tblPrincipalMemberDifference содержит изменения членства в группах (как добавленных, так и удалены членов), которые еще не обработаны в последующих действиях синхронизации служб домена Active Directory.
ms.openlocfilehash: c1d5a0d492d228b5a8292fde608fbd66c3b586c393aba8eb5bc0fbbddd45a5e2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276584"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference содержит изменения членства в группах (как добавленных, так и удалены членов), которые еще не обработаны в последующих действиях синхронизации служб домена Active Directory.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, не NULL  <br/> |GUID субъекта для измененной группы.  <br/> |
|memberADPath  <br/> |nvarchar (256)  <br/> |Различающееся имя члена.  <br/> |
|memberRemoved  <br/> |bit, не NULL  <br/> |False, если член был добавлен. True, если член был удален.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |Первичный ключ.  <br/> |
   

