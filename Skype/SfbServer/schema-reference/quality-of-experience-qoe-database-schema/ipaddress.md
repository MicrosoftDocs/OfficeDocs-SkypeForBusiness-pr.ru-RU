---
title: Таблица IPAddress
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: Таблица IPAddress сопоставляет IP-адреса с уникальными идентификаторами IP-адресов, которые используются в других местах базы данных качества взаимодействия. Эта таблица была представлена в Microsoft Lync Server 2013.
ms.openlocfilehash: 004bdbbe652a275788293bb42cda2e779b698d65
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756178"
---
# <a name="ipaddress-table"></a>Таблица IPAddress
 
Таблица IPAddress сопоставляет IP-адреса с уникальными идентификаторами IP-адресов, которые используются в других местах базы данных качества взаимодействия. Эта таблица была представлена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Primary  <br/> |Уникальный идентификатор указанного IP-адреса.  <br/> |
|**IPAddress** <br/> |varchar (50)  <br/> |Уникальные  <br/> |Уникальный IP-адрес (например, 189.168.1.1), который соответствует идентификатору IPAddressKey. Адрес может быть представлен в формате IPv4 или IPv6.  <br/> |
   

