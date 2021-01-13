---
title: Получение элементов измерений
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: Сводка. Сведения об операции get Dimension Members. Операция Get Dimension Members является частью API данных для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: ffec3b02a3c876a003adb679a28b0e8f2edb91c2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832639"
---
# <a name="get-dimension-members"></a>Получение элементов измерений
 
**Сводка:** Узнайте об операции "Получить члены измерения". Операция Get Dimension Members является частью API данных для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
  
Операция Get Dimension Members является частью API данных для панели мониторинга качества вызовов.
  
## <a name="get-dimension-members"></a>Получение элементов измерений

Операция "Получить члены измерения" возвращает список членов определенного измерения. Кроме того, это позволяет фильтровать список участников и получать подмножество, чтобы сократить затраты на передачу данных по проводной сети.
  

|**Способ**|**URI запроса**|**Версия HTTP**|
|:-----|:-----|:-----|
|POST  <br/> |https:// \<portal\> /QoEDataService/DimensionMembers  <br/> |HTTP/1.1  <br/> |
   
 **Параметры URI** — нет.
  
 **Request Headers** - No additional headers.
  
 **Тело запроса** — содержит имя измерения, для которого нужны члены. Кроме того, вы можете указать максимальное количество возвращаемого числа членов, а также указать фильтрацию, чтобы ограничить возвращаемую часть.
  
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

 **Ответ.** Ответ включает код состояния HTTP и набор загодеров отклика.
  
 **Код состояния** — успешная операция возвращает код состояния 200 (OK).
  
 **Response Headers** - No additional headers.
  
 **Тело ответа** — ниже приведен пример полезной нагрузки ответа в JSON в ответ на запрос "[StartDate]. Измерение [Month]".
  
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
