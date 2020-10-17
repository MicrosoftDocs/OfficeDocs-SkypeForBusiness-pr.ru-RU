---
title: Ручное удаление баз данных регистрации вызовов и качества взаимодействия
description: Ручное удаление баз данных регистрации вызовов и качества взаимодействия.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manually purging the call detail recording and Quality of Experience databases
ms:assetid: 3a3a965b-b861-41a4-b9a8-27184d622c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204812(v=OCS.15)
ms:contentKeyID: 48183859
ms.date: 07/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c7903431d28bf1a829991ce35c2ee7351168b4a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556565"
---
# <a name="manually-purging-the-call-detail-recording-and-quality-of-experience-databases-in-lync-server-2013"></a><span data-ttu-id="4363d-103">Ручное удаление баз данных регистрации вызовов и качества взаимодействия в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4363d-103">Manually purging the call detail recording and Quality of Experience databases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4363d-104">_**Последнее изменение темы:** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="4363d-104">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="4363d-105">Администраторы могут настроить базы данных регистрации вызовов (CDR) и/или качества взаимодействия (QoE) для автоматического удаления старых записей из базы данных. Это происходит в том случае, если для указанной базы данных (CDR или QoE) включена очистка (или), и в базе данных есть записи, которые находятся в базе данных дольше указанного промежутка времени.</span><span class="sxs-lookup"><span data-stu-id="4363d-105">Administrators can configure the Call Detail Recording (CDR) and/or the Quality of Experience (QoE) databases to automatically purge old records from the database; this occurs if purging has been enabled for the specified database (CDR or QoE) and if there are any records that have been in the database longer than the specified amount of time.</span></span> <span data-ttu-id="4363d-106">Например, каждый день в 1:00 администраторы могут настраивать систему, чтобы удалить из базы данных QoE записи старше 60 дней.</span><span class="sxs-lookup"><span data-stu-id="4363d-106">For example, every day at 1:00 AM administrators might configure the system so that QoE records more than 60 days old will be deleted from the QoE database.</span></span>

<span data-ttu-id="4363d-107">В дополнение к этой автоматической очистке в Microsoft Lync Server 2013 добавлены два новых командлета: Invoke-CsCdrDatabasePurge и Invoke-CsQoEDatbasePurge. Эти командлеты позволяют администраторам вручную удалять записи из баз данных CDR и QoE в любое время.</span><span class="sxs-lookup"><span data-stu-id="4363d-107">In addition to that automatic purging, two new cmdlets -- Invoke-CsCdrDatabasePurge and Invoke-CsQoEDatbasePurge -- have been added to Microsoft Lync Server 2013; these cmdlets allow administrators to manually purge records from the CDR and the QoE databases at any time.</span></span> <span data-ttu-id="4363d-108">Например, чтобы вручную удалить из базы данных CDR все записи старше 10 дней, вы можете использовать команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="4363d-108">For example, to manually purge all the records more than 10 days old from the CDR database you can use a command similar to this:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10

<span data-ttu-id="4363d-109">В предыдущей команде записи сведений о вызовах и записи диагностических данных старше 10 дней удаляются из базы данных мониторинга на atl-sql-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="4363d-109">In the preceding command both call detail records and diagnostic data records older than 10 days are deleted from the monitoring database on atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="4363d-110">(Записи регистрации вызовов представляют собой отчеты о пользователях/сеансах.</span><span class="sxs-lookup"><span data-stu-id="4363d-110">(Call detail records are user/session reports.</span></span> <span data-ttu-id="4363d-111">Записи диагностических данных — это журналы диагностики, отправляемые клиентскими приложениями, такими как Lync 2013.)</span><span class="sxs-lookup"><span data-stu-id="4363d-111">Diagnostic data records are diagnostic logs uploaded by client applications such as Lync 2013.)</span></span>

