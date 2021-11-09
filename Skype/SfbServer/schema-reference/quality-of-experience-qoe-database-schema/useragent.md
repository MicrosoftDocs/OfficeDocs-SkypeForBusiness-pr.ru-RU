---
title: Таблица UserAgent
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
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: Таблица UserAgent — это вспомогательная таблица, в которой хранится список различных агентов пользователей, которые участвовали в сеансах, записанных в базе данных. Каждая запись в таблице представляет одного агента пользователя
ms.openlocfilehash: 128d1c397376da7667b244e73efa2f1b77b56d37
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834817"
---
# <a name="useragent-table"></a>Таблица UserAgent
 
Таблица UserAgent — это вспомогательная таблица, в которой хранится список различных агентов пользователей, которые участвовали в сеансах, записанных в базе данных. Каждая запись в таблице представляет одного агента пользователя
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primary  <br/> |Уникальное число, идентифицирующее этот агент пользователя.  <br/> |
|**UserAgent** <br/> |nvarchar (256)  <br/> |Уникальные  <br/> |Строка Агента пользователя.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 — сервер-посредник.  <br/> 2 — сервер A/V Conferencing Server.  <br/> 4 — Skype для бизнеса.  <br/> 8 — ip-Телефон.  <br/> 16 — это консоль live meeting.  <br/> 32 — это средство проверки развертывания (DVT).  <br/> 64 — Skype для бизнеса Server компьютеров Macintosh.  <br/> 128 — Skype для бизнеса Server Attendant.  <br/> 256 — оповещение для конференц-связи службы.  <br/> 512 — это автосекретарь.  <br/> 1024 — это приложение Группы реагирования.  <br/> 2048 — это внешний голосовой контроль.  <br/> |
   

