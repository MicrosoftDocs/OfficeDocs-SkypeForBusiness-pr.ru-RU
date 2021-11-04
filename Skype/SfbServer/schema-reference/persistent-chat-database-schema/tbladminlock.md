---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock содержит блокировку администратора, необходимую для запуска некоторых команд администратора.
ms.openlocfilehash: df040a4a6d503e4ea8f7327e6ac50b5ae411cf60
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746535"
---
# <a name="tbladminlock"></a>tblAdminLock
 
tblAdminLock содержит блокировку администратора, необходимую для запуска некоторых команд администратора.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|lockExpiresTime  <br/> |datetime, не null  <br/> |Дата и время истечения срока блокировки. Владелец может периодически продлевать этот срок.  <br/> |
|lockServerID  <br/> |int, не null  <br/> |Идентификатора сервера, которому принадлежит блокировка.  <br/> |
|lockActorID  <br/> |int, не null  <br/> |Идентификатора участника, которому принадлежит блокировка.  <br/> |
   

