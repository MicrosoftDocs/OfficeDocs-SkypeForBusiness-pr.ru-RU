---
title: Таблица Mcus в Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Таблица Mcus — это вспомогательная таблица. Каждая запись хранит сведения об одной службе конференций. Они могут включать службу конференциации im и службу телефонии conferencing (которая работает как процессы на передних серверах), и службу веб-конференциации и службу A/V Conferencing.
ms.openlocfilehash: 3cd0e096a09f1b83d50d4b7cad8428318d7fdb51
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416382"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Таблица Mcus в Skype для бизнеса Server 2015 г.
 
Таблица Mcus — это вспомогательная таблица. Каждая запись хранит сведения об одной службе конференций. Они могут включать службу конференциации im и службу телефонии conferencing (которая работает как процессы на передних серверах), и службу веб-конференциации и службу A/V Conferencing. 
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот сервер конференций.  <br/> |
|**McuUri** <br/> |nvarchar (450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Foreign <br/> |Тип сервера conferencing, например conf:chat (для IMs) или conf:audio-video. Дополнительные сведения [см. в таблице UriTypes](uritypes.md) . <br/> |
   

