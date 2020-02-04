---
title: 'Lync Server 2013: Настройка кластеризации SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server clustering
ms:assetid: d7b52ef1-573c-48ed-bb94-34e37b49645c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383982(v=OCS.15)
ms:contentKeyID: 56472032
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b63d338e630da93c90b573ac098d47e0929f0d84
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-clustering-for-lync-server-2013"></a><span data-ttu-id="4f2b5-102">Настройка кластеризации SQL Server для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f2b5-102">Configure SQL Server clustering for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f2b5-103">_**Тема последнего изменения:** 2014-01-10_</span><span class="sxs-lookup"><span data-stu-id="4f2b5-103">_**Topic Last Modified:** 2014-01-10_</span></span>

<span data-ttu-id="4f2b5-104">Microsoft Lync Server 2013 поддерживает кластеризацию для SQL Server 2012 и SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-104">Microsoft Lync Server 2013 supports clustering for SQL Server 2012 and SQL Server 2008 R2.</span></span> <span data-ttu-id="4f2b5-105">Подробнее о поддерживаемых возможностях можно найти [в разделе Поддержка программного обеспечения баз данных в Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="4f2b5-105">For details about what is supported, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

<span data-ttu-id="4f2b5-106">Перед установкой и развертыванием сервера переднего плана Enterprise Edition и серверной базы данных необходимо настроить и настроить кластер SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-106">You should set up and configure the SQL Server cluster before you install and deploy the Enterprise Edition Front End Server and back-end database.</span></span> <span data-ttu-id="4f2b5-107">Рекомендации и инструкции по настройке отказоустойчивой кластеризации в SQL Server 2012 можно найти в <http://technet.microsoft.com/en-us/library/hh231721.aspx>разделе.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-107">For best practices and setup instructions for failover clustering in SQL Server 2012, see <http://technet.microsoft.com/en-us/library/hh231721.aspx>.</span></span> <span data-ttu-id="4f2b5-108">Сведения об отказоустойчивой кластеризации в SQL Server 2008 <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>можно найти в разделе.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-108">For failover clustering in SQL Server 2008, see <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>.</span></span>

<span data-ttu-id="4f2b5-p103">При установке SQL Server следует также установить SQL Server Management Studio для управления расположениями базы данных и файлов журнала. SQL Server Management Studio устанавливается с SQL Server как необязательный компонент.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-p103">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations. SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4f2b5-111">Для установки и развертывания баз данных на сервере SQL Server необходимо быть членом группы sysadmin сервера SQL Server для сервера SQL Server, на котором устанавливаются файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-111">To install and deploy the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmin group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="4f2b5-112">Если вы не являетесь членом группы sysadmin сервера SQL Server, вам придется попросить добавить его в группу, пока не будут развернуты файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-112">If you are not a member of the SQL Server sysadmin group, you will need to request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="4f2b5-113">Если вы не можете стать членом группы sysadmin, вы должны предоставить администратору базы данных SQL Server сценарий для настройки и развертывания баз данных.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-113">If you cannot be made a member of the sysadmin group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="4f2b5-114">Сведения о правильных правах пользователей и разрешениях, необходимых для выполнения этих процедур, приведены <A href="lync-server-2013-deployment-permissions-for-sql-server.md">в разделе разрешения на развертывание SQL Server в Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-114">For details about the proper user rights and permissions that you need to accomplish the procedures, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a><span data-ttu-id="4f2b5-115">Настройка кластеризации SQL Server</span><span class="sxs-lookup"><span data-stu-id="4f2b5-115">To configure SQL Server clustering</span></span>

1.  <span data-ttu-id="4f2b5-116">После завершения установки и настройки кластеризации SQL Server вы определяете хранилище SQL Server в построителе топологии с помощью имени виртуального кластера экземпляра SQL Server (как указано в разделе Настройка кластеризации SQL Server) и экземпляра. имя базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-116">After you have completed the installation and configuration of SQL Server clustering, you define the SQL Server store in Topology Builder by using the SQL Server instance virtual cluster name (as configured in the setup for SQL Server clustering) and the instance name of the SQL Server database.</span></span> <span data-ttu-id="4f2b5-117">Для сервера SQL Server, использующего сервер SQL Server, не нужно использовать полное доменное имя виртуального узла (FQDN).</span><span class="sxs-lookup"><span data-stu-id="4f2b5-117">Different from a single SQL Server-based server, you will use the virtual node fully qualified domain name (FQDN) for a clustered SQL Server-based server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4f2b5-118">Отдельные узлы кластера Windows Server не обязательно должны быть настроены для построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-118">The individual Windows Server cluster nodes do not have to be configured for Topology Builder.</span></span> <span data-ttu-id="4f2b5-119">Вы будете использовать только имя виртуального кластера SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-119">You will use only the virtual SQL Server cluster name.</span></span>

    
    </div>

