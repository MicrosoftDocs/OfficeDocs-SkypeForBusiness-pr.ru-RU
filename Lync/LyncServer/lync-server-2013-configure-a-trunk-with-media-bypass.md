---
title: 'Lync Server 2013: Настройка магистрали с обходом сервера мультимедиа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk with media bypass
ms:assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398792(v=OCS.15)
ms:contentKeyID: 48184959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 256962ace879c9d418d877b94f15227959177407
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a><span data-ttu-id="ccc71-102">Настройка магистрали с обходом сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc71-102">Configure a trunk with media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccc71-103">_**Последнее изменение темы:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="ccc71-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="ccc71-104">Выполните следующие действия, чтобы настроить магистраль с включенным режимом обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="ccc71-104">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="ccc71-105">Чтобы настроить магистральную магистральную систему с отключенным обходом сервера, ознакомьтесь со статьей [Настройка магистрали без обхода сервера мультимедиа в Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="ccc71-105">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span></span> <span data-ttu-id="ccc71-106">Обход сервера-посредника удобно использовать, когда требуется максимально сократить число развернутых серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="ccc71-106">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="ccc71-107">Обычно пул серверов-посредников разворачивается на центральном сайте и предназначается для управления шлюзами на сайтах филиалов.</span><span class="sxs-lookup"><span data-stu-id="ccc71-107">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="ccc71-108">Включение обхода сервера-посредника позволяет проходить мультимедиа для вызовов ТСОП от клиентов на сайтах филиалов непосредственно через шлюзы на этих сайтах.</span><span class="sxs-lookup"><span data-stu-id="ccc71-108">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="ccc71-109">В Lync Server 2013 маршруты исходящих вызовов и политики корпоративной голосовой связи должны быть настроены должным образом, чтобы вызовы PSTN от клиентов на сайте филиала направлялись на соответствующий шлюз.</span><span class="sxs-lookup"><span data-stu-id="ccc71-109">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="ccc71-110">Настоятельно рекомендуется включить обход сервера мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="ccc71-110">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="ccc71-111">Тем не менее, прежде чем включить обход сервера-посредника для магистрали SIP, убедитесь, что квалифицированный поставщик магистрали SIP поддерживает обход сервера-посредника и может удовлетворить требования для успешного включения этого сценария.</span><span class="sxs-lookup"><span data-stu-id="ccc71-111">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="ccc71-112">В частности, у поставщика должны быть IP-адреса серверов в внутренней сети Организации.</span><span class="sxs-lookup"><span data-stu-id="ccc71-112">Specifically, the provider must have the IP addresses of servers in your organization’s internal network.</span></span> <span data-ttu-id="ccc71-113">Если поставщик не поддерживает этот сценарий, обход сервера не будет успешным.</span><span class="sxs-lookup"><span data-stu-id="ccc71-113">If the provider cannot support this scenario, media bypass will not succeed.</span></span> <span data-ttu-id="ccc71-114">Дополнительные сведения приведены в статье [Планирование обхода сервера мультимедиа в Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="ccc71-114">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ccc71-115">Режим обхода не будет работать с каждым ТСОП-шлюзом, IP-УАТС и SBC.</span><span class="sxs-lookup"><span data-stu-id="ccc71-115">Media bypass will not interoperate with every public switched telephone network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="ccc71-116">Корпорация Майкрософт протестировала набор ТСОП-шлюзов и SBC с сертифицированными партнерами и провела некоторые тесты для Cisco IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="ccc71-116">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="ccc71-117">Обход сервера-посредника поддерживается только для продуктов и версий, перечисленных в программе Open Communications Open Communications Program — Lync Server <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>по адресу.</span><span class="sxs-lookup"><span data-stu-id="ccc71-117">Media bypass is supported only with products and versions that are listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="ccc71-p104">Описанная ниже конфигурация магистрали содержит набор параметров, применяемых к магистралям, которым она назначается. Отдельная конфигурация магистрали может действовать в глобальной области (для всех магистралей, которым не назначена более конкретная конфигурация сайта или пула), в области сайта или в области пула. Конфигурация магистрали уровня пула используется для назначения отдельной магистрали.</span><span class="sxs-lookup"><span data-stu-id="ccc71-p104">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="ccc71-121">Настройка магистрали с обходом сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="ccc71-121">To configure a trunk with media bypass</span></span>

