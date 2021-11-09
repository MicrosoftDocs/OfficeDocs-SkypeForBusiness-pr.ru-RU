---
title: Таблица NetworkConnectionDetail
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: В таблице NetworkConnectionDetail сопоставляются типы сетевых подключений с идентификаторами сетевых подключений, используемых в базе данных качества взаимодействия. Эта таблица была представлена в Microsoft Lync Server 2013.
ms.openlocfilehash: 6d39d9e8432a20102d42cea649a51596ce2c1762
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833193"
---
# <a name="networkconnectiondetail-table"></a>Таблица NetworkConnectionDetail
 
В таблице NetworkConnectionDetail сопоставляются типы сетевых подключений с идентификаторами сетевых подключений, используемых в базе данных качества взаимодействия. Эта таблица была представлена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primary  <br/> |Уникальный идентификатор типа сетевого подключения.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar (256)  <br/> |Уникальные  <br/> |Тип сетевого подключения, который соответствует значению NetworkConnectionDetailKey. Допускаются следующие значения:  <br/> 0 — проводное  <br/> 1 — беспроводное  <br/> 2 — Ethernet  <br/> 3 -- MobileBB  <br/> 4 . Другие  <br/> 5 -- Tunnel  <br/> |
   

