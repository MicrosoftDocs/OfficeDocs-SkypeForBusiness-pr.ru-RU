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
ms.openlocfilehash: 984e7d7e287e9177fff5798c9cb20ab476591f46
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-clustering-for-lync-server-2013"></a><span data-ttu-id="73b55-102">Настройка кластеризации SQL Server для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73b55-102">Configure SQL Server clustering for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73b55-103">_**Последнее изменение темы:** 2014-01-10_</span><span class="sxs-lookup"><span data-stu-id="73b55-103">_**Topic Last Modified:** 2014-01-10_</span></span>

<span data-ttu-id="73b55-104">Microsoft Lync Server 2013 поддерживает кластеризацию для SQL Server 2012 и SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="73b55-104">Microsoft Lync Server 2013 supports clustering for SQL Server 2012 and SQL Server 2008 R2.</span></span> <span data-ttu-id="73b55-105">Сведения о [поддержке программного обеспечения баз данных в Lync Server 2013](lync-server-2013-database-software-support.md).</span><span class="sxs-lookup"><span data-stu-id="73b55-105">For details about what is supported, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span>

<span data-ttu-id="73b55-106">Перед установкой и развертыванием сервера переднего плана Enterprise Edition и внутренней базы данных необходимо установить и настроить кластер SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73b55-106">You should set up and configure the SQL Server cluster before you install and deploy the Enterprise Edition Front End Server and back-end database.</span></span> <span data-ttu-id="73b55-107">Рекомендации и инструкции по настройке отказоустойчивой кластеризации в SQL Server 2012 приведены в разделе <http://technet.microsoft.com/library/hh231721.aspx>.</span><span class="sxs-lookup"><span data-stu-id="73b55-107">For best practices and setup instructions for failover clustering in SQL Server 2012, see <http://technet.microsoft.com/library/hh231721.aspx>.</span></span> <span data-ttu-id="73b55-108">Сведения об отказоустойчивой кластеризации в SQL Server 2008 <http://technet.microsoft.com/library/ms189134(v=sql.105).aspx>см.</span><span class="sxs-lookup"><span data-stu-id="73b55-108">For failover clustering in SQL Server 2008, see <http://technet.microsoft.com/library/ms189134(v=sql.105).aspx>.</span></span>

<span data-ttu-id="73b55-109">При установке SQL Server необходимо установить SQL Server Management Studio, чтобы управлять расположением баз данных и файлов журналов.</span><span class="sxs-lookup"><span data-stu-id="73b55-109">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations.</span></span> <span data-ttu-id="73b55-110">SQL Server Management Studio устанавливается в качестве необязательного компонента при установке SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73b55-110">SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="73b55-111">Чтобы установить и развернуть базы данных на сервере SQL Server, необходимо быть участником группы администраторов SQL Server на сервере SQL Server, на котором устанавливаются файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="73b55-111">To install and deploy the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmin group for the SQL Server-based server where you are installing the database files.</span></span> <span data-ttu-id="73b55-112">Если вы не являетесь участником группы администраторов SQL Server, вам потребуется добавить его в группу, пока не будут развернуты файлы базы данных.</span><span class="sxs-lookup"><span data-stu-id="73b55-112">If you are not a member of the SQL Server sysadmin group, you will need to request that you be added to the group until the database files are deployed.</span></span> <span data-ttu-id="73b55-113">Если вы не можете быть участником группы sysadmin, администратор базы данных SQL Server должен предоставить скрипт для настройки и развертывания баз данных.</span><span class="sxs-lookup"><span data-stu-id="73b55-113">If you cannot be made a member of the sysadmin group, you should provide your SQL Server database administrator with the script to configure and deploy the databases.</span></span> <span data-ttu-id="73b55-114">Для получения дополнительных сведений о надлежащих правах и разрешениях, необходимых для выполнения процедур, ознакомьтесь с <A href="lync-server-2013-deployment-permissions-for-sql-server.md">разрешениями на развертывание для SQL Server в Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="73b55-114">For details about the proper user rights and permissions that you need to accomplish the procedures, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-configure-sql-server-clustering"></a><span data-ttu-id="73b55-115">Настройка кластеризации SQL Server</span><span class="sxs-lookup"><span data-stu-id="73b55-115">To configure SQL Server clustering</span></span>

