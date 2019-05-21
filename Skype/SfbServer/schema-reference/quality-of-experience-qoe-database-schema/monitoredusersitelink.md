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
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: Таблица Мониторедусерсителинк является вспомогательной таблицей. Каждая запись представляет одну связь между двумя сайтами пользователей.
ms.openlocfilehash: 789c1a721e1a8c204ff6e214f419de77d1b7f7bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294854"
---
# <a name="monitoredusersitelink-table"></a>Таблица MonitoredUserSiteLink
 
Таблица Мониторедусерсителинк является вспомогательной таблицей. Каждая запись представляет одну связь между двумя сайтами пользователей.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |целое  <br/> |Основной, внешний  <br/> |На которую ссылается [Таблица усерсите](usersite.md).  <br/> |
|**UserSite2Key** <br/> |целое  <br/> |Основной, внешний  <br/> |Ссылка из [таблицы усерсите](usersite.md).  <br/> |
   

