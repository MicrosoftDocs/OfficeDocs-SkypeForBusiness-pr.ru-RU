---
title: 'Lync Server 2013: Настройка канала с помощью мультимедийного обхода'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a trunk with media bypass
ms:assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398792(v=OCS.15)
ms:contentKeyID: 48184959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41f5f254dfd3ad63d3f6390f16837c777bd02a91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a><span data-ttu-id="b2cff-102">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2cff-102">Configure a trunk with media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2cff-103">_**Тема последнего изменения:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="b2cff-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="b2cff-104">Выполните следующие действия, чтобы настроить магистраль с включенным режимом обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="b2cff-104">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="b2cff-105">Чтобы настроить магистраль с отключенным обходом мультимедиа, пропустите раздел [Настройка магистрали без обхода мультимедиа в Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="b2cff-105">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span></span> <span data-ttu-id="b2cff-106">Обход мультимедиа полезен, если вы хотите минимизировать количество развернутых серверов исправлений.</span><span class="sxs-lookup"><span data-stu-id="b2cff-106">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="b2cff-107">Обычно пул серверов-посредников будет развернут на центральном сайте, и он будет управлять шлюзами на сайтах филиалов.</span><span class="sxs-lookup"><span data-stu-id="b2cff-107">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="b2cff-108">Включение обхода сервера-посредника позволяет проходить мультимедиа для вызовов ТСОП от клиентов на сайтах филиалов непосредственно через шлюзы на этих сайтах.</span><span class="sxs-lookup"><span data-stu-id="b2cff-108">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="b2cff-109">В Lync Server 2013 маршруты исходящих вызовов и политики корпоративной голосовой связи должны быть настроены правильно, так что звонки между клиентами на сайте филиала направляются на соответствующий шлюз.</span><span class="sxs-lookup"><span data-stu-id="b2cff-109">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="b2cff-110">Мы настоятельно рекомендуем включить обход мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="b2cff-110">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="b2cff-111">Тем не менее, перед включением поддержки мультимедиа на магистральной магистрали SIP убедитесь в том, что поставщик магистральной магистрали SIP поддерживает обход мультимедиа и может обеспечить соответствие требованиям, предъявляемым к успешному включению сценария.</span><span class="sxs-lookup"><span data-stu-id="b2cff-111">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="b2cff-112">В частности, поставщик должен иметь IP-адреса серверов в внутренней сети Организации.</span><span class="sxs-lookup"><span data-stu-id="b2cff-112">Specifically, the provider must have the IP addresses of servers in your organization’s internal network.</span></span> <span data-ttu-id="b2cff-113">Если поставщик не поддерживает этот сценарий, обход мультимедиа не будет успешным.</span><span class="sxs-lookup"><span data-stu-id="b2cff-113">If the provider cannot support this scenario, media bypass will not succeed.</span></span> <span data-ttu-id="b2cff-114">Подробности можно найти [в разделе Планирование обхода мультимедиа в Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="b2cff-114">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b2cff-115">Обход мультимедиа не будет взаимодействовать с каждым шлюзом коммутируемой телефонной сети (PSTN), IP-УАТС и контроллером границ сеанса (SBC).</span><span class="sxs-lookup"><span data-stu-id="b2cff-115">Media bypass will not interoperate with every public switched telephone network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="b2cff-116">Корпорация Microsoft протестировала набор шлюзов ТСОП и контроллеров SBC с сертифицированными партнерами и провела некоторые тесты для Cisco IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="b2cff-116">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="b2cff-117">Обход мультимедиа поддерживается только в том случае, если у вас есть продукты и версии, которые указаны в едином приложении для <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>совместной работы с общедоступной программой Lync Server:</span><span class="sxs-lookup"><span data-stu-id="b2cff-117">Media bypass is supported only with products and versions that are listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="b2cff-p104">Описанная ниже конфигурация магистрали содержит набор параметров, применяемых к магистралям, которым она назначается. Отдельная конфигурация магистрали может действовать в глобальной области (для всех магистралей, которым не назначена более конкретная конфигурация сайта или пула), в области сайта или в области пула. Конфигурация магистрали уровня пула используется для назначения отдельной магистрали.</span><span class="sxs-lookup"><span data-stu-id="b2cff-p104">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="b2cff-121">Настройка магистрали с обходом сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="b2cff-121">To configure a trunk with media bypass</span></span>

