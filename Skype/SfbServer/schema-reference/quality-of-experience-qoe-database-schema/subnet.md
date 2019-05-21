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
localization_priority: Normal
ms.assetid: 76f5c995-96c8-4aa3-bc30-1d74991d7c42
description: Таблица подсети является вспомогательной таблицей. Каждая запись соответствует одной подсети, определенной в параметрах конфигурации сети.
ms.openlocfilehash: 9f36c5e334e92caa8bf4a81a682b7737e8999b3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294637"
---
# <a name="subnet-table"></a>Таблица Subnet
 
Таблица подсети является вспомогательной таблицей. Каждая запись соответствует одной подсети, определенной в параметрах конфигурации сети.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Субнетип** <br/> |целое  <br/> |Основной, внешний  <br/> |Целочисленное представление для IP-адреса подсети.  <br/> |
|**Сети** <br/> |целое  <br/> ||Маска подсети.  <br/> |
|**Усерситекэй** <br/> |целое  <br/> |Другом  <br/> |На которую ссылается [Таблица усерсите](usersite.md).  <br/> |
|**Субнетдескриптион** <br/> |nvarchar (512)  <br/> ||Описание подсети.  <br/> |
   

