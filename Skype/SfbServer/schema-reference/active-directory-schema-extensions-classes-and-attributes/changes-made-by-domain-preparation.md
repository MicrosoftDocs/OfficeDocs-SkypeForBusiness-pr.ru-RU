---
title: Изменения, внесенные при подготовке домена в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
description: В следующей таблице перечислены записи управления доступом (ACE), которые создаются при подготовке домена в корневом домене. Все записи ACE наследуются, если не указано иное.
ms.openlocfilehash: 2a1e5b8d7de785d08686de074e251e8c1c20709c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777799"
---
# <a name="changes-made-by-domain-preparation-in-skype-for-business-server"></a>Изменения, внесенные при подготовке домена в Skype для бизнеса Server
 
В следующей таблице перечислены записи управления доступом (ACE), которые создаются при подготовке домена в корневом домене. Все записи ACE наследуются, если не указано иное.
  
**Записи ACE, добавленные в корневой домен**

|**ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|**RTCUniversal-UserAdmins**|**RTCHSUniversal-Services**|**Проверка подлинности пользователей**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Чтение контейнера (не наследуется)  <br/> |**Да** <br/> |**Да** <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |
|Чтение User PropertySet User-Account-Restrictions  <br/> |**Да** <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |
|Чтение User PropertySet Personal-Information  <br/> |**Да** <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |
|Чтение User PropertySet General-Information  <br/> |**Да** <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |
|Чтение User PropertySet Public-Information  <br/> |**Да** <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |
|Чтение User PropertySet RTCUserSearchProperty-Set  <br/> |**Да** <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |**Да** <br/> |
|Чтение User PropertySet RTCPropertySet  <br/> |**Да** <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |
|Запись User Property Proxy-Addresses  <br/> |Нет  <br/> |Нет  <br/> |**Да** <br/> |Нет  <br/> |Нет  <br/> |
|Запись User PropertySet RTCUserSearchProperty-Set  <br/> |Нет  <br/> |Нет  <br/> |**Да** <br/> |Нет  <br/> |Нет  <br/> |
|Запись User PropertySet RTCPropertySet  <br/> |Нет  <br/> |Нет  <br/> |**Да** <br/> |Нет  <br/> |Нет  <br/> |
|Чтение PropertySet DS-Replication-Get-Changes всех объектов Active Directory  <br/> |Нет  <br/> |Нет  <br/> |Нет  <br/> |**Да** <br/> |Нет  <br/> |
   
В следующей таблице перечислены записи управления доступом (ACE), которые создаются при подготовке домена в трех встроенных контейнерах: «Пользователи», «Компьютеры», «Контроллеры доменов». Все записи ACE наследуются, если не указано иное.
**Записи ACE, добавленные во встроенные контейнеры**

|**ACE**|**RTCUniversal-UserReadOnly-Group**|**RTCUniversal-ServerReadOnly-Group**|
|:-----|:-----|:-----|
|Чтение контейнера (не наследуется)  <br/> |**Да** <br/> |**Да** <br/> |
   

