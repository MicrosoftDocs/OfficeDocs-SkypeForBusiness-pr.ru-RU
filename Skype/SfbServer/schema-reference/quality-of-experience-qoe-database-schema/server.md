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
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: Серверная таблица является вспомогательной таблицей. Каждая запись представляет один сервер.
ms.openlocfilehash: 93ba62c262b95b46b76cd445be04a0bc53c5a960
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294714"
---
# <a name="server-table"></a>Таблица Servers
 
Серверная таблица является вспомогательной таблицей. Каждая запись представляет один сервер. 
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Серверкэй** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий сервер.  <br/> |
|**Фкднорип** <br/> |nvarchar(256)  <br/> |индекса  <br/> |Строка MAC-адреса.  <br/> |
|**ServerType** <br/> |целое  <br/> |Другом  <br/> |1: сервер исправлений  <br/> 2: Server16394 конференции/V-service32769: шлюз  <br/> |
|**Пулнаме** <br/> |nvarchar (512)  <br/> ||Группа, к которой принадлежит сервер. Применимо только для сервера конференц-связи A/V.  <br/> |
|**Некступдатетс** <br/> |datetime  <br/> ||Только для внутреннего использования.  <br/> |
   

