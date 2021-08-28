---
title: Получить родительских элементов
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: Сводка. Сведения об операции Get Item Ancestors, которая является частью службы элементов. Служба элементов является частью API репозиториев для панели мониторинга качества вызовов. Панель мониторинга качества вызовов — это средство для Skype для бизнеса Server.
ms.openlocfilehash: f6977d1519b487003460e8d4eb5300fe4d98e84f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58633623"
---
# <a name="get-item-ancestors"></a>Получить родительских элементов
 
**Сводка:** Узнайте об операции Get Item Ancestors, которая входит в службу item. Служба элементов является частью API репозиториев для панели мониторинга качества вызовов. Панель мониторинга качества вызовов — это средство для Skype для бизнеса Server.
  
Операция Get Item Ancestors является частью службы элементов в API репозитория для панели мониторинга качества вызовов.
  
## <a name="get-item-ancestors"></a>Получить родительских элементов

Get Item Ancestors returns a specific items ancestors from the repository.
  

|**Способ**|**Запрос URI**|**ВЕРСИЯ HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/itemAncestors/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Параметры URI** . Нет.
  
 **Заглавные заглавные** запросы — дополнительных загонах не будет.
  
 **Тело запроса** . Нет.
  
 **Ответ.** Ответ включает код состояния HTTP и набор заглавных заглавных ответов.
  
 **Код состояния** — успешная операция возвращает код состояния 200 (OK). Если указанный код пользователя не найден, он возвращает код состояния 404 (Не найден).
  
 **Заготчики** ответа . Дополнительные заготчики не имеются.
  
 **Тело ответа** . Ниже приведен пример полезной нагрузки ответа в JSON.
  
```json
[{
"item1": 1653,
"item2": 0,
"item3": "Audio Streams Monthly Trend"
},
{
"item1": 1652,
"item2": 1,
"item3": "All Audio Streams"
}]
```

 *Item1*  — ID элемента.
  
 *Item2*  . Глубина — это расстояние от элемента. 0 является непосредственным родителем.
  
 *Item3*  — заголовок элемента.
  

