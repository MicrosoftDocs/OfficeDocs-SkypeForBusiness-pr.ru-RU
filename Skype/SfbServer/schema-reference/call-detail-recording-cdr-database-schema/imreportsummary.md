---
title: Таблица IMReportSummary в Skype для бизнеса Server 2015 г.
ms.reviewer: null
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
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: 'В таблице IMReportSummaryTable приводится общий отчет о сеансах обмена мгновенными сообщениями, которые проводятся в организации. Эта таблица была представлена в Microsoft Lync Server 2013.'
---

# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>Таблица IMReportSummary в Skype для бизнеса Server 2015 г.
 
В таблице IMReportSummaryTable приводится общий отчет о сеансах обмена мгновенными сообщениями, которые проводятся в организации. Эта таблица была представлена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |datetime  <br/> |Primary  <br/> |Дата и время начала сеанса обмена мгновенными сообщениями.  <br/> |
|**TimePeriod** <br/> |char(1)  <br/> |Primary  <br/> ||
|**PoolFQDN** <br/> |nvarchar (257)  <br/> |Primary  <br/> |Полное доменное имя пула, в котором размещается сеанс.  <br/> |
|**AuthType** <br/> |int  <br/> |Primary  <br/> |Приоритет звонка (например, срочный или несрочный). Сведения о приоритетах хранятся в таблице [CallPriorities в Skype для бизнеса Server 2015 г](callpriorities.md).  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||Общее число мгновенных сообщений, отправленных в рамках сеанса.  <br/> |
   

