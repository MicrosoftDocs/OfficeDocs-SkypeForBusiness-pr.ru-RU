---
title: 'Lync Server 2013: Настройка магистрали без обхода мультимедиа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a trunk without media bypass
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425831(v=OCS.15)
ms:contentKeyID: 48183825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e6508fe88a585c22b9936e787be2ee99b8f9b7c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-without-media-bypass-in-lync-server-2013"></a><span data-ttu-id="0f45f-102">Настройка магистрали без обхода мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f45f-102">Configure a trunk without media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f45f-103">_**Тема последнего изменения:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="0f45f-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="0f45f-104">Если вы хотите настроить магистраль с обходом сервера-посредника, выполните эти действия.</span><span class="sxs-lookup"><span data-stu-id="0f45f-104">If you want to configure a trunk with media bypass disabled, follow these steps.</span></span> <span data-ttu-id="0f45f-105">Если вы хотите настроить магистраль с включенным параметром "обойти" мультимедиа, ознакомьтесь [с Разстройкой канала передачи мультимедиа в Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="0f45f-105">If you want to configure a trunk with media bypass enabled, see [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

<span data-ttu-id="0f45f-p102">Конфигурация магистрали представляет собой набор параметров, применяемых к магистрали, которой назначается эта конфигурация. Определенная конфигурация магистрали может применяться глобально (ко всем магистралям, у которых нет особых настроек сайта или пула), к сайту или к пулу. Конфигурация магистрали уровня пула позволяет применить особую конфигурацию к отдельной магистрали.</span><span class="sxs-lookup"><span data-stu-id="0f45f-p102">A trunk configuration, as described below, groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkGenericSteps"></span>

<div>

## <a name="to-configure-a-trunk-without-media-bypass"></a><span data-ttu-id="0f45f-109">Настройка магистрали без обхода сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="0f45f-109">To configure a trunk without media bypass</span></span>

1.  <span data-ttu-id="0f45f-110">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0f45f-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="0f45f-111">Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="0f45f-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="0f45f-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0f45f-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0f45f-113">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0f45f-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0f45f-114">На левой панели навигации щелкните **Маршрутизация голосовой связи** и **Настройка магистрали**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-114">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="0f45f-115">На странице **Настройка магистрали** воспользуйтесь одним из описанных ниже методов.</span><span class="sxs-lookup"><span data-stu-id="0f45f-115">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="0f45f-116">Дважды щелкните имеющуюся магистраль (например, **Глобальную**), чтобы открыть окно **Изменение настройки магистрали**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-116">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="0f45f-117">Нажмите **Создать** и выберите область для новой конфигурации магистрали:</span><span class="sxs-lookup"><span data-stu-id="0f45f-117">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="0f45f-118">**Магистраль сайта:** Выберите сайт для этой конфигурации канала **выберите сайт** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-118">**Site trunk:** Choose the site for this trunk configuration in **Select a Site** , and then click **OK**.</span></span> <span data-ttu-id="0f45f-119">Обратите внимание, что сайты, для которых уже создана конфигурация магистрали, не отображаются в разделе **Выбор сайта**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-119">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="0f45f-120">Эта конфигурация будет применяться ко всем магистралям на сайте.</span><span class="sxs-lookup"><span data-stu-id="0f45f-120">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="0f45f-121">**Магистраль пула:** Выберите имя канала, к которому будет применена эта конфигурация магистрали в разделе **Выбор службы** , и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-121">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to in **Select a Service** and click **OK**.</span></span> <span data-ttu-id="0f45f-122">Этот магистраль может быть корневой магистралью или любыми дополнительными магистральными органами, определенными в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="0f45f-122">This trunk can be the root trunk, or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="0f45f-123">Обратите внимание, что магистрали, для которых уже создана конфигурация, не отображаются в разделе **Выбор службы**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-123">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0f45f-124">Выбранную область конфигурации магистрали нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="0f45f-124">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="0f45f-125">Поле <STRONG>Название</STRONG> заполняется названием связанного с конфигурацией магистрали сайта или службы. Изменить его нельзя.</span><span class="sxs-lookup"><span data-stu-id="0f45f-125">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="0f45f-126">Выберите один из описанных ниже вариантов для **Уровня поддержки шифрования**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-126">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="0f45f-127">**Обязательно:** Шифрование с помощью протокола передачи данных в режиме реального времени (SRTP) должно использоваться для защиты трафика между сервером-посредником и шлюзом или частным обменом филиалов (УАТС).</span><span class="sxs-lookup"><span data-stu-id="0f45f-127">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="0f45f-128">**Необязательно:** SRTP шифрование используется, если поставщик услуг или оборудования его поддерживает.</span><span class="sxs-lookup"><span data-stu-id="0f45f-128">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="0f45f-129">**Не поддерживается:** SRTP шифрование не поддерживается поставщиком услуг или производителем оборудования, поэтому оно не будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="0f45f-129">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

6.  <span data-ttu-id="0f45f-130">Убедитесь, что флажок **Разрешить обход сервера-посредника** снят.</span><span class="sxs-lookup"><span data-stu-id="0f45f-130">Be sure that the **Enable media bypass** check box is cleared.</span></span>

7.  <span data-ttu-id="0f45f-131">Установите флажок **централизованная обработка мультимедиа** , если есть известная конечная точка (например, коммутируемая коммутируемая телефонная сеть (PSTN), в которой оконечные устройства имеют тот же IP-адрес, что и оконечное прекращение сигнала.</span><span class="sxs-lookup"><span data-stu-id="0f45f-131">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a public switched telephone network (PSTN) gateway where the media termination has the same IP as the signaling termination).</span></span> <span data-ttu-id="0f45f-132">Снимите этот флажок, если в магистрали нет известной точки терминирования медиаданных.</span><span class="sxs-lookup"><span data-stu-id="0f45f-132">Clear this check box if the trunk does not have a well-known media termination point.</span></span>

8.  <span data-ttu-id="0f45f-133">Если магистральный одноранговый элемент поддерживает получение запросов на использование SIP от сервера обновлений, установите флажок **Разрешить отправку ссылку на шлюз** .</span><span class="sxs-lookup"><span data-stu-id="0f45f-133">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

9.  <span data-ttu-id="0f45f-134">(Необязательно) Чтобы включить маршрутизацию между магистральными линиями связи, сопоставьте и настройте записи режима работы с ТСОП для этой конфигурации магистральной линии связи.</span><span class="sxs-lookup"><span data-stu-id="0f45f-134">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration.</span></span> <span data-ttu-id="0f45f-135">Использование PSTN, связанное с этой конфигурацией канала, будет применяться ко всем входящим звонкам через магистраль, не исходящий из конечной точки Lync.</span><span class="sxs-lookup"><span data-stu-id="0f45f-135">The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint.</span></span> <span data-ttu-id="0f45f-136">Чтобы управлять записями режима работы с ТСОП, связанными с конфигурацией магистральной линии связи, используйте один из приведенных ниже методов.</span><span class="sxs-lookup"><span data-stu-id="0f45f-136">To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="0f45f-137">Чтобы выбрать одну или несколько записей из списка всех записей использования PSTN, доступных в вашем корпоративном развертывании, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-137">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="0f45f-138">Выделите записи, которые следует связать с этой конфигурацией магистральной линии связи, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-138">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="0f45f-139">Чтобы удалить запись режима работы с ТСОП из этой конфигурации магистральной линии связи, выберите эту запись и щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-139">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="0f45f-140">Чтобы определить новую запись режима работы с ТСОП и сопоставить ее с этой конфигурацией магистральной линии связи, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="0f45f-140">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="0f45f-141">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-141">Click **New**.</span></span>
        
        2.  <span data-ttu-id="0f45f-142">В поле **Имя** укажите уникальное описательное имя для записи.</span><span class="sxs-lookup"><span data-stu-id="0f45f-142">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="0f45f-p110">Имя записи о режиме работы с ТСОП не должно повторяться в пределах развертывания корпоративной голосовой связи. После сохранения записи поле <STRONG>Имя</STRONG> не доступно для редактирования.</span><span class="sxs-lookup"><span data-stu-id="0f45f-p110">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="0f45f-145">Используйте один из следующих методов для сопоставления и настройки маршрутов для этой записи режима работы с ТСОП:</span><span class="sxs-lookup"><span data-stu-id="0f45f-145">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="0f45f-146">Чтобы выбрать один или несколько маршрутов из списка всех доступных маршрутов в вашем корпоративном развертывании, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-146">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="0f45f-147">Выделите маршруты, которые требуется сопоставить с этой записью режима работы с ТСОП, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-147">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="0f45f-148">Чтобы удалить маршрут из записи режима работы с ТСОП, выберите этот маршрут и щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-148">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="0f45f-149">Чтобы определить новый маршрут и сопоставить его с этой записью режима работы с ТСОП, щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-149">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="0f45f-150">Дополнительные сведения можно найти [в разделе Создание голосовых маршрутов в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="0f45f-150">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="0f45f-151">Чтобы изменить маршрут, сопоставленный с этой записью режима работы с ТСОП, выберите данный маршрут и щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-151">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="0f45f-152">Подробности можно найти [в разделе Изменение голосового маршрута в Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="0f45f-152">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="0f45f-153">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-153">Click **OK**.</span></span>
    
      - <span data-ttu-id="0f45f-154">Чтобы изменить запись режима работы с ТСОП, уже сопоставленную с этой настройкой магистральной линии связи, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="0f45f-154">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="0f45f-155">Выберите запись режима работы с ТСОП, которую требуется изменить, и щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-155">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="0f45f-156">Используйте один из следующих методов для сопоставления и настройки маршрутов для этой записи режима работы с ТСОП:</span><span class="sxs-lookup"><span data-stu-id="0f45f-156">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="0f45f-157">Чтобы выбрать один или несколько маршрутов из списка всех доступных маршрутов в вашем корпоративном развертывании, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-157">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="0f45f-158">Выделите маршруты, которые требуется сопоставить с этой записью режима работы с ТСОП, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-158">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="0f45f-159">Чтобы удалить маршрут из записи режима работы с ТСОП, выберите этот маршрут и щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-159">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="0f45f-160">Чтобы определить новый маршрут и сопоставить его с этой записью режима работы с ТСОП, щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-160">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="0f45f-161">Дополнительные сведения можно найти [в разделе Создание голосовых маршрутов в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="0f45f-161">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="0f45f-162">Чтобы изменить маршрут, сопоставленный с этой записью режима работы с ТСОП, выберите данный маршрут и щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-162">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="0f45f-163">Подробности можно найти [в разделе Изменение голосового маршрута в Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="0f45f-163">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="0f45f-164">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-164">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0f45f-165">Важно связывать записи об использовании PSTN в соответствии с одноранговым элементом сервера, связанным с настройкой магистрали.</span><span class="sxs-lookup"><span data-stu-id="0f45f-165">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="0f45f-166">Если одноранговый сервер является шлюзом PSTN или контроллером границ сеанса (SBC), настоятельно рекомендуется, чтобы конфигурация канала не сопоставлена с записью использования PSTN, которая направляет маршрут в назначение PSTN или другие нижестоящие системы, подключенные через Lync. Server.</span><span class="sxs-lookup"><span data-stu-id="0f45f-166">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

10. <span data-ttu-id="0f45f-p118">Измените расположение записей режима работы с ТСОП, чтобы обеспечить оптимальную производительность. Чтобы изменить расположение записи в списке, выберите соответствующую запись режима работы с ТСОП и щелкните стрелку вверх или стрелку вниз.</span><span class="sxs-lookup"><span data-stu-id="0f45f-p118">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0f45f-169">Порядок расположения записей режима работы с ТСОП в списке является важным.</span><span class="sxs-lookup"><span data-stu-id="0f45f-169">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="0f45f-170">Lync Server обходит список сверху вниз.</span><span class="sxs-lookup"><span data-stu-id="0f45f-170">Lync Server traverses the list from top to down.</span></span>

    
    </div>

11. <span data-ttu-id="0f45f-171">Установите флажок **Разрешить блокирование RTP**, чтобы разрешить обход сервера-посредника для клиентов, находящихся за устройством NAT (преобразование сетевых адресов) или брандмауэром, и пограничного контроллера сеансов, поддерживающего блокирование.</span><span class="sxs-lookup"><span data-stu-id="0f45f-171">**Enable RTP Latching** should be selected to enable bypass media for clients behind a NAT or firewall and an SBC that supports latching.</span></span>

12. <span data-ttu-id="0f45f-172">**Включите функцию "включить переадресацию звонков** ", чтобы разрешить отправку сведений из журнала звонков на узел шлюза на сервере обновлений.</span><span class="sxs-lookup"><span data-stu-id="0f45f-172">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

13. <span data-ttu-id="0f45f-173">**Включить данные о пересылке в прямые P-утвержденные-идентификаторы** должны быть выбраны, чтобы обеспечить переадресацию сведений о паи звонке между сервером обновлений и стороной шлюза (и наоборот), если они есть.</span><span class="sxs-lookup"><span data-stu-id="0f45f-173">**Enable forward P-Asserted-Identity data** should be selected to enable PAI call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

14. <span data-ttu-id="0f45f-174">Чтобы включить быструю отработку отказа, выберите **Включить таймер отработки отказа внешней маршрутизации**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-174">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="0f45f-175">Шлюз, связанный с данной магистралью, может отправить уведомление об обработке исходящего вызова в течение 10 секунд.</span><span class="sxs-lookup"><span data-stu-id="0f45f-175">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="0f45f-176">Перенаправление на другую магистраль произойдет, если это уведомление не получено от сервера обновлений.</span><span class="sxs-lookup"><span data-stu-id="0f45f-176">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="0f45f-177">Для сетей с высокой задержкой, которая может увеличить время ответа, или для шлюзов, время отклика которых превышает 10 секунд, быстрая отработка отказа должна быть отключена.</span><span class="sxs-lookup"><span data-stu-id="0f45f-177">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

15. <span data-ttu-id="0f45f-178">(Необязательно) Сопоставьте и настройте **правила трансляции вызывающего номера** для магистральной линии связи.</span><span class="sxs-lookup"><span data-stu-id="0f45f-178">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="0f45f-179">Эти правила применяются к вызывающим номерам для исходящих вызовов</span><span class="sxs-lookup"><span data-stu-id="0f45f-179">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="0f45f-180">Чтобы выбрать одно или несколько правил из списка всех правил трансляции, доступных в вашем корпоративном развертывании, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-180">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="0f45f-181">В окне **Выбор правил трансляции** выберите правила, которые требуется сопоставить с магистральной линией связи, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-181">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="0f45f-182">Чтобы определить новое правило преобразования и сопоставить его с магистральной линией связи, щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-182">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="0f45f-183">Подробные сведения о том, как определить новое правило, приведены в разделе [Определение правил перевода в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="0f45f-183">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="0f45f-184">Чтобы изменить правило преобразования, уже сопоставленное с магистральной линией связи, щелкните имя правила, а затем выберите **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-184">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="0f45f-185">Подробности можно найти [в разделе Определение правил перевода в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="0f45f-185">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="0f45f-186">Чтобы скопировать существующее правило преобразования и использовать его в качестве отправной точки для определения нового правила, щелкните имя этого правила, щелкните **Копировать** и **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-186">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="0f45f-187">Подробности можно найти [в разделе Определение правил перевода в Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="0f45f-187">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="0f45f-188">Чтобы удалить правило преобразования из магистральной линии связи, выделите имя этого правила, а затем щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-188">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="разрешения" alt="security" /><span data-ttu-id="0f45f-190">Примечание о безопасности:</span><span class="sxs-lookup"><span data-stu-id="0f45f-190">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="0f45f-191">Не сопоставляйте правила преобразования с магистральной линией связи, если вы уже настроили их для связанной одноранговой магистральной линии связи, поскольку эти два правила могут конфликтовать друг с другом.</span><span class="sxs-lookup"><span data-stu-id="0f45f-191">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

16. <span data-ttu-id="0f45f-p126">(Необязательно) Сопоставьте и настройте **правила трансляции набранного номера** для магистральной линии связи. Эти правила применяются к вызываемым номерам для исходящих вызовов.</span><span class="sxs-lookup"><span data-stu-id="0f45f-p126">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="0f45f-194">Чтобы выбрать одно или несколько правил из списка всех правил трансляции, доступных в вашем корпоративном развертывании, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-194">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="0f45f-195">В окне **Выбор правил трансляции** выберите правила, которые требуется сопоставить с магистральной линией связи, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-195">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="0f45f-196">Чтобы определить новое правило преобразования и сопоставить его с магистральной линией связи, щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-196">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="0f45f-197">Подробные сведения о том, как определить новое правило, приведены в разделе [Определение правил перевода в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="0f45f-197">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="0f45f-198">Чтобы изменить правило преобразования, уже сопоставленное с магистральной линией связи, щелкните имя правила, а затем выберите **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-198">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="0f45f-199">Подробности можно найти [в разделе Определение правил перевода в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="0f45f-199">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="0f45f-200">Чтобы скопировать существующее правило преобразования и использовать его в качестве отправной точки для определения нового правила, щелкните имя этого правила, щелкните **Копировать** и **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-200">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="0f45f-201">Подробности можно найти [в разделе Определение правил перевода в Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="0f45f-201">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="0f45f-202">Чтобы удалить правило преобразования из магистральной линии связи, выделите имя этого правила, а затем щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-202">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="0f45f-203">Не сопоставляйте правила преобразования с магистральной линией связи, если вы уже настроили их для связанной одноранговой магистральной линии связи, поскольку эти два правила могут конфликтовать друг с другом.</span><span class="sxs-lookup"><span data-stu-id="0f45f-203">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="0f45f-p131">Правила трансляции линии связи должны быть выстроены в правильном порядке. Чтобы изменить положение правила в списке, выделите имя правила и нажмите кнопку со стрелкой вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="0f45f-p131">Make sure that the trunk’s translation rules are arranged in the correct order. To change a rule’s position in the list, highlight the rule name, and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0f45f-206">Lync Server обходит список правил перевода сверху вниз и использует первое правило, которое соответствует номеру набора.</span><span class="sxs-lookup"><span data-stu-id="0f45f-206">Lync Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="0f45f-207">Если магистраль настроена так, что набранный номер может соответствовать нескольким правилам, то более строгие правила должны предшествовать менее строгим.</span><span class="sxs-lookup"><span data-stu-id="0f45f-207">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="0f45f-208">Например, если вы добавили правило трансляции, совпадающее с любым 11-значным номером и правило, совпадающее с 11-значным номером, начинающимся на +1425, то первое правило должно располагаться <EM>ниже</EM> второго, более строгого правила.</span><span class="sxs-lookup"><span data-stu-id="0f45f-208">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

18. <span data-ttu-id="0f45f-209">После завершения настройки магистрали нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-209">When you are finished configuring the trunk, click **OK**.</span></span>

19. <span data-ttu-id="0f45f-210">На странице **Настройка магистрали** нажмите **Фиксировать** и затем **Фиксировать все**.</span><span class="sxs-lookup"><span data-stu-id="0f45f-210">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0f45f-211">После создания или изменения конфигурации магистрали следует выполнить команду <STRONG>Сохранить все</STRONG>, чтобы опубликовать изменения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0f45f-211">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="0f45f-212">Дополнительные сведения можно найти в разделе <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013</A> в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="0f45f-212">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0f45f-213">См. также</span><span class="sxs-lookup"><span data-stu-id="0f45f-213">See Also</span></span>


[<span data-ttu-id="0f45f-214">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f45f-214">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="0f45f-215">Определение правил преобразования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f45f-215">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

