---
title: Получение куба
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
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: Сводка. Сведения об операции "Получить куб", которая входит в API данных для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: a3527f21bc1751c23bba088ae06c3e6702cb8c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832629"
---
# <a name="get-cube"></a>Получение куба
 
**Сводка:** Сведения об операции "Получить куб", которая является частью API данных для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
  
Операция "Получить куб" является частью API данных для панели мониторинга качества вызовов.
  
## <a name="get-cube"></a>Получение куба

Операция "Получить куб" возвращает список доступных измерений и измерений.
  

|**Способ**|**URI запроса**|**Версия HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoEDataService/CubeStructure  <br/> |HTTP/1.1  <br/> |
   
 **Параметры URI** — нет.
  
 **Request Headers** - No additional headers.
  
 **Тело запроса** — нет.
  
 **Ответ.** Ответ включает код состояния HTTP и набор загодеров отклика.
  
 **Код состояния** : успешная операция возвращает код состояния 200 (OK).
  
 **Response Headers** - No additional headers.
  
 **Тело ответа.** Ниже приведен пример полезной нагрузки ответа в JSON.
  
> [!NOTE]
> В этом примере показаны только первые два элемента каждой группы элементов Куба. 
  
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

 *KPIs*  — зарезервировано. Раздел ХП полезной нагрузки запроса позволяет операции "Выполнить запрос" возвращать значения для ХП, определенных в кубе. В кубе QoE еще нет ХП.
  
 *Измерения —*  список измерений, которые могут использоваться в разделах "Фильтры и измерения" полезной нагрузки запроса для операции "Выполнить запрос". Чтобы использовать измерение в выражении фильтра, необходимо указать член измерения, который можно получить с помощью операции Get Dimension Members.
  
 *Измерения —*  список показателей, которые могут использоваться в разделе "Измерения" полезной нагрузки запроса для выполнения операции запроса.
  

