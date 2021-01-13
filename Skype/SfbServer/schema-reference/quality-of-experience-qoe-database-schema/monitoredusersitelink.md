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
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: Таблица MonitoredUserSiteLink является таблицей поддержки. Каждая запись представляет одну связь между двумя сайтами пользователей.
ms.openlocfilehash: 88b4d385f3c96dc93a519274c584e1f99584982f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806359"
---
# <a name="monitoredusersitelink-table"></a>Таблица MonitoredUserSiteLink
 
Таблица MonitoredUserSiteLink является таблицей поддержки. Каждая запись представляет одну связь между двумя сайтами пользователей.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Основной, Внешний  <br/> |Ссылка из [таблицы UserSite.](usersite.md)  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Основной, Внешний  <br/> |Ссылка из [таблицы UserSite.](usersite.md)  <br/> |
   

