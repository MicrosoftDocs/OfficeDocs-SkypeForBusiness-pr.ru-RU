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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: Сводка. Сведения об операции Get Integration Log, которая входит в API данных для панели мониторинга качества вызовов. Панель мониторинга качества вызовов — это средство для Skype для бизнеса Server.
ms.openlocfilehash: c4d94497a7ed2b7ca1a9c716ede0eef466b0f1ad
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578773"
---
# <a name="get-integration-log"></a>Получение журнала интеграции
 
**Сводка:** Узнайте об операции Get Integration Log, которая входит в API данных для панели мониторинга качества вызовов. Панель мониторинга качества вызовов — это средство для Skype для бизнеса Server.
  
Операция Журнал интеграции get является частью API данных для панели мониторинга качества вызовов
  
## <a name="get-integration-log"></a>Получение журнала интеграции

Операция Журнала интеграции возвращает список записей журналов, описывающих действия в обработке кубов QoE.
  
Эта операция отключена по умолчанию из соображений безопасности. При отключении возвращается пустая строка. Чтобы включить эту операцию, администраторам необходимо настроить web.config для веб-приложения хост-приложения API данных.
  

|Метод|**Запрос URI**|**ВЕРСИЯ HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **Параметры URI** . Нет.
  
 **Заглавные заглавные** запросы — дополнительных загонах не будет.
  
 **Тело запроса** . Нет.
  
 **Ответ.** Ответ включает код состояния HTTP и набор заглавных заглавных ответов.
  
 **Код состояния** — успешная операция возвращает код состояния 200 (OK).
  
 **Заготчики** ответа . Дополнительные заготчики не имеются.
  
 **Тело отклика** . Ниже приведен пример структуры записей журнала.
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


