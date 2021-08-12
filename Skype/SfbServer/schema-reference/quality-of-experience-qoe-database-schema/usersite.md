---
title: Таблица UserSite
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: Таблица UserSite — это вспомогательная таблица. Каждая запись представляет один сайт пользователя, определенный в параметре конфигурации сети.
ms.openlocfilehash: 01ab76218040d37176355d62768c6a8b8f4b7336d22ce7263c61ac9fc8c289ed
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314335"
---
# <a name="usersite-table"></a>Таблица UserSite
 
Таблица UserSite — это вспомогательная таблица. Каждая запись представляет один сайт пользователя, определенный в параметре конфигурации сети.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий сайт пользователя.  <br/> |
|**UserSiteName** <br/> |nvarchar (128)  <br/> |Уникальные  <br/> |Имя сайта пользователя.  <br/> |
|**RegionKey** <br/> |int  <br/> |Foreign  <br/> |Ссылки из [таблицы Регион](region.md).  <br/> |
   