1.  <span data-ttu-id="73b55-116">После завершения установки и настройки кластера SQL Server необходимо определить хранилище SQL Server в построителе топологий, используя имя виртуального кластера экземпляра SQL Server (как указано в разделе Установка для кластеризации SQL Server) и экземпляр имя базы данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73b55-116">After you have completed the installation and configuration of SQL Server clustering, you define the SQL Server store in Topology Builder by using the SQL Server instance virtual cluster name (as configured in the setup for SQL Server clustering) and the instance name of the SQL Server database.</span></span> <span data-ttu-id="73b55-117">Отличается от сервера SQL Server с помощью полного доменного имени (FQDN) виртуального узла для кластеризованного сервера на основе SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73b55-117">Different from a single SQL Server-based server, you will use the virtual node fully qualified domain name (FQDN) for a clustered SQL Server-based server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="73b55-118">Отдельные узлы кластера Windows Server не обязательно должны быть настроены для построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="73b55-118">The individual Windows Server cluster nodes do not have to be configured for Topology Builder.</span></span> <span data-ttu-id="73b55-119">Будет использоваться только имя виртуального кластера SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73b55-119">You will use only the virtual SQL Server cluster name.</span></span>

    
    </div>

2.  <span data-ttu-id="73b55-120">Если вы используете построитель топологий для развертывания баз данных, необходимо быть участником группы администраторов SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73b55-120">If you are using Topology Builder to deploy your databases, you must be a member of the SQL Server sysadmin group.</span></span> <span data-ttu-id="73b55-121">Если вы являетесь членом группы администраторов SQL Server, но у вас нет прав в домене (например, роль администратора базы данных SQL Server), у вас есть права на создание баз данных, но не на чтение необходимой информации в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="73b55-121">If you are a member of the SQL Server sysadmin group, but you do not have privileges in the domain (for example, a SQL Server database administrator role), then you have the rights to create the databases but not to read necessary information in Lync Server.</span></span> <span data-ttu-id="73b55-122">Дополнительные сведения о правах и разрешениях пользователей, необходимых для развертывания Lync Server, приведены [в разделе разрешения развертывания для SQL Server в Lync server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="73b55-122">For details about the user rights and permissions necessary to deploying Lync Server, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

3.  <span data-ttu-id="73b55-123">Убедитесь, что параметры папок базы данных и файлов журналов правильно сопоставляются с общими дисками в кластере SQL Server с помощью SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="73b55-123">Ensure that the database folder and log files folder defaults are mapped correctly to the shared disks in the SQL Server cluster by using SQL Server Management Studio.</span></span> <span data-ttu-id="73b55-124">Эта процедура является обязательной, если вы создадите базы данных с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="73b55-124">This is a required procedure if you will create databases by using Topology Builder.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="73b55-125">Если вы не установили SQL Server Management Studio, вы можете установить его, повторно выполнив установку SQL Server, а затем выбрав средство управления в качестве добавленной функции для существующего развертывания SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73b55-125">If you did not install SQL Server Management Studio, you can install it by rerunning the SQL Server installation, and then selecting the management tool as an added feature for the existing SQL Server deployment.</span></span>

    
    </div>

