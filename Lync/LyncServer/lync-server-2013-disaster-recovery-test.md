---
title: 'Lync Server 2013: тест аварийного восстановления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2d36ec6ad1afb8c41c7c5f614e90e03ce4d9282
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528956"
---
# <a name="disaster-recovery-test-in-lync-server-2013"></a><span data-ttu-id="43327-102">Тест аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43327-102">Disaster recovery test in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43327-103">_**Последнее изменение темы:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="43327-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="43327-104">Выполните восстановление системы для сервера пула Lync Server 2013, чтобы протестировать задокументированный процесс аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="43327-104">Perform a system recovery for a Lync Server 2013 pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="43327-105">Этот тест имитирует неисправность оборудования для одного сервера и поможет гарантировать доступность ресурсов, планов и данных для восстановления.</span><span class="sxs-lookup"><span data-stu-id="43327-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data is available for recovery.</span></span> <span data-ttu-id="43327-106">Постарайтесь попытаться поворачивать тест каждый месяц, чтобы ваша организация каждый раз протестировать сбой другого сервера или другого оборудования.</span><span class="sxs-lookup"><span data-stu-id="43327-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span>

<span data-ttu-id="43327-107">Обратите внимание, что расписание, в соответствии с которым организации выполняют тестирование аварийного восстановления, будет отличаться.</span><span class="sxs-lookup"><span data-stu-id="43327-107">Note that the schedule by which organizations perform Disaster Recovery testing will vary.</span></span> <span data-ttu-id="43327-108">Очень важно, чтобы тестирование аварийного восстановления не проигнорировалось или не было пропущено.</span><span class="sxs-lookup"><span data-stu-id="43327-108">It is very important that disaster recovery testing is not ignored or neglected.</span></span>

<div>


<span data-ttu-id="43327-109">Экспорт топологии, политик и параметров конфигурации Lync Server 2013 в файл.</span><span class="sxs-lookup"><span data-stu-id="43327-109">Export your Lync Server 2013 topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="43327-110">Помимо прочего, этот файл можно использовать для восстановления этих сведений в хранилище Центрального управления после обновления, сбоя оборудования или другой проблемы, приводящей к потере данных.</span><span class="sxs-lookup"><span data-stu-id="43327-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="43327-111">Импортируйте топологию, политики и параметры конфигурации Lync Server 2013 в центральное хранилище управления или на локальный компьютер, как показано в следующих командах:</span><span class="sxs-lookup"><span data-stu-id="43327-111">Import your Lync Server 2013 topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span>

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

<span data-ttu-id="43327-112">Для резервного копирования рабочих данных Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="43327-112">To back up production Lync Server 2013 data:</span></span>

  - <span data-ttu-id="43327-113">Выполните резервное копирование баз данных RTC и LCSLog, используя стандартный процесс резервного копирования SQL Server для дампа базы данных в файл или устройство для хранения на магнитной ленте.</span><span class="sxs-lookup"><span data-stu-id="43327-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>

  - <span data-ttu-id="43327-114">Использование стороннего приложения резервного копирования для резервного копирования данных в файл или на ленту.</span><span class="sxs-lookup"><span data-stu-id="43327-114">Use third-party backup application to back up the data to file or to tape.</span></span>

  - <span data-ttu-id="43327-115">Используйте командлет Export-CsUserData, чтобы создать экспорт XML всей базы данных RTC.</span><span class="sxs-lookup"><span data-stu-id="43327-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>

  - <span data-ttu-id="43327-116">Использование резервного копирования файловой системы или стороннего производителя для резервного копирования контента собраний и журналов соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="43327-116">Use the file system backup or third-party to back up meeting content and compliance logs.</span></span>

  - <span data-ttu-id="43327-117">Используйте средство командной строки Export-CsConfiguration для резервного копирования параметров Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="43327-117">Use the Export-CsConfiguration command-line tool to back up Lync Server 2013 settings.</span></span>

<span data-ttu-id="43327-118">Первый шаг процедуры отработки отказа включает принудительное перемещение пользователей из рабочего пула в пул аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="43327-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span>

<span data-ttu-id="43327-119">Это обязательное перемещение, так как производственный пул не будет доступен для принятия на перемещение пользователя.</span><span class="sxs-lookup"><span data-stu-id="43327-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="43327-120">В дополнение к обновлению записи в базе данных сервера RTC SQL Server 2013, можно изменить атрибут объекта учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="43327-120">The Lync Server 2013 move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span>

