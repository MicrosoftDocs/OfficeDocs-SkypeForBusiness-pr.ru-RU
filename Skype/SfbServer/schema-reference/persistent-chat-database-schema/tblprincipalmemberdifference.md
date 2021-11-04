---
title: tblPrincipalMemberDifference
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
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference содержит изменения членства в группах (как добавленных, так и удалены членов), которые еще не обработаны в последующих действиях синхронизации служб домена Active Directory.
ms.openlocfilehash: 884f1450b74300ad2915c27b524dc0419c97062d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743165"
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
   

