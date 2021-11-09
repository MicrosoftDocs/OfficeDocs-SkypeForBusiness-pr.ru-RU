---
title: Таблица UserSite
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 80286b04e408a8f80e63364e3c7a822ce8e63505
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851773"
---
# <a name="usersite-table"></a>Таблица UserSite
 
Таблица UserSite — это вспомогательная таблица. Каждая запись представляет один сайт пользователя, определенный в параметре конфигурации сети.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий сайт пользователя.  <br/> |
|**UserSiteName** <br/> |nvarchar (128)  <br/> |Уникальные  <br/> |Имя сайта пользователя.  <br/> |
|**RegionKey** <br/> |int  <br/> |Foreign  <br/> |Ссылки из [таблицы Регион](region.md).  <br/> |
   

