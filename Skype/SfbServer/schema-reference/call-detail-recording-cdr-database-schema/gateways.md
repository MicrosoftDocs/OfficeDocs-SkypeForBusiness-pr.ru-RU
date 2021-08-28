---
title: Таблица шлюзов Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: Таблица Шлюзы — это вспомогательная таблица. В каждой записи хранится информация об одном шлюзе, который участвует в общедоступных вызовах телефонной сети с переключениями (PSTN), которые имеют записи в базе данных.
ms.openlocfilehash: 7d0481def0d8693563b2558f6fa605c12d69ddfe
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601304"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Таблица шлюзов Skype для бизнеса Server 2015 г.
 
Таблица Шлюзы — это вспомогательная таблица. В каждой записи хранится информация об одном шлюзе, который участвует в общедоступных вызовах телефонной сети с переключениями (PSTN), которые имеют записи в базе данных.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот шлюз.  <br/> |
|**Шлюз** <br/> |nvarchar (256)  <br/> | <br/> |Имя шлюза.  <br/> |
   

