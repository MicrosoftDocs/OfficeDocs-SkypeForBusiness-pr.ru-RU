---
title: Таблица конечных точек
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
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Таблица Endpoint — это вспомогательная таблица, в которой хранится информация о конечных точках, участвующих в сеансах, записанных в базе данных. Каждая запись в таблице представляет одну конечную точку.
ms.openlocfilehash: 7e892d0e913f8b06fc78f00fbbb348774b9548d3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834005"
---
# <a name="endpoint-table"></a>Таблица конечных точек
 
Таблица Endpoint — это вспомогательная таблица, в которой хранится информация о конечных точках, участвующих в сеансах, записанных в базе данных. Каждая запись в таблице представляет одну конечную точку.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, определяющий эту конечную точку.  <br/> |
|**Название** <br/> |nvarchar (256)  <br/> |Уникальные  <br/> |Имя конечной точки.  <br/> |
|**OS** <br/> |nvarchar (128)  <br/> | <br/> |Операционная система (ОС) конечной точки.  <br/> |
|**Имя CPU** <br/> |nvarchar (128)  <br/> ||Имя конечной точки ЦП.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||Количество ядер ЦП конечной точки.  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||Скорость процессора ЦП конечной точки.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Флаг бита, который указывает, работает ли система в виртуализированной среде: <br/>  0x0000 - Нет <br/>  0x0001 - HyperV <br/>  0x0002 - VMWare <br/>  0x0004 — виртуальный КОМПЬЮТЕР <br/>  0x0008 Xen PC <br/> |
   

