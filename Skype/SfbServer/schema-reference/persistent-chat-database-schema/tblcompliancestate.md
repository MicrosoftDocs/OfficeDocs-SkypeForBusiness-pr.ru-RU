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
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: Таблица tblComplianceState содержит сведения о состоянии соответствия во всем пуле.
ms.openlocfilehash: 82c775b315976b0e5b112c476a41a8f5adc6a24c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809729"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
Таблица tblComplianceState содержит сведения о состоянии соответствия во всем пуле.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, NOT NULL  <br/> |Идентификатор последнего обработанного события соответствия.  <br/> |
|activeServerID  <br/> |int, NOT NULL  <br/> |Идентификатор сервера соответствия, на котором находится монопольная блокировка базы данных, или -1 при ее отсутствии.  <br/> |
|lockExpirationTime  <br/> |datetime2, NOT NULL  <br/> |Время окончания блокировки (если значение activeServerID не равно -1).  <br/> |
   

