---
title: Таблица UserSite
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: 'Таблица UserSite — это вспомогательная таблица. Каждая запись представляет один сайт пользователя, определенный в параметре конфигурации сети.'
---

# <a name="usersite-table"></a>Таблица UserSite
 
Таблица UserSite — это вспомогательная таблица. Каждая запись представляет один сайт пользователя, определенный в параметре конфигурации сети.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий сайт пользователя.  <br/> |
|**UserSiteName** <br/> |nvarchar (128)  <br/> |Уникальные  <br/> |Имя сайта пользователя.  <br/> |
|**RegionKey** <br/> |int  <br/> |Foreign  <br/> |Ссылки из [таблицы Region](region.md).  <br/> |
   