<span data-ttu-id="4363d-112">Как показано выше, при запуске командлета Invoke-CsCdrDatabasePurge вам следует включить как параметр urgeCallDetaiDataOlderThanDays, так и параметр PurgeDiagnosticDataOlderThanDays.</span><span class="sxs-lookup"><span data-stu-id="4363d-112">As shown above, when you run the Invoke-CsCdrDatabasePurge cmdlet you must include both the PurgeCallDetaiDataOlderThanDays and the PurgeDiagnosticDataOlderThanDays parameters.</span></span> <span data-ttu-id="4363d-113">Однако для этих параметров необязательно нужно устанавливать одинаковые значения.</span><span class="sxs-lookup"><span data-stu-id="4363d-113">However, these parameters do not have to be set to the same value.</span></span> <span data-ttu-id="4363d-114">Например, можно очистить записи сведений о вызовах старше 10 дней, оставив все записи диагностических данных в базе данных.</span><span class="sxs-lookup"><span data-stu-id="4363d-114">For example, it's possible to purge call detail records more than 10 days old and yet, at the same time, leave all the diagnostic data records in the database.</span></span> <span data-ttu-id="4363d-115">Для этого задайте для параметра параметру purgecalldetaildataolderthandays значение 10 и Пуржедиагностикдатаолдерсандайс значение 0.</span><span class="sxs-lookup"><span data-stu-id="4363d-115">To do that, set PurgeCallDetailDataOlderThanDays to 10 and PurgeDiagnosticDataOlderThanDays to 0.</span></span> <span data-ttu-id="4363d-116">Например:</span><span class="sxs-lookup"><span data-stu-id="4363d-116">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 0

<span data-ttu-id="4363d-117">По умолчанию при запуске Invoke-CsCdrDatabasePurge для каждой из очищаемых баз данных отображается приглашение, аналогичное данному:</span><span class="sxs-lookup"><span data-stu-id="4363d-117">By default, any time you run Invoke-CsCdrDatabasePurge you will see a prompt similar to this one for each database table that must be purged:</span></span>

    Confirm
    Are you sure you want to perform this action?
    Performing operation "Stored procedure: RtcCleanupDiag" on Target "Target SQL Server:atl-sql-001.litwareinc.com\archinst Database: lcscdr".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All [S] Suspend  [?] Help (default is "Y"):

<span data-ttu-id="4363d-p105">Для выполнения очистки базы данных вам следует ввести Y («Да») или A («Да для всех»). Если вы не хотите отображать эти запросы подтверждения, добавьте в конец вызова Invoke-CsCdrDatabasePurge следующий параметр:</span><span class="sxs-lookup"><span data-stu-id="4363d-p105">You must type either Y (for Yes) or A (for Yes to All) before the database purging will actually take place. If you would prefer to suppress these confirmation prompts, add the following parameter to the end of your call to Invoke-CsCdrDatabasePurge:</span></span>

    -Confirm:$False

<span data-ttu-id="4363d-120">Например:</span><span class="sxs-lookup"><span data-stu-id="4363d-120">For example:</span></span>

    Invoke-CsCdrDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeCallDetailDataOlderThanDays 10 -PurgeDiagnosticDataOlderThanDays 10 -Confirm:$False

<span data-ttu-id="4363d-121">Если вы сделаете это, запросы подтверждения отображаться не будут, а очистка базы данных будет выполнена немедленно.</span><span class="sxs-lookup"><span data-stu-id="4363d-121">If you do that, confirmation prompts will not be displayed, and database purging will immediately be performed.</span></span>

<span data-ttu-id="4363d-122">Чтобы очистить базу данных QoE, используйте командлет Invoke-CsQoEDatabasePurge и укажите возраст (в днях) для удаляемых записей:</span><span class="sxs-lookup"><span data-stu-id="4363d-122">To purge the QoE database, use the Invoke-CsQoEDatabasePurge cmdlet and specify the age (in days) of the records to be deleted:</span></span>

    Invoke-CsQoEDatabasePurge -Identity service:MonitoringDatabase:atl-sql-001.litwareinc.com -PurgeQoEDataOlderThanDays 10

</div>

<span> </span>

</div>

</div>

</div>

