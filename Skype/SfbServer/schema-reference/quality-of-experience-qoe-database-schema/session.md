---
title: Таблица сеансов
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: Каждая запись представляет один сеанс, который включает аудио- или аудио- и видео. Он содержит общую информацию о сеансе. Сеанс определяется как диалоговое окно протокола инициации сеанса аудио или видео(SIP) между двумя конечными точками.
ms.openlocfilehash: bc81bb3c67f91b975643929170354c7b152d2237
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768327"
---
# <a name="session-table"></a>Таблица сеансов
 
Каждая запись представляет один сеанс, который включает аудио- или аудио- и видео. Он содержит общую информацию о сеансе. Сеанс определяется как диалоговое окно протокола инициации сеанса аудио или видео(SIP) между двумя конечными точками.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Ссылки из [таблицы Диалог](dialog.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Ссылки из [таблицы Диалог](dialog.md).  <br/> |
|**ConferenceKey** <br/> |int  <br/> |Foreign  <br/> |Ключ конференции. Ссылки из [таблицы конференций](conference.md).  <br/> |
|**CorrelationKey** <br/> |int  <br/> |Foreign  <br/> |Ключ корреляции. Ссылки из [таблицы SessionCorrelation](sessioncorrelation.md).  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |Категория диалоговое окно; 0 — Skype для бизнеса Server для сервера-посредника; 1 — это сервер-посредник для шлюза PSTN.  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||Флаг, указывающий, выполнял ли вызов обход сервера-посредника.  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||Если это поле присутствует, оно указывает, почему вызов не может быть обойден, даже если идентификаторы обхода совпадают. Для Skype для бизнеса Server определяется только одно значение.  <br/> 0x0001 — неизвестный iD обхода для сетевого адаптера по умолчанию.  <br/> |
|**StartTime** <br/> |datetime  <br/> | <br/> |Время начала вызова.  <br/> |
|**EndTime** <br/> |datetime  <br/> | <br/> |Время окончания вызова.  <br/> |
|**CallerPool** <br/> |int  <br/> |Foreign  <br/> |Пул вызываемого. Ссылки из [таблицы Пул](pool.md).  <br/> |
|**CalleePool** <br/> |int  <br/> |Foreign  <br/> |Пул приемного вызова. Ссылки из [таблицы Пул](pool.md).  <br/> |
|**CalleePAI** <br/> |int  <br/> |Foreign  <br/> |SIP URI в SIP p-asserted identity (PAI) конечной точки получения. Ссылки из [таблицы Пользователей](user-0.md).  <br/> |
|**CallerURI** <br/> |int  <br/> |Foreign  <br/> |URI вызываемой. Ссылки из [таблицы Пользователей](user-0.md).  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |Foreign  <br/> |Конечная точка вызываемой. Ссылки из [таблицы Endpoint](endpoint.md).  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |Foreign  <br/> |Агент пользователя вызываемой. Ссылки из [таблицы UserAgent](useragent.md).  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||Приоритет этого вызова.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Этот столбец был обесценив и не используется в Skype для бизнеса Server. Вместо этого эти сведения сообщаются на основе строки для мультимедиа. Дополнительные сведения можно получить в таблице [MediaLine.](medialine-0.md) <br/> |
|**CallerPAI** <br/> |int  <br/> |Foreign  <br/> |P-Asserted-Identity пользователя, который разместил вызов. P-Asserted-Identity (PAI) используется для передачи истинного удостоверения пользователя, который разместил вызов.  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |Foreign  <br/> |Конечная точка, которая получила вызов.  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |Foreign  <br/> |Агент пользователя, нанятый пользователем, который получил вызов. Агенты пользователей представляют конечный клиентский аппарат.  <br/> |
|**CalleeUri** <br/> |int  <br/> |Foreign  <br/> |SIP URI пользователя, который получил вызов.  <br/> |
   

