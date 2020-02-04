---
title: 'Lync Server 2013: определение сервера-посредника в построителе топологии'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Mediation Server in Topology Builder
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48184217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdff7da86bd7298511ea0ef384b2736a47882a03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="0ac8e-102">Определение сервера-посредника в построителе топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ac8e-102">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ac8e-103">_**Тема последнего изменения:** 2013-03-25_</span><span class="sxs-lookup"><span data-stu-id="0ac8e-103">_**Topic Last Modified:** 2013-03-25_</span></span>

<span data-ttu-id="0ac8e-104">Выполните действия, описанные в этой статье, чтобы определить отдельный сервер-посредник или пул, размещенный в пуле переднего плана на сайте, для которого предварительно не было развернуто корпоративное голосовой интерфейс.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-104">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or a pool collocated with a Front End pool at a site for which you did not previously deploy Enterprise Voice.</span></span>

<span data-ttu-id="0ac8e-105">Вы можете определить топологию с помощью учетной записи, которая входит в группу "Администраторы".</span><span class="sxs-lookup"><span data-stu-id="0ac8e-105">You can define a topology using an account that is a member of the Administrators group.</span></span>

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a><span data-ttu-id="0ac8e-106">Определение сервера-посредника, выровненного с интерфейсом передней части пула</span><span class="sxs-lookup"><span data-stu-id="0ac8e-106">Define Mediation Server collocated to a Front End pool</span></span>

<span data-ttu-id="0ac8e-107">Выполните действия, описанные в этой статье, чтобы определить сервер-источник, выровненный в пуле переднего плана на сайте, где корпоративный голосовой интерфейс не был ранее развернут.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-107">Follow the steps in this topic to use Topology Builder to define a Mediation Server collocated to a Front End pool in a site where Enterprise Voice has not been previously deployed.</span></span>

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="0ac8e-108">Добавление сервера-исправления в пул переднего плана</span><span class="sxs-lookup"><span data-stu-id="0ac8e-108">To Add a Mediation Server to a Front End pool</span></span>

1.  <span data-ttu-id="0ac8e-109">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку **Построитель топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="0ac8e-110">В построителе топологии в дереве консоли разверните узел с именем сайта, для которого нужно определить пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-110">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>

3.  <span data-ttu-id="0ac8e-111">В дереве консоли щелкните правой кнопкой мыши тип пула переднего плана, а затем выберите команду **создать пул переднего плана..**.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-111">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>

4.  <span data-ttu-id="0ac8e-112">Перемещайтесь по мастеру **Определение нового пула переднего плана**, пока не откроете страницу **Выбор ролей серверов с совмещенным расположением**.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-112">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>

5.  <span data-ttu-id="0ac8e-113">В разделе Выбор размещенных **ролей сервера**установите флажок размещенный **сервер исправлений**.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-113">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="0ac8e-114">Если вы выбрали тип переднего плана для выпуска Enterprise Edition, серверный компонент будет установлен на всех серверах переднего плана в пуле внешних интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-114">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="0ac8e-115"><STRONG>Пул следующего прыжка</STRONG> , используемый сервером, будет являться пулом переднего плана, на котором размещен сервер для исправлений.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-115">The <STRONG>Next hop pool</STRONG> used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="0ac8e-116"><STRONG>Пул пограничного</STRONG> сервера, используемый сервером обновлений, будет таким же, как и пул переднего плана, связанный с пулом интерфейсов, на котором размещен сервер исправлений.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-116">The <STRONG>Edge pool</STRONG> used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="0ac8e-117">Нажмите кнопку **по умолчанию** , чтобы использовать этот пул переднего плана для маршрутизации звонков из Microsoft Office Communications Server 2007 R2 в КТСОП.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-117">Click **Make Default** to use this Front End pool to route calls from Microsoft Office Communications Server 2007 R2 to the PSTN.</span></span>

7.  <span data-ttu-id="0ac8e-118">Нажмите кнопку **Готово** , после того как вы завершите связывание одного или нескольких одноранговых элементов с пулом переднего плана.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-118">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0ac8e-119">Прежде чем перейти к следующему этапу в процессе развертывания Enterprise Voice, убедитесь в том, что в пуле сервера-посредника (то есть в пуле переднего плана с развернутым компонентом сервера-посредником) используются указанные полные доменные имена.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-119">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span>

    
    </div>

