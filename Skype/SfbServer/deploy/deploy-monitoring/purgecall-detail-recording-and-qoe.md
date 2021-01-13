---
title: Ручная очистка баз данных регистрации вызовов и качества работы в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
description: Сводка. Узнайте, как вручную очистить записи из cdR и баз данных QoE, используемых Skype для бизнеса Server.
ms.openlocfilehash: 2d36af2d06b6d6951e436ea456d4036478278600
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802149"
---
# <a name="manually-purge-the-call-detail-recording-and-quality-of-experience-databases-in-skype-for-business-server"></a><span data-ttu-id="94a85-103">Ручная очистка баз данных регистрации вызовов и качества работы в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="94a85-103">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>
 
<span data-ttu-id="94a85-104">**Сводка:** Узнайте, как вручную очищать записи из баз данных CDR и QoE, используемых Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="94a85-104">**Summary:** Learn how to manually purge records from the CDR and the QoE databases used by Skype for Business Server.</span></span>
  
<span data-ttu-id="94a85-105">Базы данных CDR и QoE можно вручную или автоматически сыметь записи.</span><span class="sxs-lookup"><span data-stu-id="94a85-105">The CDR and QoE databases can be manually or automatically purged of records.</span></span> <span data-ttu-id="94a85-106">Это может быть важно, чтобы данные не устарели или при необходимости сбросить отчеты из исходного базового плана.</span><span class="sxs-lookup"><span data-stu-id="94a85-106">Purging records can be important so that data doesn't become stale or when needing to reset reports from a starting baseline.</span></span>
  
## <a name="manually-purge-records-from-cdr-and-qoe-databases"></a><span data-ttu-id="94a85-107">Ручная очистка записей из баз данных CDR и QoE</span><span class="sxs-lookup"><span data-stu-id="94a85-107">Manually purge records from CDR and QoE databases</span></span>

<span data-ttu-id="94a85-108">Администраторы могут настроить базы данных регистрации вызовов (CDR) и /или качества обслуживания (QoE) для автоматической очистки старых записей из базы данных; это происходит, если для указанной базы данных (CDR или QoE) включена возможность ее и существуют записи, которые были в базе данных дольше указанного времени.</span><span class="sxs-lookup"><span data-stu-id="94a85-108">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time.</span></span> <span data-ttu-id="94a85-109">Например, каждый день в 1:00 администраторы могут настраивать систему, чтобы удалить из базы данных QoE записи старше 60 дней.</span><span class="sxs-lookup"><span data-stu-id="94a85-109">For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>
  
<span data-ttu-id="94a85-110">В дополнение к этой автоматической &#x2014; Invoke-CsCdrDatabasePurge и Invoke-CsQoEDatbasePurge &#x2014; в Skype для бизнеса Server; Эти данные позволяют администраторам вручную очищать записи из баз данных CDR и QoE в любое время.</span><span class="sxs-lookup"><span data-stu-id="94a85-110">In addition to that automatic purging, two new cmdlets &#x2014; Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge &#x2014; have been added to Skype for Business Server; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="94a85-111">Например, чтобы вручную удалить из базы данных CDR все записи старше 10 дней, вы можете использовать команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="94a85-111">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10
```

<span data-ttu-id="94a85-112">В предыдущей команде записи сведений о вызовах и записи диагностических данных старше 10 дней удаляются из базы данных мониторинга на atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="94a85-112">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="94a85-113">(Записи регистрации вызовов представляют собой отчеты о пользователях/сеансах.</span><span class="sxs-lookup"><span data-stu-id="94a85-113">(Call detail records are user/session reports.</span></span> <span data-ttu-id="94a85-114">Записи диагностических данных — это журналы диагностики, загруженные клиентских приложений, таких как Skype для бизнеса Server.)</span><span class="sxs-lookup"><span data-stu-id="94a85-114">Diagnostic data records are diagnostic logs uploaded by client applications such as Skype for Business Server.)</span></span>
  
<span data-ttu-id="94a85-115">Как показано выше, при запуске командлета Invoke-CsCdrDatabasePurge вам следует включить как параметр urgeCallDetaiDataOlderThanDays, так и параметр PurgeDiagnosticDataOlderThanDays.</span><span class="sxs-lookup"><span data-stu-id="94a85-115">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="94a85-116">Однако для этих параметров необязательно нужно устанавливать одинаковые значения.</span><span class="sxs-lookup"><span data-stu-id="94a85-116">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="94a85-117">Например, можно очистить записи сведений о вызовах старше 10 дней, оставив все записи диагностических данных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="94a85-117">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="94a85-118">Для этого установите для PurgeCallDetailDataOlderThanDays 10, а для PurgeDiagnosticDataOlderThanDays — 0.</span><span class="sxs-lookup"><span data-stu-id="94a85-118">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="94a85-119">Например:</span><span class="sxs-lookup"><span data-stu-id="94a85-119">For example:</span></span>
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0
```

<span data-ttu-id="94a85-120">По умолчанию при запуске Invoke-CsCdrDatabasePurge для каждой из очищаемых баз данных отображается приглашение, аналогичное данному:</span><span class="sxs-lookup"><span data-stu-id="94a85-120">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>
  
<pre>
Confirm
Are you sure you want to perform this action?
Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
[Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):
</pre>

<span data-ttu-id="94a85-p106">Для выполнения очистки базы данных вам следует ввести Y («Да») или A («Да для всех»). Если вы не хотите отображать эти запросы подтверждения, добавьте в конец вызова Invoke-CsCdrDatabasePurge следующий параметр:</span><span class="sxs-lookup"><span data-stu-id="94a85-p106">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place. If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>
  
```powershell
-Confirm:$False
```

<span data-ttu-id="94a85-123">Например:</span><span class="sxs-lookup"><span data-stu-id="94a85-123">For example:</span></span>
  
```powershell
Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False
```

<span data-ttu-id="94a85-124">Если вы сделаете это, запросы подтверждения отображаться не будут, а очистка базы данных будет выполнена немедленно.</span><span class="sxs-lookup"><span data-stu-id="94a85-124">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>
  
<span data-ttu-id="94a85-125">Чтобы очистить базу данных QoE, используйте командлет Invoke-CsQoEDatabasePurge и укажите возраст (в днях) для удаляемых записей:</span><span class="sxs-lookup"><span data-stu-id="94a85-125">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>
  
```powershell
Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10
```


