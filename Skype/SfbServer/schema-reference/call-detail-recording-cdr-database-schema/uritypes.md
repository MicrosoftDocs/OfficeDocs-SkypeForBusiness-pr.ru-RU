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
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: В таблице Уритипес содержатся различные типы URI (универсального идентификатора ресурса), отслеживаемые в Skype для бизнеса Server 2015.
ms.openlocfilehash: 5ad8e1d0432aff3278f897fbe82d3759ad3c95e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295750"
---
# <a name="uritypes-table"></a>Таблица UriTypes
 
В таблице Уритипес содержатся различные типы URI (универсального идентификатора ресурса), отслеживаемые в Skype для бизнеса Server 2015.

После создания базы данных CDR создаются две записи, представляющие Фонеури и Усерури, а также записи, созданные после того, как динамически назначены Уритипеид. 
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**Уритипеид** <br/> |tinyint  <br/> |Primary  <br/> |Уникальный идентификатор, присвоенный типу URI.  <br/> Возможные значения: от 0 до 255 |
|**Уритипе** <br/> |nvarchar(256)  <br/> || Описание различных типов URI. Следующие значения предварительно назначены: <br/>  Универсальный код ресурса (URI) на 1 номер <br/>  0 — URI пользователя <br/> <br/>  Ниже перечислены другие возможные типы. <br/>conf:applicationsharing <br/> conf:audio-video<br/> conf: чат<br/>    conf:focus<br/>   мрас<br/>
