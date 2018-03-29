---
title: Просмотр сеанса
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: Просмотр сеанса сохранение информации о сеансах с записями в базе данных. В этом представлении была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: 056067b0c0e06b3ce9eb862898345fe4c8ff131c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="session-view"></a>Просмотр сеанса
 
Просмотр сеанса сохранение информации о сеансах с записями в базе данных. В этом представлении была введена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |Ссылка из таблицы MediaLine Table.  <br/> |
|URI конференции  <br/> |nvarchar(450)  <br/> |URI конференции, если это конференции или DialogID при этом является peer-to-peer сеанса.  <br/> |
|Корреляции  <br/> |varchar(max)  <br/> |Идентификатор корреляции сеанса.  <br/> |
|DialogCategory  <br/> |бит  <br/> |Категория диалога; 0 — Скайп для Business Server до сервера-посредника; 1 — сервер-посредник ветвь шлюза ТСОП.  <br/> |
|MediationServerBypassFlag  <br/> |бит  <br/> |Указывает, будет ли того, были ли вызов обход сервера-посредника.  <br/> |
|MediaBypassWarningFlag  <br/> |целое  <br/> |В этом поле, если этот параметр указан, указывает, почему звонка не обход сервера-посредника даже при совпадении идентификаторы сервера-посредника. Для Скайп Business Server определяется только одно значение:  <br/> 0x0001 — Неизвестный идентификатор обхода для сетевого адаптера по умолчанию  <br/> |
|Время начала  <br/> |datetime  <br/> |Время начала вызова.  <br/> |
|Время окончания  <br/> |datetime  <br/> |Время окончания вызова.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |Полное доменное имя пула вызывающего абонента.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |Полное доменное имя пула вызываемого абонента.  <br/> |
|CallerPAI  <br/> |nvarchar(450)  <br/> |У вызывающего абонента удостоверения pai URI.  <br/> |
|CalleePAI  <br/> |nvarchar(450)  <br/> |У вызываемого абонента удостоверения pai URI.  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Имя конечной точки вызывающего абонента.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Имя конечной точки вызывающего абонента.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Строка агента пользователя вызывающего абонента.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Тип агента пользователя вызывающего абонента. В разделе [Таблица UserAgent](useragent.md) для получения дополнительных сведений. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Категория агента пользователя вызывающего абонента. [Таблица useragentdef (QoE)](useragentdef-qoe.md) для получения дополнительных сведений см. <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Строка агента пользователя вызываемого абонента.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Тип агента пользователя для вызываемого абонента. В разделе [Таблица UserAgent](useragent.md) для получения дополнительных сведений. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Категория агента пользователя вызываемого абонента. [Таблица useragentdef (QoE)](useragentdef-qoe.md) для получения дополнительных сведений см. <br/> |
|CallerURI  <br/> |nvarchar(450)  <br/> |URI вызывающего абонента.  <br/> |
|CalleeURI  <br/> |nvarchar(450)  <br/> |URI вызываемого абонента.  <br/> |
|CallPrioirty  <br/> |целое  <br/> |Приоритет вызова.  <br/> |
   