2.  <span data-ttu-id="4f2b5-120">Если вы используете Topology Builder для развертывания баз данных, вы должны быть участником группы sysadmin сервера SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-120">If you are using Topology Builder to deploy your databases, you must be a member of the SQL Server sysadmin group.</span></span> <span data-ttu-id="4f2b5-121">Если вы являетесь членом группы администраторов SQL Server, но у вас нет прав на доступ к домену (например, роль администратора базы данных SQL Server), у вас есть права на создание баз данных, но не на чтение необходимой информации в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-121">If you are a member of the SQL Server sysadmin group, but you do not have privileges in the domain (for example, a SQL Server database administrator role), then you have the rights to create the databases but not to read necessary information in Lync Server.</span></span> <span data-ttu-id="4f2b5-122">Дополнительные сведения о правах пользователей и разрешениях, необходимых для развертывания сервера Lync Server, приведены [в разделе разрешения на развертывание сервера SQL Server в Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="4f2b5-122">For details about the user rights and permissions necessary to deploying Lync Server, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

3.  <span data-ttu-id="4f2b5-123">Убедитесь, что папка базы данных и файлы журнала по умолчанию правильно сопоставляются общим дискам в кластере SQL Server с помощью SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-123">Ensure that the database folder and log files folder defaults are mapped correctly to the shared disks in the SQL Server cluster by using SQL Server Management Studio.</span></span> <span data-ttu-id="4f2b5-124">Эта процедура является обязательной, если вы создадите базы данных с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-124">This is a required procedure if you will create databases by using Topology Builder.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4f2b5-125">Если вы не установили SQL Server Management Studio, вы можете установить его, повторно запустив установку SQL Server, а затем выбрав средство управления как добавленную функцию для существующей конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-125">If you did not install SQL Server Management Studio, you can install it by rerunning the SQL Server installation, and then selecting the management tool as an added feature for the existing SQL Server deployment.</span></span>

    
    </div>

4.  <span data-ttu-id="4f2b5-126">Установите базы данных сервера SQL Server с помощью либо построителя топологии, либо командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-126">Install the databases for the SQL Server-based server by using either Topology Builder or Windows PowerShell cmdlets.</span></span> <span data-ttu-id="4f2b5-127">Чтобы использовать построитель топологии, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-127">To use Topology Builder, use the following procedure.</span></span> <span data-ttu-id="4f2b5-128">Чтобы использовать командлеты Windows PowerShell, ознакомьтесь [с разустановочием базы данных с помощью командной консоли Lync Server Management Shell в Lync server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="4f2b5-128">To use Windows PowerShell cmdlets, see [Database installation using Lync Server Management Shell in Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a><span data-ttu-id="4f2b5-129">Создание баз данных с помощью построителя топологии</span><span class="sxs-lookup"><span data-stu-id="4f2b5-129">To create databases using Topology Builder</span></span>

1.  <span data-ttu-id="4f2b5-130">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку **Построитель топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-130">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="4f2b5-131">В описанной ниже процедуре предполагается, что вы определили и настроили топологию в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-131">The following procedure assumes that you have defined and configured your topology in Topology Builder.</span></span> <span data-ttu-id="4f2b5-132">Подробнее о том, как определить топологию, можно найти<A href="lync-server-2013-defining-and-configuring-the-topology.md">в разделе Определение и Настройка топологии в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-132">For details about defining your topology, see<A href="lync-server-2013-defining-and-configuring-the-topology.md">Defining and configuring the topology in Lync Server 2013</A>.</span></span> <span data-ttu-id="4f2b5-133">Чтобы опубликовать топологию и настроить базу данных с помощью Topology Builder, необходимо войти в систему в качестве пользователя с правильными правами пользователей и членством в группах.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-133">To use Topology Builder to publish the topology and configure the database, you must log on as a user with the correct user rights and group memberships.</span></span> <span data-ttu-id="4f2b5-134">Сведения о необходимых правах и членстве в группах содержатся в разделе <A href="lync-server-2013-deployment-permissions-for-sql-server.md">разрешения на развертывание сервера SQL Server в Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-134">For details about the required rights and group memberships, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="4f2b5-135">В построителе топологии при публикации топологии на странице **Создание баз данных** нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-135">In Topology Builder, as you publish the topology, on the **Create databases** page, click **Advanced**.</span></span>

3.  <span data-ttu-id="4f2b5-136">На странице **Выбор расположения файла базы данных** есть два параметра, которые определяют, как файлы базы данных будут развертываться в кластере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-136">The **Select Database File Location** page has two options that determine how the database files will be deployed to the SQL Server cluster.</span></span> <span data-ttu-id="4f2b5-137">Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="4f2b5-137">Select one of the following:</span></span>
    
      - <span data-ttu-id="4f2b5-138">**Автоматически определяет расположение файла базы данных.**</span><span class="sxs-lookup"><span data-stu-id="4f2b5-138">**Automatically determine the database file location.**</span></span> <span data-ttu-id="4f2b5-139">Этот параметр использует алгоритм для определения расположений журнала базы данных и файлов данных на основе конфигурации диска на сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-139">This selection uses an algorithm to determine the database log and data file locations based on the drive configuration on the SQL Server-based server.</span></span> <span data-ttu-id="4f2b5-140">Файлы будут распределены таким образом, чтобы попытаться обеспечить оптимальную производительность.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-140">The files will be distributed in such a way as to attempt to provide optimal performance.</span></span>
    
      - <span data-ttu-id="4f2b5-141">Использовать параметры по умолчанию экземпляра SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-141">Use SQL Server instance defaults.</span></span> <span data-ttu-id="4f2b5-142">Если выбрать этот параметр, файлы журнала и данных будут установлены в соответствии с параметрами экземпляра SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-142">Selecting this option will install the log and data files according to the SQL Server instance settings.</span></span> <span data-ttu-id="4f2b5-143">После развертывания файлов базы данных на сервере SQL Server администратор базы данных SQL Server может изменить расположение файлов, чтобы оптимизировать производительность для конкретных требований к конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-143">After deployment of the database files to the SQL Server, your SQL Server database administrator may want to relocate the files to optimize performance for your particular SQL Server configuration requirements.</span></span>

4.  <span data-ttu-id="4f2b5-144">Завершите публикацию топологии и убедитесь, что во время операции ошибки не обнаружены.</span><span class="sxs-lookup"><span data-stu-id="4f2b5-144">Complete the publishing of the topology and confirm that there were no errors during the operation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

