---
title: Таблица IPAddress
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
ms.openlocfilehash: 6372d46b69046f944ba33d4deff6d29e923a94cb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="ipaddress-table"></a>Таблица IPAddress
 
Таблица IPAddress сопоставляет IP-адресов уникальный идентификаторами IP-адресов, используемыми в базе данных качества взаимодействия. Эта таблица была введена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Ключ или индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |целое  <br/> |Primary  <br/> |Уникальный идентификатор для указанного IP-адреса.  <br/> |
|**IP-адрес** <br/> |varchar(50)  <br/> |Уникальный  <br/> |Уникальный IP-адрес (например, 189.168.1.1), который соответствует идентификатору IpAddressKey. Это может быть IPv4 или IPv6-адрес.  <br/> |
   

