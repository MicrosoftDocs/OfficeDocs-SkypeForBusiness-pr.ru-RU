---
title: Таблица UserSite
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: Таблица UserSite — это вспомогательная таблица. Каждая запись представляет один сайт пользователя, определенный в параметре конфигурации сети.
ms.openlocfilehash: 5e7ae6f304d836fc2413cbbaf696200c3f514bd1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595269"
---
# <a name="usersite-table"></a>Таблица UserSite
 
Таблица UserSite — это вспомогательная таблица. Каждая запись представляет один сайт пользователя, определенный в параметре конфигурации сети.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий сайт пользователя.  <br/> |
|**UserSiteName** <br/> |nvarchar (128)  <br/> |Уникальные  <br/> |Имя сайта пользователя.  <br/> |
|**RegionKey** <br/> |int  <br/> |Foreign  <br/> |Ссылки из [таблицы Регион](region.md).  <br/> |
   

