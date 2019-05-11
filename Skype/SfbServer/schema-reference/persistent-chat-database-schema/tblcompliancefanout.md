---
title: tblComplianceFanout
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout содержит все серверы, обработавшие событие соответствия.
ms.openlocfilehash: 002ffe3fd825dd90a5223dca06316ff3a60fddd9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929926"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout содержит все серверы, обработавшие событие соответствия.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |целое  <br/> |Идентификатор события.  <br/> |
|fanoutServerID  <br/> |целое  <br/> |Идентификатор сервера (в соответствии с таблицей tblServerIdentity.serverID).  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|fanoutEventID  <br/> |Внешний ключ с поиском в таблице tblComplianceData.cmplEventID.  <br/> |
   

