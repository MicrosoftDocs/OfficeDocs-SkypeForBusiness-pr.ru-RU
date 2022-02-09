---
title: Получение куба
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
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: Сводка. Сведения об операции Get Cube, которая входит в API данных для панели мониторинга качества вызовов. Панель мониторинга качества вызовов — это средство для Skype для бизнеса Server.
ms.openlocfilehash: c4ddf8c685d4678791a5b63869e75151acdf401f
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396331"
---
# <a name="get-cube"></a>Получение куба
 
**Сводка:** Узнайте об операции Get Cube, которая входит в API данных для панели мониторинга качества вызовов. Панель мониторинга качества вызовов — это средство для Skype для бизнеса Server.
  
Операция Get Cube является частью API данных для панели мониторинга качества вызовов.
  
## <a name="get-cube"></a>Получение куба

Операция Get Cube возвращает список доступных размеров и измерений.
  

|**Способ**|**Запрос URI**|**ВЕРСИЯ HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |\<portal\>https:///QoEDataService/CubeStructure  <br/> |HTTP/1.1  <br/> |
   
 **Параметры URI** . Нет.
  
 **Заглавные заглавные** запросы — дополнительных загонах не будет.
  
 **Тело запроса** . Нет.
  
 **Ответ** . Ответ включает код состояния HTTP и набор заглавных заглавных ответов.
  
 **Код состояния** — успешная операция возвращает код состояния 200 (OK).
  
 **Заготчики** ответа . Дополнительные заготчики не имеются.
  
 **Тело ответа** . Ниже приведен пример полезной нагрузки ответа в JSON.
  
> [!NOTE]
> В этом примере показаны только первые два элемента каждой группы элементов Cube. 
  
```json
{
"Kpis": [{
"FriendlyName": "Poor Trend Month",
"DataModelName": "[KPIValue].Poor Trend Month",
"Description": null
},
{
"FriendlyName": "Poor Rate Trend Month",
"DataModelName": "[KPIValue].Poor Rate Trend Month",
"Description": null
}],
"Dimensions": [{
"Category": "Access Location Pair",
"Attributes": [{
"FriendlyName": "Location Pair",
"DataModelName": "[Access Location Pair].[Location Pair]",
"Description": "Description of Location Pair"
}]
},
{
"Category": "Audio Bandwidth Est",
"Attributes": [{
"FriendlyName": "Metric",
"DataModelName": "[Audio Bandwidth Est].[Metric]",
"Description": "Description of Metric"
}]
}],
"Measurements": [{
"FriendlyName": "Audio Streams Count",
"DataModelName": "[Measures].[Audio Streams Count]",
"Description": "Description of Audio Streams Count"
},
{
"FriendlyName": "Audio Good Streams JPDR Count",
"DataModelName": "[Measures].[Audio Good Streams JPDR Count]",
"Description": "Description of Audio Good Streams JPDR Count"
}]
}
```

 *KPIs*  — зарезервировано. Раздел KPIs полезной нагрузки запроса позволяет выполнить операцию запроса для возврата значений для KPIs, определенных в кубе. В кубе QoE пока нет KPIs.
  
 *Dimensions*  — список измерений, которые могут использоваться в разделах Filters and Dimensions полезной нагрузки запроса для операции Run Request. Чтобы использовать измерение в выражении фильтра, необходимо указать член измерения, который можно получить с помощью операции Get Dimension Members.
  
 *Измерения*  — список измерений, которые могут использоваться в разделе Измерения полезной нагрузки запроса для выполнения запроса.
  

