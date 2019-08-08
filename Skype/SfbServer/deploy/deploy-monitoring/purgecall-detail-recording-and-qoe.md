---
title: Очистка записей и данных качества связи в Skype для бизнеса Server вручную
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: 'Сводка: сведения о том, как вручную удалять записи из баз данных CDR и QoE, используемых в Skype для бизнеса Server.'
ms.openlocfilehash: ba87e05dd72e5da22cfe4e01cd68be1a9fac6242
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239880"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a>Очистка записей и данных качества связи в Skype для бизнеса Server вручную
 
**Сводка:** Сведения о том, как вручную удалять записи из баз данных CDR и QoE, используемых в Skype для бизнеса Server.
  
Базы данных CDR и QoE можно очистить от записей вручную или автоматически. Удаление записей позволяет избежать застоя данных, а также полезно, когда нужно присвоить отчетам начальную базовую линию.
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a>Очистка баз данных CDR и QoE от записей вручную

Администраторы могут настраивать базы данных регистрации вызовов (CDR) и/или качества взаимодействия (QoE) для автоматической очистки старых записей из базы данных; это происходит в том случае, если для указанной базы данных (CDR или QoE) была включена очистка и присутствуют записи, которые находятся в базе данных дольше заданного срока. Например, каждый день в 1:00 администраторы могут настраивать систему, чтобы удалить из базы данных QoE записи старше 60 дней.
  
В дополнение к этой автоматической очистке в Skype для бизнеса Server добавляются два новых командлета &#x2014; Invoke-Кскдрдатабасепурже и Invoke-Кскоедатбасепурже &#x2014;. Эти командлеты позволяют администраторам вручную удалять записи из баз данных CDR и QoE в любое время. Например, чтобы вручную удалить из базы данных CDR все записи старше 10 дней, вы можете использовать команду, аналогичную следующей:
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

В предыдущей команде записи сведений о вызовах и записи диагностических данных старше 10 дней удаляются из базы данных мониторинга на atl-sql-001.litwareinc.com. (Записи регистрации вызовов представляют собой отчеты о пользователях/сеансах. Записи диагностических данных — это журналы диагностики, загружаемые клиентскими приложениями, такими как Skype для бизнеса Server.)
  
Как показано выше, при запуске командлета Invoke-CsCdrDatabasePurge вам следует включить как параметр urgeCallDetaiDataOlderThanDays, так и параметр PurgeDiagnosticDataOlderThanDays. Однако для этих параметров необязательно нужно устанавливать одинаковые значения. Например, можно очистить записи сведений о вызовах старше 10 дней, оставив все записи диагностических данных в базе данных. Для этого установите для Пуржекаллдетаилдатаолдерсандайс значение 10 и Пуржедиагностикдатаолдерсандайс равным 0. Например:
  
```
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
  
```
-Confirm:$False
```

Например:
  
```
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

Если вы сделаете это, запросы подтверждения отображаться не будут, а очистка базы данных будет выполнена немедленно.
  
Чтобы очистить базу данных QoE, используйте командлет Invoke-CsQoEDatabasePurge и укажите возраст (в днях) для удаляемых записей:
  
```
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


