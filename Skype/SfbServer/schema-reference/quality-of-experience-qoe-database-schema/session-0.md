---
title: Представление сеанса
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: В представлении сеанса сохраняются сведения о сеансах, для которых есть записи в базе данных. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: afcff6c5032c14dbcab525a0032804493bcb0216
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393581"
---
# <a name="session-view"></a>Представление сеанса
 
В представлении сеанса сохраняются сведения о сеансах, для которых есть записи в базе данных. Это представление было представлено в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |Ссылка из таблицы линии медиаданных.  <br/> |
|ConferenceURI  <br/> |nvarchar (450)  <br/> |URI конференции, если это конференция, или DialogID, если это сеанс между одноранговыми узлами.  <br/> |
|Correlation  <br/> |varchar (max)  <br/> |Идентификатор корреляции сеанса  <br/> |
|DialogCategory  <br/> |bit  <br/> |Категория диалоговое окно; 0 — Skype для бизнеса Server для сервера-посредника; 1 — это сервер-посредник для шлюза PSTN.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Указывает, был ли обойден вызов.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Если это поле присутствует, оно указывает, почему вызов не может быть обойден, даже если идентификаторы обхода совпадают. Для Skype для бизнеса Server определяется только одно значение:  <br/> 0x0001 — неизвестный iD обхода для сетевого адаптера по умолчанию  <br/> |
|StartTime  <br/> |datetime  <br/> |Время начала вызова.  <br/> |
|EndTime  <br/> |datetime  <br/> |Время окончания вызова.  <br/> |
|CallerPool  <br/> |nvarchar (256)  <br/> |Полное доменное имя пула вызывающего абонента.  <br/> |
|CalleePool  <br/> |nvarchar (256)  <br/> |Полное доменное имя пула вызываемого абонента.  <br/> |
|CallerPAI  <br/> |nvarchar (450)  <br/> |P-asserted identity URI вызывающего пользователя.  <br/> |
|CalleePAI  <br/> |nvarchar (450)  <br/> |P-asserted identity URI callee.  <br/> |
|CallerEndpoint  <br/> |nvarchar (256)  <br/> |Имя конечной точки вызываемой точки.  <br/> |
|CalleeEndpoint  <br/> |nvarchar (256)  <br/> |Имя конечной точки вызываемой точки.  <br/> |
|CallerUserAgent  <br/> |nvarchar (256)  <br/> |Строка агента пользователя вызываемой.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Тип агента пользователя вызываемого пользователя. Сведения см. [в таблице UserAgent](useragent.md) . <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Категория агента пользователя вызываемого пользователя. Сведения см. [в таблице UserAgentDef (QoE](useragentdef-qoe.md) ). <br/> |
|CalleeUserAgent  <br/> |nvarchar (256)  <br/> |Строка агента пользователя callee.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Тип агента пользователя вызываемого абонента. Сведения см. [в таблице UserAgent](useragent.md) . <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Категория агента пользователя вызываемого абонента. Сведения см. [в таблице UserAgentDef (QoE](useragentdef-qoe.md) ). <br/> |
|CallerURI  <br/> |nvarchar (450)  <br/> |URI вызываемой.  <br/> |
|CalleeURI  <br/> |nvarchar (450)  <br/> |URI вызываемой.  <br/> |
|CallPrioirty  <br/> |int  <br/> |Приоритет вызова.  <br/> |
   

