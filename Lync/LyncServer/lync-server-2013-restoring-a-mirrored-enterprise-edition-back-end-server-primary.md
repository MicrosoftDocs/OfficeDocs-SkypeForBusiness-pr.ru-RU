---
title: Восстановление зеркального сервера выпуска Enterprise Edition — основной
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07546b59839631cbd558e91e3e617fefd1c6e362
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a><span data-ttu-id="7b4d9-102">Восстановление зеркального сервера выпуска Enterprise Edition на сервере Lync Server 2013-PRIMARY</span><span class="sxs-lookup"><span data-stu-id="7b4d9-102">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b4d9-103">_**Тема последнего изменения:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="7b4d9-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="7b4d9-104">Если в зеркальной конфигурации есть сервер, на котором установлен корпоративный выпуск Enterprise Edition, и не удалось выполнить только основную базу данных, выполните действия, описанные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-104">If you have an Enterprise Edition Back End Server in a mirrored configuration and only the primary database fails, follow the procedures in this section.</span></span> <span data-ttu-id="7b4d9-105">В случае сбоя основной базы данных и зеркала ознакомьтесь со сведениями о [восстановлении сервера выпуска Enterprise Edition в Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span><span class="sxs-lookup"><span data-stu-id="7b4d9-105">If both the primary database and mirror fail, see [Restoring an Enterprise Edition Back End Server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md).</span></span> <span data-ttu-id="7b4d9-106">Если возникает ошибка только в зеркальном отображении, ознакомьтесь со сведениями о том, [как восстановить зеркальный сервер уровня Enterprise Edition в Lync server 2013 — Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md).</span><span class="sxs-lookup"><span data-stu-id="7b4d9-106">If only the mirror fails, see [Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md).</span></span> <span data-ttu-id="7b4d9-107">Если база данных, на которой размещено центральное хранилище, не проходит, ознакомьтесь со сведениями о том, как [восстановить сервер, на котором размещено центральное хранилище в Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span><span class="sxs-lookup"><span data-stu-id="7b4d9-107">If the database hosting the Central Management store fails, see [Restoring the server hosting the Central Management store in Lync Server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).</span></span> <span data-ttu-id="7b4d9-108">Если сервер, на котором выводится сообщение, не входит в состав сервера Enterprise Edition, ознакомьтесь со сведениями о [восстановлении рядового сервера выпуска Enterprise Edition в Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span><span class="sxs-lookup"><span data-stu-id="7b4d9-108">If an Enterprise Edition member server that is not the Back End Server fails, see [Restoring an Enterprise Edition member server in Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).</span></span>

<span data-ttu-id="7b4d9-109">Прежде чем начать восстановление, мы рекомендуем использовать копию системы с изображением.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-109">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="7b4d9-110">Вы можете использовать это изображение как точку отката, если что-то пойдет не так во время восстановления.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-110">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="7b4d9-111">После установки операционной системы и сервера SQL Server вы можете использовать копию изображения, а также восстановить или подать заявку на сертификаты.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-111">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>

<span data-ttu-id="7b4d9-112">В этой статье пример базы данных-источника имеет полное доменное имя (FQDN) BE1.contoso.com, а зеркальной базе данных — полное доменное (FQDN) BE2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-112">In this topic, the example primary database will have a fully qualified domain name (FQDN) of BE1.contoso.com, and the mirror database will have an FQDN of BE2.contoso.com.</span></span>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a><span data-ttu-id="7b4d9-113">Восстановление основной базы данных сервера выпуска Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="7b4d9-113">To restore an Enterprise Edition Back End Server Primary Database</span></span>

1.  <span data-ttu-id="7b4d9-114">Войдите на сервер переднего плана из учетной записи пользователя, который является членом группы Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-114">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

