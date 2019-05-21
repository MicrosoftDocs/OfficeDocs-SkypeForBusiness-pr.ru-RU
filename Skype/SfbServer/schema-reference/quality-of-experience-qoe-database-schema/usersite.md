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
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: Таблица Усерсите является вспомогательной таблицей. Каждая запись соответствует одному сайту пользователя, определенному в параметрах конфигурации сети.
ms.openlocfilehash: 21f60afdb1690024f85dc74e11f856642413e6a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294574"
---
# <a name="usersite-table"></a>Таблица UserSite
 
Таблица Усерсите является вспомогательной таблицей. Каждая запись соответствует одному сайту пользователя, определенному в параметрах конфигурации сети.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Усерситекэй** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий сайт пользователя.  <br/> |
|**Усерситенаме** <br/> |nvarchar(128  <br/> |Повторя  <br/> |Имя сайта пользователя.  <br/> |
|**Регионкэй** <br/> |целое  <br/> |Другом  <br/> |Ссылка на из [таблицы Region](region.md).  <br/> |
   

