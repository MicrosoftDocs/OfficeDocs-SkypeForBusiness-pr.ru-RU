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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: Таблица Еджесерверс является вспомогательной таблицей. Каждая запись содержит сведения о одном пограничном сервере, который участвует в звонках, которые содержат записи в базе данных.
ms.openlocfilehash: 7a1621e3416b6cff48c430e7bc2e45057ecb3e14
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815267"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a>Таблица Еджесерверс в Skype для бизнеса Server 2015
 
Таблица Еджесерверс является вспомогательной таблицей. Каждая запись содержит сведения о одном пограничном сервере, который участвует в звонках, которые содержат записи в базе данных.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**еджесерверид** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот сервер пограничного сервера.  <br/> |
|**Пограничный сервер** <br/> |nvarchar(256)  <br/> | <br/> |Имя пограничного сервера.  <br/> |
   

