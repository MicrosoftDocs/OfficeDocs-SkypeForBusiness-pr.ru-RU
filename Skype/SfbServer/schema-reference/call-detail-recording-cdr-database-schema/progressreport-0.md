---
title: Представление ProgressReport
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: Представление ProgressReport хранит сведения о завершенных сеансах. Отчеты о состоянии записываются только для вызовов и сеансов с Lync Server 2013 определяет, могут оказаться полезными для диагностики. В этом представлении была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: 5f7cbba2580b83a65dbce00588f3c567317f4df4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891119"
---
# <a name="progressreport-view"></a>Представление ProgressReport
 
Представление ProgressReport хранит сведения о завершенных сеансах. Отчеты о состоянии записываются только для вызовов и сеансов с Lync Server 2013 определяет, могут оказаться полезными для диагностики. В этом представлении была введена в Microsoft Lync Server 2013.
  
> [!NOTE]
> Поля ErrorTime, ErrorReportSeq и progressreportseq могут указывать не обязательно ссылаются на ошибки, но к сообщениям, указывающим состояние вызовов или сообщений. 
  
|**Столбец**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Ошибки времени. Используется в сочетании с ErrorReportSeq для уникальной идентификации ошибку.  <br/> |
|**ErrorReportSeq** <br/> |целое  <br/> |Номер идентификатора для определения ошибки. Используется в сочетании с ErrorTime для уникальной идентификации ошибку.  <br/> |
|**Progressreportseq могут относиться** <br/> |целое  <br/> |Идентификатор для идентификации отчет о ходе выполнения. Используется для различения отчеты о состоянии же сообщения об ошибке.  <br/> |
|**MsDiagId** <br/> |целое  <br/> |КОД диагностики для отчета об ошибках.  <br/> |
|**Источник** <br/> |nvarchar(256)  <br/> |Имя сервера, на котором произошла ошибка (Если отчет был отправлен серверным компонентом).  <br/> |
|**Application** <br/> |nvarchar(256)  <br/> |Имя приложения, в котором произошла ошибка (Если отчет был отправлен серверным компонентом).  <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |Уникальный идентификатор времени присоединения для разных компонентов, задействованных в конференции.  <br/> |
|**SessionSetupTime** <br/> |целое  <br/> |Время (в миллисекундах), требуемое определенному компоненту для присоединения к конференции.  <br/> |
|**MsDiagHeader** <br/> |varchar(max)  <br/> |Дополнительные сведения об ошибке.  <br/> |
   

