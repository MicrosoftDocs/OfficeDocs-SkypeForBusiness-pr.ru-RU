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
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: Таблица UserSite является вспомогательной. Каждая запись представляет один сайт пользователя, определенный в параметре конфигурации сети.
ms.openlocfilehash: 88df08875ea3254ee355a96aa3b12d3ee7f5ccaf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799919"
---
# <a name="usersite-table"></a>Таблица UserSite
 
Таблица UserSite является вспомогательной. Каждая запись представляет один сайт пользователя, определенный в параметре конфигурации сети.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий сайт пользователя.  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |Уникальные  <br/> |Имя сайта пользователя.  <br/> |
|**RegionKey** <br/> |int  <br/> |Внешняя  <br/> |Ссылка из [таблицы Region.](region.md)  <br/> |
   

