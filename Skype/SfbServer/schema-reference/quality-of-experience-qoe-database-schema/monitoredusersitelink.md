---
title: Таблица MonitoredUserSiteLink
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: Таблица Мониторедусерсителинк является вспомогательной таблицей. Каждая запись представляет одну связь между двумя сайтами пользователей.
ms.openlocfilehash: 2cf229947da143fb01b3009020cfa432a4b558a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807797"
---
# <a name="monitoredusersitelink-table"></a>Таблица MonitoredUserSiteLink
 
Таблица Мониторедусерсителинк является вспомогательной таблицей. Каждая запись представляет одну связь между двумя сайтами пользователей.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |целое  <br/> |Основной, внешний  <br/> |На которую ссылается [Таблица усерсите](usersite.md).  <br/> |
|**UserSite2Key** <br/> |целое  <br/> |Основной, внешний  <br/> |Ссылка из [таблицы усерсите](usersite.md).  <br/> |
   

