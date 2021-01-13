---
title: Таблица ProgressReport
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
ms.assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
description: Отчеты о ходе выполнения строятся на основе данных, отправляемых клиентом в базу данных после завершения вызова или сеанса. Отчеты о ходе выполнения будут записаны только для звонков и сеансов, которые Skype для бизнеса Server 2015 определяет как полезные для диагностических целей.
ms.openlocfilehash: 4169ab029c0ce491b77b39735e309e102ac6e356
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823179"
---
# <a name="progressreport-table"></a>Таблица ProgressReport
 
Отчеты о ходе выполнения строятся на основе данных, отправляемых клиентом в базу данных после завершения вызова или сеанса. Отчеты о ходе выполнения будут записаны только для звонков и сеансов, которые Skype для бизнеса Server 2015 определяет как полезные для диагностических целей.
  
Поля ErrorTime, ErrorReportSeq и ProgressReportSeq ссылаются не на ошибки, а на сообщения, которые указывают состояние вызовов или сообщений.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Первичный, внешний  <br/> |Дата и время отчета об ошибках хода выполнения, который содержит этот отчет о ходе выполнения. Дополнительные сведения см. в таблице [ErrorReport в Skype для бизнеса Server 2015.](errorreport.md) <br/> |
|**ErrorId** <br/> |int  <br/> |Первичный, внешний  <br/> |Идентификатор, используемый вместе с ErrorTime и ProgressReportSeq для однозначного определения отчета о ходе выполнения. Дополнительные сведения см. в таблице [ErrorReport в Skype для бизнеса Server 2015.](errorreport.md) <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Первичный, внешний  <br/> |Идентификатор отчета об ошибках. ErrorReporSeq используется вместе с ErrorTime для однозначного определения отчета об ошибках. Дополнительные сведения см. в таблице [ErrorReport в Skype для бизнеса Server 2015](errorreport.md) <br/> Это поле было впервые введено в Microsoft Lync Server 2013.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |Primary  <br/> |Идентификатор отчета о ходе выполнения. Используется вместе с ErrorTime и ErrorReportSeq для однозначного определения отчета о ходе выполнения.  <br/> |
|**MsDiagId** <br/> |int  <br/> ||Диагностический идентификатор отчета о ходе выполнения.  <br/> Это поле было впервые введено в Microsoft Lync Server 2013.  <br/> |
|**SourceId** <br/> |int  <br/> |Внешняя  <br/> |Сервер, отправив отчет об ошибке (если отчет был отправлен из компонента сервера). Дополнительные [сведения см. в](servers.md) таблице "Серверы". Это поле было впервые введено в Microsoft Lync Server 2013. <br/> |
|**ApplicationId** <br/> |int  <br/> ||Процесс Lync Server, к которому относится отчет. Дополнительные сведения см. в таблице приложений.  <br/> |
|**Detail** <br/> |изображение  <br/> ||Сведения о выполнении сохраняются в двоичном формате для экономии места. Эти данные можно преобразовать в текстовый формат с помощью следующего синтаксиса:  <br/> cast(cast(Detail as varbinary(max)) as varchar(max))  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||Уникальный идентификатор, который сопоставляет сведения о времени присоединения для разных компонентов, вовлеченных в конференцию.  <br/> Это поле было впервые введено в Microsoft Lync Server 2013.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||Время (в миллисекундах) для присоединения к конференции конкретного компонента.  <br/> Это поле было впервые введено в Microsoft Lync Server 2013.  <br/> |
   

