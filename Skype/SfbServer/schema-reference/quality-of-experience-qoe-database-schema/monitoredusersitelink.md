---
title: Таблица MonitoredUserSiteLink
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: Таблица MonitoredUserSiteLink является таблицей поддержки. Каждая запись представляет одну связь между двумя сайтами пользователей.
ms.openlocfilehash: 83278162f5e2a499bd68b874ca9eb961c09cf3d3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829763"
---
# <a name="monitoredusersitelink-table"></a>Таблица MonitoredUserSiteLink
 
Таблица MonitoredUserSiteLink является таблицей поддержки. Каждая запись представляет одну связь между двумя сайтами пользователей.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Основной, Внешний  <br/> |Ссылки из [таблицы UserSite](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Основной, Внешний  <br/> |Справка из [таблицы UserSite.](usersite.md)  <br/> |
   

