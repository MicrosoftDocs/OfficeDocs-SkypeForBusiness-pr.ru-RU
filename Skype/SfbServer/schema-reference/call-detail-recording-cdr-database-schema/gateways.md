---
title: Таблица шлюзы в Скайп для Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: В таблице шлюзов представляет собой вспомогательную таблицу. Каждая запись сохранение информации о один шлюз, задействованных в телефонной сети (общего пользования PSTN) вызовы с записями в базе данных.
ms.openlocfilehash: e9592b227e8ccff6829748230abd3e8ddb8edb75
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Таблица шлюзы в Скайп для Business Server 2015
 
В таблице шлюзов представляет собой вспомогательную таблицу. Каждая запись сохранение информации о один шлюз, задействованных в телефонной сети (общего пользования PSTN) вызовы с записями в базе данных.
  
|**Столбец**|**Тип данных**|**Ключ или индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот шлюз.  <br/> |
|**Шлюз** <br/> |nvarchar(256)  <br/> | <br/> |Имя шлюза.  <br/> |
   

