---
title: Получение вложенных элементов
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
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: Сводка. Сведения об операции get Sub-Items, которая входит в состав службы элементов. Служба элементов является частью API репозитория для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: defb0b898c5101513cbb4f6da4382a8bb43bce6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832509"
---
# <a name="get-sub-items"></a>Получение вложенных элементов
 
**Сводка:** Узнайте об операции get Sub-Items, которая входит в состав службы элементов. Служба элементов является частью API репозитория для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
  
Операция Get Sub-Items является частью службы элементов в API репозитория для панели мониторинга качества вызовов.
  
## <a name="get-sub-items"></a>Получение вложенных элементов

При Sub-Items возвращается подустанавли определенного элемента.
  

|**Способ**|**URI запроса**|**Версия HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}/subitem  <br/> |HTTP/1.1  <br/> |
   
 **Параметры URI** — нет.
  
 **Request Headers** - No additional headers.
  
 **Тело запроса** — нет.
  
 **Ответ.** Ответ включает код состояния HTTP и набор загодеров отклика.
  
 **Код состояния** : успешная операция возвращает код состояния 200 (OK). Если указанный код пользователя не найден, возвращается код состояния 404 (не найден).
  
 **Response Headers** - No additional headers.
  
 **Тело ответа.** Ниже приведен пример полезной нагрузки ответа в JSON.
  
> [!NOTE]
> Возвращается массив объекта Item. 
  
```json
[{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1710,
"userId": 0,
"type": "json"
}]
```

Объект Item, возвращенный Sub-Items, содержит только следующие три поля. 
  
 *itemId*  — ИД элемента.
  
 *userId*  — ИД пользователя, которому принадлежит этот элемент.
  
 *type*  — тип контента. Это поле устанавливается приложениями.
  
> [!NOTE]
>  `Content` поля не включаются в ответ, чтобы уменьшить объем данных, передаваемых `subItems` по сети.
  

