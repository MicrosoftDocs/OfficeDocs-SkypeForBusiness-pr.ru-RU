---
title: tblComplianceState
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
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: Таблица tblComplianceState содержит сведения о состоянии соответствия во всем пуле.
ms.openlocfilehash: 96b603ac859664163339a9c5628bdec394881657
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854042"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
Таблица tblComplianceState содержит сведения о состоянии соответствия во всем пуле.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, NOT NULL  <br/> |Идентификатор последнего обработанного события соответствия.  <br/> |
|activeServerID  <br/> |int, NOT NULL  <br/> |Идентификатор сервера соответствия, на котором находится монопольная блокировка базы данных, или -1 при ее отсутствии.  <br/> |
|lockExpirationTime  <br/> |datetime2, NOT NULL  <br/> |Время окончания блокировки (если значение activeServerID не равно -1).  <br/> |
   