<span data-ttu-id="43327-121">Эти данные можно восстановить с помощью следующих двух процессов:</span><span class="sxs-lookup"><span data-stu-id="43327-121">This data can be restored through the following two processes:</span></span>

  - <span data-ttu-id="43327-122">Базу данных RTC можно восстановить из исходного устройства резервного копирования на рабочем сервере SQL Server с помощью стандартного процесса восстановления SQL Server или с помощью стороннего средства резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="43327-122">RTC database can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

  - <span data-ttu-id="43327-123">Данные контакта пользователя можно восстановить с помощью служебной программы DBIMPEXP.exe с помощью XML-файла, созданного при экспорте в рабочую среду SQL Server.</span><span class="sxs-lookup"><span data-stu-id="43327-123">User contact data can be restored with the DBIMPEXP.exe utility using the XML file that was created from the production SQL Server export.</span></span>

<span data-ttu-id="43327-124">После восстановления этих данных пользователи могут эффективно подключаться к пулу Lync Server 2013 с аварийным восстановлением и работать как обычно.</span><span class="sxs-lookup"><span data-stu-id="43327-124">After this data is restored, users can effectively connect to the Disaster Recovery Lync Server 2013 pool, and operate as usual.</span></span>

<span data-ttu-id="43327-125">Чтобы разрешить пользователям подключаться к пулу 2013 Lync Server с аварийным восстановлением, потребуется изменение записи DNS.</span><span class="sxs-lookup"><span data-stu-id="43327-125">To enable users to connect to the Disaster Recovery Lync Server 2013 pool, a DNS record change will be required.</span></span>

<span data-ttu-id="43327-126">На рабочий пул Lync Server 2013 будут ссылаться клиенты, использующие записи DNS SRV для автоматической настройки и DNS:</span><span class="sxs-lookup"><span data-stu-id="43327-126">The production Lync Server 2013 pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

  - <span data-ttu-id="43327-127">SRV: \_ SIP. \_ аутентифицирован.\<domain\></span><span class="sxs-lookup"><span data-stu-id="43327-127">SRV: \_sip.\_tls.\<domain\></span></span> <span data-ttu-id="43327-128">/КНАМЕ: SIP.\<domain\></span><span class="sxs-lookup"><span data-stu-id="43327-128">/CNAME: SIP.\<domain\></span></span>

  - <span data-ttu-id="43327-129">CNAME: SIP.\<domain\></span><span class="sxs-lookup"><span data-stu-id="43327-129">CNAME: SIP.\<domain\></span></span> <span data-ttu-id="43327-130">/cvc-pool-1.\<domain\></span><span class="sxs-lookup"><span data-stu-id="43327-130">/cvc-pool-1.\<domain\></span></span>

<span data-ttu-id="43327-131">Чтобы упростить отработку отказа, эту запись CNAME необходимо обновить, чтобы она ссылалась на полное доменное имя Дрокспул:</span><span class="sxs-lookup"><span data-stu-id="43327-131">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

  - <span data-ttu-id="43327-132">CNAME: SIP.\<domain\></span><span class="sxs-lookup"><span data-stu-id="43327-132">CNAME: SIP.\<domain\></span></span> <span data-ttu-id="43327-133">/дрокспул.\<domain\></span><span class="sxs-lookup"><span data-stu-id="43327-133">/DROCSPool.\<domain\></span></span>

  - <span data-ttu-id="43327-134">Панели.\<domain\></span><span class="sxs-lookup"><span data-stu-id="43327-134">Sip.\<domain\></span></span>

  - <span data-ttu-id="43327-135">Передаче.\<domain\></span><span class="sxs-lookup"><span data-stu-id="43327-135">AV.\<domain\></span></span>

  - <span data-ttu-id="43327-136">WebConf.\<domain\></span><span class="sxs-lookup"><span data-stu-id="43327-136">webconf.\<domain\></span></span>

  - <span data-ttu-id="43327-137">Окссервицес.\<domain\></span><span class="sxs-lookup"><span data-stu-id="43327-137">OCSServices.\<domain\></span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="43327-138">Подробные процедуры администрирования и управления приведены в статье <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">резервное копирование и восстановление Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="43327-138">For detailed administration and management procedures, see <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Backing up and restoring Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="43327-139">См. также</span><span class="sxs-lookup"><span data-stu-id="43327-139">See Also</span></span>


[<span data-ttu-id="43327-140">Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43327-140">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[<span data-ttu-id="43327-141">Командлеты резервного копирования и высокой доступности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43327-141">Backup and high availability cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[<span data-ttu-id="43327-142">Import — CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="43327-142">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="43327-143">Резервное копирование и восстановление Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43327-143">Backing up and restoring Lync Server 2013</span></span>](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[<span data-ttu-id="43327-144">Управление аварийным восстановлением, высокой доступностью и службой резервного копирования Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43327-144">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

