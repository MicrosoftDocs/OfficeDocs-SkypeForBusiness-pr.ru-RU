---
title: Таблица Еджесерверс в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: Таблица Еджесерверс является вспомогательной таблицей. Каждая запись содержит сведения о одном пограничном сервере, который участвует в звонках, которые содержат записи в базе данных.
ms.openlocfilehash: a78acd3b6297bbef3348ef87047c8cb7f0893231
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296345"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a>Таблица Еджесерверс в Skype для бизнеса Server 2015
 
Таблица Еджесерверс является вспомогательной таблицей. Каждая запись содержит сведения о одном пограничном сервере, который участвует в звонках, которые содержат записи в базе данных.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Еджесерверид** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот сервер пограничного сервера.  <br/> |
|**Пограничный сервер** <br/> |nvarchar(256)  <br/> | <br/> |Имя пограничного сервера.  <br/> |
   

