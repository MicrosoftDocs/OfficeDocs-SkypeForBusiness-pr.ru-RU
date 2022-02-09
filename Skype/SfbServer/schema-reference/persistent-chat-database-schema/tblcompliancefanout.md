---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: fdddd6bc1157e76ff94d86d6553da3a7308cd0f2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62420882"
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
   

