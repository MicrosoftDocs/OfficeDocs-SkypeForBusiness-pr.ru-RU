---
title: Таблица MonitoredUserSiteLink
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: a5a8802f3821fff3d08c2365d4f76655b5824606
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610576"
---
# <a name="monitoredusersitelink-table"></a>Таблица MonitoredUserSiteLink
 
Таблица MonitoredUserSiteLink является таблицей поддержки. Каждая запись представляет одну связь между двумя сайтами пользователей.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Основной, Внешний  <br/> |Ссылки из [таблицы UserSite](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Основной, Внешний  <br/> |Справка из [таблицы UserSite.](usersite.md)  <br/> |
   

