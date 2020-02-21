---
title: 'Lync Server 2013: определение сервера-посредника в построителе топологий'
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
ms.openlocfilehash: 782491b0df1c8d2432a9b4c69240293ccc126e7c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a><span data-ttu-id="057bd-102">Определение сервера-посредника в построителе топологий в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="057bd-102">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="057bd-103">_**Последнее изменение темы:** 2013-03-25_</span><span class="sxs-lookup"><span data-stu-id="057bd-103">_**Topic Last Modified:** 2013-03-25_</span></span>

<span data-ttu-id="057bd-104">Выполните действия, описанные в этом разделе, чтобы использовать построитель топологий, чтобы определить автономный сервер-посредник или пул, размещенный в пуле переднего плана на сайте, для которого ранее не было развернуто Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="057bd-104">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or a pool collocated with a Front End pool at a site for which you did not previously deploy Enterprise Voice.</span></span>

<span data-ttu-id="057bd-105">Вы можете определить топологию с помощью учетной записи, входящей в группу администраторов.</span><span class="sxs-lookup"><span data-stu-id="057bd-105">You can define a topology using an account that is a member of the Administrators group.</span></span>

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a><span data-ttu-id="057bd-106">Определение сервера-посредника, размещенного в пуле переднего плана</span><span class="sxs-lookup"><span data-stu-id="057bd-106">Define Mediation Server collocated to a Front End pool</span></span>

<span data-ttu-id="057bd-107">Выполните действия, описанные в этом разделе, чтобы использовать построитель топологий, чтобы определить сервер-посредник, размещенный в пуле переднего плана на сайте, на котором ранее не было развернуто Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="057bd-107">Follow the steps in this topic to use Topology Builder to define a Mediation Server collocated to a Front End pool in a site where Enterprise Voice has not been previously deployed.</span></span>

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a><span data-ttu-id="057bd-108">Добавление сервера-посредника в пул переднего плана</span><span class="sxs-lookup"><span data-stu-id="057bd-108">To Add a Mediation Server to a Front End pool</span></span>

1.  <span data-ttu-id="057bd-109">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="057bd-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="057bd-110">В построителе топологий в дереве консоли разверните узел с именем сайта, для которого нужно определить пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="057bd-110">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Front End pool.</span></span>

3.  <span data-ttu-id="057bd-111">В дереве консоли щелкните правой кнопкой мыши необходимый тип пула переднего плана, а затем выберите команду **создать пул переднего плана..**.</span><span class="sxs-lookup"><span data-stu-id="057bd-111">In the console tree, right-click the type of Front End pool you want, and then click **New Front End pool..**.</span></span>

4.  <span data-ttu-id="057bd-112">Перемещайтесь по мастеру **Определение нового пула переднего плана**, пока не откроете страницу **Выбор ролей серверов с совмещенным расположением**.</span><span class="sxs-lookup"><span data-stu-id="057bd-112">Navigate through the **Define New Front End Pool** wizard until you reach the **Select collocated server roles** page.</span></span>

5.  <span data-ttu-id="057bd-113">В разделе Выбор размещенных **ролей сервера**установите флажок совместный доступ к **серверу-посреднику**.</span><span class="sxs-lookup"><span data-stu-id="057bd-113">In **Select collocated server roles**, check the option **Collocate Mediation Server**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="057bd-114">Если для выбранного типа пула переднего плана выбран корпоративный выпуск, компонент сервера-посредника будет установлен на всех серверах переднего плана этого интерфейсного пула.</span><span class="sxs-lookup"><span data-stu-id="057bd-114">If the type of Front End pool you selected is the Enterprise Edition, then the Mediation Server component will be installed on all the Front End Servers of that Front End pool.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="057bd-115"><STRONG>Пул следующего прыжка</STRONG> , используемый сервером-посредником, будет интерфейсным пулом, в котором размещен сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="057bd-115">The <STRONG>Next hop pool</STRONG> used by the Mediation Server will be the Front End pool where the Mediation Server is collocated on.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="057bd-116"><STRONG>Пограничный пул</STRONG> , используемый сервером-посредником, будет таким же, как и пул переднего плана, связанный с пулом переднего плана, на котором размещен сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="057bd-116">The <STRONG>Edge pool</STRONG> used by the Mediation Server will be the same Edge pool associated with the Front End pool where the Mediation Server is collocated on.</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="057bd-117">Щелкните **по умолчанию** , чтобы использовать этот пул переднего плана для маршрутизации вызовов из Microsoft Office Communications Server 2007 R2 в PSTN.</span><span class="sxs-lookup"><span data-stu-id="057bd-117">Click **Make Default** to use this Front End pool to route calls from Microsoft Office Communications Server 2007 R2 to the PSTN.</span></span>

