---
title: Таблица Mcus в Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: Таблица Mcus — это вспомогательная таблица. Каждая запись хранит сведения об одной службе конференций. Они могут включать службу конференциации im и службу телефонии conferencing (которая работает как процессы на передних серверах), и службу веб-конференциации и службу A/V Conferencing.
ms.openlocfilehash: 501736f91073b193f68a22dee8bf54899ee1250373258cf49fb19ed02af5c5e1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54352078"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Таблица Mcus в Skype для бизнеса Server 2015 г.
 
Таблица Mcus — это вспомогательная таблица. Каждая запись хранит сведения об одной службе конференций. Они могут включать службу конференциации im и службу телефонии conferencing (которая работает как процессы на передних серверах), и службу веб-конференциации и службу A/V Conferencing. 
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот сервер конференций.  <br/> |
|**McuUri** <br/> |nvarchar (450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Foreign <br/> |Тип сервера conferencing, например conf:chat (для IMs) или conf:audio-video. Дополнительные сведения см. в таблице [UriTypes.](uritypes.md) <br/> |
   

