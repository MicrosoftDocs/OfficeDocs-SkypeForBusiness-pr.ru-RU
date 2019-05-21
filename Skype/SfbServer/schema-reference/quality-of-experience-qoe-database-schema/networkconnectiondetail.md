---
title: Таблица Нетворкконнектиондетаил
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: Таблица Нетворкконнектиондетаил сопоставляет типы сетевых подключений с идентификаторами сетевых подключений, используемыми в базе данных качества обслуживания. Эта таблица введена в Microsoft Lync Server 2013.
ms.openlocfilehash: c13725e7df8a164766faa6847fc8097a24a9df53
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294819"
---
# <a name="networkconnectiondetail-table"></a>Таблица Нетворкконнектиондетаил
 
Таблица Нетворкконнектиондетаил сопоставляет типы сетевых подключений с идентификаторами сетевых подключений, используемыми в базе данных качества обслуживания. Эта таблица введена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Нетворкконнектиондетаилкэй** <br/> |tinyint  <br/> |Primary  <br/> |Уникальный идентификатор типа сетевого подключения.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar (256)  <br/> |Повторя  <br/> |Тип сетевого подключения, соответствующий Нетворкконнектиондетаилкэй. Допустимые значения:  <br/> 0--проводное подключение  <br/> 1--WiFi  <br/> 2--Ethernet  <br/> 3--Мобилебб  <br/> 4 – другие  <br/> 5--туннель  <br/> |
   