2.  <span data-ttu-id="7b4d9-115">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7b4d9-116">Принудительная переход всех настроенных баз данных на зеркальный.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-116">Force all of the configured databases to fail over to the Mirror.</span></span> <span data-ttu-id="7b4d9-117">Для каждого из типов баз данных, настроенных на этом сервере, введите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="7b4d9-117">For each of the database types that you have configured on this server, type the following cmdlet:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    <span data-ttu-id="7b4d9-118">Например:</span><span class="sxs-lookup"><span data-stu-id="7b4d9-118">For example:</span></span>
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > <span data-ttu-id="7b4d9-119">Если вы настроили серверную базу данных для использования синхронизированного отражения с следящим сервером, переход на другой ресурс выполняется автоматически.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-119">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span>

    
    </div>

4.  <span data-ttu-id="7b4d9-120">После завершения отработки отказа выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-120">After completing failover, perform the following:</span></span>
    
      - <span data-ttu-id="7b4d9-121">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку **Построитель топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-121">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="7b4d9-122">Отключение зеркального отображения на обратном сервере: щелкните правой кнопкой мыши пул в разделе **пулов на фоне Enterprise Edition** и выберите пункт **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-122">Disable mirroring on the Back End Server: Right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="7b4d9-123">На вкладке **Общие** в группе **сопоставления**снимите флажок **включить зеркальное отображение хранилища SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="7b4d9-123">On the **General** tab, under **Associations**, clear the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="7b4d9-124">Сделайте это при необходимости для архивации и мониторинга.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-124">Do this for Archiving and Monitoring as necessary.</span></span> <span data-ttu-id="7b4d9-125">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-125">Then click **OK**.</span></span>
    
      - <span data-ttu-id="7b4d9-126">Щелкните правой кнопкой мыши узел Lync Server 2013, выберите пункт **топология**и нажмите кнопку **опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-126">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="7b4d9-127">Выберите по-прежнему работающую серверную базу данных (BE2.contoso.com) в качестве нового магазина SQL.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-127">Select the still functioning backend (BE2.contoso.com) to be the new SQL store.</span></span> <span data-ttu-id="7b4d9-128">Для этого щелкните правой кнопкой мыши пул в разделе **Пулы переднего плана Enterprise Edition** и выберите пункт **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-128">To do this, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="7b4d9-129">На вкладке **Общие** в группе **сопоставления**введите полное доменное имя действующей серверной части в поле **хранилище SQL Server** (в нашем примере — BE2.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="7b4d9-129">On the **General** tab, under **Associations**, type the FQDN of the functioning backend in the **SQL Server store** field (in our example, BE2.contoso.com).</span></span>
    
      - <span data-ttu-id="7b4d9-130">Щелкните правой кнопкой мыши узел Lync Server 2013, выберите пункт **топология**и нажмите кнопку **опубликовать**.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-130">Right-click the Lync Server 2013 node, click **Topology**, and then click **Publish**.</span></span>
    
      - <span data-ttu-id="7b4d9-131">Перезапустите службы, чтобы каждый сервер мог прочитать новую топологию.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-131">Restart services so that each server can read the new topology.</span></span> <span data-ttu-id="7b4d9-132">В командной консоли Lync Server выполните следующие командлеты на каждом сервере переднего плана, который входит в этот пул:</span><span class="sxs-lookup"><span data-stu-id="7b4d9-132">From a Lync Server Management Shell, run the following cmdlets on each Front End Server that belongs to this pool:</span></span>
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  <span data-ttu-id="7b4d9-133">Удаление зеркального отображения.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-133">Uninstall mirroring.</span></span> <span data-ttu-id="7b4d9-134">В командной консоли Lync Server выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="7b4d9-134">From a Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    <span data-ttu-id="7b4d9-135">Например:</span><span class="sxs-lookup"><span data-stu-id="7b4d9-135">For example:</span></span>
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    <span data-ttu-id="7b4d9-136">Сделайте это для всех типов баз данных на этом сервере.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-136">Do this for all database types on this server.</span></span>

