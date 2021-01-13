---
title: Таблица ConferenceMessageCount в Skype для бизнеса Server 2015
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
description: Каждая запись в этой таблице представляет одного пользователя в одной конференции с мгновенными сообщениями и включает количество сообщений, отправленных этим пользователем. Каждая конференция представлена несколькими записями в этой таблице; одна запись для каждого пользователя.
ms.openlocfilehash: b931b45915fc12fb01ea36f81bee62f36914e903
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813279"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a>Таблица ConferenceMessageCount в Skype для бизнеса Server 2015
 
Каждая запись в этой таблице представляет одного пользователя в одной конференции с мгновенными сообщениями и включает количество сообщений, отправленных этим пользователем. Каждая конференция представлена несколькими записями в этой таблице; одна запись для каждого пользователя.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Основной, внешний  <br/> |Время экземпляра конференции. Используется в сочетании с **SessionIdSeq** для уникальной идентификации экземпляра конференции. Дополнительные сведения см. в таблице ["Конференции" в Skype для бизнеса Server 2015.](conferences.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Основной, Внешний  <br/> |Идентификатор для определения экземпляра конференции. Используется в сочетании с **SessionIdTime** для уникальной идентификации экземпляра конференции. Дополнительные сведения см. в таблице ["Конференции" в Skype для бизнеса Server 2015.](conferences.md) <br/> |
|**UserId** <br/> |int  <br/> |Внешняя  <br/> |Уникальный номер, идентифицирующий этого пользователя, на который ссылается [таблица Users.](users.md)  <br/> |
|**MessageCount** <br/> |smallint  <br/> | <br/> |Количество сообщений, отправленных этим пользователем во время этой конференции.  <br/> |
   

