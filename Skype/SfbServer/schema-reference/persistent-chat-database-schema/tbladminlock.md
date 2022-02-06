---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: 'tblAdminLock содержит блокировку администратора, необходимую для запуска некоторых команд администратора.'
---

# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock содержит блокировку администратора, необходимую для запуска некоторых команд администратора.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime, не null  <br/> |Дата и время истечения срока блокировки. Владелец может периодически продлевать этот срок.  <br/> |
|lockServerID  <br/> |int, не null  <br/> |Идентификатора сервера, которому принадлежит блокировка.  <br/> |
|lockActorID  <br/> |int, не null  <br/> |Идентификатора участника, которому принадлежит блокировка.  <br/> |
   