1.  <span data-ttu-id="b2cff-122">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b2cff-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="b2cff-123">Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="b2cff-123">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="b2cff-124">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b2cff-124">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b2cff-125">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b2cff-125">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b2cff-126">На левой панели навигации щелкните **Маршрутизация голосовой связи** и **Настройка магистрали**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-126">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="b2cff-127">На странице **Настройка магистрали** воспользуйтесь одним из описанных ниже методов.</span><span class="sxs-lookup"><span data-stu-id="b2cff-127">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="b2cff-128">Дважды щелкните имеющуюся магистраль (например, **Глобальную**), чтобы открыть окно **Изменение настройки магистрали**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-128">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="b2cff-129">Нажмите **Создать** и выберите область для новой конфигурации магистрали:</span><span class="sxs-lookup"><span data-stu-id="b2cff-129">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="b2cff-130">**Магистраль сайта:** Выберите сайт для этой конфигурации канала и **выберите сайт**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-130">**Site trunk:** Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="b2cff-131">Обратите внимание, что сайты, для которых уже создана конфигурация магистрали, не отображаются в разделе **Выбор сайта**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-131">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="b2cff-132">Эта конфигурация будет применяться ко всем магистралям на сайте.</span><span class="sxs-lookup"><span data-stu-id="b2cff-132">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="b2cff-133">**Магистраль пула:** Выберите имя канала, к которому будет применена эта конфигурация магистрали.</span><span class="sxs-lookup"><span data-stu-id="b2cff-133">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="b2cff-134">Этот магистраль может быть корневым магистральом или любыми дополнительными магистральными магистрали, определенными в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="b2cff-134">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="b2cff-135">В разделе **Выбор службы** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-135">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="b2cff-136">Обратите внимание, что магистрали, для которых уже создана конфигурация, не отображаются в разделе **Выбор службы**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-136">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b2cff-137">Выбранную область конфигурации магистрали нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="b2cff-137">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="b2cff-138">Поле <STRONG>Название</STRONG> заполняется названием связанного с конфигурацией магистрали сайта или службы. Изменить его нельзя.</span><span class="sxs-lookup"><span data-stu-id="b2cff-138">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="b2cff-p109">Укажите значение в поле **Максимальное количество поддерживаемых предварительных диалогов**. Это максимальное число разветвленных ответов, которые может получить ТСОП-шлюз, IP-УАТС или пограничный контроллер сеансов ITSP (SBC) на запрос INVITE, отправленный серверу-посреднику. Значение по умолчанию: 20.</span><span class="sxs-lookup"><span data-stu-id="b2cff-p109">Specify a value in **Maximum early dialogs supported**. This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server. The default value is 20.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b2cff-142">Перед сменой данного значения, проконсультируйтесь со своим поставщиком или производителем оборудования насчет информации о возможностях своей системы.</span><span class="sxs-lookup"><span data-stu-id="b2cff-142">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

    
    </div>

6.  <span data-ttu-id="b2cff-143">Выберите один из описанных ниже вариантов для **Уровня поддержки шифрования**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-143">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="b2cff-144">**Обязательно:** Шифрование с помощью протокола передачи данных в режиме реального времени (SRTP) должно использоваться для защиты трафика между сервером-посредником и шлюзом или частным обменом филиалов (УАТС).</span><span class="sxs-lookup"><span data-stu-id="b2cff-144">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="b2cff-145">**Необязательно:** SRTP шифрование используется, если поставщик услуг или оборудования его поддерживает.</span><span class="sxs-lookup"><span data-stu-id="b2cff-145">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="b2cff-146">**Не поддерживается:** SRTP шифрование не поддерживается поставщиком услуг или производителем оборудования, поэтому оно не будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="b2cff-146">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

