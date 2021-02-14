---
title: Таблица Endpoint
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
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: Таблица Endpoint — это вспомогательная таблица, в которой хранится информация о конечных точках, которые участвовали в сеансах, записанных в базе данных. Каждая запись в таблице представляет одну конечную точку.
ms.openlocfilehash: 9caa0571e562a84c1678208f0e70c27317deda3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823069"
---
# <a name="endpoint-table"></a>Таблица Endpoint
 
Таблица Endpoint — это вспомогательная таблица, в которой хранится информация о конечных точках, которые участвовали в сеансах, записанных в базе данных. Каждая запись в таблице представляет одну конечную точку.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий эту конечную точку.  <br/> |
|**Название** <br/> |nvarchar(256)  <br/> |Уникальные  <br/> |Имя конечной точки.  <br/> |
|**ОС** <br/> |nvarchar(128)  <br/> | <br/> |Операционная система (ОС) конечной точки.  <br/> |
|**CPUName** <br/> |nvarchar(128)  <br/> ||Имя ЦП конечной точки.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||Количество ядер ЦП конечной точки.  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||Скорость процессора ЦП конечной точки.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Флаг бита, который указывает, работает ли система в виртуализированной среде: <br/>  0x0000 - Нет <br/>  0x0001 — HyperV <br/>  0x0002 VMWare <br/>  0x0004 виртуальный КОМПЬЮТЕР <br/>  0x0008 Xen PC <br/> |
   

