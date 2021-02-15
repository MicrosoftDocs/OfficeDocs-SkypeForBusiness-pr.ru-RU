---
title: Получение параметра пользователя
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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: Сводка. Сведения об операции "Получить параметр пользователя", которая входит в состав службы параметров пользователей. Служба параметров пользователя является частью API репозитория для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: 82632f5de7ae215d6f34d9f0b39e500fb713a1be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832489"
---
# <a name="get-user-setting"></a>Получение параметра пользователя
 
**Сводка:** Узнайте об операции "Получить параметр пользователя", которая входит в состав службы параметров пользователей. Служба параметров пользователя является частью API репозитория для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
  
Операция "Получить параметр пользователя" является частью службы пользовательских параметров в API репозитория для панели мониторинга качества вызовов.
  
## <a name="get-user-setting"></a>Получение параметра пользователя

При этом возвращается один параметр пользователя.
  

|**Способ**|**URI запроса**|**Версия HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting/{key}  <br/> |HTTP/1.1  <br/> |
   
 **Параметры URI** — нет.
  
 **Request Headers** - No additional headers.
  
 **Тело запроса** — нет.
  
 **Ответ.** Ответ включает код состояния HTTP и набор загодеров отклика.
  
 **Код состояния** — успешная операция возвращает код состояния 200 (OK).
  
 **Response Headers** - No additional headers.
  
 **Тело ответа.** Ниже приведен пример полезной нагрузки ответа в JSON.
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 *userId*  — ИД пользователя.
  
 *key*  — ключ параметра.
  
 *value*  — значение параметра.
  

