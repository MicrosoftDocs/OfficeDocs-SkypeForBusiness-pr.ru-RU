---
title: Получение пользователей
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
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: Сводка. Сведения об операции "Получить пользователей", которая входит в состав службы пользователей. Служба пользователей является частью API репозитория для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: a830663fc97d8fda727d1ebb008d97407796cc7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832429"
---
# <a name="get-users"></a>Получение пользователей
 
**Сводка:** Узнайте об операции "Получить пользователей", которая входит в состав службы пользователей. Служба пользователей является частью API репозитория для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
  
Операция "Получить пользователей" является частью службы пользователей в API репозитория для панели мониторинга качества вызовов.
  
## <a name="get-users"></a>Получение пользователей

Get Users returns a list of users in the repository.
  
|**Способ**|**URI запроса**|**Версия HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user  <br/> |HTTP/1.1  <br/> |
   
 **Параметры URI** — нет.
  
 **Request Headers** - No additional headers.
  
 **Тело запроса** — нет.
  
 **Ответ.** Ответ включает код состояния HTTP и набор загодеров отклика.
  
 **Код состояния** : успешная операция возвращает код состояния 200 (OK).
  
 **Response Headers** - No additional headers.
  
 **Тело ответа.** Ниже приведен пример полезной нагрузки ответа в JSON.
  
> [!NOTE]
> Возвращается массив объектов User. Подробные сведения об объекте User см. в сведениях о get User. 
  
```json
[{
"userId": 0,
"loginName": "system",
"defaultItemId": 1652
},
{
"userId": 1,
"loginName": "SAMPLEDOMAIN\\testuser1",
"defaultItemId": 1652
},
{
"userId": 2,
"loginName": "SAMPLEDOMAIN\\testuser2",
"defaultItemId": 1774
}]
```


