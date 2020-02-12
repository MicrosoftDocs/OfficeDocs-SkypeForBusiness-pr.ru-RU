---
title: Получение куба
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Сводка: сведения о операции "получить куб", которая входит в API данных для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.'
ms.openlocfilehash: 1d8327439d79e7d02182dc7195bc0052bf6c923c
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888828"
---
# <a name="get-cube"></a>Получение куба
 
**Сводка:** Сведения о выполнении операции "получить куб", которая входит в API данных для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.
  
Операция "получить куб" входит в API данных для панели мониторинга качества звонков.
  
## <a name="get-cube"></a>Получение куба

Операция "получить куб" возвращает список доступных размеров и измерений.
  

|**Способов**|**URI запроса**|**Версия HTTP**|
|:-----|:-----|:-----|
|Получить  <br/> |/Коедатасервице/кубеструктуре\<портала\>HTTPS://  <br/> |HTTP/1.1  <br/> |
   
 **Параметры универсального кода ресурса** (None).
  
 **Заголовки запроса** — без дополнительных заголовков.
  
 **Запросить текст** -None.
  
 **Response (ответ** ) — ответ включает код состояния HTTP и набор заголовков ответа.
  
 **Код состояния** — успешная операция возвращает код состояния 200 (ОК).
  
 **Заголовки ответа** — без дополнительных заголовков.
  
 **Тело ответа** — ниже показан пример полезных данных ответа в JSON.
  
> [!NOTE]
> В этом примере показаны первые два элемента каждой группы элементов куба. 
  
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

 *Ключевые показатели эффективности* — зарезервированы. Раздел КИП в полезных данных запроса допускает операцию выполнения запроса, возвращающую значения для ключевых показателей эффективности, определенных в Кубе. В Кубе QoE пока нет ключевых индикаторов производительности.
  
 *Dimensions* — список измерений, которые можно использовать в разделах "фильтры" и "измерения" полезных данных запроса для выполнения операции запроса. Чтобы использовать измерение в выражении фильтра, необходимо указать элемент измерения, который можно получить с помощью операции "получить элементы измерения".
  
 *Измерения* — список измерений, которые можно использовать в разделе "измерения" полезных данных запроса для выполнения операции запроса.
  

