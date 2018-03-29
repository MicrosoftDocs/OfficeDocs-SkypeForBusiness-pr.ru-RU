---
title: Таблица Subnet
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
ms.openlocfilehash: ed54341e66c3370086047eb9b073d2560172a261
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="subnet-table"></a>Таблица Subnet
 
Таблица Subnet представляет собой вспомогательную таблицу. Каждая запись представляет одну подсеть, определенные на странице параметров конфигурации сети.
  
|**Столбец**|**Тип данных**|**Ключ или индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |целое  <br/> |Основной, внешний  <br/> |Целое число, представляющее IP-адреса подсети.  <br/> |
|**Маска подсети** <br/> |целое  <br/> ||Маска подсети.  <br/> |
|**UserSiteKey** <br/> |целое  <br/> |Внешний  <br/> |Ссылка из [таблицы UserSite table](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar(512)  <br/> ||Описание подсети.  <br/> |
   

