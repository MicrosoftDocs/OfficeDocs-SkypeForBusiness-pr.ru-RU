---
title: Таблица MonitoredUserSiteLink
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: Таблица monitoredusersitelink представляет собой вспомогательную таблицу. Каждая запись представляет одну ссылку между двумя узлами пользователя.
ms.openlocfilehash: 8022286289d4acd5fab8ea821c72897d9500597b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874261"
---
# <a name="monitoredusersitelink-table"></a>Таблица MonitoredUserSiteLink
 
Таблица monitoredusersitelink представляет собой вспомогательную таблицу. Каждая запись представляет одну ссылку между двумя узлами пользователя.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |целое  <br/> |Основной, внешний  <br/> |Ссылка из [таблицы UserSite table](usersite.md).  <br/> |
|**UserSite2Key** <br/> |целое  <br/> |Основной, внешний  <br/> |Ссылка из [таблицы UserSite table](usersite.md).  <br/> |
   