1.  <span data-ttu-id="ccc71-122">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ccc71-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="ccc71-123">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="ccc71-123">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ccc71-124">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ccc71-124">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ccc71-125">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ccc71-125">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ccc71-126">В левой панели навигации щелкните **Маршрутизация голосовой связи**, а затем выберите **Настройка линии связи**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-126">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="ccc71-127">На странице **Конфигурация магистрали** используйте один из следующих методов для настройки магистрали:</span><span class="sxs-lookup"><span data-stu-id="ccc71-127">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="ccc71-128">Дважды щелкните существующую магистраль (например, в **глобальную** магистраль), чтобы открыть диалоговое окно **Изменение конфигурации магистрали**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-128">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="ccc71-129">Нажмите кнопку **Создать**, а затем выберите область для конфигурации новой магистрали:</span><span class="sxs-lookup"><span data-stu-id="ccc71-129">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="ccc71-130">**Магистраль сайта:** Выберите сайт для этой конфигурации магистрали, **выбрав сайт**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-130">**Site trunk:** Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="ccc71-131">Обратите внимание, что сайты, для которых уже создана конфигурация магистрали, не отображаются в разделе **Выбор сайта**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-131">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="ccc71-132">Эта конфигурация будет применяться ко всем магистралям на сайте.</span><span class="sxs-lookup"><span data-stu-id="ccc71-132">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="ccc71-133">**Магистральная магистраль пула:** Выберите имя магистрали, к которой применяется данная конфигурация магистрали.</span><span class="sxs-lookup"><span data-stu-id="ccc71-133">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="ccc71-134">Это может быть корневая магистраль или любые дополнительные магистральные линии, определенные в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="ccc71-134">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="ccc71-135">В разделе **Выбор службы** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-135">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="ccc71-136">Обратите внимание, что магистрали, для которых уже создана конфигурация, не отображаются в разделе **Выбор службы**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-136">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ccc71-137">Выбранную область действия конфигурации магистрали уже нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="ccc71-137">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="ccc71-138">Поле <STRONG>Название</STRONG> заполняется названием связанного с конфигурацией магистрали сайта или службы. Изменить его нельзя.</span><span class="sxs-lookup"><span data-stu-id="ccc71-138">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="ccc71-p109">Укажите значение в поле **Максимальное количество поддерживаемых предварительных диалогов**. Это максимальное число разветвленных ответов, которые может получить ТСОП-шлюз, IP-УАТС или пограничный контроллер сеансов ITSP (SBC) на запрос INVITE, отправленный серверу-посреднику. Значение по умолчанию — 20.</span><span class="sxs-lookup"><span data-stu-id="ccc71-p109">Specify a value in **Maximum early dialogs supported**. This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server. The default value is 20.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ccc71-142">Перед сменой данного значения, проконсультируйтесь со своим поставщиком или производителем оборудования насчет информации о возможностях своей системы.</span><span class="sxs-lookup"><span data-stu-id="ccc71-142">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

    
    </div>

6.  <span data-ttu-id="ccc71-143">Выберите один из следующих вариантов для **Уровня поддержки шифрования**:</span><span class="sxs-lookup"><span data-stu-id="ccc71-143">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="ccc71-144">**Обязательный атрибут:** Чтобы защитить трафик между сервером-посредником и шлюзом или УАТС (УАТС), необходимо использовать шифрование протокола SRTP.</span><span class="sxs-lookup"><span data-stu-id="ccc71-144">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="ccc71-145">**Необязательно:** Шифрование SRTP будет использоваться, если поставщик услуг или производитель оборудования его поддерживает.</span><span class="sxs-lookup"><span data-stu-id="ccc71-145">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="ccc71-146">**Не поддерживается:** Шифрование SRTP не поддерживается поставщиком услуг или производителем оборудования, поэтому не будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="ccc71-146">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

