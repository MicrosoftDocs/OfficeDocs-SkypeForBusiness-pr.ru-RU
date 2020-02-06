---
title: Таблица UriTypes
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: В таблице Уритипес содержатся различные типы URI (универсального идентификатора ресурса), отслеживаемые в Skype для бизнеса Server 2015.
ms.openlocfilehash: 81cd00503f88eac03f952b63ef7a3bd9464c1f51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814847"
---
# <a name="uritypes-table"></a>Таблица UriTypes
 
В таблице Уритипес содержатся различные типы URI (универсального идентификатора ресурса), отслеживаемые в Skype для бизнеса Server 2015.

После создания базы данных CDR создаются две записи, представляющие Фонеури и Усерури, а также записи, созданные после того, как динамически назначены Уритипеид. 
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**уритипеид** <br/> |tinyint  <br/> |Primary  <br/> |Уникальный идентификатор, присвоенный типу URI.  <br/> Возможные значения: от 0 до 255 |
|**уритипе** <br/> |nvarchar(256)  <br/> || Описание различных типов URI. Следующие значения предварительно назначены: <br/>  Универсальный код ресурса (URI) на 1 номер <br/>  0 — URI пользователя <br/> <br/>  Ниже перечислены другие возможные типы. <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf: чат<br/>    conf:focus<br/>   мрас<br/>
