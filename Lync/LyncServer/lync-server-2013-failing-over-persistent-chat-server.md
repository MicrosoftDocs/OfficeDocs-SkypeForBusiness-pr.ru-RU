---
title: 'Lync Server 2013: отработка отказа сервером сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 570ed42bb2ff1d5b1f4ab58e9bbd9aad9159bef3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="9428d-102">Отработка отказа сервером сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9428d-102">Failing over Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9428d-103">_**Последнее изменение темы:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="9428d-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="9428d-104">Отработка отказа для сервера сохраняемого чата разработана в основном для ручного процесса.</span><span class="sxs-lookup"><span data-stu-id="9428d-104">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>

<span data-ttu-id="9428d-105">Процедура отработки отказа основана на предположении, что дополнительный центр обработки данных работает, но службы сервера сохраняемого чата, где расположена основная база данных сохраняемого чата, полностью недоступны, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="9428d-105">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>

  - <span data-ttu-id="9428d-106">Основная база данных сервера сохраняемого чата и зеркальная база данных сервера сохраняемого чата не работают.</span><span class="sxs-lookup"><span data-stu-id="9428d-106">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>

  - <span data-ttu-id="9428d-107">Сервер переднего плана Lync Server не работает.</span><span class="sxs-lookup"><span data-stu-id="9428d-107">Lync Server Front End Server is down.</span></span>

<span data-ttu-id="9428d-108">Вся процедура состоит из двух основных этапов:</span><span class="sxs-lookup"><span data-stu-id="9428d-108">The procedure is based on two basic steps:</span></span>

  - <span data-ttu-id="9428d-109">Восстановите основную базу данных сохраняемого чата (MGC).</span><span class="sxs-lookup"><span data-stu-id="9428d-109">Recover the primary Persistent Chat database (mgc).</span></span>

  - <span data-ttu-id="9428d-110">Реализация зеркального отображения для новой базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="9428d-110">Establish mirroring for the new primary database.</span></span>

<span data-ttu-id="9428d-111">Не отменяется отработка отказа базы данных соответствия сохраняемого чата (mgccomp).</span><span class="sxs-lookup"><span data-stu-id="9428d-111">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="9428d-112">Содержимое этой базы данных является временным и очищается по мере обработки данных адаптером соответствия.</span><span class="sxs-lookup"><span data-stu-id="9428d-112">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="9428d-113">В качестве администратора сохраняемого чата вы обязаны правильно управлять выходными данными адаптера, чтобы избежать потери данных.</span><span class="sxs-lookup"><span data-stu-id="9428d-113">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>

<div>

## <a name="to-fail-over-persistent-chat-server"></a><span data-ttu-id="9428d-114">Чтобы отработка отказа на сервере сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="9428d-114">To fail over Persistent Chat Server</span></span>

1.  <span data-ttu-id="9428d-115">Удалите доставку журналов из базы данных доставки журналов резервного копирования сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="9428d-115">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
    1.  <span data-ttu-id="9428d-116">С помощью SQL Server Management Studio подключитесь к экземпляру базы данных, где находится база данных MGC резервного копирования сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="9428d-116">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
    2.  <span data-ttu-id="9428d-117">Откройте окно отправки запроса в базу данных master.</span><span class="sxs-lookup"><span data-stu-id="9428d-117">Open a query window to the master database.</span></span>
    
    3.  <span data-ttu-id="9428d-118">Используйте следующую команду для сброса доставки журналов:</span><span class="sxs-lookup"><span data-stu-id="9428d-118">Use the following command to drop log shipping:</span></span>
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  <span data-ttu-id="9428d-119">Скопируйте все нескопированные файлы резервных копий из общей папки резервных копий в конечную папку копирования на резервном сервере.</span><span class="sxs-lookup"><span data-stu-id="9428d-119">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>

3.  <span data-ttu-id="9428d-120">По порядку примените все непримененные резервные копии журналов транзакций к базе данных-получателю.</span><span class="sxs-lookup"><span data-stu-id="9428d-120">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="9428d-121">Дополнительные сведения см. в разделе "как: применение резервной копии журнала транзакций (Transact-SQL) https://go.microsoft.com/fwlink/p/?linkid=247428" по адресу.</span><span class="sxs-lookup"><span data-stu-id="9428d-121">For details, see "How to: Apply a Transaction Log Backup (Transact-SQL)" at https://go.microsoft.com/fwlink/p/?linkid=247428.</span></span>

