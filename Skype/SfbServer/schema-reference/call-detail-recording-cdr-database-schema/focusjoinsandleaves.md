---
title: Таблица FocusJoinsAndLeaves в Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: Каждая запись в этой таблице содержит сведения CDR о том, как присоединиться к одному пользователю и оставить информацию для одной конференции. Каждая конференция представлена в этой таблице одной записью каждый раз, когда пользователь присоединяется и покидает конференцию.
ms.openlocfilehash: 879c4df8dce048820e2d1a23f62ff5c7070611a7e0331cb496a50363aa98f3b9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54352088"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>Таблица FocusJoinsAndLeaves в Skype для бизнеса Server 2015 г.
 
Каждая запись в этой таблице содержит сведения CDR о том, как присоединиться к одному пользователю и оставить информацию для одной конференции. Каждая конференция представлена в этой таблице одной записью каждый раз, когда пользователь присоединяется и покидает конференцию.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Основной, внешний  <br/> |Время экземпляра конференции. Используется совместно с **SessionIdSeq** для уникального определения экземпляра конференции. Дополнительные сведения см. в таблице [конференций Skype для бизнеса Server 2015](conferences.md) г. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Основной, Внешний  <br/> |Идентификатор для определения экземпляра конференции. Используется совместно с **SessionIdTime** для уникальной идентификации экземпляра конференции. Дополнительные сведения см. в таблице [конференций Skype для бизнеса Server 2015](conferences.md) г. <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Основной, внешний  <br/> |Время запроса сеанса. В сочетании с параметром **SessionIdSeq** определяет сеанс уникальным образом. Дополнительные сведения см. в таблице [Диалоги Skype для бизнеса Server 2015](dialogs.md) г. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Основной, внешний  <br/> |Идентификатор для идентификации сеанса. В сочетании с параметром **SessionIdTime** определяет сеанс уникальным образом. дополнительные сведения см. в таблице [Диалоги Skype для бизнеса Server 2015](dialogs.md) г. <br/> |
|**UserId** <br/> |int  <br/> |Foreign  <br/> |Уникальный номер, идентифицирующий этого пользователя, ссылаясь на [таблицу Пользователи](users.md).  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||Если пользователь вошел в систему одновременно на нескольких компьютерах или устройствах, **userInstance** используется для уникальной идентификации сочетания пользователя и устройства. <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |Вошел ли пользователь из внутреннего или нет.  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |Роль этого пользователя в конференции, например Presenter или Attendee.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |Время, когда этот пользователь присоединяется к конференции.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |Время, когда этот пользователь покидает конференцию.  <br/> |
|**ClientVerId** <br/> |int  <br/> |Foreign  <br/> |Версия клиентского программного обеспечения пользователя, со ссылкой на таблицу [ClientVersions в Skype для бизнеса Server 2015 г.](clientversions.md)  <br/> |
|**UserEndpointId** <br/> |uniqueIdentifier  <br/> ||Глобальный уникальный идентификатор (GUID) конечной точки, используемой на конференции.  <br/> Это поле было внедрено в Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Для внутреннего использования службой мониторинга.  <br/> Это поле было введено Skype для бизнеса Server 2015 г.  <br/> |
   