4.  <span data-ttu-id="73b55-126">Установите базы данных для сервера SQL Server, используя либо построитель топологий, либо командлеты Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="73b55-126">Install the databases for the SQL Server-based server by using either Topology Builder or Windows PowerShell cmdlets.</span></span> <span data-ttu-id="73b55-127">Чтобы использовать построитель топологий, используйте следующую процедуру.</span><span class="sxs-lookup"><span data-stu-id="73b55-127">To use Topology Builder, use the following procedure.</span></span> <span data-ttu-id="73b55-128">Чтобы использовать командлеты Windows PowerShell, ознакомьтесь со статьей [Установка базы данных с помощью командной консоли Lync Server в Lync server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="73b55-128">To use Windows PowerShell cmdlets, see [Database installation using Lync Server Management Shell in Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="to-create-databases-using-topology-builder"></a><span data-ttu-id="73b55-129">Создание баз данных с помощью построителя топологий</span><span class="sxs-lookup"><span data-stu-id="73b55-129">To create databases using Topology Builder</span></span>

1.  <span data-ttu-id="73b55-130">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="73b55-130">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="73b55-131">В следующей процедуре предполагается, что вы определили и настроили топологию в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="73b55-131">The following procedure assumes that you have defined and configured your topology in Topology Builder.</span></span> <span data-ttu-id="73b55-132">Подробнее об определении топологии можно узнать в статье<A href="lync-server-2013-defining-and-configuring-the-topology.md">Определение и Настройка топологии в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="73b55-132">For details about defining your topology, see<A href="lync-server-2013-defining-and-configuring-the-topology.md">Defining and configuring the topology in Lync Server 2013</A>.</span></span> <span data-ttu-id="73b55-133">Чтобы использовать построитель топологий для публикации топологии и настройки базы данных, необходимо войти в систему с учетной записью пользователя с правильными правами пользователя и членством в группах.</span><span class="sxs-lookup"><span data-stu-id="73b55-133">To use Topology Builder to publish the topology and configure the database, you must log on as a user with the correct user rights and group memberships.</span></span> <span data-ttu-id="73b55-134">Сведения о необходимых правах и членстве в группах содержатся в разделе <A href="lync-server-2013-deployment-permissions-for-sql-server.md">разрешения развертывания для SQL Server в Lync server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="73b55-134">For details about the required rights and group memberships, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="73b55-135">В построителе топологий при публикации топологии на странице **Создание баз данных** нажмите кнопку **Дополнительно**.</span><span class="sxs-lookup"><span data-stu-id="73b55-135">In Topology Builder, as you publish the topology, on the **Create databases** page, click **Advanced**.</span></span>

3.  <span data-ttu-id="73b55-136">Страница **Выбор расположения файлов базы данных** имеет два параметра, которые определяют, как файлы баз данных будут развернуты в кластере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73b55-136">The **Select Database File Location** page has two options that determine how the database files will be deployed to the SQL Server cluster.</span></span> <span data-ttu-id="73b55-137">Выберите один из приведенных ниже параметров:</span><span class="sxs-lookup"><span data-stu-id="73b55-137">Select one of the following:</span></span>
    
      - <span data-ttu-id="73b55-138">**Автоматически определять местоположение файла базы данных.**</span><span class="sxs-lookup"><span data-stu-id="73b55-138">**Automatically determine the database file location.**</span></span> <span data-ttu-id="73b55-139">Этот параметр использует алгоритм для определения расположений журнала базы данных и файлов данных на основе конфигурации диска на сервере SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73b55-139">This selection uses an algorithm to determine the database log and data file locations based on the drive configuration on the SQL Server-based server.</span></span> <span data-ttu-id="73b55-140">Файлы будут распространяться таким образом, чтобы попытаться обеспечить оптимальную производительность.</span><span class="sxs-lookup"><span data-stu-id="73b55-140">The files will be distributed in such a way as to attempt to provide optimal performance.</span></span>
    
      - <span data-ttu-id="73b55-141">Использовать параметры по умолчанию экземпляра SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73b55-141">Use SQL Server instance defaults.</span></span> <span data-ttu-id="73b55-142">При выборе этого параметра будут установлены файлы журнала и данных в соответствии с параметрами экземпляра SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73b55-142">Selecting this option will install the log and data files according to the SQL Server instance settings.</span></span> <span data-ttu-id="73b55-143">После развертывания файлов базы данных на сервере SQL Server администратору базы данных SQL Server может потребоваться переместить файлы, чтобы оптимизировать производительность для определенных требований к конфигурации SQL Server.</span><span class="sxs-lookup"><span data-stu-id="73b55-143">After deployment of the database files to the SQL Server, your SQL Server database administrator may want to relocate the files to optimize performance for your particular SQL Server configuration requirements.</span></span>

4.  <span data-ttu-id="73b55-144">Завершите публикацию топологии и убедитесь в отсутствии ошибок во время выполнения этой операции.</span><span class="sxs-lookup"><span data-stu-id="73b55-144">Complete the publishing of the topology and confirm that there were no errors during the operation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

