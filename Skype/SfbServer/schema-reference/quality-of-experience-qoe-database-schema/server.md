---
title: Таблица сервера
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
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: Таблица Server является таблицей поддержки. Каждая запись в этой таблице представляет один сервер.
ms.openlocfilehash: c061176c7a3dbb30fbbe696241fccd54db8dc9b2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834927"
---
# <a name="server-table"></a>Таблица сервера
 
Таблица Server является таблицей поддержки. Каждая запись в этой таблице представляет один сервер. 
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий сервер.  <br/> |
|**FQDNOrIP** <br/> |nvarchar (256)  <br/> |index  <br/> |Строка MAC-адреса.  <br/> |
|**ServerType** <br/> |int  <br/> |Foreign  <br/> |1: сервер-посредник  <br/> 2: сервер аудио- и видеоконференций 16394: пограничная служба аудио- и видеосвязи 32769: шлюз  <br/> |
|**PoolName** <br/> |nvarchar (512)  <br/> ||Пул, которому принадлежит сервер. Применяется только для серверов аудио- и видеоконференций.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Только для внутреннего использования.  <br/> |
   

