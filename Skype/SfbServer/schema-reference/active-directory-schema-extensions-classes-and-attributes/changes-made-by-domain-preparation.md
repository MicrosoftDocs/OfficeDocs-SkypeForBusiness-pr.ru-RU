---
title: Изменения, внесенные с подготовки домена в Скайп для Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: В следующей таблице перечислены записи управления доступом (ACE), которые создает подготовки домена в корневом домене. Все элементы управления доступом наследуются, если не указано иное.
ms.openlocfilehash: 5cf239e37badafee9980140d08fd20a11e3c233d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213454"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Изменения, внесенные с подготовки домена в Скайп для Business Server
 
В следующей таблице перечислены записи управления доступом (ACE), которые создает подготовки домена в корневом домене. Все элементы управления доступом наследуются, если не указано иное.
  
**Записи ACE, добавленные в корневой домен**

|**ЭЛЕМЕНТ УПРАВЛЕНИЯ ДОСТУПОМ**|**RTCUniversal UserReadOnly группы**|**RTCUniversal ServerReadOnly группы**|**RTCUniversal UserAdmins**|**RTCHSUniversal служб**|**Прошедшие проверку**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Чтение контейнера (не наследуется)  <br/> |**Да** <br/> |**Да** <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |
|Чтение PropertySet User-Account-Restrictions пользователя  <br/> |**Да** <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |
|Чтение пользователя PropertySet Personal-Information  <br/> |**Да** <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |
|Чтение User PropertySet General-Information  <br/> |**Да** <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |
|Чтение User PropertySet Public-Information  <br/> |**Да** <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |
|Чтение User PropertySet RTCUserSearchProperty-Set  <br/> |**Да** <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |**Да** <br/> |
|Чтение User PropertySet RTCPropertySet  <br/> |**Да** <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |
|Запись свойства прокси адреса пользователей  <br/> |Нет  <br/> |Нет  <br/> |**Да** <br/> |Нет  <br/> |Нет  <br/> |
|Запись User PropertySet RTCUserSearchProperty-Set  <br/> |Нет  <br/> |Нет  <br/> |**Да** <br/> |Нет  <br/> |Нет  <br/> |
|Запись User PropertySet RTCPropertySet  <br/> |Нет  <br/> |Нет  <br/> |**Да** <br/> |Нет  <br/> |Нет  <br/> |
|Чтение PropertySet DS-репликации-Get-Changes всех объектов Active Directory  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |**Да** <br/> |Нет  <br/> |
   
В следующей таблице перечислены элементы управления доступом подготовки домена создает в три встроенные контейнеры: пользователи, компьютеры и контроллеры доменов. Все элементы управления доступом наследуются, если не указано иное.
**Записи ACE, добавленные во встроенные контейнеры**

|**ЭЛЕМЕНТ УПРАВЛЕНИЯ ДОСТУПОМ**|**RTCUniversal UserReadOnly группы**|**RTCUniversal ServerReadOnly группы**|
|:-----|:-----|:-----|
|Чтение контейнера (не наследуется)  <br/> |**Да** <br/> |**Да** <br/> |
   

