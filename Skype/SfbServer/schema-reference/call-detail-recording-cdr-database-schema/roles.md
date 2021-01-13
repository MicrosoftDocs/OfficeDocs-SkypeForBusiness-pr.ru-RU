---
title: Таблица Roles
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
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.
ms.openlocfilehash: 6c5e28ccd2d186b0122d70f91621a3365e6d2b07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809979"
---
# <a name="roles-table"></a>Таблица Roles
 
The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**Role** <br/> |nvarchar(256)  <br/> || Допустимые значения: <br/>  0 — неизвестно <br/>  1 — выступающий <br/>  2 — участник <br/> |
   

