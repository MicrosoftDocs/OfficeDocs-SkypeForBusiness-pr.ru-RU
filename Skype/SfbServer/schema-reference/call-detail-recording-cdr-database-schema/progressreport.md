---
title: Таблица ProgressReport
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: Отчеты о ходе выполнения строятся на основе данных, отправляемых клиентом в базу данных после завершения вызова или сеанса. Отчеты о ходе работы будут писаться только для звонков и сеансов, которые Skype для бизнеса Server 2015 г. могут быть полезны для диагностических целей.
ms.openlocfilehash: 7004361a1f66232df3827c3276a624d2699ac50b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856466"
---
# <a name="progressreport-table"></a>Таблица ProgressReport
 
Отчеты о ходе выполнения строятся на основе данных, отправляемых клиентом в базу данных после завершения вызова или сеанса. Отчеты о ходе работы будут писаться только для звонков и сеансов, которые Skype для бизнеса Server 2015 г. могут быть полезны для диагностических целей.
  
Поля ErrorTime, ErrorReportSeq и ProgressReportSeq ссылаются не на ошибки, а на сообщения, которые указывают состояние вызовов или сообщений.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Первичный, внешний  <br/> |Дата и время отчета об ошибках хода выполнения, который содержит этот отчет о ходе выполнения. Дополнительные сведения см. в таблице [ErrorReport Skype для бизнеса Server 2015](errorreport.md) г. <br/> |
|**ErrorId** <br/> |int  <br/> |Первичный, внешний  <br/> |Идентификатор, используемый вместе с ErrorTime и ProgressReportSeq для однозначного определения отчета о ходе выполнения. Дополнительные сведения см. в таблице [ErrorReport Skype для бизнеса Server 2015](errorreport.md) г. <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Первичный, внешний  <br/> |Идентификатор отчета об ошибках. ErrorReporSeq используется вместе с ErrorTime для однозначного определения отчета об ошибках. Дополнительные сведения см. в таблице [ErrorReport Skype для бизнеса Server 2015](errorreport.md) г. <br/> Это поле было внедрено в Microsoft Lync Server 2013.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |Primary  <br/> |Идентификатор отчета о ходе выполнения. Используется вместе с ErrorTime и ErrorReportSeq для однозначного определения отчета о ходе выполнения.  <br/> |
|**MsDiagId** <br/> |int  <br/> ||Диагностический идентификатор отчета о ходе выполнения.  <br/> Это поле было внедрено в Microsoft Lync Server 2013.  <br/> |
|**SourceId** <br/> |int  <br/> |Foreign  <br/> |Сервер, отправив отчет об ошибке (если отчет был отправлен из компонента сервера). Дополнительные сведения см. в таблице [Servers.](servers.md) Это поле было внедрено в Microsoft Lync Server 2013. <br/> |
|**ApplicationId** <br/> |int  <br/> ||Процесс Lync Server, к которому относится отчет. Дополнительные сведения см. в таблице приложений.  <br/> |
|**Detail** <br/> |изображение  <br/> ||Сведения о выполнении сохраняются в двоичном формате для экономии места. Эти данные можно преобразовать в текстовый формат с помощью следующего синтаксиса:  <br/> cast(cast(Detail as varbinary(max)) as varchar(max))  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Уникальный идентификатор, который сопоставляет сведения о времени присоединения для разных компонентов, вовлеченных в конференцию.  <br/> Это поле было внедрено в Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Время (в миллисекундах) для присоединения к конференции конкретного компонента.  <br/> Это поле было внедрено в Microsoft Lync Server 2013.  <br/> |
   

