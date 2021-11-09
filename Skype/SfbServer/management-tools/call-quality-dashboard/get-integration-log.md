---
title: Получение журнала интеграции
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: cb995e4b7d955514c64cfab772b19e100669d078
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834167"
---
# <a name="get-integration-log"></a>Получение журнала интеграции
 
**Сводка:** Узнайте об операции Get Integration Log, которая входит в API данных для панели мониторинга качества вызовов. Панель мониторинга качества вызовов — это средство для Skype для бизнеса Server.
  
Операция Журнал интеграции get является частью API данных для панели мониторинга качества вызовов
  
## <a name="get-integration-log"></a>Получение журнала интеграции

Операция Журнала интеграции возвращает список записей журналов, описывающих действия в обработке кубов QoE.
  
Эта операция отключена по умолчанию из соображений безопасности. При отключении возвращается пустая строка. Чтобы включить эту операцию, администраторам необходимо настроить web.config для веб-приложения хост-приложения API данных.
  

|Method|**Запрос URI**|**ВЕРСИЯ HTTP**|
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


