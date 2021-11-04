---
title: Таблица шлюзов Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.openlocfilehash: 35b552239d272f47d1f21c0940620dda4e6f075d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777759"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Таблица шлюзов Skype для бизнеса Server 2015 г.
 
Таблица Шлюзы — это вспомогательная таблица. В каждой записи хранится информация об одном шлюзе, который участвует в общедоступных вызовах телефонной сети с переключениями (PSTN), которые имеют записи в базе данных.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот шлюз.  <br/> |
|**Шлюз** <br/> |nvarchar (256)  <br/> | <br/> |Имя шлюза.  <br/> |
   

