---
title: tblADUpdates
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: Таблица tblADUpdates содержит изменения доменных служб Active Directory, которые еще не были обработаны с последующих этапах синхронизации Active Directory.
ms.openlocfilehash: 33d2ae6d2113d3f55b0fdf54439e2383ca142589
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tbladupdates"></a>tblADUpdates
 
Таблица tblADUpdates содержит изменения доменных служб Active Directory, которые еще не были обработаны с последующих этапах синхронизации Active Directory.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|prinGuid  <br/> |Идентификатор GUID, не может быть null  <br/> |Глобальный Уникальный ИД измененного объекта.  <br/> |
|prinADPath  <br/> |nvarchar (384), отлично от null  <br/> |Различающееся имя объекта.  <br/> |
|prinAttributesChanged  <br/> |bit, не может быть null  <br/> |Значение true, если хотя бы один атрибут объекта изменяется.  <br/> |
|prinMembersChanged  <br/> |bit, не может быть null  <br/> |Значение true, если изменилось членство.  <br/> |
|prinAffiliationsChanged  <br/> |bit, не может быть null  <br/> |Не используется.  <br/> |
|prinDeleted  <br/> |bit, не может быть null  <br/> |Значение true, если объект был удален.  <br/> |
|lastUpdated  <br/> |DateTime, не может быть null  <br/> |Когда строка была вставлена метка времени.  <br/> |
   

