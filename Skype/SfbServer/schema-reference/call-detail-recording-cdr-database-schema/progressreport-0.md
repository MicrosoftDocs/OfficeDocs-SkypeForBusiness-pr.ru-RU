---
title: Представление ProgressReport
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: В представлении ProgressReport хранятся сведения о завершенных сеансах. Отчеты о ходе выполнения записываются только для тех звонков и сеансов, которые Lync Server 2013 определяет как полезные для диагностических целей. Это представление впервые было введено в Microsoft Lync Server 2013.
ms.openlocfilehash: 6cc8295e73463fff9d4913efbf9d4844f9316149
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823189"
---
# <a name="progressreport-view"></a>Представление ProgressReport
 
В представлении ProgressReport хранятся сведения о завершенных сеансах. Отчеты о ходе выполнения записываются только для тех звонков и сеансов, которые Lync Server 2013 определяет как полезные для диагностических целей. Это представление впервые было введено в Microsoft Lync Server 2013.
  
> [!NOTE]
> Поля ErrorTime, ErrorReportSeq и ProgressReportSeq ссылаются не на ошибки, а на сообщения, которые указывают состояние вызовов или сообщений. 
  
|**Столбец**|**Тип данных**|**Details**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Время возникновения ошибки. Используется в сочетании с параметром ErrorReportSeq для уникальной идентификации ошибки.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Идентификационный номер ошибки. В сочетании со значением ErrorTime уникально идентифицирует ошибку.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |Идентификатор отчета о ходе выполнения. Используется для различения отчетов о ходе выполнения в рамках одного отчета об ошибках.  <br/> |
|**MsDiagId** <br/> |int  <br/> |ИД диагностики для отчета об ошибках.  <br/> |
|**Source** <br/> |nvarchar(256)  <br/> |Имя сервера, с которого поступило сообщение об ошибке (если отчет был отправлен серверным компонентом).  <br/> |
|**Приложение** <br/> |nvarchar(256)  <br/> |Имя приложения, в котором произошла ошибка (если отчет был отправлен компонентом сервера).  <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |Уникальный идентификатор времени присоединения для различных компонентов, участвующих в конференции.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |Время (в миллисекундах), требуемое определенному компоненту для присоединения к конференции.  <br/> |
|**MsDiagHeader** <br/> |varchar(max)  <br/> |Дополнительные сведения об ошибке.  <br/> |
   

