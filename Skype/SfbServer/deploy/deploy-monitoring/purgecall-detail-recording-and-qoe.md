---
title: Вручную очищают базы данных данных о детализации вызовов и качестве Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: Сводка. Узнайте, как вручную очищать записи из баз данных CDR и QoE, используемых Skype для бизнеса Server.
ms.openlocfilehash: edaeb5d34fefe1ea8f50da4d7bb4bb31c94c62b5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851603"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a>Вручную очищают базы данных данных о детализации вызовов и качестве Skype для бизнеса Server
 
**Сводка:** Узнайте, как вручную очищать записи из баз данных CDR и QoE, используемых Skype для бизнеса Server.
  
Базы данных CDR и QoE можно вручную или автоматически сдуть записи. Чистка записей может иметь важное значение, чтобы данные не устарели или при необходимости сброса отчетов из начального базового плана.
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>Вручную очищать записи из баз данных CDR и QoE

Администраторы могут настраивать базы данных записи окружных данных (CDR) и/или базы данных "Качество работы" (QoE), чтобы автоматически очищать старые записи из базы данных; это происходит, если для указанной базы данных (CDR или QoE) включена чистка, а также если в базе данных есть записи дольше указанного времени. Например, каждый день в 1:00 администраторы могут настраивать систему, чтобы удалить из базы данных QoE записи старше 60 дней.
  
Помимо автоматической чистки в &#x2014; Invoke-CsCdrDatabasePurge и Invoke-CsQoEDatbasePurge &#x2014; добавлены два новых Skype для бизнеса Server; эти комлеты позволяют администраторам вручную очищать записи из баз данных CDR и QoE в любое время. Например, чтобы вручную удалить из базы данных CDR все записи старше 10 дней, вы можете использовать команду, аналогичную следующей:
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

В предыдущей команде записи сведений о вызовах и записи диагностических данных старше 10 дней удаляются из базы данных мониторинга на atl-sql-001.litwareinc.com. (Записи регистрации вызовов представляют собой отчеты о пользователях/сеансах. Диагностические записи данных — это диагностические журналы, загруженные клиентными приложениями, такими как Skype для бизнеса Server.)
  
Как показано выше, при запуске командлета Invoke-CsCdrDatabasePurge вам следует включить как параметр urgeCallDetaiDataOlderThanDays, так и параметр PurgeDiagnosticDataOlderThanDays. Однако для этих параметров необязательно нужно устанавливать одинаковые значения. Например, можно очистить записи сведений о вызовах старше 10 дней, оставив все записи диагностических данных в базе данных. Для этого установите purgeCallDetailDataOlderThanDays до 10, а PurgeDiagnosticDataOlderThanDays — 0. Например:
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

По умолчанию при запуске Invoke-CsCdrDatabasePurge для каждой из очищаемых баз данных отображается приглашение, аналогичное данному:
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

Для выполнения очистки базы данных вам следует ввести Y («Да») или A («Да для всех»). Если вы не хотите отображать эти запросы подтверждения, добавьте в конец вызова Invoke-CsCdrDatabasePurge следующий параметр:
  
```powershell
-Confirm:$False
```

Например:
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

Если вы сделаете это, запросы подтверждения отображаться не будут, а очистка базы данных будет выполнена немедленно.
  
Чтобы очистить базу данных QoE, используйте командлет Invoke-CsQoEDatabasePurge и укажите возраст (в днях) для удаляемых записей:
  
```powershell
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


