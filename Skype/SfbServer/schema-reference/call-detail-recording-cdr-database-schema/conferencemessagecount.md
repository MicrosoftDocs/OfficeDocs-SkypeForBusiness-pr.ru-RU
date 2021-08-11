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
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Каждая запись в этой таблице представляет одного пользователя в одной конференции по мгновенным сообщениями и включает количество сообщений, отправленных этим пользователем. Каждая конференция представлена несколькими записями в этой таблице; по одной записи для каждого пользователя.
ms.openlocfilehash: 7e713e6d2eb9f856ee039345a0ab2e920e5ee09778b80201c823b14fbc270009
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289507"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>Таблица ConferenceMessageCount в Skype для бизнеса Server 2015 г.
 
Каждая запись в этой таблице представляет одного пользователя в одной конференции по мгновенным сообщениями и включает количество сообщений, отправленных этим пользователем. Каждая конференция представлена несколькими записями в этой таблице; по одной записи для каждого пользователя.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Основной, внешний  <br/> |Время экземпляра конференции. Используется совместно с **SessionIdSeq** для уникального определения экземпляра конференции. Дополнительные сведения см. в таблице [конференций Skype для бизнеса Server 2015](conferences.md) г. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Основной, Внешний  <br/> |Идентификатор для определения экземпляра конференции. Используется совместно с **SessionIdTime** для уникальной идентификации экземпляра конференции. Дополнительные сведения см. в таблице [конференций Skype для бизнеса Server 2015](conferences.md) г. <br/> |
|**UserId** <br/> |int  <br/> |Foreign  <br/> |Уникальный номер, идентифицирующий этого пользователя, ссылаясь на [таблицу Пользователи](users.md).  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |Количество сообщений, отправленных этим пользователем во время этой конференции.  <br/> |
   

