---
title: Таблица UserAgent
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
ms.localizationpriority: medium
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: Таблица UserAgent — это вспомогательная таблица, в которой хранится список различных агентов пользователей, которые участвовали в сеансах, записанных в базе данных. Каждая запись в таблице представляет одного агента пользователя
ms.openlocfilehash: 0c23582550e659f4a48661c80770c385e168ed3c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590063"
---
# <a name="useragent-table"></a>Таблица UserAgent
 
Таблица UserAgent — это вспомогательная таблица, в которой хранится список различных агентов пользователей, которые участвовали в сеансах, записанных в базе данных. Каждая запись в таблице представляет одного агента пользователя
  
|**Столбец**|**Тип данных**|**Key/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primary  <br/> |Уникальное число, идентифицирующее этот агент пользователя.  <br/> |
|**UserAgent** <br/> |nvarchar (256)  <br/> |Уникальные  <br/> |Строка Агента пользователя.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 — сервер-посредник.  <br/> 2 — сервер A/V Conferencing Server.  <br/> 4 — Skype для бизнеса.  <br/> 8 — ip-Телефон.  <br/> 16 — это консоль live meeting.  <br/> 32 — это средство проверки развертывания (DVT).  <br/> 64 — Skype для бизнеса Server компьютеров Macintosh.  <br/> 128 — Skype для бизнеса Server Attendant.  <br/> 256 — оповещение для конференц-связи службы.  <br/> 512 — это автосекретарь.  <br/> 1024 — это приложение Группы реагирования.  <br/> 2048 — это внешний голосовой контроль.  <br/> |
   