7.  <span data-ttu-id="057bd-118">По завершении связывания одного или нескольких одноранговых узлов с пулом переднего плана нажмите кнопку **Готово** .</span><span class="sxs-lookup"><span data-stu-id="057bd-118">Click **Finish** when you are finished associating one or more peers to the Front End pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="057bd-119">Прежде чем перейти к следующему шагу в процессе развертывания корпоративной голосовой связи, убедитесь, что в качестве пула серверов-посредников (то есть интерфейсного пула с размещенным компонентом сервера-посредником) используются указанные полные доменные имена.</span><span class="sxs-lookup"><span data-stu-id="057bd-119">Before you proceed to the next step in the Enterprise Voice deployment process, make sure that the Mediation Server pool (i.e. Front End pool with the Mediation Server component collocated) is using the FQDNs that you specified.</span></span>

    
    </div>

8.  <span data-ttu-id="057bd-120">После этого выполните действия, описанные в статье [Публикация топологии в Lync Server 2013](lync-server-2013-publish-the-topology.md) , в руководстве по развертыванию, чтобы добавить сервер-посредник в топологию, прежде чем переходить к следующему этапу изменения портов прослушивания сервера-посредника, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="057bd-120">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment Guide documentation to add the Mediation Server to your topology before proceeding to the next step of modifying the listening ports of the Mediation Server if needed.</span></span> <span data-ttu-id="057bd-121">Топологию необходимо опубликовать каждый раз, когда вы используете построитель топологий, чтобы определить или изменить топологию.</span><span class="sxs-lookup"><span data-stu-id="057bd-121">You must publish your topology each time you use Topology Builder to define or modify your topology.</span></span>

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a><span data-ttu-id="057bd-122">Определение изолированного сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="057bd-122">Define stand-alone Mediation Server</span></span>

<span data-ttu-id="057bd-123">Выполните действия, описанные в этом разделе, чтобы использовать построитель топологий для определения изолированного сервера-посредника или пула на сайте, на котором ранее не было развернуто Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="057bd-123">Follow the steps in this topic to use Topology Builder to define a stand-alone Mediation Server or pool at a site where Enterprise Voice has not been previously deployed.</span></span>

<span data-ttu-id="057bd-124">Если вы уже развернули серверы-посредники, размещенные в пулах переднего плана на этом сайте, вы можете пропустить этот раздел и [установить файлы сервера-посредника в Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) , прежде чем приступать к [настройке магистральных каналов в Lync Server 2013](lync-server-2013-configuring-trunks.md).</span><span class="sxs-lookup"><span data-stu-id="057bd-124">If you already deployed Mediation Servers collocated to Front End pools at this site, you can skip this section and [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md) before proceeding to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="057bd-125">В этом разделе предполагается, что вы уже настроили по крайней мере один интерфейсный пул, как описано в статье <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Определение и Настройка пула переднего плана или сервера Standard Edition в Lync server 2013</A> и <A href="lync-server-2013-publish-the-topology.md">Публикация топологии в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="057bd-125">This section assumes that you have already setup at least one Front End pool, as described in <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Define and configure a Front End pool or Standard Edition server in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment Guide documentation.</span></span>



</div>

<div>

## <a name="to-add-a-mediation-server"></a><span data-ttu-id="057bd-126">Добавление сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="057bd-126">To Add a Mediation Server</span></span>

1.  <span data-ttu-id="057bd-127">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="057bd-127">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="057bd-128">В построителе топологий в дереве консоли разверните узел с именем сайта, для которого требуется определить сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="057bd-128">In Topology Builder, in the console tree, expand the name of the site for which you want to define a Mediation Server.</span></span>

3.  <span data-ttu-id="057bd-129">В дереве консоли щелкните правой кнопкой мыши узел **Пулы-посредники** и выберите пункт **пул серверов-посредников**.</span><span class="sxs-lookup"><span data-stu-id="057bd-129">In the console tree, right-click the **Mediation pools** node, and then click **Mediation Server pool**.</span></span>

4.  <span data-ttu-id="057bd-130">В окне **Определение нового пула-посредника**введите полное доменное имя пула серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="057bd-130">In **Define New Mediation Pool**, type the Mediation Server pool fully qualified domain name (FQDN).</span></span>

