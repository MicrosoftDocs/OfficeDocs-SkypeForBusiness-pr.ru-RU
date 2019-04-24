---
title: Таблица UserSite
ms.reviewer: ''
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
ms.openlocfilehash: a52f5cd9aa7059e2b545dec3bcc7ccb86191347a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212048"
---
# <a name="usersite-table"></a>Таблица UserSite
 
Таблицы UserSite table представляет собой вспомогательную таблицу. Каждая запись представляет один сайт пользователя, определенные на странице параметров конфигурации сети.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий сайт пользователя.  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |Уникальный  <br/> |Имя сайта пользователя.  <br/> |
|**RegionKey** <br/> |целое  <br/> |Внешний  <br/> |Ссылка из [Region table](region.md).  <br/> |
   

