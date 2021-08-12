---
title: Таблица конечных точек
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
description: Таблица Endpoint — это вспомогательная таблица, в которой хранится информация о конечных точках, участвующих в сеансах, записанных в базе данных. Каждая запись в таблице представляет одну конечную точку.
ms.openlocfilehash: 821f24ae2be38a699ce1c21255a66ec4a2fa2f17e448a1cc7b69a5a91d91d714
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302203"
---
# <a name="endpoint-table"></a>Таблица конечных точек
 
Таблица Endpoint — это вспомогательная таблица, в которой хранится информация о конечных точках, участвующих в сеансах, записанных в базе данных. Каждая запись в таблице представляет одну конечную точку.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, определяющий эту конечную точку.  <br/> |
|**Название** <br/> |nvarchar (256)  <br/> |Уникальные  <br/> |Имя конечной точки.  <br/> |
|**OS** <br/> |nvarchar (128)  <br/> | <br/> |Операционная система (ОС) конечной точки.  <br/> |
|**Имя CPU** <br/> |nvarchar (128)  <br/> ||Имя конечной точки ЦП.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||Количество ядер ЦП конечной точки.  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||Скорость процессора ЦП конечной точки.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Флаг бита, который указывает, работает ли система в виртуализированной среде: <br/>  0x0000 - Нет <br/>  0x0001 - HyperV <br/>  0x0002 - VMWare <br/>  0x0004 — виртуальный КОМПЬЮТЕР <br/>  0x0008 Xen PC <br/> |
   

