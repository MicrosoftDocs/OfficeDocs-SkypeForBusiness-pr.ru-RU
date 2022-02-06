---
title: Таблица ErrorReport в Skype для бизнеса Server 2015 г.
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: 'В таблице ErrorReport хранится информация об ошибках, которые произошли. Каждая запись соответствует одному случаю возникновения ошибки. Ошибки фиксируются агентом CDR, работающим на сервере переднего плана, или передаются клиентом.'
---

# <a name="errorreport-table-in-skype-for-business-server-2015"></a>Таблица ErrorReport в Skype для бизнеса Server 2015 г.
 
В таблице ErrorReport хранится информация об ошибках, которые произошли. Каждая запись соответствует одному случаю возникновения ошибки. Ошибки фиксируются агентом CDR, работающим на сервере переднего плана, или передаются клиентом.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Primary  <br/> |Дата и время ошибки.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primary  <br/> |ID-номер для определения отчета об ошибке. Используется совместно с **ErrorTime** для уникальной идентификации отчета об ошибке. <br/> |
|**ErrorId** <br/> |int  <br/> |Foreign  <br/> |Уникальный ID типа ошибки. Дополнительные сведения см. в таблице [ErrorDef Skype для бизнеса Server 2015](errordef.md) г. <br/> |
|**FromUserId** <br/> |int  <br/> |Foreign  <br/> |Пользователь, зародивший запрос, вызваввший ошибку. Дополнительные [сведения см](users.md) . в таблице Пользователи. <br/> |
|**ToUserId** <br/> |int  <br/> |Foreign  <br/> |Пользователь назначения для запроса, который вызвал ошибку. Дополнительные [сведения см](users.md) . в таблице Пользователи. <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Foreign  <br/> |URI конференции связан с ошибкой. Дополнительные [сведения см. в таблице ConferenceUris Skype для бизнеса Server 2015](conferenceuris.md) г. Как правило, если ConferenceUriId не является null, то либо FromUserId, либо ToUserId будет null. <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |Foreign  <br/> |В сочетании с параметром **SessionIdSeq** определяет сеанс уникальным образом. Дополнительные сведения см. в таблице [Диалоги Skype для бизнеса Server 2015](dialogs.md) г. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Foreign  <br/> |Идентификатор для идентификации сеанса. В сочетании с параметром **SessionIdTime** определяет сеанс уникальным образом. Дополнительные сведения см. в таблице [Диалоги Skype для бизнеса Server 2015](dialogs.md) г. <br/> |
|**SourceId** <br/> |int  <br/> |Foreign  <br/> |Сервер, отправив отчет об ошибке (если отчет отправляется из компонента сервера). Дополнительные [сведения см. в таблице Servers](servers.md) . <br/> Это поле было внедрено в Microsoft Lync Server 2013.  <br/> |
|**ApplicationId** <br/> |int  <br/> |Foreign  <br/> |Сервер, отправив отчет об ошибке (если отчет отправляется из компонента сервера). Дополнительные [сведения см. в таблице приложения Skype для бизнеса Server 2015](application.md) г. <br/> Это поле было внедрено в Microsoft Lync Server 2013.  <br/> |
|**MsDiagHeader** <br/> |изображение  <br/> | <br/> |Дополнительные сведения об ошибке.  <br/> Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |Foreign  <br/> |Клиентская версия конечной точки, которая отправляет отчет об ошибке. Дополнительные сведения см. в таблице [ClientVersions Skype для бизнеса Server 2015](clientversions.md) г. <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||Является ли отчет об ошибке, захваченный агентом CDR, работающим на переднем сервере или отправленным клиентом.  <br/> |
|**Флаг** <br/> |smallint  <br/> ||Зарезервировано для будущего использования.  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Уникальный идентификатор времени присоединения для различных компонентов, участвующих в конференции.  <br/> Это поле было внедрено в Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Время (в миллисекундах), необходимое для присоединения к конференции определенного компонента.  <br/> Это поле было внедрено в Microsoft Lync Server 2013.  <br/> |
|**ServerId** <br/> |int  <br/> |Foreign  <br/> |Представляет полностью квалифицированное доменное имя сервера, сгенеризовав отчет об ошибке.  <br/> |
|**PoolId** <br/> |int  <br/> |Foreign  <br/> |Представляет полностью квалифицированное доменное имя пула, в котором был создан отчет об ошибке.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Для внутреннего использования службой мониторинга.  <br/> Это поле было введено Skype для бизнеса Server 2015 г.  <br/> |
   