7.  <span data-ttu-id="ccc71-147">Установите флажок **Включить режим обхода сервера-посредника**, если нужно, чтобы одноранговые узлы магистрали обходили сервер-посредник при передаче медиаданных.</span><span class="sxs-lookup"><span data-stu-id="ccc71-147">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ccc71-148">Для успешной работы обхода сервера-посредника шлюз PSTN, IP-УАТС или пограничный контроллер сеансов ITSP должны поддерживать определенные возможности.</span><span class="sxs-lookup"><span data-stu-id="ccc71-148">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="ccc71-149">Дополнительные сведения приведены в статье <A href="lync-server-2013-planning-for-media-bypass.md">Планирование обхода сервера мультимедиа в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="ccc71-149">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="ccc71-p111">Установите флажок **Централизованная обработка медиаданных**, если имеется хорошо известная конечная точка для медиаданных (например, ТСОП-шлюз, где завершение медиаданных имеет тот же IP что и завершение сигнала). Сбросьте данный флажок, если у магистрали нет такой точки.</span><span class="sxs-lookup"><span data-stu-id="ccc71-p111">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

9.  <span data-ttu-id="ccc71-152">Если магистральный узел поддерживает получение запросов SIP на получение запросов SIP от сервера-посредника, установите флажок **Разрешить отправку ссылку на шлюз** .</span><span class="sxs-lookup"><span data-stu-id="ccc71-152">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ccc71-153">Если этот параметр отключен, а параметр <STRONG>включить обход сервера-посредника</STRONG> установлен, требуются дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="ccc71-153">If you disable this option while the <STRONG>Enable media bypass</STRONG> option is selected, additional settings are required.</span></span> <span data-ttu-id="ccc71-154">Если магистральный узел не поддерживает получение запросов SIP от сервера-посредника, а обход сервера-посредника включен, необходимо также выполнить командлет <STRONG>Set-CsTrunkConfiguration</STRONG> , чтобы отключить RTCP для активных и удерживаемых вызовов для поддержки соответствующих условий для обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="ccc71-154">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="ccc71-155">Дополнительные сведения см. в документации по <A href="lync-server-2013-lync-server-management-shell.md">командной консоли Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="ccc71-155">For details, see the <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> documentation.</span></span><BR><span data-ttu-id="ccc71-156">Если необходимо, чтобы переключенные звонки обходили медиаданные и шлюз не поддерживал запросы SIP REFER, выберите <STRONG>Разрешить ссылку с использованием стороннего контроля вызовов</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ccc71-156">Alternatively, you can select <STRONG>Enable refer using third-party-call control</STRONG> if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

    
    </div>

