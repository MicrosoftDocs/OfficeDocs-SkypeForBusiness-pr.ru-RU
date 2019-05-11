---
title: Таблица UriTypes
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: Таблица UriTypes содержит различные типы URI (универсальный код ресурса), отслеживаемые в Скайп для Business Server 2015.
ms.openlocfilehash: 72704715ff5e5fd3a354b75b0aa6baff45ecea54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930271"
---
# <a name="uritypes-table"></a>Таблица UriTypes
 
Таблица UriTypes содержит различные типы URI (универсальный код ресурса), отслеживаемые в Скайп для Business Server 2015.

При создании базы данных регистрации Вызовов, создаются две записи для представления PhoneUri и UserUri и записей, создаваемых после динамически назначены UriTypeId. 
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primary  <br/> |Уникальный идентификатор, назначенный типа URI.  <br/> Допустимые значения — от 0 до 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || Описание различных типов URI. Назначенный доступны следующие значения: <br/>  1 — Uri телефона <br/>  0 — Uri пользователя <br/> <br/>  Другие возможные типы: <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:Chat<br/>    conf:focus<br/>   MRAS<br/>
