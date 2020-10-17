---
title: 'Lync Server 2013: Настройка магистрали с обходом сервера мультимедиа'
description: 'Lync Server 2013: Настройка магистрали с обходом сервера мультимедиа.'
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
ms.openlocfilehash: 51bd58a685e1f4c222a863c21022b3c9dc7c70d6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566755"
---
# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a><span data-ttu-id="56272-103">Настройка магистрали с обходом сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56272-103">Configure a trunk with media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56272-104">_**Последнее изменение темы:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="56272-104">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="56272-105">Выполните следующие действия, чтобы настроить магистраль с включенным режимом обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="56272-105">Follow these steps to configure a trunk with media bypass enabled.</span></span> <span data-ttu-id="56272-106">Чтобы настроить магистральную магистральную систему с отключенным обходом сервера, ознакомьтесь со статьей [Настройка магистрали без обхода сервера мультимедиа в Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="56272-106">To configure a trunk with media bypass disabled, see [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md).</span></span> <span data-ttu-id="56272-107">Обход сервера-посредника удобно использовать, когда требуется максимально сократить число развернутых серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="56272-107">Media bypass is useful when you want to minimize the number of Mediation Servers deployed.</span></span> <span data-ttu-id="56272-108">Обычно пул серверов-посредников разворачивается на центральном сайте и предназначается для управления шлюзами на сайтах филиалов.</span><span class="sxs-lookup"><span data-stu-id="56272-108">Typically, a Mediation Server pool will be deployed at a central site, and it will control gateways at branch sites.</span></span> <span data-ttu-id="56272-109">Включение обхода сервера-посредника позволяет проходить мультимедиа для вызовов ТСОП от клиентов на сайтах филиалов непосредственно через шлюзы на этих сайтах.</span><span class="sxs-lookup"><span data-stu-id="56272-109">Enabling media bypass allows media for public switched telephone network (PSTN) calls from clients at branch sites to flow directly through the gateways at those sites.</span></span> <span data-ttu-id="56272-110">В Lync Server 2013 маршруты исходящих вызовов и политики корпоративной голосовой связи должны быть настроены должным образом, чтобы вызовы PSTN от клиентов на сайте филиала направлялись на соответствующий шлюз.</span><span class="sxs-lookup"><span data-stu-id="56272-110">Lync Server 2013 outbound call routes and Enterprise Voice policies must be properly configured so that PSTN calls from clients at a branch site are routed to the appropriate gateway.</span></span>

