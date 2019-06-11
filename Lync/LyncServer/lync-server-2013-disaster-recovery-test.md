---
title: 'Lync Server 2013: тест аварийного восстановления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9b17f5841cad96cb83399082f61c00194ec4828
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disaster-recovery-test-in-lync-server-2013"></a><span data-ttu-id="61284-102">Тест аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61284-102">Disaster recovery test in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61284-103">_**Тема последнего изменения:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="61284-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="61284-104">Выполните восстановление системы для сервера Lync Server 2013 пула, чтобы протестировать задокументированный процесс аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="61284-104">Perform a system recovery for a Lync Server 2013 pool server to test your documented disaster recovery process.</span></span> <span data-ttu-id="61284-105">Данный тест смоделирует полный сбой в работе оборудования для одного сервера, а также поможет гарантировать, что ресурсы, планы и данные будут доступны для восстановления.</span><span class="sxs-lookup"><span data-stu-id="61284-105">This test will simulate a complete hardware failure for one server, and will help guarantee that the resources, plans, and data is available for recovery.</span></span> <span data-ttu-id="61284-106">Попробуйте менять ориентир теста каждый месяц, чтобы в организации каждый раз проверялись сбои в работе разных серверов или других компонентов оборудования.</span><span class="sxs-lookup"><span data-stu-id="61284-106">Try to rotate the focus of the test each month so that your organization tests the failure of a different server or other piece of equipment every time.</span></span>

<span data-ttu-id="61284-p102">Обратите внимание, что расписание выполнения организациями проверки аварийного восстановления будет отличаться. Очень важно, чтобы проверка аварийного восстановления выполнялась.</span><span class="sxs-lookup"><span data-stu-id="61284-p102">Note that the schedule by which organizations perform Disaster Recovery testing will vary. It is very important that disaster recovery testing is not ignored or neglected.</span></span>

<div>


<span data-ttu-id="61284-109">Экспортируйте топологию, политики и параметры конфигурации Lync Server 2013 в файл.</span><span class="sxs-lookup"><span data-stu-id="61284-109">Export your Lync Server 2013 topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="61284-110">Помимо прочего, данный файл может быть использован для восстановления данной информации в центральном хранилище управления после обновления, сбоя в работе оборудования или некоторых других неполадок, в результате которых произошла потеря данных.</span><span class="sxs-lookup"><span data-stu-id="61284-110">Among other things, this file can then be used to restore this information to the Central Management store after an upgrade, a hardware failure, or some other issue has resulted in data loss.</span></span>

<span data-ttu-id="61284-111">Импортируйте топологию, политики и параметры конфигурации Lync Server 2013 в хранилище Центрального управления или на локальный компьютер, как показано в следующих командах:</span><span class="sxs-lookup"><span data-stu-id="61284-111">Import your Lync Server 2013 topology, policies, and configuration settings to either the Central Management store or to the local computer as shown in the following commands:</span></span>

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

<span data-ttu-id="61284-112">Чтобы выполнить резервное копирование данных рабочего сервера Lync Server 2013, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="61284-112">To back up production Lync Server 2013 data:</span></span>

  - <span data-ttu-id="61284-113">Создавайте резервные копии баз данных RTC и Лкслог, используя стандартный процесс резервного копирования SQL Server, чтобы выгрузить ее из файла или накопительного дампа.</span><span class="sxs-lookup"><span data-stu-id="61284-113">Back up the RTC and LCSLog databases by using the standard SQL Server backup process to dump the database to a file or tape dump device.</span></span>

  - <span data-ttu-id="61284-114">Используйте стороннее приложение резервного копирования для создания резервной копии данных в файле или на ленте.</span><span class="sxs-lookup"><span data-stu-id="61284-114">Use third-party backup application to back up the data to file or to tape.</span></span>

  - <span data-ttu-id="61284-115">Используйте командлет Export-CsUserData для создания экспорта XML всей базы данных RTC полностью.</span><span class="sxs-lookup"><span data-stu-id="61284-115">Use the Export-CsUserData cmdlet to create an XML export of the whole RTC database.</span></span>

  - <span data-ttu-id="61284-116">Используйте резервное копирование файловой системы или стороннего производителя для создания резервной копии содержимого собрания и журналов соответствия.</span><span class="sxs-lookup"><span data-stu-id="61284-116">Use the file system backup or third-party to back up meeting content and compliance logs.</span></span>

  - <span data-ttu-id="61284-117">С помощью средства командной строки Export-Ксконфигуратион можно создавать резервные копии параметров Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="61284-117">Use the Export-CsConfiguration command-line tool to back up Lync Server 2013 settings.</span></span>

<span data-ttu-id="61284-118">Первый этап процедуры обхода неисправностей содержит принудительное перемещение пользователей из производственного пула в пул аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="61284-118">The first step in the failover procedure includes a forced move of users from the production pool to the Disaster Recovery pool.</span></span>

<span data-ttu-id="61284-119">Данное перемещение будет принудительным, потому что производственный пул не будет доступен для принятия перемещения пользователей.</span><span class="sxs-lookup"><span data-stu-id="61284-119">This will be a forced move because the production pool won't be available to accept the user relocation.</span></span>