8.  <span data-ttu-id="0ac8e-120">Затем выполните действия, описанные в статье [Публикация топологии в Lync Server 2013](lync-server-2013-publish-the-topology.md) в руководстве по развертыванию, чтобы добавить сервер исправлений в топологию, прежде чем переходить к следующему действию при необходимости изменения портов прослушивания на сервере обновлений.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-120">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment Guide documentation to add the Mediation Server to your topology before proceeding to the next step of modifying the listening ports of the Mediation Server if needed.</span></span> <span data-ttu-id="0ac8e-121">Вы должны публиковать топологию каждый раз, когда вы используете Topology Builder, чтобы определить или изменить топологию.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-121">You must publish your topology each time you use Topology Builder to define or modify your topology.</span></span>

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a><span data-ttu-id="0ac8e-122">Определение сервера изолированных исправлений</span><span class="sxs-lookup"><span data-stu-id="0ac8e-122">Define stand-alone Mediation Server</span></span>

<span data-ttu-id="0ac8e-123">Выполните действия, описанные в этом разделе, чтобы определить изолированный сервер или пул, на котором не развернута Корпоративная работа с помощью Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-123">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or pool at a site where Enterprise Voice has not been previously deployed.</span></span>

<span data-ttu-id="0ac8e-124">Если вы уже развернули серверы исправлений, размещенные в пулах переднего плана на этом сайте, вы можете пропустить этот раздел и [установить сервер исправлений для сервера обновлений в Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) , прежде чем переходить к [настройке каналов в Lync Server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="0ac8e-124">If you already deployed Mediation Servers collocated to Front End pools at this site, you can skip this section and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) before proceeding to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0ac8e-125">В этом разделе предполагается, что вы уже настроили по крайней мере один пул переднего плана, как описано в статье <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Определение и настройка переднего плана или сервера Standard Edition в Lync server 2013</A> , а также <A href="lync-server-2013-publish-the-topology.md">опубликуйте топологию в Lync Server 2013</A> в документации руководства по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-125">This section assumes that you have already setup at least one Front End pool, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment Guide documentation.</span></span>



</div>

<div>

## <a name="to-add-a-mediation-server"></a><span data-ttu-id="0ac8e-126">Добавление сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="0ac8e-126">To Add a Mediation Server</span></span>

1.  <span data-ttu-id="0ac8e-127">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку **Построитель топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-127">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="0ac8e-128">В построителе топологии в дереве консоли разверните узел с именем сайта, для которого нужно определить сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-128">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>

3.  <span data-ttu-id="0ac8e-129">В дереве консоли щелкните правой кнопкой мыши узел **Пулы** ресурсов и выберите пункт **пул серверных обновлений**.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-129">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>

4.  <span data-ttu-id="0ac8e-130">В разделе **Определение нового пула исправлений**введите полное доменное имя пула серверов обновлений (FQDN).</span><span class="sxs-lookup"><span data-stu-id="0ac8e-130">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>

5.  <span data-ttu-id="0ac8e-131">Затем выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-131">Next, do one of the following:</span></span>
    
      - <span data-ttu-id="0ac8e-132">Если вы хотите развернуть несколько серверов обновлений в пуле для обеспечения высокой доступности, выберите пункт **несколько пулов компьютеров**.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-132">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="0ac8e-133">Необходимо развернуть балансировку нагрузки DNS для пулов серверов с несколькими серверами-исправлений.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-133">You must deploy DNS load balancing to support Mediation Server pools that have multiple Mediation Servers.</span></span> <span data-ttu-id="0ac8e-134">Дополнительные сведения можно найти в разделе Использование балансировки нагрузки DNS для пулов серверов исправлений <A href="lync-server-2013-dns-load-balancing.md">в средстве балансировки нагрузки DNS в системе Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-134">For details, see the Using DNS Load Balancing on Mediation Server Pools section of <A href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</A> in the Planning documentation.</span></span>

        
        </div>
    
      - <span data-ttu-id="0ac8e-135">Если вы хотите развернуть только один сервер-посредник в пуле, так как вам не требуется высокая доступность, выберите **один пул компьютеров**.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="0ac8e-136">Пропустите описанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-136">Skip the following step.</span></span>

6.  <span data-ttu-id="0ac8e-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="0ac8e-138">Повторите этот шаг для всех других серверов, которые вы хотите добавить в пул.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="0ac8e-139">When you have defined all the computers in the pool, click **Next**.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-139">When you have defined all the computers in the pool, click **Next**.</span></span>

