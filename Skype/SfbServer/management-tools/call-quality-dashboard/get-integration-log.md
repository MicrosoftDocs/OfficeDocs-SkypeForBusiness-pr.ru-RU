---
title: Получение журнала интеграции
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
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: Сводка. Сведения об операции "Получить журнал интеграции", которая входит в API данных для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: 69827fa9f3fd3f56843a41867b029a071799ba66
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832599"
---
# <a name="get-integration-log"></a>Получение журнала интеграции
 
**Сводка:** Сведения об операции "Получить журнал интеграции", которая входит в API данных для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
  
Операция "Получить журнал интеграции" является частью API данных для панели мониторинга качества вызовов
  
## <a name="get-integration-log"></a>Получение журнала интеграции

Операция "Получить журнал интеграции" возвращает список записей журнала, описывающих действия в обработке куба QoE.
  
По умолчанию эта операция отключена из соображений безопасности. При отключке возвращается пустая строка. Чтобы включить эту операцию, администраторам необходимо настроить web.config для хост-веб-приложения API данных.
  

|Метод|**URI запроса**|**Версия HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **Параметры URI** — нет.
  
 **Request Headers** - No additional headers.
  
 **Тело запроса** — нет.
  
 **Ответ.** Ответ включает код состояния HTTP и набор загодеров отклика.
  
 **Код состояния** — успешная операция возвращает код состояния 200 (OK).
  
 **Response Headers** - No additional headers.
  
 **Тело ответа** . Ниже приведен пример структуры записей журнала.
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


