---
title: Получение пользователей
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Сводка: сведения о команде Get Users, которая входит в состав службы пользователей. Служба User входит в API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.'
ms.openlocfilehash: 6cf2248035c780c2efce6b1f4539a39cd2a5829a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992616"
---
# <a name="get-users"></a>Получение пользователей
 
**Сводка:** Сведения о выполнении операции Get Users, которая входит в состав службы "Пользователи". Служба User входит в API репозитория для панели мониторинга качества звонков. Панель мониторинга качества звонков — это средство для Skype для бизнеса Server.
  
Операция Get Users является частью службы пользователей в API репозитория для панели мониторинга качества звонков.
  
## <a name="get-users"></a>Получение пользователей

Функция Get Users возвращает список пользователей в репозитории.
  
|**Способов**|**URI запроса**|**Версия HTTP**|
|:-----|:-----|:-----|
|Получить  <br/> |/Коерепоситорисервице/репоситори/Усер\<портала\>HTTPS://  <br/> |HTTP/1.1  <br/> |
   
 **Параметры универсального кода ресурса** (None).
  
 **Заголовки запроса** — без дополнительных заголовков.
  
 **Запросить текст** -None.
  
 **Response (ответ** ) — ответ включает код состояния HTTP и набор заголовков ответа.
  
 **Код состояния** — успешная операция возвращает код состояния 200 (ОК).
  
 **Заголовки ответа** — без дополнительных заголовков.
  
 **Тело ответа** — ниже показан пример полезных данных ответа в JSON.
  
> [!NOTE]
> Возвращается массив объектов пользователя. Сведения об объекте User можно найти в статьях получение пользователя. 
  
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


