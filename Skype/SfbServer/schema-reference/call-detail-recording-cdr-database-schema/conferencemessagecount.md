---
title: Таблица ConferenceMessageCount в Skype для бизнеса Server 2015 г.
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
ms.localizationpriority: medium
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Каждая запись в этой таблице представляет одного пользователя в одной конференции по мгновенным сообщениями и включает количество сообщений, отправленных этим пользователем. Каждая конференция представлена несколькими записями в этой таблице; по одной записи для каждого пользователя.
ms.openlocfilehash: 17b6d97da1795762419fe84527d9b4f5e7bcc137
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590973"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>Таблица ConferenceMessageCount в Skype для бизнеса Server 2015 г.
 
Каждая запись в этой таблице представляет одного пользователя в одной конференции по мгновенным сообщениями и включает количество сообщений, отправленных этим пользователем. Каждая конференция представлена несколькими записями в этой таблице; по одной записи для каждого пользователя.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Основной, внешний  <br/> |Время экземпляра конференции. Используется совместно с **SessionIdSeq** для уникального определения экземпляра конференции. Дополнительные сведения см. в таблице [конференций Skype для бизнеса Server 2015](conferences.md) г. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Основной, Внешний  <br/> |Идентификатор для определения экземпляра конференции. Используется совместно с **SessionIdTime** для уникальной идентификации экземпляра конференции. Дополнительные сведения см. в таблице [конференций Skype для бизнеса Server 2015](conferences.md) г. <br/> |
|**UserId** <br/> |int  <br/> |Foreign  <br/> |Уникальный номер, идентифицирующий этого пользователя, ссылаясь на [таблицу Пользователи](users.md).  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |Количество сообщений, отправленных этим пользователем во время этой конференции.  <br/> |
   

