---
title: Восстановление зеркального сервера переднего план выпуска Enterprise Edition — зеркало
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - mirror
ms:assetid: 4b3c8eae-6f1f-4377-b39b-6699e725c517
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945626(v=OCS.15)
ms:contentKeyID: 51541471
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e4bbb7d74c6bf660c69a15ff8250d95f04fed98
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511586"
---
# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---mirror"></a><span data-ttu-id="68f51-102">Восстановление зеркального сервера переднего план выпуска Enterprise Edition в Lync Server 2013 — зеркало</span><span class="sxs-lookup"><span data-stu-id="68f51-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68f51-103">_**Последнее изменение темы:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="68f51-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="68f51-104">При наличии внутреннего сервера Enterprise Edition в зеркальной конфигурации и сбоя зеркального отображения выполните процедуры, описанные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="68f51-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the mirror fails, follow the procedures in this section.</span></span> <span data-ttu-id="68f51-105">Если произойдет ошибка основной базы данных и зеркала, ознакомьтесь с разделом [Восстановление внутреннего сервера Enterprise Edition в Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span><span class="sxs-lookup"><span data-stu-id="68f51-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="68f51-106">Если возникает только основной сбой, ознакомьтесь [со статьей восстановление зеркального внутреннего сервера Enterprise Edition в Lync Server 2013 — основной](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md).</span><span class="sxs-lookup"><span data-stu-id="68f51-106">If only the primary fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md).</span></span> <span data-ttu-id="68f51-107">Если база данных, в которой размещается центральное хранилище управления, не проходит, ознакомьтесь со статьей [восстановление сервера, на котором размещается центральное хранилище управления в Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="68f51-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="68f51-108">В случае сбоя рядового сервера Enterprise Edition, который не является внутренним сервером, ознакомьтесь со статьей [Восстановление рядового сервера Enterprise Edition в Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="68f51-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="68f51-109">Перед началом восстановления рекомендуется использовать копию системы в виде образа.</span><span class="sxs-lookup"><span data-stu-id="68f51-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="68f51-110">Это изображение можно использовать в качестве точки отката, если в процессе восстановления что-то пойдет не так.</span><span class="sxs-lookup"><span data-stu-id="68f51-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="68f51-111">Вы можете использовать копию образа после установки операционной системы и SQL Server, а также для восстановления или повторной регистрации сертификатов.</span><span class="sxs-lookup"><span data-stu-id="68f51-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-mirror-database"></a><span data-ttu-id="68f51-112">Восстановление зеркального сервера базы данных переднего планов Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="68f51-112">To restore an Enterprise Edition Back End Server Mirror Database</span></span>

1.  <span data-ttu-id="68f51-113">Войдите на сервер переднего плана из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="68f51-113">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="68f51-114">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="68f51-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="68f51-115">Удаление зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="68f51-115">Uninstall mirroring.</span></span> <span data-ttu-id="68f51-116">Сначала введите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="68f51-116">First, type the following cmdlet:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn <PrimaryServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="68f51-117">Например:</span><span class="sxs-lookup"><span data-stu-id="68f51-117">For example:</span></span>
    
        Uninstall -CsMirrorDatabase -DatabaseType User -SqlServerFqdn server4.contoso.com -SqlInstanceName archinst -verbose
    
    <span data-ttu-id="68f51-118">Выполните это действие для всех типов баз данных на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="68f51-118">Do this for all database types on this server.</span></span>

4.  <span data-ttu-id="68f51-119">Создайте чистый или новый сервер с таким же полным доменным именем (DB1.contoso.com) в качестве неисправного компьютера, установите операционную систему, а затем восстановите или повторно зарегистрируйте сертификаты.</span><span class="sxs-lookup"><span data-stu-id="68f51-119">Create a clean or new server that has the same fully qualified domain name (FQDN) (DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="68f51-120">Этот сервер будет работать как новый зеркальный сервер.</span><span class="sxs-lookup"><span data-stu-id="68f51-120">This server will function as the new mirror.</span></span>

5.  <span data-ttu-id="68f51-121">Войдите на новый сервер из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="68f51-121">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

6.  <span data-ttu-id="68f51-122">Установите SQL Server 2012 или SQL Server 2008 R2, сохранив имена экземпляров так же, как и до сбоя.</span><span class="sxs-lookup"><span data-stu-id="68f51-122">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

7.  <span data-ttu-id="68f51-123">Войдите на сервер переднего плана из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="68f51-123">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

8.  <span data-ttu-id="68f51-124">Используйте построитель топологий для установки зеркальной базы данных.</span><span class="sxs-lookup"><span data-stu-id="68f51-124">Use Topology Builder to install the mirror database.</span></span> <span data-ttu-id="68f51-125">Выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="68f51-125">Perform the following:</span></span>
    
      - <span data-ttu-id="68f51-126">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="68f51-126">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="68f51-127">Щелкните правой кнопкой мыши узел Lync Server 2013, выберите пункт **топология**, а затем — **установить базу данных**.</span><span class="sxs-lookup"><span data-stu-id="68f51-127">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="68f51-128">Следуйте инструкциям мастера **установки базы данных** .</span><span class="sxs-lookup"><span data-stu-id="68f51-128">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="68f51-129">На странице " **Создание баз данных** " выберите базы данных, которые требуется повторно создать.</span><span class="sxs-lookup"><span data-stu-id="68f51-129">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="68f51-130">Следуйте указаниям мастера, пока не появится запрос на **Создание зеркальной базы данных** .</span><span class="sxs-lookup"><span data-stu-id="68f51-130">Follow the wizard until a prompt of **Create Mirror Database** appears.</span></span> <span data-ttu-id="68f51-131">Выберите базу данных, которую вы хотите установить, и выполните эту процедуру.</span><span class="sxs-lookup"><span data-stu-id="68f51-131">Select the database that you want to install and complete this process.</span></span>
        
        <div>
        

        > [!TIP]
        > <span data-ttu-id="68f51-132">Вместо запуска построителя топологий можно использовать командлет <STRONG>Install – CsMirrorDatabase</STRONG> для настройки зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="68f51-132">Instead of running Topology Builder, you can use the <STRONG>Install-CsMirrorDatabase</STRONG> cmdlet to configure mirroring.</span></span> <span data-ttu-id="68f51-133">Дополнительные сведения см. в документации Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="68f51-133">For details, see the Lync Server Management Shell documentation.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

