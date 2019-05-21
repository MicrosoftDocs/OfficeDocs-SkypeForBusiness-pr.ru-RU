---
title: Таблица IP-адреса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: В таблице IPAddress IP-адреса сопоставляются с уникальными идентификаторами IP-адресов, которые используются в базе данных качества обслуживания. Эта таблица введена в Microsoft Lync Server 2013.
ms.openlocfilehash: 74d74636b7183d1369db85c363997460a434d8f3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294924"
---
# <a name="ipaddress-table"></a>Таблица IP-адреса
 
В таблице IPAddress IP-адреса сопоставляются с уникальными идентификаторами IP-адресов, которые используются в базе данных качества обслуживания. Эта таблица введена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Ипаддресскэй** <br/> |целое  <br/> |Primary  <br/> |Уникальный идентификатор указанного IP-адреса.  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |Повторя  <br/> |Уникальный IP-адрес (например, 189.168.1.1), сопоставляемый с Ипаддресскэй. Это может быть либо IPv4, либо IPv6-адрес.  <br/> |
   

