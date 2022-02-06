---
title: tblADUpdates
ms.reviewer: null
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: 'tblADUpdates содержит изменения служб домена Active Directory, которые еще не обработаны в последующих действиях синхронизации Active Directory.'
---

# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates содержит изменения служб домена Active Directory, которые еще не обработаны в последующих действиях синхронизации Active Directory.
  
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
   

