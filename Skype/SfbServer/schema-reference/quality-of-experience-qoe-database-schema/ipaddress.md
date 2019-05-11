---
title: Таблица IPAddress
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: Таблица IPAddress сопоставляет IP-адресов уникальный идентификаторами IP-адресов, используемыми в базе данных качества взаимодействия. Эта таблица была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: d7d3b5f9192c2385836f42f9c430da5b99752892
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920035"
---
# <a name="ipaddress-table"></a>Таблица IPAddress
 
Таблица IPAddress сопоставляет IP-адресов уникальный идентификаторами IP-адресов, используемыми в базе данных качества взаимодействия. Эта таблица была введена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |целое  <br/> |Primary  <br/> |Уникальный идентификатор для указанного IP-адреса.  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |Уникальный  <br/> |Уникальный IP-адрес (например, 189.168.1.1), который соответствует идентификатору IpAddressKey. Это может быть IPv4 или IPv6-адрес.  <br/> |
   

