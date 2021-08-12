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
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: Таблица Шлюзы — это вспомогательная таблица. В каждой записи хранится информация об одном шлюзе, который участвует в общедоступных вызовах телефонной сети с переключениями (PSTN), которые имеют записи в базе данных.
ms.openlocfilehash: 62bbe3ab802736a50d1fb049a3585cba286ee7ec16907335aa831ab49259b0fc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349671"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Таблица шлюзов Skype для бизнеса Server 2015 г.
 
Таблица Шлюзы — это вспомогательная таблица. В каждой записи хранится информация об одном шлюзе, который участвует в общедоступных вызовах телефонной сети с переключениями (PSTN), которые имеют записи в базе данных.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот шлюз.  <br/> |
|**Шлюз** <br/> |nvarchar (256)  <br/> | <br/> |Имя шлюза.  <br/> |
   

