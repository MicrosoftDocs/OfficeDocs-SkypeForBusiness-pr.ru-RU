---
title: Таблица Session
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: Каждая запись представляет один сеанс, в котором участвуют звук или звук и видео. Он содержит общие сведения о сеансе. Сеанс определяется как диалоговое окно SIP между двумя конечными точками.
ms.openlocfilehash: cdf639e7360248e02378c66eb68a60d49acb9749
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802679"
---
# <a name="session-table"></a>Таблица Session
 
Каждая запись представляет один сеанс, в котором участвуют звук или звук и видео. Он содержит общие сведения о сеансе. Сеанс определяется как диалоговое окно SIP между двумя конечными точками.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Ссылка из [таблицы Dialog](dialog.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Ссылка из [таблицы Dialog](dialog.md).  <br/> |
|**ConferenceKey** <br/> |int  <br/> |Внешняя  <br/> |Ключ конференции. Ссылка из [таблицы Conference](conference.md).  <br/> |
|**CorrelationKey** <br/> |int  <br/> |Внешняя  <br/> |Ключ корреляции. Ссылка из [таблицы SessionCorrelation.](sessioncorrelation.md)  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |Категория диалоговых окной; 0 — это этап между Сервером-посредником и Skype для бизнеса Server; 1 — это сервер-посредник для шлюза STN.  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||Флаг, указывающий, выполнял ли вызов обход сервера-посредника.  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||Если это поле присутствует, оно указывает, почему вызов не может быть обойден, даже если идентификаторы обхода совпадают. Для Skype для бизнеса Server определено только одно значение.  <br/> 0x0001 — неизвестный ид обхода для сетевого адаптера по умолчанию.  <br/> |
|**StartTime** <br/> |datetime  <br/> | <br/> |Время начала вызова.  <br/> |
|**EndTime** <br/> |datetime  <br/> | <br/> |Время окончания вызова.  <br/> |
|**CallerPool** <br/> |int  <br/> |Внешняя  <br/> |Пул вызываемого. Ссылка из [таблицы Pool.](pool.md)  <br/> |
|**CalleePool** <br/> |int  <br/> |Внешняя  <br/> |Пул приемник вызовов. Ссылка из [таблицы Pool.](pool.md)  <br/> |
|**CalleePAI** <br/> |int  <br/> |Внешняя  <br/> |URI SIP в удостоверении P-asserted SIP (PAI) конечной точки получения. Ссылка из таблицы [User](user-0.md).  <br/> |
|**CallerURI** <br/> |int  <br/> |Внешняя  <br/> |URI вызываемой. Ссылка из таблицы [User](user-0.md).  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |Внешняя  <br/> |Конечная точка вызываемой точки. Ссылка из [таблицы Endpoint.](endpoint.md)  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |Внешняя  <br/> |Агент пользователя вызываемой точки. Ссылка из [таблицы UserAgent.](useragent.md)  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||Приоритет этого вызова.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Этот столбец является неподготовленным и не используется в Skype для бизнеса Server. Вместо этого эти сведения сообщаются на основе строк для разных мультимедиа. Дополнительные сведения можно найти в таблице [MediaLine.](medialine-0.md) <br/> |
|**CallerPAI** <br/> |int  <br/> |Внешняя  <br/> |P-Asserted-Identity пользователя, выместившего вызов. P-Asserted-Identity (PAI) используется для передачи действительного удостоверения пользователя, который разместил вызов.  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |Внешняя  <br/> |Конечная точка, которая получила вызов.  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |Внешняя  <br/> |Агент пользователя, использованный пользователем, который принял вызов. Агенты пользователя представляют клиентские конечные точки.  <br/> |
|**CalleeUri** <br/> |int  <br/> |Внешняя  <br/> |URI SIP пользователя, который принял вызов.  <br/> |
   