7.  <span data-ttu-id="b2cff-147">Установите флажок **Включить режим обхода сервера-посредника**, если нужно, чтобы одноранговые узлы магистрали обходили сервер-посредник при передаче медиаданных.</span><span class="sxs-lookup"><span data-stu-id="b2cff-147">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b2cff-148">Для успешной работы данного режима ТСОП-шлюз, IP-УАТС или пограничный контроллер сеансов ITSP должны иметь определенные возможности.</span><span class="sxs-lookup"><span data-stu-id="b2cff-148">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="b2cff-149">Подробности можно найти <A href="lync-server-2013-planning-for-media-bypass.md">в разделе Планирование обхода мультимедиа в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="b2cff-149">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="b2cff-p111">Установите флажок **Централизованная обработка медиаданных**, если имеется хорошо известная конечная точка для медиаданных (например, ТСОП-шлюз, где завершение медиаданных имеет тот же IP что и завершение сигнала). Сбросьте данный флажок, если у магистрали нет такой точки.</span><span class="sxs-lookup"><span data-stu-id="b2cff-p111">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

9.  <span data-ttu-id="b2cff-152">Если магистральный одноранговый элемент поддерживает получение запросов на использование SIP от сервера обновлений, установите флажок **Разрешить отправку ссылку на шлюз** .</span><span class="sxs-lookup"><span data-stu-id="b2cff-152">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b2cff-153">Если отключить данную опцию при установленной <STRONG>Включить режим обхода медиаданных</STRONG> потребуется указание дополнительных параметров.</span><span class="sxs-lookup"><span data-stu-id="b2cff-153">If you disable this option while the <STRONG>Enable media bypass</STRONG> option is selected, additional settings are required.</span></span> <span data-ttu-id="b2cff-154">Если узел магистрали не поддерживает получение запросов SIP REFER от сервера-посредника и включен режим обхода, необходимо также запустить командлет <STRONG>Set-CsTrunkConfiguration</STRONG>, чтобы отключить RTCP для активных и удерживаемых звонков и обеспечить нужные условия для обхода.</span><span class="sxs-lookup"><span data-stu-id="b2cff-154">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="b2cff-155">Подробные сведения можно найти в руководстве по <A href="lync-server-2013-lync-server-management-shell.md">среде управления Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="b2cff-155">For details, see the <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> documentation.</span></span><BR><span data-ttu-id="b2cff-156">Если необходимо, чтобы переключенные звонки обходили медиаданные и шлюз не поддерживал запросы SIP REFER, выберите <STRONG>Разрешить ссылку с использованием стороннего контроля вызовов</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="b2cff-156">Alternatively, you can select <STRONG>Enable refer using third-party-call control</STRONG> if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

    
    </div>

