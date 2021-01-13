---
title: Получение элементов
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
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: Сводка. Сведения об операции "Получить элементы", которая входит в состав службы элементов. Служба элементов является частью API репозитория для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: 7da3ba77e782abe44896a7c1eb51a458d9a7e0b8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832539"
---
# <a name="get-items"></a>Получение элементов
 
**Сводка:** Узнайте об операции "Получить элементы", которая входит в состав службы элементов. Служба элементов является частью API репозитория для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
  
Операция "Получить элементы" является частью службы элементов в API репозитория для панели мониторинга качества вызовов.
  
## <a name="get-items"></a>Получение элементов

При этом возвращаются все элементы в репозитории.
  
|**Способ**|**URI запроса**|**Версия HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/item  <br/> |HTTP/1.1  <br/> |
   
 **Параметры URI** — нет.
  
 **Request Headers** - No additional headers.
  
 **Тело запроса** — нет.
  
 **Ответ.** Ответ включает код состояния HTTP и набор загодеров отклика.
  
 **Код состояния** — успешная операция возвращает код состояния 200 (OK).
  
 **Response Headers** - No additional headers.
  
 **Тело ответа.** Ниже приведен пример полезной нагрузки ответа в JSON.
  
> [!NOTE]
> Возвращается массив объектов Item. Подробные сведения об объекте Item см. в статье "Получить элемент". 
  
```json
[{
"itemId": 1652,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1654,
"userId": 0,
"type": "application/json"
}]
```
