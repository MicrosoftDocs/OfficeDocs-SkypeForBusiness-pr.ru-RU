---
title: tblComplianceFanout
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout содержит все серверы, обработавшие событие соответствия.
ms.openlocfilehash: 81ee29e5b25080f841ab578214694f563c7cc6b14fe791b1c6b26dc5ea741859
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351938"
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
   

