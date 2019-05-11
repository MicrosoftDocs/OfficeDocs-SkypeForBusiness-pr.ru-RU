---
title: Таблица Endpoint
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: В таблице конечная точка представляет собой вспомогательную таблицу, в которой хранятся сведения о конечных точках, которые участвовали в сеансах, записанные в базе данных. Каждая запись в таблице представляет одной конечной точки.
ms.openlocfilehash: 4917b0817d8fcedbc3a20b2c41d3ed62ce468c5c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920112"
---
# <a name="endpoint-table"></a>Таблица Endpoint
 
В таблице конечная точка представляет собой вспомогательную таблицу, в которой хранятся сведения о конечных точках, которые участвовали в сеансах, записанные в базе данных. Каждая запись в таблице представляет одной конечной точки.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий эту конечную точку.  <br/> |
|**Имя**. <br/> |nvarchar(256)  <br/> |Уникальный  <br/> |Имя конечной точки.  <br/> |
|**OS** <br/> |nvarchar(128)  <br/> | <br/> |Операционная система конечной точки.  <br/> |
|**CPUName** <br/> |nvarchar(128)  <br/> ||Имя ЦП конечной точки.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||Число ядер ЦП конечной точки.  <br/> |
|**CPUProcessorSpeed** <br/> |целое  <br/> ||Скорость ЦП конечной точки.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Битовый флаг, указывающий, если в системе запущена в виртуализованной среде: <br/>  0x0000 - нет <br/>  0x0001 - HyperV <br/>  0x0002 - VMWare <br/>  0x0004 - virtual PC <br/>  0x0008 - Xen ПК <br/> |
   

