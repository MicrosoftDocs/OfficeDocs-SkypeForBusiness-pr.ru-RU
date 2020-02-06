---
title: Таблица шлюзов в Skype для бизнеса Server 2015
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
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: Таблица Gateways является вспомогательной таблицей. Каждая запись содержит сведения об одном шлюзе, который участвует в звонках по коммутируемой телефонной сети (PSTN), которые содержат записи в базе данных.
ms.openlocfilehash: ce85b36d5ad587a096c99ca3f3f496642d3a3dd5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815167"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Таблица шлюзов в Skype для бизнеса Server 2015
 
Таблица Gateways является вспомогательной таблицей. Каждая запись содержит сведения об одном шлюзе, который участвует в звонках по коммутируемой телефонной сети (PSTN), которые содержат записи в базе данных.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**гатевайид** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот шлюз.  <br/> |
|**Шлюз** <br/> |nvarchar(256)  <br/> | <br/> |Имя шлюза.  <br/> |
   

