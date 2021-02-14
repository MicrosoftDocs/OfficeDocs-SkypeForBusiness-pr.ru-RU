---
title: Таблица NetworkConnectionDetail
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: В таблице NetworkConnectionDetail сопоставляются типы сетевых подключений с идентификаторами сетевых подключений, используемых в базе данных качества взаимодействия. Эта таблица была представлена в Microsoft Lync Server 2013.
ms.openlocfilehash: 2e03e7935370e71a8070ed1882f61ac5480f312e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806309"
---
# <a name="networkconnectiondetail-table"></a>Таблица NetworkConnectionDetail
 
В таблице NetworkConnectionDetail сопоставляются типы сетевых подключений с идентификаторами сетевых подключений, используемых в базе данных качества взаимодействия. Эта таблица была представлена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primary  <br/> |Уникальный идентификатор типа сетевого подключения.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |Уникальные  <br/> |Тип сетевого подключения, который соответствует значению NetworkConnectionDetailKey. Допускаются следующие значения:  <br/> 0 — проводное  <br/> 1 — беспроводное  <br/> 2 — Ethernet  <br/> 3 — MobileBB  <br/> 4 — другие  <br/> 5 — туннель  <br/> |
   

