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
ms.localizationpriority: medium
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: Таблица UriTypes содержит различные типы URI (единообразный идентификатор ресурсов), отслеживаются в Skype для бизнеса Server 2015 г.
ms.openlocfilehash: e6be4abb02fc29fb5becd9da8a1b45c4d8c6271f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583773"
---
# <a name="uritypes-table"></a>Таблица UriTypes
 
Таблица UriTypes содержит различные типы URI (единообразный идентификатор ресурсов), отслеживаются в Skype для бизнеса Server 2015 г.

После создания CDR DB создаются две записи, которые представляют PhoneUri и UserUri, и записи, созданные после этого, динамически назначены UriTypeId. 
  
|**Столбец**|**Тип данных**|**Key/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primary  <br/> |Уникальный идентификатор типа URI.  <br/> Возможные значения - от 0 до 255 |
|**UriType** <br/> |nvarchar (256)  <br/> || Описания различных типов URI. Заранее назначены следующие значения: <br/>  1 - Телефон Uri <br/>  0 - Пользовательский Uri <br/> <br/>  Другие возможные типы: <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf:chat<br/>    conf:focus<br/>   mras<br/>
