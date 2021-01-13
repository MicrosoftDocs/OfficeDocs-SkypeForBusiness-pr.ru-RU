---
title: Получение элемента
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
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: Сводка. Сведения об операции "Получить элемент", которая входит в состав службы элементов. Служба элементов является частью API репозитория для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: 896540c4572fb3991356ce055f01690ed702c6f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832569"
---
# <a name="get-item"></a>Получение элемента
 
**Сводка:** Узнайте об операции "Получить элемент", которая входит в состав службы элементов. Служба элементов является частью API репозитория для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
  
Операция "Получить элемент" является частью службы элементов в API репозитория для панели мониторинга качества вызовов.
  
## <a name="get-item"></a>Получение элемента

Get Item возвращает определенный элемент в репозитории.
  
|**Способ**|**URI запроса**|**Версия HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Параметры URI** — нет.
  
 **Request Headers** - No additional headers.
  
 **Тело запроса** — нет.
  
 **Ответ.** Ответ включает код состояния HTTP и набор загодеров отклика.
  
 **Код состояния** — успешная операция возвращает код состояния 200 (OK). Если указанный код элемента не найден, возвращается код состояния 404 (не найден).
  
 **Response Headers** - No additional headers.
  
 **Тело ответа.** Ниже приведен пример полезной нагрузки ответа в JSON.
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 *itemId*  — ИД элемента.
  
 *userId*  — ИД пользователя, которому принадлежит этот элемент.
  
 *content*  — содержимое для конкретного приложения.
  
 *type*  — тип контента. Это поле устанавливается приложениями.
  
 *subItemIds*  — ИД в субподрядных элементов, если они есть. Это кратковременная операция Get Sub-Items для сохранения вызова. Приложения также могут получить те же сведения с помощью операции Get Sub-Items.
  

