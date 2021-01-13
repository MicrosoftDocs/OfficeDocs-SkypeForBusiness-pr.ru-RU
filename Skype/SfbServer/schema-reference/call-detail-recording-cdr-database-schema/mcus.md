---
title: Таблица Mcus в Skype для бизнеса Server 2015
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
description: Таблица Mcus является вспомогательной. В каждой записи хранится информация об одной службе conferencing. Они могут включать службу im Conferencing и службу телефонной связи (которая работает как процессы на серверах переднего сервера), а также службу веб-службы и службу A/V Conferencing.
ms.openlocfilehash: fe43bfc747cd08febe00a68925ad520b6add5846
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821429"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a>Таблица Mcus в Skype для бизнеса Server 2015
 
Таблица Mcus является вспомогательной. В каждой записи хранится информация об одной службе conferencing. Они могут включать службу im Conferencing и службу телефонной связи (которая работает как процессы на серверах переднего сервера), а также службу веб-службы и службу A/V Conferencing. 
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**McuId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот сервер.  <br/> |
|**McuUri** <br/> |nvarchar(450)  <br/> | <br/> | <br/> |
|**McuTypeId** <br/> |inyint  <br/> | Внешняя <br/> |Тип сервера аудиоконференции, например conf:chat (для IMs) или conf:audio-video. Дополнительные сведения см. в таблице [UriTypes.](uritypes.md) <br/> |
   

