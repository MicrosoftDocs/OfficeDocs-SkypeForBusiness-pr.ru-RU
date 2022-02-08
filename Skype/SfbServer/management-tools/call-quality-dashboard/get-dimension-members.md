---
title: Получение элементов измерений
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
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: Сводка. Сведения об операции Get Dimension Members. Операция Get Dimension Members является частью API данных для панели мониторинга качества вызовов. Панель мониторинга качества вызовов — это средство для Skype для бизнеса Server.
ms.openlocfilehash: a88ae16a3ccf15a60a36805f475894b657641e6e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391041"
---
# <a name="get-dimension-members"></a>Получение элементов измерений
 
**Сводка:** Узнайте об операции Get Dimension Members. Операция Get Dimension Members является частью API данных для панели мониторинга качества вызовов. Панель мониторинга качества вызовов — это средство для Skype для бизнеса Server.
  
Операция Get Dimension Members является частью API данных для панели мониторинга качества вызовов.
  
## <a name="get-dimension-members"></a>Получение элементов измерений

Операция "Участники измерения" возвращает список участников определенного измерения. Это также дает возможность фильтровать список участников и получать подмножество, чтобы снизить стоимость переноса провода.
  

|**Способ**|**Запрос URI**|**ВЕРСИЯ HTTP**|
|:-----|:-----|:-----|
|POST  <br/> |\<portal\>https:///QoEDataService/DimensionMembers  <br/> |HTTP/1.1  <br/> |
   
 **Параметры URI** . Нет.
  
 **Заглавные заглавные** запросы — дополнительных загонах не будет.
  
 **Тело запроса** . Это содержит имя измерения, для которого нужны участники. Кроме того, максимальное число возвращенных участников, кроме того, вы можете указать некоторые фильтрации, чтобы ограничить возвращенных членов.
  
```json
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 **Ответ** . Ответ включает код состояния HTTP и набор заглавных заглавных ответов.
  
 **Код состояния** — успешная операция возвращает код состояния 200 (OK).
  
 **Заготчики** ответа . Дополнительные заготчики не имеются.
  
 **Тело ответа** . Ниже приведен пример полезной нагрузки ответа в JSON в ответ на запрос "[StartDate]. [Month]".
  
> [!NOTE]
> В списке отображается только небольшая часть списка. 
  
```json
{
"MembersCount": 493,
"Members": [["[1990-01-01T00:00:00]",
"January 1990"],
["[1990-02-01T00:00:00]",
"February 1990"],
["[1990-03-01T00:00:00]",
"March 1990"],
 
    ...
    
["[2030-10-01T00:00:00]",
"October 2030"],
["[2030-11-01T00:00:00]",
"November 2030"],
["[2030-12-01T00:00:00]",
"December 2030"],
["[2031-01-01T00:00:00]",
"January 2031"]]
}
```
