---
title: Таблица UserSite
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: Таблицы UserSite table представляет собой вспомогательную таблицу. Каждая запись представляет один сайт пользователя, определенные на странице параметров конфигурации сети.
ms.openlocfilehash: effc2404a91bf122dc9be9ad371372e8355b230f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="usersite-table"></a>Таблица UserSite
 
Таблицы UserSite table представляет собой вспомогательную таблицу. Каждая запись представляет один сайт пользователя, определенные на странице параметров конфигурации сети.
  
|**Столбец**|**Тип данных**|**Ключ или индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий сайт пользователя.  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |Уникальный  <br/> |Имя сайта пользователя.  <br/> |
|**RegionKey** <br/> |целое  <br/> |Внешний  <br/> |Ссылка из [Region table](region.md).  <br/> |
   

