---
title: Таблица Subnet
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Таблица Subnet представляет собой вспомогательную таблицу. Каждая запись представляет одну подсеть, определенные на странице параметров конфигурации сети.
ms.openlocfilehash: aa91202bfb46a96f86ea3a631be3b964a17a6058
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880478"
---
# <a name="subnet-table"></a>Таблица Subnet
 
Таблица Subnet представляет собой вспомогательную таблицу. Каждая запись представляет одну подсеть, определенные на странице параметров конфигурации сети.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |целое  <br/> |Основной, внешний  <br/> |Целое число, представляющее IP-адреса подсети.  <br/> |
|**Маска подсети** <br/> |целое  <br/> ||Маска подсети.  <br/> |
|**UserSiteKey** <br/> |целое  <br/> |Внешний  <br/> |Ссылка из [таблицы UserSite table](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||Описание подсети.  <br/> |
   

