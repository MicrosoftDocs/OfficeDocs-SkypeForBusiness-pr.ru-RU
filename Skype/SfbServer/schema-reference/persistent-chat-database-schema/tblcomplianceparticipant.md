---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: Таблица ComplianceParticipant содержит текущих участников по каналам или по серверам.
ms.openlocfilehash: 8c94aab78c7f0cc9a04e849a2ad798134ff38e42
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627771"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
Таблица ComplianceParticipant содержит текущих участников по каналам или по серверам.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|channelUri  <br/> |nvarchar (255), not null  <br/> |Универсальный код ресурса (URI) для канала.  <br/> |
|userId  <br/> |int, not null  <br/> |Идентификатор участника (в соответствии с таблицей tblPrincipal.prinID).  <br/> |
|joinedAt  <br/> |bigint, not null  <br/> |Метка времени события присоединения.  <br/> |
|partedAt  <br/> |bigint  <br/> |Null, если участник еще присоединен.Если не null, то метка времени события выхода из канала.  <br/> Эти записи в конечном итоге удаляются, когда все переводчики обработают событие.  <br/> |
|userUri  <br/> |nvarchar(255), not null  <br/> |URI пользователя.  <br/> |
|serverID  <br/> |int  <br/> |Удостоверение сервера (в соответствии с таблицей tblServerIdentity.serverID).  <br/> |
|sessionId  <br/> |bigint  <br/> |Сеанс сервера. Это произвольный номер, который создается каждый раз при запуске службы чата. Он используется, чтобы различать сеансы в целях идентификации потерянных участников.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |Первичный ключ.  <br/> |
   

