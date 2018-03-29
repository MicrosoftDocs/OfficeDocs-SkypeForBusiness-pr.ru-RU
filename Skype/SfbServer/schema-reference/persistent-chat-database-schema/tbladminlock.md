---
title: tblAdminLock
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock содержит блокировку администратора, необходимую для запуска некоторых команд администратора.
ms.openlocfilehash: 919ead84ed9baab859e1e85eb2f30f5ff6902531
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock содержит блокировку администратора, необходимую для запуска некоторых команд администратора.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |DateTime, не может быть null  <br/> |Блокировка срока действия. Владелец можно расширить это значение периодически.  <br/> |
|lockServerID  <br/> |int, не null  <br/> |Идентификатор сервера, которому принадлежит блокировка.  <br/> |
|lockActorID  <br/> |int, не null  <br/> |Идентификатор участника, которому принадлежит блокировка.  <br/> |
   