10. <span data-ttu-id="b2cff-157">(Необязательно) Чтобы включить маршрутизацию между магистральными линиями связи, сопоставьте и настройте записи режима работы с ТСОП для этой конфигурации магистральной линии связи.</span><span class="sxs-lookup"><span data-stu-id="b2cff-157">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="b2cff-158">Использование PSTN, связанное с этой конфигурацией канала, будет применяться ко всем входящим звонкам через магистраль, не исходящий из конечной точки Lync.</span><span class="sxs-lookup"><span data-stu-id="b2cff-158">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint.</span></span> <span data-ttu-id="b2cff-159">Чтобы управлять записями режима работы с ТСОП, связанными с конфигурацией магистральной линии связи, используйте один из приведенных ниже методов.</span><span class="sxs-lookup"><span data-stu-id="b2cff-159">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="b2cff-160">Чтобы выбрать одну или несколько записей из списка всех записей использования PSTN, доступных в вашем корпоративном развертывании, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-160">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="b2cff-161">Выделите записи, которые следует связать с этой конфигурацией магистральной линии связи, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-161">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="b2cff-162">Чтобы удалить запись режима работы с ТСОП из этой конфигурации магистральной линии связи, выберите эту запись и щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-162">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="b2cff-163">Чтобы определить новую запись режима работы с ТСОП и сопоставить ее с этой конфигурацией магистральной линии связи, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b2cff-163">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="b2cff-164">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-164">Click **New**.</span></span>
        
        2.  <span data-ttu-id="b2cff-165">В поле **Имя** укажите уникальное описательное имя для записи.</span><span class="sxs-lookup"><span data-stu-id="b2cff-165">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="b2cff-p115">Имя записи о режиме работы с ТСОП не должно повторяться в пределах развертывания корпоративной голосовой связи. После сохранения записи поле <STRONG>Имя</STRONG> не доступно для редактирования.</span><span class="sxs-lookup"><span data-stu-id="b2cff-p115">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="b2cff-168">Используйте один из следующих методов для сопоставления и настройки маршрутов для этой записи режима работы с ТСОП:</span><span class="sxs-lookup"><span data-stu-id="b2cff-168">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="b2cff-169">Чтобы выбрать один или несколько маршрутов из списка всех доступных маршрутов в вашем корпоративном развертывании, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-169">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="b2cff-170">Выделите маршруты, которые требуется сопоставить с этой записью режима работы с ТСОП, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-170">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="b2cff-171">Чтобы удалить маршрут из записи режима работы с ТСОП, выберите этот маршрут и щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-171">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="b2cff-172">Чтобы определить новый маршрут и сопоставить его с этой записью режима работы с ТСОП, щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-172">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="b2cff-173">Дополнительные сведения можно найти [в разделе Создание голосовых маршрутов в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="b2cff-173">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="b2cff-174">Чтобы изменить маршрут, сопоставленный с этой записью режима работы с ТСОП, выберите данный маршрут и щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-174">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="b2cff-175">Подробности можно найти [в разделе Изменение голосового маршрута в Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="b2cff-175">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="b2cff-176">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-176">Click **OK**.</span></span>
    
      - <span data-ttu-id="b2cff-177">Чтобы изменить запись режима работы с ТСОП, уже сопоставленную с этой настройкой магистральной линии связи, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b2cff-177">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="b2cff-178">Выберите запись режима работы с ТСОП, которую требуется изменить, и щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-178">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="b2cff-179">Используйте один из следующих методов для сопоставления и настройки маршрутов для этой записи режима работы с ТСОП:</span><span class="sxs-lookup"><span data-stu-id="b2cff-179">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="b2cff-180">Чтобы выбрать один или несколько маршрутов из списка всех доступных маршрутов в вашем корпоративном развертывании, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-180">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="b2cff-181">Выделите маршруты, которые требуется сопоставить с этой записью режима работы с ТСОП, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-181">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="b2cff-182">Чтобы удалить маршрут из записи режима работы с ТСОП, выберите этот маршрут и щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-182">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="b2cff-183">Чтобы определить новый маршрут и сопоставить его с этой записью режима работы с ТСОП, щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-183">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="b2cff-184">Дополнительные сведения можно найти [в разделе Создание голосовых маршрутов в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="b2cff-184">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="b2cff-185">Чтобы изменить маршрут, сопоставленный с этой записью режима работы с ТСОП, выберите данный маршрут и щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-185">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="b2cff-186">Подробности можно найти [в разделе Изменение голосового маршрута в Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="b2cff-186">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="b2cff-187">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-187">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b2cff-188">Важно связывать записи об использовании PSTN в соответствии с одноранговым элементом сервера, связанным с настройкой магистрали.</span><span class="sxs-lookup"><span data-stu-id="b2cff-188">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="b2cff-189">Если одноранговый сервер является шлюзом PSTN или контроллером границ сеанса (SBC), настоятельно рекомендуется, чтобы конфигурация канала не сопоставлена с записью использования PSTN, которая направляет маршрут в назначение PSTN или другие нижестоящие системы, подключенные через Lync. Server.</span><span class="sxs-lookup"><span data-stu-id="b2cff-189">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

11. <span data-ttu-id="b2cff-p123">Измените расположение записей режима работы с ТСОП, чтобы обеспечить оптимальную производительность. Чтобы изменить расположение записи в списке, выберите соответствующую запись режима работы с ТСОП и щелкните стрелку вверх или стрелку вниз.</span><span class="sxs-lookup"><span data-stu-id="b2cff-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b2cff-192">Порядок расположения записей режима работы с ТСОП в списке является важным.</span><span class="sxs-lookup"><span data-stu-id="b2cff-192">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="b2cff-193">Lync Server обходит список сверху вниз.</span><span class="sxs-lookup"><span data-stu-id="b2cff-193">Lync Server traverses the list from top to down.</span></span>

    
    </div>

12. <span data-ttu-id="b2cff-194">Чтобы включить обход медиаданных для клиентов, защищенных системой преобразования сетевых адресов (NAT) или брандмауэром и SBC с поддержкой блокировки, выберите **Разрешить блокирование RTP**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-194">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

13. <span data-ttu-id="b2cff-195">**Включите функцию "включить переадресацию звонков** ", чтобы разрешить отправку сведений из журнала звонков на узел шлюза на сервере обновлений.</span><span class="sxs-lookup"><span data-stu-id="b2cff-195">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

14. <span data-ttu-id="b2cff-196">**Включите функцию переадресации с Поутвержденными данными** об удостоверениях, чтобы включить в нее сведения о выдаче сигнала p-Assert (паи), которые нужно перенаправить на сторону сервера-посредника и на сторону шлюза (и наоборот) (и наоборот).</span><span class="sxs-lookup"><span data-stu-id="b2cff-196">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

15. <span data-ttu-id="b2cff-197">Чтобы включить быструю отработку отказа, выберите **Включить таймер отработки отказа внешней маршрутизации**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-197">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="b2cff-198">Шлюз, связанный с данной магистралью, может отправить уведомление об обработке исходящего вызова в течение 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="b2cff-198">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="b2cff-199">Перенаправление на другую магистраль произойдет, если это уведомление не получено от сервера обновлений.</span><span class="sxs-lookup"><span data-stu-id="b2cff-199">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="b2cff-200">Для сетей с высокой задержкой, которая может увеличить время ответа, или для шлюзов, время отклика которых превышает 10 секунд, быстрая отработка отказа должна быть отключена.</span><span class="sxs-lookup"><span data-stu-id="b2cff-200">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

16. <span data-ttu-id="b2cff-201">(Необязательно) Сопоставьте и настройте **правила трансляции вызывающего номера** для магистральной линии связи.</span><span class="sxs-lookup"><span data-stu-id="b2cff-201">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="b2cff-202">Эти правила применяются к вызывающим номерам для исходящих вызовов</span><span class="sxs-lookup"><span data-stu-id="b2cff-202">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="b2cff-203">Чтобы выбрать одно или несколько правил из списка всех правил трансляции, доступных в вашем корпоративном развертывании, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-203">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="b2cff-204">В окне **Выбор правил трансляции** выберите правила, которые требуется сопоставить с магистральной линией связи, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-204">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="b2cff-205">Чтобы определить новое правило преобразования и сопоставить его с магистральной линией связи, щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-205">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="b2cff-206">Подробные сведения о том, как определить новое правило, приведены в разделе [Определение правил перевода в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="b2cff-206">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="b2cff-207">Чтобы изменить правило преобразования, уже сопоставленное с магистральной линией связи, щелкните имя правила, а затем выберите **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-207">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="b2cff-208">Подробности можно найти [в разделе Определение правил перевода в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="b2cff-208">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="b2cff-209">Чтобы скопировать существующее правило преобразования и использовать его в качестве отправной точки для определения нового правила, щелкните имя этого правила, щелкните **Копировать** и **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-209">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="b2cff-210">Подробности можно найти [в разделе Определение правил перевода в Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="b2cff-210">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="b2cff-211">Чтобы удалить правило преобразования из магистральной линии связи, выделите имя этого правила, а затем щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-211">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="b2cff-212">Не сопоставляйте правила преобразования с магистральной линией связи, если вы уже настроили их для связанной одноранговой магистральной линии связи, поскольку эти два правила могут конфликтовать друг с другом.</span><span class="sxs-lookup"><span data-stu-id="b2cff-212">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="b2cff-p131">(Необязательно) Сопоставьте и настройте **правила трансляции набранного номера** для магистральной линии связи. Эти правила применяются к вызываемым номерам для исходящих вызовов.</span><span class="sxs-lookup"><span data-stu-id="b2cff-p131">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="b2cff-215">Чтобы выбрать одно или несколько правил из списка всех правил трансляции, доступных в вашем корпоративном развертывании, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-215">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="b2cff-216">В окне **Выбор правил трансляции** выберите правила, которые требуется сопоставить с магистральной линией связи, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-216">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="b2cff-217">Чтобы определить новое правило преобразования и сопоставить его с магистральной линией связи, щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-217">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="b2cff-218">Подробные сведения о том, как определить новое правило, приведены в разделе [Определение правил перевода в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="b2cff-218">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="b2cff-219">Чтобы изменить правило преобразования, уже сопоставленное с магистральной линией связи, щелкните имя правила, а затем выберите **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-219">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="b2cff-220">Подробности можно найти [в разделе Определение правил перевода в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="b2cff-220">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="b2cff-221">Чтобы скопировать существующее правило преобразования и использовать его в качестве отправной точки для определения нового правила, щелкните имя этого правила, щелкните **Копировать** и **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-221">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="b2cff-222">Подробности можно найти [в разделе Определение правил перевода в Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="b2cff-222">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="b2cff-223">Чтобы удалить правило преобразования из магистральной линии связи, выделите имя этого правила, а затем щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-223">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="b2cff-224">Не сопоставляйте правила преобразования с магистральной линией связи, если вы уже настроили их для связанной одноранговой магистральной линии связи, поскольку эти два правила могут конфликтовать друг с другом.</span><span class="sxs-lookup"><span data-stu-id="b2cff-224">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

18. <span data-ttu-id="b2cff-p136">Правила трансляции линии связи должны быть выстроены в правильном порядке. Для изменения позиции правила, выделите его в списке и нажмите кнопку со стрелкой вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="b2cff-p136">Make sure that the trunk’s translation rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b2cff-227">Lync Server 2013 обходит список правил перевода сверху вниз и использует первое правило, которое соответствует номеру набора.</span><span class="sxs-lookup"><span data-stu-id="b2cff-227">Lync Server 2013 traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="b2cff-228">Если магистраль настроена так, что набранный номер может соответствовать нескольким правилам, то более строгие правила должны предшествовать менее строгим.</span><span class="sxs-lookup"><span data-stu-id="b2cff-228">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="b2cff-229">Например, если вы добавили правило трансляции, совпадающее с любым 11-значным номером и правило, совпадающее с 11-значным номером, начинающимся на +1425, то первое правило должно располагаться <EM>ниже</EM> второго, более строгого правила.</span><span class="sxs-lookup"><span data-stu-id="b2cff-229">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

19. <span data-ttu-id="b2cff-230">После завершения настройки магистрали нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-230">When you are finished configuring the trunk, click **OK**.</span></span>

20. <span data-ttu-id="b2cff-231">На странице **Настройка магистрали** нажмите **Фиксировать** и затем **Фиксировать все**.</span><span class="sxs-lookup"><span data-stu-id="b2cff-231">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b2cff-232">После создания или изменения конфигурации магистрали следует выполнить команду <STRONG>Сохранить все</STRONG>, чтобы опубликовать изменения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b2cff-232">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="b2cff-233">Дополнительные сведения можно найти в разделе <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013</A> в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="b2cff-233">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

<span data-ttu-id="b2cff-234">После настройки магистральной магистрали Продолжайте настраивать режим обхода мультимедиа, выбирая между глобальными параметрами обхода мультимедиа, как описано в разделе [Общие параметры обхода мультимедиа в Lync Server 2013](lync-server-2013-global-media-bypass-options.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="b2cff-234">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Global media bypass options in Lync Server 2013](lync-server-2013-global-media-bypass-options.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b2cff-235">См. также</span><span class="sxs-lookup"><span data-stu-id="b2cff-235">See Also</span></span>


[<span data-ttu-id="b2cff-236">Настройка магистрали без обхода мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2cff-236">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[<span data-ttu-id="b2cff-237">Настройка обхода сервера-посредника в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2cff-237">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="b2cff-238">Глобальные параметры обхода мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2cff-238">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="b2cff-239">Определение правил преобразования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2cff-239">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

