---
title: Таблица Session
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: Каждая запись представляет один сеанс, который включает в себя аудио- или аудио и видео. Здесь приводятся общие сведения о сеансе. Сеанс определяется как аудио- или видеозвонка Session Initiation Protocol (SIP) диалоговое окно с между двумя конечными точками.
ms.openlocfilehash: 7a0ea3f9753529c22299ef46017b863c314319b5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881380"
---
# <a name="session-table"></a>Таблица Session
 
Каждая запись представляет один сеанс, который включает в себя аудио- или аудио и видео. Здесь приводятся общие сведения о сеансе. Сеанс определяется как аудио- или видеозвонка Session Initiation Protocol (SIP) диалоговое окно с между двумя конечными точками.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Ссылка из [таблицы Dialog table](dialog.md).  <br/> |
|**SessionSeq** <br/> |целое  <br/> |Primary  <br/> |Ссылка из [таблицы Dialog table](dialog.md).  <br/> |
|**ConferenceKey** <br/> |целое  <br/> |Внешний  <br/> |Ключ конференции. Ссылка из [таблицы конференции](conference.md).  <br/> |
|**CorrelationKey** <br/> |целое  <br/> |Внешний  <br/> |Ключ корреляции. Ссылка из [Таблица sessioncorrelation](sessioncorrelation.md).  <br/> |
|**DialogCategory** <br/> |бит  <br/> | <br/> |Категория диалога; 0 — Скайп для Business Server до сервера-посредника; 1 — сервер-посредник ветвь шлюза ТСОП.  <br/> |
|**MediationServerBypassFlag** <br/> |бит  <br/> ||Флаг, указывающий ли вызов обход сервера-посредника или нет.  <br/> |
|**MediaBypassWarningFlag** <br/> |целое  <br/> ||В этом поле, если этот параметр указан, указывает, почему звонка не обход сервера-посредника даже при совпадении идентификаторы сервера-посредника. Для Скайп Business Server определяется только одно значение.  <br/> 0x0001 — Неизвестный идентификатор обхода для сетевого адаптера по умолчанию.  <br/> |
|**StartTime** <br/> |datetime  <br/> | <br/> |Время начала вызова.  <br/> |
|**EndTime** <br/> |datetime  <br/> | <br/> |Время окончания вызова.  <br/> |
|**CallerPool** <br/> |целое  <br/> |Внешний  <br/> |Пула вызывающего абонента. Ссылка из [таблицы пула](pool.md).  <br/> |
|**CalleePool** <br/> |целое  <br/> |Внешний  <br/> |Пул получателя вызова. Ссылка из [таблицы пула](pool.md).  <br/> |
|**CalleePAI** <br/> |целое  <br/> |Внешний  <br/> |URI SIP в SIP удостоверения pai (PAI) получающей конечной точки. Ссылка из [таблицы пользователей](user-0.md).  <br/> |
|**CallerURI** <br/> |целое  <br/> |Внешний  <br/> |URI вызывающего абонента. Ссылка из [таблицы пользователей](user-0.md).  <br/> |
|**CallerEndpoint** <br/> |целое  <br/> |Внешний  <br/> |Конечная точка вызывающего абонента. Ссылка из [таблицы конечной точки](endpoint.md).  <br/> |
|**CallerUserAgent** <br/> |бит  <br/> |Внешний  <br/> |Агент пользователя вызывающего абонента. Ссылка из [таблицы UserAgent](useragent.md).  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||Приоритет вызова.  <br/> |
|**ClassifiedPoorCall** <br/> |бит  <br/> ||Этот столбец был удален и в Скайп Business Server не используется. Вместо этого эти сведения отчета о базовых классов строки-media. Обратитесь к [таблице MediaLine](medialine-0.md) для получения дополнительных сведений. <br/> |
|**CallerPAI** <br/> |целое  <br/> |Внешний  <br/> |P-Asserted-Identity пользователя, выполнившего звонок. P-Asserted-Identity (PAI) используется для передачи значение true, идентификатор пользователя, выполнившего звонок.  <br/> |
|**CalleeEndpoint** <br/> |целое  <br/> |Внешний  <br/> |Конечная точка, принявшего звонок.  <br/> |
|**CalleeUserAgent** <br/> |целое  <br/> |Внешний  <br/> |Агент пользователя используемого пользователем, принявшим вызов. Агенты пользователей представления устройства конечная точка клиента.  <br/> |
|**CalleeUri** <br/> |целое  <br/> |Внешний  <br/> |URI-адрес SIP пользователя, принявшего звонок.  <br/> |
   