<span data-ttu-id="56272-111">Настоятельно рекомендуется включить обход сервера мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="56272-111">We strongly recommend that you enable media bypass.</span></span> <span data-ttu-id="56272-112">Тем не менее, прежде чем включить обход сервера-посредника для магистрали SIP, убедитесь, что квалифицированный поставщик магистрали SIP поддерживает обход сервера-посредника и может удовлетворить требования для успешного включения этого сценария.</span><span class="sxs-lookup"><span data-stu-id="56272-112">However, before you enable media bypass on a SIP trunk, confirm that your qualified SIP trunk provider supports media bypass and is able to accommodate the requirements for successfully enabling the scenario.</span></span> <span data-ttu-id="56272-113">В частности, у поставщика должны быть IP-адреса серверов в внутренней сети Организации.</span><span class="sxs-lookup"><span data-stu-id="56272-113">Specifically, the provider must have the IP addresses of servers in your organization’s internal network.</span></span> <span data-ttu-id="56272-114">Если поставщик не поддерживает этот сценарий, обход сервера не будет успешным.</span><span class="sxs-lookup"><span data-stu-id="56272-114">If the provider cannot support this scenario, media bypass will not succeed.</span></span> <span data-ttu-id="56272-115">Дополнительные сведения приведены в статье [Планирование обхода сервера мультимедиа в Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="56272-115">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="56272-116">Режим обхода не будет работать с каждым ТСОП-шлюзом, IP-УАТС и SBC.</span><span class="sxs-lookup"><span data-stu-id="56272-116">Media bypass will not interoperate with every public switched telephone network (PSTN) gateway, IP-PBX, and Session Border Controller (SBC).</span></span> <span data-ttu-id="56272-117">Корпорация Майкрософт протестировала набор ТСОП-шлюзов и SBC с сертифицированными партнерами и провела некоторые тесты для Cisco IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="56272-117">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="56272-118">Обход сервера-посредника поддерживается только для продуктов и версий, перечисленных в программе Open Communications Open Communications Program — Lync Server по адресу <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .</span><span class="sxs-lookup"><span data-stu-id="56272-118">Media bypass is supported only with products and versions that are listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="56272-p104">Описанная ниже конфигурация магистрали содержит набор параметров, применяемых к магистралям, которым она назначается. Отдельная конфигурация магистрали может действовать в глобальной области (для всех магистралей, которым не назначена более конкретная конфигурация сайта или пула), в области сайта или в области пула. Конфигурация магистрали уровня пула используется для назначения отдельной магистрали.</span><span class="sxs-lookup"><span data-stu-id="56272-p104">A trunk configuration as described below groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a><span data-ttu-id="56272-122">Настройка магистрали с обходом сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="56272-122">To configure a trunk with media bypass</span></span>

1.  <span data-ttu-id="56272-123">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="56272-123">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="56272-124">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="56272-124">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="56272-125">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="56272-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="56272-126">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="56272-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="56272-127">В левой панели навигации щелкните **Маршрутизация голосовой связи**, а затем выберите **Настройка линии связи**.</span><span class="sxs-lookup"><span data-stu-id="56272-127">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="56272-128">На странице **Конфигурация магистрали** используйте один из следующих методов для настройки магистрали:</span><span class="sxs-lookup"><span data-stu-id="56272-128">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="56272-129">Дважды щелкните существующую магистраль (например, в **глобальную** магистраль), чтобы открыть диалоговое окно **Изменение конфигурации магистрали**.</span><span class="sxs-lookup"><span data-stu-id="56272-129">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="56272-130">Нажмите кнопку **Создать**, а затем выберите область для конфигурации новой магистрали:</span><span class="sxs-lookup"><span data-stu-id="56272-130">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="56272-131">**Магистраль сайта:** Выберите сайт для этой конфигурации магистрали, **выбрав сайт**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="56272-131">**Site trunk:** Choose the site for this trunk configuration from **Select a Site**, and then click **OK**.</span></span> <span data-ttu-id="56272-132">Обратите внимание, что сайты, для которых уже создана конфигурация магистрали, не отображаются в разделе **Выбор сайта**.</span><span class="sxs-lookup"><span data-stu-id="56272-132">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="56272-133">Эта конфигурация будет применяться ко всем магистралям на сайте.</span><span class="sxs-lookup"><span data-stu-id="56272-133">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="56272-134">**Магистральная магистраль пула:** Выберите имя магистрали, к которой применяется данная конфигурация магистрали.</span><span class="sxs-lookup"><span data-stu-id="56272-134">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to.</span></span> <span data-ttu-id="56272-135">Это может быть корневая магистраль или любые дополнительные магистральные линии, определенные в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="56272-135">This trunk can be the root trunk or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="56272-136">В разделе **Выбор службы** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="56272-136">From **Select a Service**, click **OK**.</span></span> <span data-ttu-id="56272-137">Обратите внимание, что магистрали, для которых уже создана конфигурация, не отображаются в разделе **Выбор службы**.</span><span class="sxs-lookup"><span data-stu-id="56272-137">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="56272-138">Выбранную область действия конфигурации магистрали уже нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="56272-138">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="56272-139">Поле <STRONG>Название</STRONG> заполняется названием связанного с конфигурацией магистрали сайта или службы. Изменить его нельзя.</span><span class="sxs-lookup"><span data-stu-id="56272-139">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="56272-p109">Укажите значение в поле **Максимальное количество поддерживаемых предварительных диалогов**. Это максимальное число разветвленных ответов, которые может получить ТСОП-шлюз, IP-УАТС или пограничный контроллер сеансов ITSP (SBC) на запрос INVITE, отправленный серверу-посреднику. Значение по умолчанию — 20.</span><span class="sxs-lookup"><span data-stu-id="56272-p109">Specify a value in **Maximum early dialogs supported**. This is the maximum number of forked responses a public switched telephone network (PSTN) gateway, IP-PBX, or ITSP Session Border Controller (SBC) can receive to an INVITE that it sent to the Mediation Server. The default value is 20.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="56272-143">Перед сменой данного значения, проконсультируйтесь со своим поставщиком или производителем оборудования насчет информации о возможностях своей системы.</span><span class="sxs-lookup"><span data-stu-id="56272-143">Before you change this value, consult your service provider or equipment manufacturer for details about the capabilities of your system.</span></span>

    
    </div>

6.  <span data-ttu-id="56272-144">Выберите один из следующих вариантов для **Уровня поддержки шифрования**:</span><span class="sxs-lookup"><span data-stu-id="56272-144">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="56272-145">**Обязательный атрибут:** Чтобы защитить трафик между сервером-посредником и шлюзом или УАТС (УАТС), необходимо использовать шифрование протокола SRTP.</span><span class="sxs-lookup"><span data-stu-id="56272-145">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="56272-146">**Необязательно:** Шифрование SRTP будет использоваться, если поставщик услуг или производитель оборудования его поддерживает.</span><span class="sxs-lookup"><span data-stu-id="56272-146">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="56272-147">**Не поддерживается:** Шифрование SRTP не поддерживается поставщиком услуг или производителем оборудования, поэтому не будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="56272-147">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

7.  <span data-ttu-id="56272-148">Установите флажок **Включить режим обхода сервера-посредника**, если нужно, чтобы одноранговые узлы магистрали обходили сервер-посредник при передаче медиаданных.</span><span class="sxs-lookup"><span data-stu-id="56272-148">Select the **Enable media bypass** check box if you want media to bypass the Mediation Server for processing by the trunk peer.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="56272-149">Для успешной работы обхода сервера-посредника шлюз PSTN, IP-УАТС или пограничный контроллер сеансов ITSP должны поддерживать определенные возможности.</span><span class="sxs-lookup"><span data-stu-id="56272-149">For media bypass to work successfully, the PSTN gateway, IP-PBX, or ITSP Session Border Controller must support certain capabilities.</span></span> <span data-ttu-id="56272-150">Дополнительные сведения приведены в статье <A href="lync-server-2013-planning-for-media-bypass.md">Планирование обхода сервера мультимедиа в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="56272-150">For details, see <A href="lync-server-2013-planning-for-media-bypass.md">Planning for media bypass in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

8.  <span data-ttu-id="56272-p111">Установите флажок **Централизованная обработка медиаданных**, если имеется хорошо известная конечная точка для медиаданных (например, ТСОП-шлюз, где завершение медиаданных имеет тот же IP что и завершение сигнала). Сбросьте данный флажок, если у магистрали нет такой точки.</span><span class="sxs-lookup"><span data-stu-id="56272-p111">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a PSTN gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

9.  <span data-ttu-id="56272-153">Если магистральный узел поддерживает получение запросов SIP на получение запросов SIP от сервера-посредника, установите флажок **Разрешить отправку ссылку на шлюз** .</span><span class="sxs-lookup"><span data-stu-id="56272-153">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="56272-154">Если этот параметр отключен, а параметр <STRONG>включить обход сервера-посредника</STRONG> установлен, требуются дополнительные параметры.</span><span class="sxs-lookup"><span data-stu-id="56272-154">If you disable this option while the <STRONG>Enable media bypass</STRONG> option is selected, additional settings are required.</span></span> <span data-ttu-id="56272-155">Если магистральный узел не поддерживает получение запросов SIP от сервера-посредника, а обход сервера-посредника включен, необходимо также выполнить командлет <STRONG>Set-CsTrunkConfiguration</STRONG> , чтобы отключить RTCP для активных и удерживаемых вызовов для поддержки соответствующих условий для обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="56272-155">If the trunk peer does not support receiving SIP REFER requests from the Mediation Server and media bypass is enabled, you must also run the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to disable RTCP for active and held calls in order to support proper conditions for media bypass.</span></span> <span data-ttu-id="56272-156">Дополнительные сведения см. в документации по <A href="lync-server-2013-lync-server-management-shell.md">командной консоли Lync Server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="56272-156">For details, see the <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> documentation.</span></span><BR><span data-ttu-id="56272-157">Если необходимо, чтобы переключенные звонки обходили медиаданные и шлюз не поддерживал запросы SIP REFER, выберите <STRONG>Разрешить ссылку с использованием стороннего контроля вызовов</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="56272-157">Alternatively, you can select <STRONG>Enable refer using third-party-call control</STRONG> if you want transferred calls to be media bypassed, and the gateway does not support SIP REFER requests.</span></span>

    
    </div>

10. <span data-ttu-id="56272-p113">(Необязательно) Чтобы включить маршрутизацию между магистральными линиями связи, сопоставьте и настройте записи режима работы с ТСОП для этой конфигурации магистральной линии связи. Записи режима работы с ТСОП, связанные с этой конфигурацией магистральной линии связи, будут применены ко всем входящим вызовам через магистральную линию связи, которые начинаются за пределами конечной точки Lync. Чтобы управлять записями режима работы с ТСОП, связанными с конфигурацией магистральной линии связи, используйте один из приведенных ниже методов.</span><span class="sxs-lookup"><span data-stu-id="56272-p113">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration. The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint. To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="56272-161">Чтобы выбрать одну или несколько записей из списка всех записей использования PSTN, доступных в развертывании корпоративной голосовой связи, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="56272-161">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="56272-162">Выделите записи, которые следует связать с этой конфигурацией магистральной линии связи, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="56272-162">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="56272-163">Чтобы удалить запись режима работы с ТСОП из этой конфигурации магистральной линии связи, выберите эту запись и щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="56272-163">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="56272-164">Чтобы определить новую запись режима работы с ТСОП и сопоставить ее с этой конфигурацией магистральной линии связи, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="56272-164">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="56272-165">Щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="56272-165">Click **New**.</span></span>
        
        2.  <span data-ttu-id="56272-166">В поле **Имя** укажите уникальное описательное имя для записи.</span><span class="sxs-lookup"><span data-stu-id="56272-166">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="56272-p115">Имя записи режима работы с ТСОП должно быть уникальным в рамках развертывания корпоративной голосовой связи. После сохранения записи поле <STRONG>Имя</STRONG> изменить невозможно.</span><span class="sxs-lookup"><span data-stu-id="56272-p115">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="56272-169">Используйте один из следующих методов для сопоставления и настройки маршрутов для этой записи режима работы с ТСОП:</span><span class="sxs-lookup"><span data-stu-id="56272-169">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="56272-170">Чтобы выбрать один или несколько маршрутов из списка доступных маршрутов в развертывании корпоративной голосовой связи, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="56272-170">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="56272-171">Выделите маршруты, которые хотите сопоставить с этой записью режима использования ТСОП, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="56272-171">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="56272-172">Чтобы удалить маршрут из записи режима работы с ТСОП, выберите этот маршрут и щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="56272-172">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="56272-173">Чтобы определить новый маршрут и сопоставить его с этой записью режима работы с ТСОП, щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="56272-173">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="56272-174">Дополнительные сведения см. [в статье Создание маршрута голосовых вызовов в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="56272-174">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="56272-175">Чтобы изменить маршрут, сопоставленный с этой записью режима работы с ТСОП, выберите маршрут и щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="56272-175">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="56272-176">Дополнительную информацию можно узнать [в статье изменение маршрута голосовой связи в Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="56272-176">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="56272-177">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="56272-177">Click **OK**.</span></span>
    
      - <span data-ttu-id="56272-178">Чтобы изменить запись режима работы с ТСОП, уже сопоставленную с этой конфигурацией магистральной линии связи, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="56272-178">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="56272-179">Выберите запись режима работы с ТСОП, которую требуется изменить, и щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="56272-179">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="56272-180">Используйте один из следующих методов для сопоставления и настройки маршрутов для этой записи режима работы с ТСОП:</span><span class="sxs-lookup"><span data-stu-id="56272-180">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="56272-181">Чтобы выбрать один или несколько маршрутов из списка доступных маршрутов в развертывании корпоративной голосовой связи, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="56272-181">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="56272-182">Выделите маршруты, которые хотите сопоставить с этой записью режима использования ТСОП, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="56272-182">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="56272-183">Чтобы удалить маршрут из записи режима работы с ТСОП, выберите этот маршрут и щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="56272-183">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="56272-184">Чтобы определить новый маршрут и сопоставить его с этой записью режима работы с ТСОП, щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="56272-184">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="56272-185">Дополнительные сведения см. [в статье Создание маршрута голосовых вызовов в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="56272-185">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="56272-186">Чтобы изменить маршрут, сопоставленный с этой записью режима работы с ТСОП, выберите маршрут и щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="56272-186">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="56272-187">Дополнительную информацию можно узнать [в статье изменение маршрута голосовой связи в Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="56272-187">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="56272-188">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="56272-188">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="56272-189">Важно связать записи об использовании PSTN в соответствии с одноранговым узлом сервера-посредника, связанным с настраиваемой магистралью.</span><span class="sxs-lookup"><span data-stu-id="56272-189">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="56272-190">Если узел сервера-посредника является шлюзом PSTN или пограничным контроллером сеансов (SBC), настоятельно рекомендуется, чтобы конфигурация магистрали не сопоставлена с записью использования PSTN, которая подключается к назначению PSTN или к любым другим подчиненным системам, подключенным через Lync Server.</span><span class="sxs-lookup"><span data-stu-id="56272-190">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

11. <span data-ttu-id="56272-p123">Измените расположение записей режима работы с ТСОП, чтобы обеспечить оптимальную производительность. Чтобы изменить расположение записи в списке, выберите соответствующую запись режима работы с ТСОП и щелкните стрелку вверх или стрелку вниз.</span><span class="sxs-lookup"><span data-stu-id="56272-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="56272-193">Порядок расположения записей режима работы с ТСОП в списке является важным.</span><span class="sxs-lookup"><span data-stu-id="56272-193">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="56272-194">Lync Server выполняет обход списка сверху вниз.</span><span class="sxs-lookup"><span data-stu-id="56272-194">Lync Server traverses the list from top to down.</span></span>

    
    </div>

12. <span data-ttu-id="56272-195">Чтобы включить обход медиаданных для клиентов, защищенных системой преобразования сетевых адресов (NAT) или брандмауэром и SBC с поддержкой блокировки, выберите **Разрешить блокирование RTP**.</span><span class="sxs-lookup"><span data-stu-id="56272-195">**Enable RTP Latching** should be selected to enable bypass media for clients behind a network address translation (NAT) or firewall and an SBC that supports latching.</span></span>

13. <span data-ttu-id="56272-196">Чтобы включить отправку сведений о журнале вызовов на узел шлюза сервера-посредника, необходимо **Включить журнал вызовов переадресации** .</span><span class="sxs-lookup"><span data-stu-id="56272-196">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

14. <span data-ttu-id="56272-197">**Включить данные о пересылке p-Assert-Identity** необходимо выбрать, чтобы включить сведения о инициаторе вызова p-Assert-Identity (PAI) для перенаправления между сервером-посредником и на стороне шлюза (и наоборот), если они есть.</span><span class="sxs-lookup"><span data-stu-id="56272-197">**Enable forward P-Asserted-Identity data** should be selected to enable the P-Asserted-Identity (PAI) call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

15. <span data-ttu-id="56272-198">Установите флажок **Включить таймер отработки отказа внешней маршрутизации**, чтобы включить быструю отработку отказа.</span><span class="sxs-lookup"><span data-stu-id="56272-198">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="56272-199">Шлюз, сопоставленный с этой магистралью, может в течение 10 секунд выдать уведомление о том, что он обрабатывает исходящий вызов.</span><span class="sxs-lookup"><span data-stu-id="56272-199">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="56272-200">Перенаправление на другую магистраль произойдет, если это уведомление не получено сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="56272-200">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="56272-201">В сетях, где задержка может увеличить время ответа или где на ответ шлюзу требуется более 10 секунд, быструю отработку отказа следует отключить.</span><span class="sxs-lookup"><span data-stu-id="56272-201">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

16. <span data-ttu-id="56272-202">(Необязательно) Сопоставьте и настройте **правила трансляции вызывающего номера** для магистральной линии связи.</span><span class="sxs-lookup"><span data-stu-id="56272-202">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="56272-203">Эти правила применяются к вызывающим номерам для исходящих вызовов</span><span class="sxs-lookup"><span data-stu-id="56272-203">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="56272-204">Чтобы выбрать одно или несколько правил из списка всех правил трансляции, доступных в развертывании корпоративной голосовой связи, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="56272-204">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="56272-205">В окне **Выбор правил трансляции** выберите правила, которые требуется сопоставить с магистральной линией связи, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="56272-205">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="56272-206">Чтобы определить новое правило преобразования и сопоставить его с магистралью, нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="56272-206">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="56272-207">Дополнительные сведения об определении нового правила приведены в статье [Определение правил преобразования в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="56272-207">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="56272-208">Чтобы изменить правило преобразования, которое уже сопоставлено с магистралью, щелкните имя правила, затем нажмите кнопку **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="56272-208">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="56272-209">Дополнительные сведения приведены в статье [Определение правил преобразования в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="56272-209">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="56272-210">Чтобы скопировать существующее правило преобразования и использовать его в качестве отправной точки для определения нового правила, щелкните имя правила и нажмите кнопку **Копировать**, а затем кнопку **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="56272-210">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="56272-211">Дополнительные сведения см. [в статье Определение правил преобразования в Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="56272-211">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="56272-212">Чтобы удалить правило преобразования из магистральной линии связи, выделите имя этого правила, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="56272-212">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="56272-213">Не сопоставляйте правила преобразования с магистралью, если вы настроили правила преобразования на сопоставленном одноранговом узле, поскольку два правила могут конфликтовать.</span><span class="sxs-lookup"><span data-stu-id="56272-213">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="56272-p131">(Необязательно) Сопоставьте и настройте **правила трансляции набранного номера** для магистральной линии связи. Эти правила применяются к вызываемым номерам для исходящих вызовов.</span><span class="sxs-lookup"><span data-stu-id="56272-p131">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="56272-216">Чтобы выбрать одно или несколько правил из списка всех правил трансляции, доступных в развертывании корпоративной голосовой связи, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="56272-216">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="56272-217">В окне **Выбор правил трансляции** выберите правила, которые требуется сопоставить с магистральной линией связи, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="56272-217">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="56272-218">Чтобы определить новое правило преобразования и сопоставить его с магистралью, нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="56272-218">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="56272-219">Дополнительные сведения об определении нового правила приведены в статье [Определение правил преобразования в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="56272-219">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="56272-220">Чтобы изменить правило преобразования, которое уже сопоставлено с магистралью, щелкните имя правила, затем нажмите кнопку **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="56272-220">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="56272-221">Дополнительные сведения приведены в статье [Определение правил преобразования в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="56272-221">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="56272-222">Чтобы скопировать существующее правило преобразования и использовать его в качестве отправной точки для определения нового правила, щелкните имя правила и нажмите кнопку **Копировать**, а затем кнопку **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="56272-222">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="56272-223">Дополнительные сведения см. [в статье Определение правил преобразования в Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="56272-223">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="56272-224">Чтобы удалить правило преобразования из магистральной линии связи, выделите имя этого правила, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="56272-224">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="56272-225">Не сопоставляйте правила преобразования с магистральной линией связи, если вы уже настроили их для связанной одноранговой магистральной линии связи, поскольку эти два правила могут конфликтовать друг с другом.</span><span class="sxs-lookup"><span data-stu-id="56272-225">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

18. <span data-ttu-id="56272-226">Убедитесь, что правила преобразования магистральной линии упорядочены в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="56272-226">Make sure that the trunk’s translation rules are arranged in the correct order.</span></span> <span data-ttu-id="56272-227">Чтобы изменить расположение правила в списке, выделите имя правила и нажмите кнопку со стрелкой вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="56272-227">To change a rule’s position in the list, highlight the rule name and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="56272-228">Lync Server 2013 перебирает список правил преобразования сверху вниз и использует первое правило, которое соответствует набранному номеру.</span><span class="sxs-lookup"><span data-stu-id="56272-228">Lync Server 2013 traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="56272-229">Если вы настраиваете магистраль таким образом, чтобы набираемый номер мог соответствовать нескольким правилам преобразования, убедитесь, что более строгие правила расположены над менее строгими.</span><span class="sxs-lookup"><span data-stu-id="56272-229">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="56272-230">Например, если вы включаете правило преобразования, соответствующее любому 11-значному номеру, и правило преобразования, которое соответствует только 11-значным номерам, начинающимся с +1425, убедитесь, что правило, соответствующее любому 11-значному номеру, располагается <EM>ниже</EM> более строгого правила.</span><span class="sxs-lookup"><span data-stu-id="56272-230">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

19. <span data-ttu-id="56272-231">Закончив настройку магистрали, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="56272-231">When you are finished configuring the trunk, click **OK**.</span></span>

20. <span data-ttu-id="56272-232">На странице **Конфигурация магистрали** нажмите кнопку **Передать**, а затем щелкните **Передать все**.</span><span class="sxs-lookup"><span data-stu-id="56272-232">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="56272-233">При каждом создании или изменении конфигурации магистрали необходимо выполнить команду <STRONG>Сохранить все</STRONG>, чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="56272-233">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="56272-234">Дополнительные сведения см в статье <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</A> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="56272-234">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

<span data-ttu-id="56272-235">После настройки магистрали Продолжайте настраивать обход сервера мультимедиа, выбирая между глобальными параметрами обхода сервера мультимедиа, как описано в разделе [глобальные параметры обхода мультимедиа в Lync Server 2013](lync-server-2013-global-media-bypass-options.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="56272-235">After you have configured the trunk, continue configuring media bypass by choosing between global media bypass options, as described in [Global media bypass options in Lync Server 2013](lync-server-2013-global-media-bypass-options.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="56272-236">См. также</span><span class="sxs-lookup"><span data-stu-id="56272-236">See Also</span></span>


[<span data-ttu-id="56272-237">Настройка магистрали без обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56272-237">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[<span data-ttu-id="56272-238">Настройка обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56272-238">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="56272-239">Глобальные параметры обхода мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56272-239">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="56272-240">Определение правил преобразования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="56272-240">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