<span data-ttu-id="61284-120">В дополнение к обновлению записи в базе данных сервера реального времени на сервере Lync Server 2013 можно изменить атрибут объекта учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="61284-120">The Lync Server 2013 move user process is effectively a change to an attribute on the user account object in addition to a record update on the RTC SQL database.</span></span>

<span data-ttu-id="61284-121">Эти данные можно восстановить с помощью двух следующих процессов.</span><span class="sxs-lookup"><span data-stu-id="61284-121">This data can be restored through the following two processes:</span></span>

  - <span data-ttu-id="61284-122">Базу данных RTC можно восстановить из исходного устройства резервного копирования на рабочем сервере SQL Server с помощью стандартного процесса восстановления SQL Server или с помощью сторонней программы резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="61284-122">RTC database can be restored from the original backup dump device from the production SQL Server using the standard SQL Server restore process, or using a third-party backup/restore utility.</span></span>

  - <span data-ttu-id="61284-123">Контактные данные пользователя можно восстановить с помощью служебной программы DBIMPEXP.exe, используя файл XML, который был создан из экспорта производственного сервера SQL Server.</span><span class="sxs-lookup"><span data-stu-id="61284-123">User contact data can be restored with the DBIMPEXP.exe utility using the XML file that was created from the production SQL Server export.</span></span>

<span data-ttu-id="61284-124">После восстановления эти данные пользователи могут подключаться к аварийному восстановлению Lync Server 2013 и работать в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="61284-124">After this data is restored, users can effectively connect to the Disaster Recovery Lync Server 2013 pool, and operate as usual.</span></span>

<span data-ttu-id="61284-125">Чтобы разрешить пользователям подключаться к службе аварийного восстановления Lync Server 2013, потребуется изменение DNS-записи.</span><span class="sxs-lookup"><span data-stu-id="61284-125">To enable users to connect to the Disaster Recovery Lync Server 2013 pool, a DNS record change will be required.</span></span>

<span data-ttu-id="61284-126">На рабочем месте рабочего 2013 сервера Lync Server будут ссылаться клиенты, использующие записи автоматической настройки и DNS SRV:</span><span class="sxs-lookup"><span data-stu-id="61284-126">The production Lync Server 2013 pool will be referenced by clients using the auto-configuration and DNS SRV records of:</span></span>

  - <span data-ttu-id="61284-127">SRV: \_SIP. \_TLS. \<Domain\> /кнаме: SIP. \<Domain (домен)\></span><span class="sxs-lookup"><span data-stu-id="61284-127">SRV: \_sip.\_tls.\<domain\> /CNAME: SIP.\<domain\></span></span>

  - <span data-ttu-id="61284-128">CNAME: SIP. \<домен\> /CVC-Pool-1. \<Domain (домен)\></span><span class="sxs-lookup"><span data-stu-id="61284-128">CNAME: SIP.\<domain\> /cvc-pool-1.\<domain\></span></span>

<span data-ttu-id="61284-129">Для облегчения процедуры отработки отказа данная запись CNAME должна быть обновлена с помощью ссылки на DROCSPool FQDN:</span><span class="sxs-lookup"><span data-stu-id="61284-129">To facilitate the failover, this CNAME record must be updated to reference the DROCSPool FQDN:</span></span>

  - <span data-ttu-id="61284-130">CNAME: SIP. \<домен\> /дрокспул. \<Domain (домен)\></span><span class="sxs-lookup"><span data-stu-id="61284-130">CNAME: SIP.\<domain\> /DROCSPool.\<domain\></span></span>

  - <span data-ttu-id="61284-131">Установка. \<Domain (домен)\></span><span class="sxs-lookup"><span data-stu-id="61284-131">Sip.\<domain\></span></span>

  - <span data-ttu-id="61284-132">AV.\<domain\></span><span class="sxs-lookup"><span data-stu-id="61284-132">AV.\<domain\></span></span>

  - <span data-ttu-id="61284-133">"". \<Domain (домен)\></span><span class="sxs-lookup"><span data-stu-id="61284-133">webconf.\<domain\></span></span>

  - <span data-ttu-id="61284-134">Окссервицес. \<Domain (домен)\></span><span class="sxs-lookup"><span data-stu-id="61284-134">OCSServices.\<domain\></span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="61284-135">Подробное описание процедур администрирования и управления см. в разделе <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">резервное копирование и восстановление сервера Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="61284-135">For detailed administration and management procedures, see <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">Backing up and restoring Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="61284-136">См. также</span><span class="sxs-lookup"><span data-stu-id="61284-136">See Also</span></span>


[<span data-ttu-id="61284-137">Планирование высокой доступности и аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61284-137">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[<span data-ttu-id="61284-138">Командлеты резервного копирования и высокой доступности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61284-138">Backup and high availability cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[<span data-ttu-id="61284-139">Import-CsConfiguration</span><span class="sxs-lookup"><span data-stu-id="61284-139">Import-CsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[<span data-ttu-id="61284-140">Резервное копирование и восстановление Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61284-140">Backing up and restoring Lync Server 2013</span></span>](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[<span data-ttu-id="61284-141">Управление аварийным восстановлением, высокой доступностью и службой резервного копирования Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61284-141">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

