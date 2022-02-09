---
title: Таблица конечных точек
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Таблица Endpoint — это вспомогательная таблица, в которой хранится информация о конечных точках, участвующих в сеансах, записанных в базе данных. Каждая запись в таблице представляет одну конечную точку.
ms.openlocfilehash: 4085b8e22aea565054dbb03de10808712c54361e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399563"
---
# <a name="endpoint-table"></a>Таблица конечных точек
 
Таблица Endpoint — это вспомогательная таблица, в которой хранится информация о конечных точках, участвующих в сеансах, записанных в базе данных. Каждая запись в таблице представляет одну конечную точку.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, определяющий эту конечную точку.  <br/> |
|**Имя** <br/> |nvarchar (256)  <br/> |Уникальные  <br/> |Имя конечной точки.  <br/> |
|**ОС** <br/> |nvarchar (128)  <br/> | <br/> |Операционная система (ОС) конечной точки.  <br/> |
|**Имя CPU** <br/> |nvarchar (128)  <br/> ||Имя конечной точки ЦП.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||Количество ядер ЦП конечной точки.  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||Скорость процессора ЦП конечной точки.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Флаг бита, который указывает, работает ли система в виртуализированной среде: <br/>  0x0000 - Нет <br/>  0x0001 - HyperV <br/>  0x0002 - VMWare <br/>  0x0004 — виртуальный КОМПЬЮТЕР <br/>  0x0008 Xen PC <br/> |
   

