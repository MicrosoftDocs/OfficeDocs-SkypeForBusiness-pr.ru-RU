---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates содержит изменения доменных служб Active Directory, которые еще не были обработаны в последующих шагах синхронизации Active Directory.
ms.openlocfilehash: 16bb393eb57e7aaf8d3fea7001157eaabbe70c52
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821389"
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates содержит изменения доменных служб Active Directory, которые еще не были обработаны в последующих шагах синхронизации Active Directory.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, not null  <br/> |Глобальный уникальный ИД измененного объекта.  <br/> |
|prinADPath  <br/> |nvarchar (384), not null  <br/> |Различающееся имя объекта.  <br/> |
|prinAttributesChanged  <br/> |bit, not null  <br/> |TRUE, если изменился хотя бы один атрибут объекта.  <br/> |
|prinMembersChanged  <br/> |bit, not null  <br/> |TRUE, если изменилось членство.  <br/> |
|prinAffiliationsChanged  <br/> |bit, not null  <br/> |Не используется.  <br/> |
|prinDeleted  <br/> |bit, not null  <br/> |TRUE, если объект был удален.  <br/> |
|lastUpdated  <br/> |datetime, not null  <br/> |Метка времени добавления строки.  <br/> |
   

