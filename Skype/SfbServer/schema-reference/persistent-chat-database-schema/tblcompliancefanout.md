---
title: tblComplianceFanout
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout содержит все серверы, обработавшие событие соответствия.
ms.openlocfilehash: 6c0ae5a9b00945494c125511e1206f4177432703
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765077"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout содержит все серверы, обработавшие событие соответствия.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |Идентификатор события.  <br/> |
|fanoutServerID  <br/> |int  <br/> |Идентификатор сервера (в соответствии с таблицей tblServerIdentity.serverID).  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|fanoutEventID  <br/> |Внешний ключ с поиском в таблице tblComplianceData.cmplEventID.  <br/> |
   

