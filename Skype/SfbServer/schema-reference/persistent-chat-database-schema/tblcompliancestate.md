---
title: tblComplianceState
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
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: Таблица tblComplianceState содержит сведения о состоянии соответствия во всем пуле.
ms.openlocfilehash: c96f43c27179d5dd933aeba7f1483be3e1f7ee7e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580403"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
Таблица tblComplianceState содержит сведения о состоянии соответствия во всем пуле.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, NOT NULL  <br/> |Идентификатор последнего обработанного события соответствия.  <br/> |
|activeServerID  <br/> |int, NOT NULL  <br/> |Идентификатор сервера соответствия, на котором находится монопольная блокировка базы данных, или -1 при ее отсутствии.  <br/> |
|lockExpirationTime  <br/> |datetime2, NOT NULL  <br/> |Время окончания блокировки (если значение activeServerID не равно -1).  <br/> |
   

