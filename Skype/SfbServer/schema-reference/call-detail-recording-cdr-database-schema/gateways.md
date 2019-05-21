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
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: Таблица Gateways является вспомогательной таблицей. Каждая запись содержит сведения об одном шлюзе, который участвует в звонках по коммутируемой телефонной сети (PSTN), которые содержат записи в базе данных.
ms.openlocfilehash: 6c827b6661e6dadd0550506f1e593462ec9d8c7a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296184"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Таблица шлюзов в Skype для бизнеса Server 2015
 
Таблица Gateways является вспомогательной таблицей. Каждая запись содержит сведения об одном шлюзе, который участвует в звонках по коммутируемой телефонной сети (PSTN), которые содержат записи в базе данных.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Гатевайид** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот шлюз.  <br/> |
|**Шлюз** <br/> |nvarchar(256)  <br/> | <br/> |Имя шлюза.  <br/> |
   

