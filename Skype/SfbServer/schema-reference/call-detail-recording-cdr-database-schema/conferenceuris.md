---
title: Таблица ConferenceUris в Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris — это вспомогательная таблица, в которой хранится список различных URI конференций, используемых в сеансах конференций, записанных в базе данных. Каждая запись в таблице представляет один URI конференции.
ms.openlocfilehash: f21e86324559f909ad5a38cd2447003967d21819e9195ab9c73a4e84888cf9b9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295396"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Таблица ConferenceUris в Skype для бизнеса Server 2015 г.
 
ConfereneUris — это вспомогательная таблица, в которой хранится список различных URI конференций, используемых в сеансах конференций, записанных в базе данных. Каждая запись в таблице представляет один URI конференции.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |Primary  <br/> |Метка времени; для внутреннего использования.  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот URI конференции.  <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> ||URI конференции.  <br/> |
|**Контрольная сумма** <br/> |int  <br/> ||Контрольная сумма ConferenceUri. Используется для повышения скорости поиска в базе данных.  <br/> |
|**UriTypeId** <br/> |int  <br/> |Foreign  <br/> |Тип URI, например conf:chat для конференции обмена мгновенными сообщениями или conf:audio-video для аудио- и видеоконференции. Дополнительные сведения см. в таблице [UriTypes.](uritypes.md) <br/> |
   

