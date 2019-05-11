---
title: Таблица UserAgent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: Таблица UserAgent представляет собой вспомогательную таблицу, в которой хранится список различных агентов пользователя, которые участвовали в сеансах, записанные в базе данных. Каждая запись в таблице представляет один агент пользователя
ms.openlocfilehash: 432f5ccc26d790aff07f221a7ef9912d16c49499
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907005"
---
# <a name="useragent-table"></a>Таблица UserAgent
 
Таблица UserAgent представляет собой вспомогательную таблицу, в которой хранится список различных агентов пользователя, которые участвовали в сеансах, записанные в базе данных. Каждая запись в таблице представляет один агент пользователя
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот агент пользователя.  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |Уникальный  <br/> |Строка агента пользователя.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 — сервер-посредник.  <br/> 2-A / V Server конференц-связи.  <br/> 4 — Скайп для бизнеса.  <br/> 8 — IP-телефона.  <br/> 16 — консоль Live Meeting.  <br/> 32 — средство проверки развертывания (DVT).  <br/> 64 — Скайп для Business Server на компьютерах Macintosh.  <br/> 128 — Скайп для помощника Business Server.  <br/> 256 — служба оповещения для конференц-связи.  <br/> 512 — автосекретарь конференц-связи.  <br/> 1024 — приложение группы ответа.  <br/> 2048 — управление внешней голосовой связью.  <br/> |
   

