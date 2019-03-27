---
title: Таблица шлюзы в Скайп для Business Server 2015
ms.reviewer: ''
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
ms.openlocfilehash: 16860e924fb69f1dfe337e05c13d54fb66a8ed81
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899083"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Таблица шлюзы в Скайп для Business Server 2015
 
В таблице шлюзов представляет собой вспомогательную таблицу. Каждая запись сохранение информации о один шлюз, задействованных в телефонной сети (общего пользования PSTN) вызовы с записями в базе данных.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот шлюз.  <br/> |
|**Шлюз** <br/> |nvarchar(256)  <br/> | <br/> |Имя шлюза.  <br/> |
   

