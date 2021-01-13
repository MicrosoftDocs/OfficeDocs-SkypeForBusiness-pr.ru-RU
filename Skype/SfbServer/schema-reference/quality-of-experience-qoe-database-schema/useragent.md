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
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: Таблица UserAgent — это вспомогательная таблица, в которой хранится список различных агентов пользователей, которые участвовали в сеансах, записанных в базе данных. Каждая запись в таблице представляет одного агента пользователя
ms.openlocfilehash: a1d0e647ff78d409555988a27592228fac2643be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799939"
---
# <a name="useragent-table"></a>Таблица UserAgent
 
Таблица UserAgent — это вспомогательная таблица, в которой хранится список различных агентов пользователей, которые участвовали в сеансах, записанных в базе данных. Каждая запись в таблице представляет одного агента пользователя
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primary  <br/> |Уникальное число, идентифицирующее этот агент пользователя.  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |Уникальные  <br/> |Строка агента пользователя.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 — сервер-посредник.  <br/> 2 — сервер A/V Conferencing Server.  <br/> 4 — Skype для бизнеса.  <br/> 8 — IP-телефон.  <br/> 16 — консоль Live Meeting.  <br/> 32 — это средство проверки развертывания (DVT).  <br/> 64 — Skype для бизнеса Server на компьютерах Macintosh.  <br/> 128 — помощник skype для бизнеса Server.  <br/> 256 — служба объявлений для conferencing.  <br/> 512 — это автосекретарь.  <br/> 1024 — приложение группы ответа.  <br/> 2048 — это внешний голосовой контроль.  <br/> |
   

