---
title: tblComplianceState
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: Таблица tblComplianceState содержит сведения о состоянии соответствия во всем пуле.
ms.openlocfilehash: e46db9c73f4489ade9bbed90f0061567fd14af1d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
Таблица tblComplianceState содержит сведения о состоянии соответствия во всем пуле.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, не может быть null  <br/> |Идентификатор последнего обработанного события соответствия.  <br/> |
|значение activeServerID  <br/> |int, не null  <br/> |Идентификатор сервера соответствия, удерживая монопольная блокировка базы данных, или значение -1, если нет.  <br/> |
|lockExpirationTime  <br/> |datetime2, не может быть null  <br/> |Время окончания блокировки (если значение activeServerID не -1).  <br/> |
   