10. <span data-ttu-id="ccc71-p113">(Необязательно) Чтобы включить маршрутизацию между магистральными линиями связи, сопоставьте и настройте записи режима работы с ТСОП для этой конфигурации магистральной линии связи. Записи режима работы с ТСОП, связанные с этой конфигурацией магистральной линии связи, будут применены ко всем входящим вызовам через магистральную линию связи, которые начинаются за пределами конечной точки Lync. Чтобы управлять записями режима работы с ТСОП, связанными с конфигурацией магистральной линии связи, используйте один из приведенных ниже методов.</span><span class="sxs-lookup"><span data-stu-id="ccc71-p113">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration. The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint. To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="ccc71-160">Чтобы выбрать одну или несколько записей из списка всех записей использования PSTN, доступных в развертывании корпоративной голосовой связи, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-160">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="ccc71-161">Выделите записи, которые следует связать с этой конфигурацией магистральной линии связи, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-161">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="ccc71-162">Чтобы удалить запись режима работы с ТСОП из этой конфигурации магистральной линии связи, выберите эту запись и щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-162">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="ccc71-163">Чтобы определить новую запись режима работы с ТСОП и сопоставить ее с этой конфигурацией магистральной линии связи, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="ccc71-163">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="ccc71-164">Щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-164">Click **New**.</span></span>
        
        2.  <span data-ttu-id="ccc71-165">В поле **Имя** укажите уникальное описательное имя для записи.</span><span class="sxs-lookup"><span data-stu-id="ccc71-165">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="ccc71-p115">Имя записи режима работы с ТСОП должно быть уникальным в рамках развертывания корпоративной голосовой связи. После сохранения записи поле <STRONG>Имя</STRONG> изменить невозможно.</span><span class="sxs-lookup"><span data-stu-id="ccc71-p115">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="ccc71-168">Используйте один из следующих методов для сопоставления и настройки маршрутов для этой записи режима работы с ТСОП:</span><span class="sxs-lookup"><span data-stu-id="ccc71-168">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="ccc71-169">Чтобы выбрать один или несколько маршрутов из списка доступных маршрутов в развертывании корпоративной голосовой связи, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-169">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="ccc71-170">Выделите маршруты, которые хотите сопоставить с этой записью режима использования ТСОП, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-170">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="ccc71-171">Чтобы удалить маршрут из записи режима работы с ТСОП, выберите этот маршрут и щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-171">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="ccc71-172">Чтобы определить новый маршрут и сопоставить его с этой записью режима работы с ТСОП, щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-172">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="ccc71-173">Дополнительные сведения см. [в статье Создание маршрута голосовых вызовов в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="ccc71-173">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="ccc71-174">Чтобы изменить маршрут, сопоставленный с этой записью режима работы с ТСОП, выберите маршрут и щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-174">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="ccc71-175">Дополнительную информацию можно узнать [в статье изменение маршрута голосовой связи в Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="ccc71-175">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="ccc71-176">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-176">Click **OK**.</span></span>
    
      - <span data-ttu-id="ccc71-177">Чтобы изменить запись режима работы с ТСОП, уже сопоставленную с этой конфигурацией магистральной линии связи, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="ccc71-177">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="ccc71-178">Выберите запись режима работы с ТСОП, которую требуется изменить, и щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-178">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="ccc71-179">Используйте один из следующих методов для сопоставления и настройки маршрутов для этой записи режима работы с ТСОП:</span><span class="sxs-lookup"><span data-stu-id="ccc71-179">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="ccc71-180">Чтобы выбрать один или несколько маршрутов из списка доступных маршрутов в развертывании корпоративной голосовой связи, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-180">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="ccc71-181">Выделите маршруты, которые хотите сопоставить с этой записью режима использования ТСОП, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-181">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="ccc71-182">Чтобы удалить маршрут из записи режима работы с ТСОП, выберите этот маршрут и щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-182">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="ccc71-183">Чтобы определить новый маршрут и сопоставить его с этой записью режима работы с ТСОП, щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-183">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="ccc71-184">Дополнительные сведения см. [в статье Создание маршрута голосовых вызовов в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="ccc71-184">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="ccc71-185">Чтобы изменить маршрут, сопоставленный с этой записью режима работы с ТСОП, выберите маршрут и щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-185">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="ccc71-186">Дополнительную информацию можно узнать [в статье изменение маршрута голосовой связи в Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="ccc71-186">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="ccc71-187">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-187">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ccc71-188">Важно связать записи об использовании PSTN в соответствии с одноранговым узлом сервера-посредника, связанным с настраиваемой магистралью.</span><span class="sxs-lookup"><span data-stu-id="ccc71-188">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="ccc71-189">Если узел сервера-посредника является шлюзом PSTN или пограничным контроллером сеансов (SBC), настоятельно рекомендуется, чтобы конфигурация магистрали не сопоставлена с записью использования PSTN, которая подключается к назначению PSTN или другим подчиненным системам, подключенным через Lync. Сервер.</span><span class="sxs-lookup"><span data-stu-id="ccc71-189">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

11. <span data-ttu-id="ccc71-p123">Измените расположение записей режима работы с ТСОП, чтобы обеспечить оптимальную производительность. Чтобы изменить расположение записи в списке, выберите соответствующую запись режима работы с ТСОП и щелкните стрелку вверх или стрелку вниз.</span><span class="sxs-lookup"><span data-stu-id="ccc71-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ccc71-192">Порядок расположения записей режима работы с ТСОП в списке является важным.</span><span class="sxs-lookup"><span data-stu-id="ccc71-192">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="ccc71-193">Lync Server выполняет обход списка сверху вниз.</span><span class="sxs-lookup"><span data-stu-id="ccc71-193">Lync Server traverses the list from top to down.</span></span>

    
    </div>

12. <span data-ttu-id="ccc71-194">Чтобы включить обход медиаданных для клиентов, защищенных системой преобразования сетевых адресов (NAT) или брандмауэром и SBC с поддержкой блокировки, выберите **Разрешить блокирование RTP**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-194">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

13. <span data-ttu-id="ccc71-195">Чтобы включить отправку сведений о журнале вызовов на узел шлюза сервера-посредника, необходимо **Включить журнал вызовов переадресации** .</span><span class="sxs-lookup"><span data-stu-id="ccc71-195">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

14. <span data-ttu-id="ccc71-196">**Включить данные о пересылке p-Assert-Identity** необходимо выбрать, чтобы включить сведения о инициаторе вызова p-Assert-Identity (PAI) для перенаправления между сервером-посредником и на стороне шлюза (и наоборот), если они есть.</span><span class="sxs-lookup"><span data-stu-id="ccc71-196">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

15. <span data-ttu-id="ccc71-197">Установите флажок **Включить таймер отработки отказа внешней маршрутизации**, чтобы включить быструю отработку отказа.</span><span class="sxs-lookup"><span data-stu-id="ccc71-197">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="ccc71-198">Шлюз, сопоставленный с этой магистралью, может в течение 10 секунд выдать уведомление о том, что он обрабатывает исходящий вызов.</span><span class="sxs-lookup"><span data-stu-id="ccc71-198">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="ccc71-199">Перенаправление на другую магистраль произойдет, если это уведомление не получено сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="ccc71-199">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="ccc71-200">В сетях, где задержка может увеличить время ответа или где на ответ шлюзу требуется более 10 секунд, быструю отработку отказа следует отключить.</span><span class="sxs-lookup"><span data-stu-id="ccc71-200">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

16. <span data-ttu-id="ccc71-201">(Необязательно) Сопоставьте и настройте **правила трансляции вызывающего номера** для магистральной линии связи.</span><span class="sxs-lookup"><span data-stu-id="ccc71-201">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="ccc71-202">Эти правила применяются к вызывающим номерам для исходящих вызовов</span><span class="sxs-lookup"><span data-stu-id="ccc71-202">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="ccc71-203">Чтобы выбрать одно или несколько правил из списка всех правил трансляции, доступных в развертывании корпоративной голосовой связи, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-203">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="ccc71-204">В окне **Выбор правил трансляции** выберите правила, которые требуется сопоставить с магистральной линией связи, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-204">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="ccc71-205">Чтобы определить новое правило преобразования и сопоставить его с магистралью, нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-205">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="ccc71-206">Дополнительные сведения об определении нового правила приведены в статье [Определение правил преобразования в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="ccc71-206">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="ccc71-207">Чтобы изменить правило преобразования, которое уже сопоставлено с магистралью, щелкните имя правила, затем нажмите кнопку **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-207">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="ccc71-208">Дополнительные сведения приведены в статье [Определение правил преобразования в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="ccc71-208">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="ccc71-209">Чтобы скопировать существующее правило преобразования и использовать его в качестве отправной точки для определения нового правила, щелкните имя правила и нажмите кнопку **Копировать**, а затем кнопку **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-209">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="ccc71-210">Дополнительные сведения см. [в статье Определение правил преобразования в Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="ccc71-210">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="ccc71-211">Чтобы удалить правило преобразования из магистральной линии связи, выделите имя этого правила, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-211">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="ccc71-212">Не сопоставляйте правила преобразования с магистралью, если вы настроили правила преобразования на сопоставленном одноранговом узле, поскольку два правила могут конфликтовать.</span><span class="sxs-lookup"><span data-stu-id="ccc71-212">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="ccc71-p131">(Необязательно) Сопоставьте и настройте **правила трансляции набранного номера** для магистральной линии связи. Эти правила применяются к вызываемым номерам для исходящих вызовов.</span><span class="sxs-lookup"><span data-stu-id="ccc71-p131">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="ccc71-215">Чтобы выбрать одно или несколько правил из списка всех правил трансляции, доступных в развертывании корпоративной голосовой связи, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-215">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="ccc71-216">В окне **Выбор правил трансляции** выберите правила, которые требуется сопоставить с магистральной линией связи, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-216">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="ccc71-217">Чтобы определить новое правило преобразования и сопоставить его с магистралью, нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-217">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="ccc71-218">Дополнительные сведения об определении нового правила приведены в статье [Определение правил преобразования в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="ccc71-218">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="ccc71-219">Чтобы изменить правило преобразования, которое уже сопоставлено с магистралью, щелкните имя правила, затем нажмите кнопку **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-219">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="ccc71-220">Дополнительные сведения приведены в статье [Определение правил преобразования в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="ccc71-220">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="ccc71-221">Чтобы скопировать существующее правило преобразования и использовать его в качестве отправной точки для определения нового правила, щелкните имя правила и нажмите кнопку **Копировать**, а затем кнопку **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-221">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="ccc71-222">Дополнительные сведения см. [в статье Определение правил преобразования в Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="ccc71-222">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="ccc71-223">Чтобы удалить правило преобразования из магистральной линии связи, выделите имя этого правила, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-223">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="ccc71-224">Не сопоставляйте правила преобразования с магистральной линией связи, если вы уже настроили их для связанной одноранговой магистральной линии связи, поскольку эти два правила могут конфликтовать друг с другом.</span><span class="sxs-lookup"><span data-stu-id="ccc71-224">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

18. <span data-ttu-id="ccc71-225">Убедитесь, что правила преобразования магистральной линии упорядочены в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="ccc71-225">Make sure that the trunk’s translation rules are arranged in the correct order.</span></span> <span data-ttu-id="ccc71-226">Чтобы изменить расположение правила в списке, выделите имя правила и нажмите кнопку со стрелкой вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="ccc71-226">To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="ccc71-227">Lync Server 2013 перебирает список правил преобразования сверху вниз и использует первое правило, которое соответствует набранному номеру.</span><span class="sxs-lookup"><span data-stu-id="ccc71-227">Lync Server 2013 traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="ccc71-228">Если вы настраиваете магистраль таким образом, чтобы набираемый номер мог соответствовать нескольким правилам преобразования, убедитесь, что более строгие правила расположены над менее строгими.</span><span class="sxs-lookup"><span data-stu-id="ccc71-228">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="ccc71-229">Например, если вы включаете правило преобразования, соответствующее любому 11-значному номеру, и правило преобразования, которое соответствует только 11-значным номерам, начинающимся с +1425, убедитесь, что правило, соответствующее любому 11-значному номеру, располагается <EM>ниже</EM> более строгого правила.</span><span class="sxs-lookup"><span data-stu-id="ccc71-229">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

19. <span data-ttu-id="ccc71-230">Закончив настройку магистрали, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-230">When you are finished configuring the trunk, click **OK**.</span></span>

20. <span data-ttu-id="ccc71-231">На странице **Конфигурация магистрали** нажмите кнопку **Передать**, а затем щелкните **Передать все**.</span><span class="sxs-lookup"><span data-stu-id="ccc71-231">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ccc71-232">При каждом создании или изменении конфигурации магистрали необходимо выполнить команду <STRONG>Сохранить все</STRONG>, чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ccc71-232">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="ccc71-233">Дополнительные сведения см в статье <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</A> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="ccc71-233">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

<span data-ttu-id="ccc71-234">После настройки магистрали Продолжайте настраивать обход сервера мультимедиа, выбирая между глобальными параметрами обхода сервера мультимедиа, как описано в разделе [глобальные параметры обхода мультимедиа в Lync Server 2013](lync-server-2013-global-media-bypass-options.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="ccc71-234">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Global media bypass options in Lync Server 2013](lync-server-2013-global-media-bypass-options.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ccc71-235">См. также</span><span class="sxs-lookup"><span data-stu-id="ccc71-235">See Also</span></span>


[<span data-ttu-id="ccc71-236">Настройка магистрали без обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc71-236">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[<span data-ttu-id="ccc71-237">Настройка обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc71-237">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="ccc71-238">Глобальные параметры обхода мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc71-238">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="ccc71-239">Определение правил преобразования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ccc71-239">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

