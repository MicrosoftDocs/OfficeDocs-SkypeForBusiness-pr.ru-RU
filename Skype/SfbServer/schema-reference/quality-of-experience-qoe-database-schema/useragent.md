---
title: Таблица UserAgent
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: Таблица UserAgent представляет собой вспомогательную таблицу, в которой хранится список различных агентов пользователя, которые участвовали в сеансах, записанные в базе данных. Каждая запись в таблице представляет один агент пользователя
ms.openlocfilehash: 17cb395569e8a634925be27705b878b104a3b70a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893106"
---
# <a name="useragent-table"></a>Таблица UserAgent
 
Таблица UserAgent представляет собой вспомогательную таблицу, в которой хранится список различных агентов пользователя, которые участвовали в сеансах, записанные в базе данных. Каждая запись в таблице представляет один агент пользователя
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот агент пользователя.  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |Уникальный  <br/> |Строка агента пользователя.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 — сервер-посредник.  <br/> 2-A / V Server конференц-связи.  <br/> 4 — Скайп для бизнеса.  <br/> 8 — IP-телефона.  <br/> 16 — консоль Live Meeting.  <br/> 32 — средство проверки развертывания (DVT).  <br/> 64 — Скайп для Business Server на компьютерах Macintosh.  <br/> 128 — Скайп для помощника Business Server.  <br/> 256 — служба оповещения для конференц-связи.  <br/> 512 — автосекретарь конференц-связи.  <br/> 1024 — приложение группы ответа.  <br/> 2048 — управление внешней голосовой связью.  <br/> |
   

