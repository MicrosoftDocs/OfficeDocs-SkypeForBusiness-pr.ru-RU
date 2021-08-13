---
title: Таблица сервера
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
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: Таблица Server является таблицей поддержки. Каждая запись в этой таблице представляет один сервер.
ms.openlocfilehash: e43e245e62b1b40f318d1920ae93d82ae9e8bad0e28436f31d9cc2f0fe54bac1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341624"
---
# <a name="server-table"></a>Таблица сервера
 
Таблица Server является таблицей поддержки. Каждая запись в этой таблице представляет один сервер. 
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий сервер.  <br/> |
|**FQDNOrIP** <br/> |nvarchar (256)  <br/> |index  <br/> |Строка MAC-адреса.  <br/> |
|**ServerType** <br/> |int  <br/> |Foreign  <br/> |1: сервер-посредник  <br/> 2: сервер аудио- и видеоконференций 16394: пограничная служба аудио- и видеосвязи 32769: шлюз  <br/> |
|**PoolName** <br/> |nvarchar (512)  <br/> ||Пул, которому принадлежит сервер. Применяется только для серверов аудио- и видеоконференций.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Только для внутреннего использования.  <br/> |
   

