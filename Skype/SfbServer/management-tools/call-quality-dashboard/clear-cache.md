---
title: Очистка кэша
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: Сводка. Сведения о операции Clear Cache, которая входит в API данных для панели мониторинга качества вызовов. Панель мониторинга качества вызовов — это средство для Skype для бизнеса Server.
ms.openlocfilehash: f81e22b11851f4b2121f2444d7ded824f3d8530a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396371"
---
# <a name="clear-cache"></a>Очистка кэша
 
**Сводка:** Сведения о операции Clear Cache, которая входит в API данных для панели мониторинга качества вызовов. Панель мониторинга качества вызовов — это средство для Skype для бизнеса Server.
  
Операция Clear Cache является частью API данных для панели мониторинга качества вызовов.
  
## <a name="clear-cache"></a>Очистка кэша

Операция Clear Cache удаляет кэш на сервере для запросов и данных. Это сбросит кэш, после чего мы будем получать свежие данные из QoE Cube для новых запросов.
  

|**Способ**|**Запрос URI**|**ВЕРСИЯ HTTP**|
|:-----|:-----|:-----|
|POST  <br/> |\<portal\>https:///QoEDataService/ClearCache  <br/> |HTTP/1.1  <br/> |
   
 **Параметры URI** . Нет.
  
 **Заглавные заглавные** запросы — дополнительных загонах не будет.
  
 **Тело запроса** . Нет.
  
 **Ответ** . Ответ включает код состояния HTTP и набор заглавных заглавных ответов.
  
 **Код состояния** — успешная операция возвращает код состояния 200 (OK).
  
 **Заготчики** ответа . Дополнительные заготчики не имеются.
  
 **Тело отклика** . Нет.
  

