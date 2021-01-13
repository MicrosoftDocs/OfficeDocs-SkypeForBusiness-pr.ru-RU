---
title: Таблица Gateways в Skype для бизнеса Server 2015
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
description: Таблица Gateways является вспомогательной. В каждой записи хранится информация об одном шлюзе, который участвует в вызовах телефонной сети общего звонков (PSTN), в базе данных которых есть записи.
ms.openlocfilehash: e945e5464093eb0eb58965fa1ef8a734ea0afa75
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821589"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Таблица Gateways в Skype для бизнеса Server 2015
 
Таблица Gateways является вспомогательной. В каждой записи хранится информация об одном шлюзе, который участвует в вызовах телефонной сети общего звонков (PSTN), в базе данных которых есть записи.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот шлюз.  <br/> |
|**Шлюз** <br/> |nvarchar(256)  <br/> | <br/> |Имя шлюза.  <br/> |
   

