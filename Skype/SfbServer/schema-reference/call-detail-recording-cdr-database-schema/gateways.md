---
title: Таблица шлюзов Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 27f575163dc90e566013728f646689d883de6ef2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847112"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Таблица шлюзов Skype для бизнеса Server 2015 г.
 
Таблица Шлюзы — это вспомогательная таблица. В каждой записи хранится информация об одном шлюзе, который участвует в общедоступных вызовах телефонной сети с переключениями (PSTN), которые имеют записи в базе данных.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот шлюз.  <br/> |
|**Шлюз** <br/> |nvarchar (256)  <br/> | <br/> |Имя шлюза.  <br/> |
   

