---
title: Таблица шлюзов Skype для бизнеса Server 2015 г.
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: 'Таблица Шлюзы — это вспомогательная таблица. В каждой записи хранится информация об одном шлюзе, который участвует в общедоступных вызовах телефонной сети с переключениями (PSTN), которые имеют записи в базе данных.'
---

# <a name="gateways-table-in-skype-for-business-server-2015"></a>Таблица шлюзов Skype для бизнеса Server 2015 г.
 
Таблица Шлюзы — это вспомогательная таблица. В каждой записи хранится информация об одном шлюзе, который участвует в общедоступных вызовах телефонной сети с переключениями (PSTN), которые имеют записи в базе данных.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот шлюз.  <br/> |
|**Шлюз** <br/> |nvarchar (256)  <br/> | <br/> |Имя шлюза.  <br/> |
   

