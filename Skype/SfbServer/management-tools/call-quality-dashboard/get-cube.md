---
title: Получение куба
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Сводка: Сведения о операцию получения куб, который является частью API данных для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server.'
ms.openlocfilehash: 3d6d1ceecb330219bdc563ca126bb13c49d1902b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886882"
---
# <a name="get-cube"></a>Получение куба
 
**Сводка:** Узнайте о операцию получения куб, который является частью API данных для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Скайп для Business Server.
  
Операция получения куба является частью API данных для панели мониторинга качества звонков.
  
## <a name="get-cube"></a>Получение куба

Операция куба Get возвращает список доступных измерений и измерения.
  

|**Метод**|**URI запроса**|**Версия HTTP**|
|:-----|:-----|:-----|
|Получить  <br/> |https://\<портала\>/QoEDataService/CubeStructure  <br/> |HTTP/1.1  <br/> |
   
 **Параметры URI** — нет.
  
 **Заголовки запроса** — без дополнительных заголовков.
  
 **Текст запроса** — нет.
  
 **Ответа** - ответ включает код состояния HTTP и набор заголовков ответов.
  
 **Код состояния** - успешные операции возвращает код состояния 200 (ОК).
  
 **Заголовки ответа** — без дополнительных заголовков.
  
 **Тело ответа** - ниже приведен пример полезные данные ответа в формате JSON в.
  
> [!NOTE]
> В этом примере показано только первые два элемента каждой группы элементов куба. 
  
```
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

 *Ключевые показатели эффективности* — зарезервировано. Ключевые показатели эффективности части полезных данных запроса позволяет выполнить запрос операции для возврата значения для ключевых индикаторов производительности, определенных в кубе. Не ключевые показатели эффективности еще не существует в кубе качества взаимодействия.
  
 *Измерения* - список измерений, которые могут быть использованы в разделах фильтры и размеры полезных данных запроса для операции выполнить запрос. Чтобы использовать измерения в выражение фильтра, необходимо указать элемент измерения, который можно получить с помощью операции получения элементов измерения.
  
 *Измерения* — список измерений, которые могут быть использованы в разделе измерения полезных данных запроса для операции выполнить запрос.
  