6.  <span data-ttu-id="7b4d9-137">Создайте чистый или новый сервер с таким же полным доменным именем (в этом примере — DB1.contoso.com) в качестве компьютера, на котором произошел сбой, установите операционную систему, а затем восстановите или порегистрируйте сертификаты.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-137">Create a clean or new server that has the same FQDN (in this example, DB1.contoso.com) as the failed computer, install the operating system, and then restore or reenroll the certificates.</span></span> <span data-ttu-id="7b4d9-138">Этот сервер будет работать в качестве новой зеркальной копии.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-138">This server will function as the new mirror.</span></span>

7.  <span data-ttu-id="7b4d9-139">Войдите в учетную запись пользователя, которая входит в группу Рткуниверсалсерверадминс, на новый сервер.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-139">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the new server.</span></span>

8.  <span data-ttu-id="7b4d9-140">Установите SQL Server 2012 или SQL Server 2008 R2, сохранив имена экземпляров так же, как и до сбоя.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-140">Install SQL Server 2012 or SQL Server 2008 R2, keeping the instance names the same as before the failure.</span></span>

9.  <span data-ttu-id="7b4d9-141">Войдите на сервер переднего плана из учетной записи пользователя, который является членом группы Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-141">From a user account that is a member of the RTCUniversalServerAdmins group, log on to a Front End Server.</span></span>

10. <span data-ttu-id="7b4d9-142">Установите зеркальную базу данных с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-142">Use Topology Builder to install mirror DB.</span></span> <span data-ttu-id="7b4d9-143">Выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-143">Perform the following steps:</span></span>
    
      - <span data-ttu-id="7b4d9-144">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку **Построитель топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-144">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>
    
      - <span data-ttu-id="7b4d9-145">Включите зеркальное отображение на обратном стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-145">Enable mirroring on the Back End Server.</span></span> <span data-ttu-id="7b4d9-146">Для этого щелкните правой кнопкой мыши пул в разделе **Пулы переднего плана Enterprise Edition** и выберите пункт **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-146">To do so, right-click on the pool under **Enterprise Edition Front End pools** and select **Edit Properties**.</span></span> <span data-ttu-id="7b4d9-147">На вкладке **Общие** в группе **связи**установите флажок **включить зеркальное отображение хранилища SQL Server** .</span><span class="sxs-lookup"><span data-stu-id="7b4d9-147">On the **General** tab, under **Associations**, select the **Enable SQL Server store mirroring** check box.</span></span> <span data-ttu-id="7b4d9-148">Кроме того, при необходимости сделайте это для архивации и мониторинга.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-148">Also do this for Archiving and Monitoring, if necessary.</span></span>
        
        <span data-ttu-id="7b4d9-149">Затем в поле **зеркальное отображение хранилища SQL Server** введите полное доменное имя нового сервера (например, BE1.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="7b4d9-149">Then, in the **Mirroring SQL Server store** field, type the FQDN of the new server (n this example, BE1.contoso.com).</span></span> <span data-ttu-id="7b4d9-150">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-150">Then click **OK**.</span></span>
    
      - <span data-ttu-id="7b4d9-151">Щелкните правой кнопкой мыши узел Lync Server 2013, выберите пункт **топология**и щелкните **установить базу данных**.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-151">Right-click the Lync Server 2013 node, click **Topology**, and then click **Install Database**.</span></span>
    
      - <span data-ttu-id="7b4d9-152">Следуйте указаниям мастера **установки базы данных** .</span><span class="sxs-lookup"><span data-stu-id="7b4d9-152">Follow the **Install Database** wizard.</span></span> <span data-ttu-id="7b4d9-153">На странице **Создание баз данных** выберите базы данных, которые вы хотите повторно создать.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-153">On the **Create databases** page, select the databases that you want to recreate.</span></span>
    
      - <span data-ttu-id="7b4d9-154">Следуйте указаниям мастера, пока не появится сообщение с запросом, **Создайте зеркальную базу данных**.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-154">Follow the wizard until you come to the prompt, **Create Mirror Database**.</span></span> <span data-ttu-id="7b4d9-155">Выберите базу данных, которую вы хотите установить, и выполните описанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="7b4d9-155">Select the database that you want to install, and complete this process.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

