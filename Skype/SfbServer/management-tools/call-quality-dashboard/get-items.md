---
title: Получение элементов
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
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: Сводка. Сведения об операции Get Items, которая является частью службы элементов. Служба элементов является частью API репозиториев для панели мониторинга качества вызовов. Панель мониторинга качества вызовов — это средство для Skype для бизнеса Server.
ms.openlocfilehash: 3c4db6558f0cdbc6403c71a8dc1dc46fb5d4d64c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851983"
---
# <a name="get-items"></a>Получение элементов
 
**Сводка:** Узнайте об операции Get Items, которая является частью службы элементов. Служба элементов является частью API репозиториев для панели мониторинга качества вызовов. Панель мониторинга качества вызовов — это средство для Skype для бизнеса Server.
  
Операция Get Items является частью службы элементов в API репозитория для панели мониторинга качества вызовов.
  
## <a name="get-items"></a>Получение элементов

Get Items возвращает все элементы в репозитории.
  
|**Способ**|**Запрос URI**|**ВЕРСИЯ HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/item  <br/> |HTTP/1.1  <br/> |
   
 **Параметры URI** . Нет.
  
 **Заглавные заглавные** запросы — дополнительных загонах не будет.
  
 **Тело запроса** . Нет.
  
 **Ответ.** Ответ включает код состояния HTTP и набор заглавных заглавных ответов.
  
 **Код состояния** — успешная операция возвращает код состояния 200 (OK).
  
 **Заготчики** ответа . Дополнительные заготчики не имеются.
  
 **Тело ответа** . Ниже приведен пример полезной нагрузки ответа в JSON.
  
> [!NOTE]
> Возвращается массив объектов Item. Сведения об объекте Item см. в статье Get Item. 
  
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
