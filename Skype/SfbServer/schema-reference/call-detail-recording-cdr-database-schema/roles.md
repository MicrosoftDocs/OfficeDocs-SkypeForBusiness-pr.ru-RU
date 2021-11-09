---
title: Таблица ролей
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
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.
ms.openlocfilehash: 67faf16a478a8ca1f4c2f3bc21bd5d4a6f28909f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60842651"
---
# <a name="roles-table"></a>Таблица ролей
 
The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**Role** <br/> |nvarchar (256)  <br/> || Допустимые значения: <br/>  0 — неизвестно <br/>  1 — выступающий <br/>  2 — участник <br/> |
   

