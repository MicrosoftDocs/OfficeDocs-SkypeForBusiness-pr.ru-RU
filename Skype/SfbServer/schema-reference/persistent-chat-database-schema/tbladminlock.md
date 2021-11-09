---
title: tblAdminLock
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock содержит блокировку администратора, необходимую для запуска некоторых команд администратора.
ms.openlocfilehash: 1527cee53bc93c9b26a1cb961bba0a7fa53ae2e8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852843"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock содержит блокировку администратора, необходимую для запуска некоторых команд администратора.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime, не null  <br/> |Дата и время истечения срока блокировки. Владелец может периодически продлевать этот срок.  <br/> |
|lockServerID  <br/> |int, не null  <br/> |Идентификатора сервера, которому принадлежит блокировка.  <br/> |
|lockActorID  <br/> |int, не null  <br/> |Идентификатора участника, которому принадлежит блокировка.  <br/> |
   

