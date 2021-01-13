---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock содержит блокировку администратора, необходимую для запуска некоторых команд администратора.
ms.openlocfilehash: aed7720a9b74483a34704c0009958ea91a786fc1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809889"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock содержит блокировку администратора, необходимую для запуска некоторых команд администратора.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime, не null  <br/> |Дата и время истечения срока блокировки. Владелец может периодически продлевать этот срок.  <br/> |
|lockServerID  <br/> |int, не null  <br/> |Идентификатора сервера, которому принадлежит блокировка.  <br/> |
|lockActorID  <br/> |int, не null  <br/> |Идентификатора участника, которому принадлежит блокировка.  <br/> |
   

