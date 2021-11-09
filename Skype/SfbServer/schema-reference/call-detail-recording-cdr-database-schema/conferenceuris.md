---
title: Таблица ConferenceUris в Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 04867ec3e8c82b210e6f6f9663030b23879b996b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836187"
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
   

