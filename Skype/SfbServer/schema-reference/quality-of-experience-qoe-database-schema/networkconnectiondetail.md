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
ms.openlocfilehash: d1aa430f821233fcbf89f166bf76d3d8fadf76a9f7401ce5c9009629fccea70a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306700"
---
# <a name="networkconnectiondetail-table"></a>Таблица NetworkConnectionDetail
 
В таблице NetworkConnectionDetail сопоставляются типы сетевых подключений с идентификаторами сетевых подключений, используемых в базе данных качества взаимодействия. Эта таблица была представлена в Microsoft Lync Server 2013.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primary  <br/> |Уникальный идентификатор типа сетевого подключения.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar (256)  <br/> |Уникальные  <br/> |Тип сетевого подключения, который соответствует значению NetworkConnectionDetailKey. Допускаются следующие значения:  <br/> 0 — проводное  <br/> 1 — беспроводное  <br/> 2 — Ethernet  <br/> 3 -- MobileBB  <br/> 4 . Другие  <br/> 5 -- Tunnel  <br/> |
   