5.  <span data-ttu-id="057bd-131">Затем выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="057bd-131">Next, do one of the following:</span></span>
    
      - <span data-ttu-id="057bd-132">Если вы хотите развернуть несколько серверов-посредников в пуле, чтобы обеспечить высокую доступность, выберите **пул с несколькими компьютерами**.</span><span class="sxs-lookup"><span data-stu-id="057bd-132">If you want to deploy multiple Mediation Servers in the pool to provide high availability, then select **Multiple computer pool**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="057bd-133">Для поддержки пулов серверов-посредников с несколькими серверами-посредниками необходимо развернуть балансировку нагрузки на DNS.</span><span class="sxs-lookup"><span data-stu-id="057bd-133">You must deploy DNS load balancing to support Mediation Server pools that have multiple Mediation Servers.</span></span> <span data-ttu-id="057bd-134">Дополнительные сведения можно найти в разделе Использование балансировки нагрузки на DNS в пулах серверов <A href="lync-server-2013-dns-load-balancing.md">-посредников в разделе Балансировка нагрузки на DNS в среде Lync server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="057bd-134">For details, see the Using DNS Load Balancing on Mediation Server Pools section of <A href="lync-server-2013-dns-load-balancing.md">DNS load balancing in Lync Server 2013</A> in the Planning documentation.</span></span>

        
        </div>
    
      - <span data-ttu-id="057bd-135">Если вы хотите развернуть только один сервер-посредник в пуле, так как не требуется высокая доступность, выберите **один пул компьютеров**.</span><span class="sxs-lookup"><span data-stu-id="057bd-135">If you want to deploy only one Mediation Server in the pool because you do not require high availability, then select **Single computer pool**.</span></span> <span data-ttu-id="057bd-136">Пропустите следующий шаг.</span><span class="sxs-lookup"><span data-stu-id="057bd-136">Skip the following step.</span></span>

6.  <span data-ttu-id="057bd-137">Если на предыдущем шаге вы выбрали вариант **Пул на нескольких компьютерах**, в разделе **Определение компьютеров в этом пуле** щелкните поле **Полное доменное имя компьютера**, введите полное доменное имя каждого сервера в пуле и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="057bd-137">If you selected **Multiple computer pool** in the previous step, on the **Define the computers in this pool** item, click **Computer FQDN**, type the FQDN of each server in the pool, and then click **Add**.</span></span> <span data-ttu-id="057bd-138">Повторите это действие для всех остальных серверов-посредников, которые необходимо добавить в пул.</span><span class="sxs-lookup"><span data-stu-id="057bd-138">Repeat this step for all other Mediation Servers that you want to add to the pool.</span></span> <span data-ttu-id="057bd-139">Определив все компьютеры в пуле, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="057bd-139">When you have defined all the computers in the pool, click **Next**.</span></span>

7.  <span data-ttu-id="057bd-140">На странице **Выбор следующего прыжка** щелкните **пул следующего прыжка**, выберите полное доменное имя интерфейсного пула, который будет использовать этот пул серверов-посредника, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="057bd-140">On the **Select the next hop** page, click **Next hop pool**, click the FQDN of the Front End pool that will use this Mediation Server pool, and then click **Next**.</span></span>

8.  <span data-ttu-id="057bd-141">На странице **Выбор пограничного сервера** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="057bd-141">On the **Select an Edge Server** page, do one of the following:</span></span>
    
      - <span data-ttu-id="057bd-142">Если вы хотите предоставить доступ к сети PSTN внешним пользователям, для которых включена поддержка корпоративной голосовой связи, в группе **выберите Пограничный пул, используемую сервером-посредником**выберите полное доменное имя пула пограничных серверов, который будет использовать этот пул серверов-посредника для предоставления подключения PSTN к этим внешним пользователям, а затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="057bd-142">If you want to provide PSTN connectivity to external users enabled for Enterprise Voice, under **Select Edge Pool used by this Mediation Server**, click the FQDN of the Edge Server pool that will use this Mediation Server pool to provide PSTN connectivity to those external users, and then click **Next**.</span></span>
    
      - <span data-ttu-id="057bd-143">Если вы не планируете включить внешних пользователей для корпоративной голосовой связи или если вы не хотите предоставлять доступ к сети PSTN пользователям, находящимся за пределами внутренней сети, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="057bd-143">If you do not plan to enable external users for Enterprise Voice, or if you do not want to provide PSTN connectivity to users when they are outside the internal network, click **Next**.</span></span>

