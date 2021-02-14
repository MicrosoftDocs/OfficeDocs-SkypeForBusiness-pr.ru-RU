---
title: Представление сеанса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: В представлении сеанса сохраняются сведения о сеансах, для которых есть записи в базе данных. Это представление впервые было введено в Microsoft Lync Server 2013.
ms.openlocfilehash: 34619c1555fac5935563dd72895f52d045c388ae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802699"
---
# <a name="session-view"></a>Представление сеанса
 
В представлении сеанса сохраняются сведения о сеансах, для которых есть записи в базе данных. Это представление впервые было введено в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Details**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |Ссылка из таблицы линии медиаданных.  <br/> |
|ConferenceURI  <br/> |nvarchar(450)  <br/> |URI конференции, если это конференция, или DialogID, если это сеанс между одноранговыми узлами.  <br/> |
|Correlation  <br/> |varchar(max)  <br/> |Идентификатор корреляции сеанса  <br/> |
|DialogCategory  <br/> |bit  <br/> |Категория диалоговых окной; 0 — это этап между Сервером-посредником и Skype для бизнеса Server; 1 — это сервер-посредник для шлюза STN.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Указывает, был ли обойден вызов.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Если это поле присутствует, оно указывает, почему вызов не может быть обойден, даже если идентификаторы обхода совпадают. Для Skype для бизнеса Server определено только одно значение:  <br/> 0x0001 - Неизвестный ИД обхода для сетевого адаптера по умолчанию  <br/> |
|StartTime  <br/> |datetime  <br/> |Время начала вызова.  <br/> |
|EndTime  <br/> |datetime  <br/> |Время окончания вызова.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |Полное доменное имя пула вызывающего абонента.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |Полное доменное имя пула вызываемого абонента.  <br/> |
|CallerPAI  <br/> |nvarchar(450)  <br/> |URI удостоверения p-asserted вызывающего.  <br/> |
|CalleePAI  <br/> |nvarchar(450)  <br/> |URI удостоверения p-asserted вызываемого вызываемого.  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Имя конечной точки вызываемой точки.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Имя конечной точки вызываемой точки.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Строка агента пользователя вызываемой.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Тип агента пользователя вызываемого пользователя. Подробные сведения см. в таблице [UserAgent.](useragent.md) <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Категория агента пользователя вызываемого пользователя. Подробные сведения см. в таблице [UserAgentDef (QoE).](useragentdef-qoe.md) <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Строка агента пользователя вызываемой.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Тип агента пользователя вызываемого абонента. Подробные сведения см. в таблице [UserAgent.](useragent.md) <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Категория агента пользователя вызываемого абонента. Подробные сведения см. в таблице [UserAgentDef (QoE).](useragentdef-qoe.md) <br/> |
|CallerURI  <br/> |nvarchar(450)  <br/> |URI вызываемой.  <br/> |
|CalleeURI  <br/> |nvarchar(450)  <br/> |URI вызываемой.  <br/> |
|CallPrioirty  <br/> |int  <br/> |Приоритет вызова.  <br/> |
   