4.  <span data-ttu-id="9428d-p103">Подключите резервную базу данных mgc к сети. В окне запроса, которое было открыто в действии 1b, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9428d-p103">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
    1.  <span data-ttu-id="9428d-124">Завершите все подключения к базе данных mgc при их наличии:</span><span class="sxs-lookup"><span data-stu-id="9428d-124">End all connections to the mgc database, if there are any:</span></span>
        
        1.  <span data-ttu-id="9428d-125">**exec SP\_who2** для определения подключений к базе данных mgc.</span><span class="sxs-lookup"><span data-stu-id="9428d-125">**exec sp\_who2** to identify connections to the mgc database.</span></span>
        
        2.  <span data-ttu-id="9428d-126">\*\*удалите \<SPID\> \*\* , чтобы завершить эти подключения.</span><span class="sxs-lookup"><span data-stu-id="9428d-126">**kill \<spid\>** to end these connections.</span></span>
    
    2.  <span data-ttu-id="9428d-127">Подключите базу данных к сети.</span><span class="sxs-lookup"><span data-stu-id="9428d-127">Bring the database online:</span></span>
        
        1.  <span data-ttu-id="9428d-128">**Восстановление базы данных MGC с восстановлением**.</span><span class="sxs-lookup"><span data-stu-id="9428d-128">**restore database mgc with recovery**.</span></span>

5.  <span data-ttu-id="9428d-129">В консоли управления Lync Server используйте команду **Set-CsPersistentChatState-Identity "Service: ATL-CS-001.litwareinc.com" – PoolState FailedOver** , чтобы отработка отказа на резервную базу данных mgc.</span><span class="sxs-lookup"><span data-stu-id="9428d-129">In Lync Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" –PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="9428d-130">Обязательно замените полное доменное имя пула сохраняемого чата для atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="9428d-130">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="9428d-131">Резервная база данных mgc теперь выступает в качестве базы данных-источника.</span><span class="sxs-lookup"><span data-stu-id="9428d-131">The mgc backup database now serves as the primary database.</span></span>

6.  <span data-ttu-id="9428d-132">В командной консоли Lync Server используйте командлет **Install – CsMirrorDatabase** , чтобы установить зеркало высокой доступности для базы данных резервных копий, которая теперь выступает в качестве основной базы данных.</span><span class="sxs-lookup"><span data-stu-id="9428d-132">In Lync Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="9428d-133">Используйте экземпляр резервной базы данных в качестве базы данных источника и экземпляр резервной зеркальной базы данных в качестве экземпляра зеркала.</span><span class="sxs-lookup"><span data-stu-id="9428d-133">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="9428d-134">Это не то же самое зеркало, которое изначально было настроено для базы данных-источника в процессе установки.</span><span class="sxs-lookup"><span data-stu-id="9428d-134">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span> <span data-ttu-id="9428d-135">Дополнительные сведения можно найти в разделе "использование командлетов командной консоли Lync Server" в разделе [Развертывание зеркального отображения SQL для обеспечения высокой доступности внутреннего сервера в Lync server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span><span class="sxs-lookup"><span data-stu-id="9428d-135">For details, see the section "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

7.  <span data-ttu-id="9428d-136">Задайте для сервера сохраняемого чата активные серверы.</span><span class="sxs-lookup"><span data-stu-id="9428d-136">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="9428d-137">В командной консоли Lync Server используйте командлет **Set – CsPersistentChatActiveServer** , чтобы задать список активных серверов.</span><span class="sxs-lookup"><span data-stu-id="9428d-137">From the Lync Server Command Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9428d-138">Все активные серверы должны располагаться в одном центре обработки данных с новой базой данных-источником или в центре обработки данных, имеющем подключение к базе данных с низкой задержкой и высокой пропускной способностью.</span><span class="sxs-lookup"><span data-stu-id="9428d-138">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>
    
    <span data-ttu-id="9428d-139">На этом шаге отработка отказа из основной базы данных сервера сохраняемого чата в резервную базу данных сервера сохраняемого чата успешно завершена.</span><span class="sxs-lookup"><span data-stu-id="9428d-139">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

