---
title: Таблица ConferenceMessageCount в Skype для бизнеса Server 2015 г.
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
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Каждая запись в этой таблице представляет одного пользователя в одной конференции по мгновенным сообщениями и включает количество сообщений, отправленных этим пользователем. Каждая конференция представлена несколькими записями в этой таблице; по одной записи для каждого пользователя.
ms.openlocfilehash: 4c2db60023594a86d12be16be84375311ce089e0
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863456"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>Таблица ConferenceMessageCount в Skype для бизнеса Server 2015 г.
 
Каждая запись в этой таблице представляет одного пользователя в одной конференции по мгновенным сообщениями и включает количество сообщений, отправленных этим пользователем. Каждая конференция представлена несколькими записями в этой таблице; по одной записи для каждого пользователя.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Основной, внешний  <br/> |Время экземпляра конференции. Используется совместно с **SessionIdSeq** для уникального определения экземпляра конференции. Дополнительные сведения см. в таблице [конференций Skype для бизнеса Server 2015](conferences.md) г. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Основной, Внешний  <br/> |Идентификатор для определения экземпляра конференции. Используется совместно с **SessionIdTime** для уникальной идентификации экземпляра конференции. Дополнительные сведения см. в таблице [конференций Skype для бизнеса Server 2015](conferences.md) г. <br/> |
|**UserId** <br/> |int  <br/> |Foreign  <br/> |Уникальный номер, идентифицирующий этого пользователя, ссылаясь на [таблицу Пользователи](users.md).  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |Количество сообщений, отправленных этим пользователем во время этой конференции.  <br/> |
   

