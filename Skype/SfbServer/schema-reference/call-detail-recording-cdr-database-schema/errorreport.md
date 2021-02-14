---
title: Таблица ErrorReport в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: В таблице ErrorReport хранится информация о произошедших ошибках. Каждая запись соответствует одному случаю возникновения ошибки. Ошибки фиксируются агентом CDR, работающим на сервере переднего плана, или передаются клиентом.
ms.openlocfilehash: b2f81df1134294185124d78b90c2e4f639575ded
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821679"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>Таблица ErrorReport в Skype для бизнеса Server 2015
 
В таблице ErrorReport хранится информация о произошедших ошибках. Каждая запись соответствует одному случаю возникновения ошибки. Ошибки фиксируются агентом CDR, работающим на сервере переднего плана, или передаются клиентом.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Primary  <br/> |Дата и время ошибки.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primary  <br/> |Идентификация отчета об ошибках. Используется в сочетании с **ErrorTime для** уникальной идентификации отчета об ошибках. <br/> |
|**ErrorId** <br/> |int  <br/> |Внешняя  <br/> |Уникальный ИД типа ошибки. Дополнительные сведения см. в таблице [ErrorDef в Skype для бизнеса Server 2015.](errordef.md) <br/> |
|**FromUserId** <br/> |int  <br/> |Внешняя  <br/> |Пользователь, который вызвал запрос, вызваввший ошибку. Дополнительные [сведения см.](users.md) в таблице "Пользователи". <br/> |
|**ToUserId** <br/> |int  <br/> |Внешняя  <br/> |Пользователь назначения для запроса, который вызвал ошибку. Дополнительные [сведения см.](users.md) в таблице "Пользователи". <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Внешняя  <br/> |URI конференции, связанный с ошибкой. Дополнительные сведения см. в таблице [ConferenceUris в Skype для бизнеса Server 2015.](conferenceuris.md) Как правило, если conferenceUriId не имеет null, то для FromUserId или ToUserId будет задано null. <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |Внешняя  <br/> |В сочетании с параметром **SessionIdSeq** определяет сеанс уникальным образом. Дополнительные сведения см. в таблице [Dialogs в Skype для бизнеса Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Внешняя  <br/> |Идентификатор для идентификации сеанса. В сочетании с параметром **SessionIdTime** определяет сеанс уникальным образом. Дополнительные сведения см. в таблице [Dialogs в Skype для бизнеса Server 2015.](dialogs.md) <br/> |
|**SourceId** <br/> |int  <br/> |Внешняя  <br/> |Сервер, отправив отчет об ошибке (если отчет отправляется из компонента сервера). Дополнительные [сведения см. в](servers.md) таблице "Серверы". <br/> Это поле было впервые введено в Microsoft Lync Server 2013.  <br/> |
|**ApplicationId** <br/> |int  <br/> |Внешняя  <br/> |Сервер, отправив отчет об ошибке (если отчет отправляется из компонента сервера). Дополнительные сведения см. в таблице приложений [в Skype для бизнеса Server 2015.](application.md) <br/> Это поле было впервые введено в Microsoft Lync Server 2013.  <br/> |
|**MsDiagHeader** <br/> |изображение  <br/> | <br/> |Дополнительные сведения об ошибке.  <br/> Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |Внешняя  <br/> |Версия клиента конечной точки, отправив отчет об ошибках. Дополнительные сведения см. в таблице [ClientVersions в Skype для бизнеса Server 2015.](clientversions.md) <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||Отчет об ошибках, который захватывает агент CDR, запущенный на сервере переднего сервера, или отправляется клиентом.  <br/> |
|**Flag** <br/> |smallint  <br/> ||Зарезервировано для будущего использования.  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Уникальный идентификатор времени присоединения для различных компонентов, участвующих в конференции.  <br/> Это поле было впервые введено в Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Время (в миллисекундах), необходимое для присоединения к конференции определенного компонента.  <br/> Это поле было впервые введено в Microsoft Lync Server 2013.  <br/> |
|**ServerId** <br/> |int  <br/> |Внешняя  <br/> |Представляет полное доменное имя сервера, который вызвал отчет об ошибках.  <br/> |
|**PoolId** <br/> |int  <br/> |Внешняя  <br/> |Представляет полное доменное имя пула, в котором был создан отчет об ошибках.  <br/> |
|**LastModifiedTime** <br/> |Дата и время  <br/> ||Для внутреннего использования службой мониторинга.  <br/> Это поле было впервые введено в Skype для бизнеса Server 2015.  <br/> |
   

