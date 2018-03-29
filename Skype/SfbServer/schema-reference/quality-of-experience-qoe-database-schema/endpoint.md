---
title: Таблица Endpoint
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: В таблице конечная точка представляет собой вспомогательную таблицу, в которой хранятся сведения о конечных точках, которые участвовали в сеансах, записанные в базе данных. Каждая запись в таблице представляет одной конечной точки.
ms.openlocfilehash: 64eb55a0c1bebe7f2ce992351ce21db2fdc575d7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="endpoint-table"></a>Таблица Endpoint
 
В таблице конечная точка представляет собой вспомогательную таблицу, в которой хранятся сведения о конечных точках, которые участвовали в сеансах, записанные в базе данных. Каждая запись в таблице представляет одной конечной точки.
  
|**Столбец**|**Тип данных**|**Ключ или индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий эту конечную точку.  <br/> |
|**Имя**. <br/> |nvarchar(256)  <br/> |Уникальный  <br/> |Имя конечной точки.  <br/> |
|**ОПЕРАЦИОННАЯ СИСТЕМА** <br/> |nvarchar(128)  <br/> | <br/> |Операционная система конечной точки.  <br/> |
|**CPUName** <br/> |nvarchar(128)  <br/> ||Имя ЦП конечной точки.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||Число ядер ЦП конечной точки.  <br/> |
|**CPUProcessorSpeed** <br/> |целое  <br/> ||Скорость ЦП конечной точки.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Битовый флаг, указывающий, если в системе запущена в виртуализованной среде: <br/>  0x0000 - нет <br/>  0x0001 - HyperV <br/>  0x0002 - VMWare <br/>  0x0004 - virtual PC <br/>  0x0008 - Xen ПК <br/> |
   