9.  <span data-ttu-id="057bd-144">После этого выполните действия, описанные в статье [Публикация топологии в Lync Server 2013](lync-server-2013-publish-the-topology.md) , в документации по развертыванию, чтобы добавить сервер-посредник в топологию.</span><span class="sxs-lookup"><span data-stu-id="057bd-144">Next, follow the procedures in [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md) in the Deployment documentation to add the Mediation Server to the topology.</span></span> <span data-ttu-id="057bd-145">Топологию необходимо опубликовать каждый раз, когда вы используете построитель топологий для создания или изменения топологии, чтобы можно было использовать эти данные для установки файлов для серверов, на которых работает Lync Server.</span><span class="sxs-lookup"><span data-stu-id="057bd-145">You must publish your topology each time you use Topology Builder to build or modify your topology so that the data can be used to install the files for servers that are running Lync Server.</span></span> <span data-ttu-id="057bd-146">Далее перейдите к следующим этапам, чтобы изменить прослушивающие порты на сервере-посреднике, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="057bd-146">Then continue to the next steps to modify the listening ports on the Mediation Server, if necessary.</span></span>

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a><span data-ttu-id="057bd-147">Определение портов прослушивания сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="057bd-147">Define the Mediation Server Listening Ports</span></span>

<span data-ttu-id="057bd-148">Выполните действия, описанные в этом разделе, чтобы использовать построитель топологий для определения портов прослушивания сервер-посредник или пул будет принимать входящие подключения от узла шлюза.</span><span class="sxs-lookup"><span data-stu-id="057bd-148">Follow the steps in this topic to use Topology Builder to define the listening ports a Mediation Server or pool will accept incoming connections from a gateway peer.</span></span>

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a><span data-ttu-id="057bd-149">Изменение портов прослушивания сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="057bd-149">To Modify the Mediation Server Listening Ports</span></span>

1.  <span data-ttu-id="057bd-150">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="057bd-150">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="057bd-151">В построителе топологий в дереве консоли разверните узел **Пулы посредников** и щелкните правой кнопкой мыши сервер-посредник, созданный ранее.</span><span class="sxs-lookup"><span data-stu-id="057bd-151">In Topology Builder, in the console tree, expand the **Mediation pools** node, and right-click the Mediation Server previously created.</span></span>

3.  <span data-ttu-id="057bd-152">По умолчанию порты SIP на сервере-посреднике 5070 для трафика TLS из Lync Server, 5067 для трафика TLS от кэширующих узлов (шлюзы, УАТС или SBCs).</span><span class="sxs-lookup"><span data-stu-id="057bd-152">By default, the SIP listening ports on the Mediation Server are 5070 for TLS traffic from Lync Server, 5067 for TLS traffic from peers (gateways, PBXes, or SBCs).</span></span> <span data-ttu-id="057bd-153">TCP-порт по умолчанию отключен.</span><span class="sxs-lookup"><span data-stu-id="057bd-153">TCP port is disabled by default.</span></span> <span data-ttu-id="057bd-154">Необходимо включить TCP-порт, если имеются шлюзы, не поддерживающие TLS.</span><span class="sxs-lookup"><span data-stu-id="057bd-154">You must enable TCP port if you have gateways that do not support TLS.</span></span>

4.  <span data-ttu-id="057bd-155">Укажите требуемый диапазон портов для прослушивания TLS или TCP. сервер-посредник принимает входящие подключения от шлюзов PSTN.</span><span class="sxs-lookup"><span data-stu-id="057bd-155">Specify the desired TLS or TCP listening port range the Mediation Server will accept incoming connections from PSTN gateways.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="057bd-156">Ввод диапазона портов TCP не является обязательным, если не установлен флажок  <STRONG>Включить порт TCP</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="057bd-156">Entering a TCP port range is not required if <STRONG>Enable TCP port</STRONG> is not checked.</span></span> <span data-ttu-id="057bd-157">Эта запись не является обязательной.</span><span class="sxs-lookup"><span data-stu-id="057bd-157">This setting is optional.</span></span>

    
    </div>

<span data-ttu-id="057bd-158">Затем [Определите шлюз в построителе топологий в Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) и установите файлы на каждом сервере-посреднике в пуле, выполнив процедуры, описанные в разделе [Установка файлов для сервера-посредника в Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="057bd-158">Next, [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) and install the files on each Mediation Server in the pool by following the procedures in [Install the files for Mediation Server in Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

