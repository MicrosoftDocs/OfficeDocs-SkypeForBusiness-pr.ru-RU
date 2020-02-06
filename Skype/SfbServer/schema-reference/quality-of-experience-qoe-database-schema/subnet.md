---
title: Таблица Subnet
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Таблица подсети является вспомогательной таблицей. Каждая запись соответствует одной подсети, определенной в параметрах конфигурации сети.
ms.openlocfilehash: 562684fdb4df9ac90216489c209754309885fa98
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805207"
---
# <a name="subnet-table"></a>Таблица Subnet
 
Таблица подсети является вспомогательной таблицей. Каждая запись соответствует одной подсети, определенной в параметрах конфигурации сети.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**субнетип** <br/> |целое  <br/> |Основной, внешний  <br/> |Целочисленное представление для IP-адреса подсети.  <br/> |
|**Сети** <br/> |целое  <br/> ||Маска подсети.  <br/> |
|**усерситекэй** <br/> |целое  <br/> |Другом  <br/> |На которую ссылается [Таблица усерсите](usersite.md).  <br/> |
|**субнетдескриптион** <br/> |nvarchar (512)  <br/> ||Описание подсети.  <br/> |
   

