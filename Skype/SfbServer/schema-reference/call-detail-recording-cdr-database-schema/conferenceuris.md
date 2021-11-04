---
title: Таблица ConferenceUris в Skype для бизнеса Server 2015 г.
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
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris — это вспомогательная таблица, в которой хранится список различных URI конференций, используемых в сеансах конференций, записанных в базе данных. Каждая запись в таблице представляет один URI конференции.
ms.openlocfilehash: 7d7f0ea8504faa3e23d981a74e65062fdb6d5836
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60744025"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Таблица ConferenceUris в Skype для бизнеса Server 2015 г.
 
ConfereneUris — это вспомогательная таблица, в которой хранится список различных URI конференций, используемых в сеансах конференций, записанных в базе данных. Каждая запись в таблице представляет один URI конференции.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |Primary  <br/> |Метка времени; для внутреннего использования.  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот URI конференции.  <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> ||URI конференции.  <br/> |
|**Контрольная сумма** <br/> |int  <br/> ||Контрольная сумма ConferenceUri. Используется для повышения скорости поиска в базе данных.  <br/> |
|**UriTypeId** <br/> |int  <br/> |Foreign  <br/> |Тип URI, например conf:chat для конференции обмена мгновенными сообщениями или conf:audio-video для аудио- и видеоконференции. Дополнительные сведения см. в таблице [UriTypes.](uritypes.md) <br/> |
   

