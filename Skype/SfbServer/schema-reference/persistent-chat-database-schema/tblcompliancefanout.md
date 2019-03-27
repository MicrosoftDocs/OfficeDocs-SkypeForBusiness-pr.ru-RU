---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout содержит все серверы, обработавшие событие соответствия.
ms.openlocfilehash: 7f24b1a78dab16b43036734e21d5a8a9b876ca7a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874059"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout содержит все серверы, обработавшие событие соответствия.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**.|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |целое  <br/> |Идентификатор события.  <br/> |
|fanoutServerID  <br/> |целое  <br/> |Идентификатор сервера (в соответствии с таблицей tblServerIdentity.serverID).  <br/> |
   
**Ключ**

|**Столбец**|**Описание**.|
|:-----|:-----|
|fanoutEventID  <br/> |Внешний ключ с поиском в таблице tblComplianceData.cmplEventID.  <br/> |
   

