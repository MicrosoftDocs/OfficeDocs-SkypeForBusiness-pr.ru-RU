---
title: Таблица UriTypes
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: Таблица UriTypes содержит различные типы URI (универсальный код ресурса), отслеживаемые в Скайп для Business Server 2015.
ms.openlocfilehash: cb9c131901a322f9d22c8d29aa52a73dc27c9ea1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899647"
---
# <a name="uritypes-table"></a>Таблица UriTypes
 
Таблица UriTypes содержит различные типы URI (универсальный код ресурса), отслеживаемые в Скайп для Business Server 2015.

При создании базы данных регистрации Вызовов, создаются две записи для представления PhoneUri и UserUri и записей, создаваемых после динамически назначены UriTypeId. 
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primary  <br/> |Уникальный идентификатор, назначенный типа URI.  <br/> Допустимые значения — от 0 до 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || Описание различных типов URI. Назначенный доступны следующие значения: <br/>  1 — Uri телефона <br/>  0 — Uri пользователя <br/> <br/>  Другие возможные типы: <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:Chat<br/>    conf:focus<br/>   MRAS<br/>
