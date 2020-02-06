---
title: Таблица UserSite
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: Таблица Усерсите является вспомогательной таблицей. Каждая запись соответствует одному сайту пользователя, определенному в параметрах конфигурации сети.
ms.openlocfilehash: e1d6c4ddc3a756f2e5df0713d6abe1cb7b61295f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805007"
---
# <a name="usersite-table"></a>Таблица UserSite
 
Таблица Усерсите является вспомогательной таблицей. Каждая запись соответствует одному сайту пользователя, определенному в параметрах конфигурации сети.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**усерситекэй** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий сайт пользователя.  <br/> |
|**усерситенаме** <br/> |nvarchar(128  <br/> |Повторя  <br/> |Имя сайта пользователя.  <br/> |
|**регионкэй** <br/> |целое  <br/> |Другом  <br/> |Ссылка на из [таблицы Region](region.md).  <br/> |
   

