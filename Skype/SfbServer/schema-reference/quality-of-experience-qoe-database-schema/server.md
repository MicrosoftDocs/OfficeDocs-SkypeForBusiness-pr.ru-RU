---
title: Таблица Servers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: Серверная таблица является вспомогательной таблицей. Каждая запись представляет один сервер.
ms.openlocfilehash: e57bb96fd715d67a5b6676a2399dc520f08bac96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41806137"
---
# <a name="server-table"></a>Таблица Servers
 
Серверная таблица является вспомогательной таблицей. Каждая запись представляет один сервер. 
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**серверкэй** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий сервер.  <br/> |
|**фкднорип** <br/> |nvarchar(256)  <br/> |индекса  <br/> |Строка MAC-адреса.  <br/> |
|**ServerType** <br/> |целое  <br/> |Другом  <br/> |1: сервер исправлений  <br/> 2: Server16394 конференции/V-service32769: шлюз  <br/> |
|**пулнаме** <br/> |nvarchar (512)  <br/> ||Группа, к которой принадлежит сервер. Применимо только для сервера конференц-связи A/V.  <br/> |
|**некступдатетс** <br/> |datetime  <br/> ||Только для внутреннего использования.  <br/> |
   