7.  <span data-ttu-id="0ac8e-140">На странице **Выбор следующего прыжка** щелкните **пул очередного прыжка**, выберите полное доменное имя пула, который будет использоваться этим пулом серверов исправлений, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>

8.  <span data-ttu-id="0ac8e-141">На странице **Выбор пограничного сервера** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
      - <span data-ttu-id="0ac8e-142">Если вы хотите обеспечить подключение к сети PSTN для внешних пользователей, для которых разрешено использование корпоративной голосовой связи, в разделе **Выбор пула EDGE, используемого этим сервером исправлений**, выберите полное доменное имя пула пограничного сервера, который будет использоваться этим пулом серверов, для предоставления доступа к сети PSTN для внешних пользователей, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
      - <span data-ttu-id="0ac8e-143">Если вы не планируете включать внешних пользователей для корпоративной голосовой связи или не хотите предоставлять доступ к КТСОП для пользователей за пределами внутренней сети, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>

9.  <span data-ttu-id="0ac8e-144">Затем выполните действия, описанные в разделе [Публикация топологии в Lync Server 2013](lync-server-2013-publish-the-topology.md) в документации по развертыванию, чтобы добавить сервер исправлений в топологию.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-144">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation to add the Mediation Server to the topology.</span></span> <span data-ttu-id="0ac8e-145">Вы должны публиковать топологию каждый раз, когда используется построитель топологии для создания или изменения топологии, чтобы эти данные можно было использовать для установки файлов для серверов с Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-145">You must publish your topology each time you use Topology Builder to build or modify your topology so that the data can be used to install the files for servers that are running Lync Server.</span></span> <span data-ttu-id="0ac8e-146">Затем перейдите к следующим действиям, чтобы при необходимости изменить порты прослушивания на сервере обновлений.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-146">Then continue to the next steps to modify the listening ports on the Mediation Server, if necessary.</span></span>

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="0ac8e-147">Определение Прослушивающихх портов сервера</span><span class="sxs-lookup"><span data-stu-id="0ac8e-147">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="0ac8e-148">Выполните действия, описанные в этом разделе, чтобы определить порты прослушивания сервер или группа, которые будут получать входящие соединения от кэширующего узла шлюза.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-148">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="0ac8e-149">Изменение портов для прослушивания сервера исправлений</span><span class="sxs-lookup"><span data-stu-id="0ac8e-149">To Modify the Mediation Server Listening Ports</span></span>

1.  <span data-ttu-id="0ac8e-150">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку **Построитель топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-150">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="0ac8e-151">В построителе топологии в дереве консоли разверните узел **Пулы исправлений** и щелкните правой кнопкой мыши сервер-посредника, который вы создали ранее.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-151">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>

3.  <span data-ttu-id="0ac8e-152">По умолчанию порты для прослушивания SIP на сервере-посреднике — это 5070 для трафика TLS из Lync Server, 5067 для TLS-трафика от одноранговых серверов (шлюзы, Пбксес или SBCs).</span><span class="sxs-lookup"><span data-stu-id="0ac8e-152">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Lync Server, 5067 for TLS traffic from peers (gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="0ac8e-153">TCP-порт по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-153">TCP port is disabled by default.</span></span> <span data-ttu-id="0ac8e-154">Необходимо включить TCP-порт, если имеются шлюзы, не поддерживающие TLS.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-154">You must enable TCP port if you have gateways that do not support TLS.</span></span>

4.  <span data-ttu-id="0ac8e-155">Укажите требуемый диапазон портов для прослушивания TLS или TCP. сервер исправлений будет принимать входящие подключения от шлюзов PSTN.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-155">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0ac8e-156">Ввод диапазона портов TCP не обязателен, если не установлен флажок <STRONG>Включить порт TCP</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-156">Entering a TCP port range is not required if <STRONG>Enable TCP port</STRONG> is not checked.</span></span> <span data-ttu-id="0ac8e-157">Это настройка не обязательна.</span><span class="sxs-lookup"><span data-stu-id="0ac8e-157">This setting is optional.</span></span>

    
    </div>

<span data-ttu-id="0ac8e-158">Затем [Определите шлюз в построителе топологии в Lync server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) и установите файлы на каждый сервер-посредник в пуле, выполнив действия, описанные в разделе [Установка сервера обновлений файлов для исправлений в Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="0ac8e-158">Next, [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) and install the files on each Mediation Server in the pool by following the procedures in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

