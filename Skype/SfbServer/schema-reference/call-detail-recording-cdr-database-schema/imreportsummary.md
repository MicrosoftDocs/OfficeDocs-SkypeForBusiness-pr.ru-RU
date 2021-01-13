---
title: Таблица IMReportSummary в Skype для бизнеса Server 2015
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
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: В таблице IMReportSummaryTable приводится общий отчет о сеансах обмена мгновенными сообщениями, которые проводятся в организации. Эта таблица была представлена в Microsoft Lync Server 2013.
ms.openlocfilehash: 6a80918376440c13d60e059744d88c09c2705853
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821529"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>Таблица IMReportSummary в Skype для бизнеса Server 2015
 
В таблице IMReportSummaryTable приводится общий отчет о сеансах обмена мгновенными сообщениями, которые проводятся в организации. Эта таблица была представлена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |datetime  <br/> |Primary  <br/> |Дата и время начала сеанса обмена мгновенными сообщениями.  <br/> |
|**TimePeriod** <br/> |char(1)  <br/> |Primary  <br/> ||
|**PoolFQDN** <br/> |nvarchar(257)  <br/> |Primary  <br/> |Полное доменное имя пула, в котором размещается сеанс.  <br/> |
|**AuthType** <br/> |int  <br/> |Primary  <br/> |Приоритет звонка (например, срочный или несрочный). Сведения о приоритетах хранятся в таблице [CallPriorities в Skype для бизнеса Server 2015.](callpriorities.md)  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||Общее число мгновенных сообщений, отправленных в рамках сеанса.  <br/> |
   

