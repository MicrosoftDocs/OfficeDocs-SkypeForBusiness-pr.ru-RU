---
title: Таблица UriTypes
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: Таблица UriTypes содержит различные типы URI (идентификатор единого ресурса), отслеживаемого в Skype для бизнеса Server 2015.
ms.openlocfilehash: 622384086dbd1031633b70758cdcea600ad31d43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831689"
---
# <a name="uritypes-table"></a>Таблица UriTypes
 
Таблица UriTypes содержит различные типы URI (идентификатор единого ресурса), отслеживаемого в Skype для бизнеса Server 2015.

После создания базы данных CDR создаются две записи, которые представляют PhoneUri и UserUri, и записи, созданные после этого, динамически назначены UriTypeId. 
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primary  <br/> |Уникальный идентификатор типа URI.  <br/> Возможные значения — от 0 до 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || Описания различных типов URI. Предварительно назначены следующие значения: <br/>  1 — URI телефона <br/>  0 — URI пользователя <br/> <br/>  Другие возможные типы: <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:chat<br/>    conf:focus<br/>   mras<br/>
