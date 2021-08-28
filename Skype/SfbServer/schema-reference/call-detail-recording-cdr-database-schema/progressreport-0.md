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
ms.localizationpriority: medium
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: В представлении ProgressReport хранятся сведения о завершенных сеансах. Отчеты о ходе выполнения записываются только для тех звонков и сеансов, которые Lync Server 2013 определяет как полезные для диагностических целей. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: 8e21b83b1ca6c4856ba31a579e4a7999ba8b31a6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623541"
---
# <a name="progressreport-view"></a>Представление ProgressReport
 
В представлении ProgressReport хранятся сведения о завершенных сеансах. Отчеты о ходе выполнения записываются только для тех звонков и сеансов, которые Lync Server 2013 определяет как полезные для диагностических целей. Это представление было представлено в Microsoft Lync Server 2013.
  
> [!NOTE]
> Поля ErrorTime, ErrorReportSeq и ProgressReportSeq ссылаются не на ошибки, а на сообщения, которые указывают состояние вызовов или сообщений. 
  
|**Столбец**|**Тип данных**|**Details**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Время возникновения ошибки. Используется в сочетании с параметром ErrorReportSeq для уникальной идентификации ошибки.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Идентификационный номер ошибки. В сочетании со значением ErrorTime уникально идентифицирует ошибку.  <br/> |
|**ProgressReportSeq** <br/> |int  <br/> |Идентификатор отчета о ходе выполнения. Используется для различения отчетов о ходе выполнения в рамках одного отчета об ошибках.  <br/> |
|**MsDiagId** <br/> |int  <br/> |ИД диагностики для отчета об ошибках.  <br/> |
|**Source** <br/> |nvarchar (256)  <br/> |Имя сервера, с которого поступило сообщение об ошибке (если отчет был отправлен серверным компонентом).  <br/> |
|**Приложение** <br/> |nvarchar (256)  <br/> |Имя приложения, в котором произошла ошибка (если отчет был отправлен компонентом сервера).  <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |Уникальный идентификатор времени присоединения для различных компонентов, участвующих в конференции.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> |Время (в миллисекундах), требуемое определенному компоненту для присоединения к конференции.  <br/> |
|**MsDiagHeader** <br/> |varchar (max)  <br/> |Дополнительные сведения об ошибке.  <br/> |
   

