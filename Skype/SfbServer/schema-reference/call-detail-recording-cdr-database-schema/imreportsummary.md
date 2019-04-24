---
title: Таблица imreportsummary в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: В таблице IMReportSummaryTable приводится общий отчет о сеансах обмена мгновенными сообщениями в организации. Эта таблица была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: fd907165f7db131e94d09d2b9a531eeb20812734
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213034"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>Таблица imreportsummary в Скайп для Business Server 2015
 
В таблице IMReportSummaryTable приводится общий отчет о сеансах обмена мгновенными сообщениями в организации. Эта таблица была введена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |datetime  <br/> |Primary  <br/> |Дата и время начала сеанса обмена мгновенными сообщениями.  <br/> |
|**TimePeriod** <br/> |char(1)  <br/> |Primary  <br/> ||
|**PoolFQDN** <br/> |nvarchar(257)  <br/> |Primary  <br/> |Полное доменное имя пула, в котором размещается сеанс.  <br/> |
|**AuthType** <br/> |целое  <br/> |Primary  <br/> |Приоритет вызова (например, срочные или не срочный). Сведения о приоритет хранятся в [Таблица CallPriorities в Скайп для Business Server 2015](callpriorities.md).  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||Общее количество мгновенных сообщений, отправленных в рамках сеанса.  <br/> |
   

