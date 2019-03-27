---
title: Таблица IPAddress
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: Таблица IPAddress сопоставляет IP-адресов уникальный идентификаторами IP-адресов, используемыми в базе данных качества взаимодействия. Эта таблица была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: b118d85eff7c0f8e355a43e354f97de3c66da7d0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876960"
---
# <a name="ipaddress-table"></a>Таблица IPAddress
 
Таблица IPAddress сопоставляет IP-адресов уникальный идентификаторами IP-адресов, используемыми в базе данных качества взаимодействия. Эта таблица была введена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |целое  <br/> |Primary  <br/> |Уникальный идентификатор для указанного IP-адреса.  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |Уникальный  <br/> |Уникальный IP-адрес (например, 189.168.1.1), который соответствует идентификатору IpAddressKey. Это может быть IPv4 или IPv6-адрес.  <br/> |
   

