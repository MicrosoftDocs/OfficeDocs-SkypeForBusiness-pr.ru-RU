---
title: Таблица subnet
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Таблица Subnet является вспомогательной. Каждая запись представляет одну подсеть, определенную в параметрах конфигурации сети.
ms.openlocfilehash: b0c10fae89fe76c184e3aaffec4e1166c4cdb94c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768317"
---
# <a name="subnet-table"></a>Таблица subnet
 
Таблица Subnet является вспомогательной. Каждая запись представляет одну подсеть, определенную в параметрах конфигурации сети.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**SubnetIP** <br/> |int  <br/> |Основной, внешний  <br/> |Целочисленное представление IP-адреса подсети.  <br/> |
|**SubnetMask** <br/> |int  <br/> ||Маска подсети.  <br/> |
|**UserSiteKey** <br/> |int  <br/> |Foreign  <br/> |Ссылки из [таблицы UserSite](usersite.md).  <br/> |
|**SubnetDescription** <br/> |nvarchar (512)  <br/> ||Описание подсети.  <br/> |
   

