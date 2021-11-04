---
title: Таблица ролей
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
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.
ms.openlocfilehash: 2bd15fd98aff2ce8066a396efac0b538d4891a8f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776159"
---
# <a name="roles-table"></a>Таблица ролей
 
The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**Role** <br/> |nvarchar (256)  <br/> || Допустимые значения: <br/>  0 — неизвестно <br/>  1 — выступающий <br/>  2 — участник <br/> |
   

