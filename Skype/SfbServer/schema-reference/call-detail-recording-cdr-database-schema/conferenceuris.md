---
title: Таблица ConferenceUris в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: В таблице ConfereneUris представляет собой вспомогательную таблицу, в которой хранится список различных конференции URI, которые участвовали в сеансах конференц записаны в базе данных. Каждая запись в таблице представляет одну URI конференции.
ms.openlocfilehash: 70cb3ccecf1c63dd128cbffd6ac205e77c771835
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901068"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Таблица ConferenceUris в Скайп для Business Server 2015
 
В таблице ConfereneUris представляет собой вспомогательную таблицу, в которой хранится список различных конференции URI, которые участвовали в сеансах конференц записаны в базе данных. Каждая запись в таблице представляет одну URI конференции.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |Primary  <br/> |Метка времени для внутреннего использования.  <br/> |
|**ConferenceUriId** <br/> |целое  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот URI конференции.  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> ||URI конференции.  <br/> |
|**Контрольная сумма** <br/> |целое  <br/> ||Контрольная сумма URI конференции. Используется для ускоряет базы данных поиска.  <br/> |
|**UriTypeId** <br/> |целое  <br/> |Внешний  <br/> |Тип URI, например conf:chat для обмена Мгновенными сообщениями или conf:audio-видео для аудиовизуальной конференции. В таблице [UriTypes таблицы](uritypes.md) для получения дополнительных сведений см. <br/> |
   

