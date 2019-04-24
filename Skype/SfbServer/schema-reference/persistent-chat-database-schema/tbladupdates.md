---
title: tblADUpdates
ms.reviewer: ''
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
ms.openlocfilehash: 0e7bde110ad3d0495cb7ddea55e405eac21d96b4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212644"
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
   

