---
title: 'Lync Server 2013: Настройка магистрали без обхода сервера мультимедиа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk without media bypass
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425831(v=OCS.15)
ms:contentKeyID: 48183825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd810c64f546c907f0fd00d2dc2fea43e09fa1bf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028800"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-without-media-bypass-in-lync-server-2013"></a><span data-ttu-id="f3427-102">Настройка магистрали без обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3427-102">Configure a trunk without media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3427-103">_**Последнее изменение темы:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="f3427-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="f3427-104">Если вы хотите настроить магистраль с обходом сервера-посредника, выполните эти действия.</span><span class="sxs-lookup"><span data-stu-id="f3427-104">If you want to configure a trunk with media bypass disabled, follow these steps.</span></span> <span data-ttu-id="f3427-105">Если вы хотите настроить магистраль с включенным обходом сервера мультимедиа, ознакомьтесь со статьей [Настройка магистрали с обходом сервера в Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="f3427-105">If you want to configure a trunk with media bypass enabled, see [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

<span data-ttu-id="f3427-p102">Конфигурация магистрали представляет собой набор параметров, применяемых к магистрали, которой назначается эта конфигурация. Определенная конфигурация магистрали может применяться глобально (ко всем магистралям, у которых нет особых настроек сайта или пула), к сайту или к пулу. Конфигурация магистрали уровня пула позволяет применить особую конфигурацию к отдельной магистрали.</span><span class="sxs-lookup"><span data-stu-id="f3427-p102">A trunk configuration, as described below, groups a set of parameters that are applied to trunks assigned this trunk configuration. A particular trunk configuration can be scoped globally (to all trunks that do not have more specific site or pool configuration), or to a site, or to a pool. The pool-level trunk configuration is used to scope a specific trunk configuration to a single trunk.</span></span>

<span id="BKMK_ConfigTrunkGenericSteps"></span>

<div>

## <a name="to-configure-a-trunk-without-media-bypass"></a><span data-ttu-id="f3427-109">Настройка магистрали без обхода сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="f3427-109">To configure a trunk without media bypass</span></span>

1.  <span data-ttu-id="f3427-110">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f3427-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="f3427-111">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f3427-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f3427-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f3427-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f3427-113">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f3427-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f3427-114">В левой панели навигации щелкните **Маршрутизация голосовой связи**, а затем выберите **Настройка линии связи**.</span><span class="sxs-lookup"><span data-stu-id="f3427-114">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

4.  <span data-ttu-id="f3427-115">На странице **Конфигурация магистрали** используйте один из следующих методов для настройки магистрали:</span><span class="sxs-lookup"><span data-stu-id="f3427-115">On the **Trunk Configuration** page, use one of the following methods to configure a trunk:</span></span>
    
      - <span data-ttu-id="f3427-116">Дважды щелкните существующую магистраль (например, в **глобальную** магистраль), чтобы открыть диалоговое окно **Изменение конфигурации магистрали**.</span><span class="sxs-lookup"><span data-stu-id="f3427-116">Double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>
    
      - <span data-ttu-id="f3427-117">Нажмите кнопку **Создать**, а затем выберите область для конфигурации новой магистрали:</span><span class="sxs-lookup"><span data-stu-id="f3427-117">Click **New**, and then select a scope for the new trunk configuration:</span></span>
        
          - <span data-ttu-id="f3427-118">**Магистраль сайта:** Выберите сайт для этой конфигурации магистрали в разделе **Выбор сайта** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f3427-118">**Site trunk:** Choose the site for this trunk configuration in **Select a Site** , and then click **OK**.</span></span> <span data-ttu-id="f3427-119">Обратите внимание, что сайты, для которых уже создана конфигурация магистрали, не отображаются в разделе **Выбор сайта**.</span><span class="sxs-lookup"><span data-stu-id="f3427-119">Note that if a trunk configuration has already been created for a site, the site does not appear in **Select a Site**.</span></span> <span data-ttu-id="f3427-120">Эта конфигурация будет применяться ко всем магистралям на сайте.</span><span class="sxs-lookup"><span data-stu-id="f3427-120">This trunk configuration will be applied to all trunks in the site.</span></span>
        
          - <span data-ttu-id="f3427-121">**Магистральная магистраль пула:** Выберите имя магистрали, к которой применяется эта конфигурация магистрали, в окне **Выбор службы** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f3427-121">**Pool trunk:** Choose the name of the trunk that this trunk configuration applies to in **Select a Service** and click **OK**.</span></span> <span data-ttu-id="f3427-122">Эта магистраль может быть корневой магистралью или любым дополнительным магистральным каналом, определенным в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="f3427-122">This trunk can be the root trunk, or any additional trunks defined in Topology Builder.</span></span> <span data-ttu-id="f3427-123">Обратите внимание, что магистрали, для которых уже создана конфигурация, не отображаются в разделе **Выбор службы**.</span><span class="sxs-lookup"><span data-stu-id="f3427-123">Note that if a trunk configuration has already been created for a specific trunk, the trunk does not appear in **Select a Service**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f3427-124">Выбранную область действия конфигурации магистрали уже нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="f3427-124">After you select the scope of the trunk configuration, it cannot be changed.</span></span><BR><span data-ttu-id="f3427-125">В поле <STRONG>Имя</STRONG> указывается имя связанного с конфигурацией магистрали сайта или службы магистрали, это имя нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="f3427-125">The <STRONG>Name</STRONG> field is prepopulated with the name of the trunk configuration’s associated site or service and cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="f3427-126">Выберите один из следующих параметров в поле **Уровень поддержки шифрования**:</span><span class="sxs-lookup"><span data-stu-id="f3427-126">Select one of the following **Encryption support level** options:</span></span>
    
      - <span data-ttu-id="f3427-127">**Обязательный атрибут:** Чтобы защитить трафик между сервером-посредником и шлюзом или УАТС (УАТС), необходимо использовать шифрование протокола SRTP.</span><span class="sxs-lookup"><span data-stu-id="f3427-127">**Required:** Secure real-time transport protocol (SRTP) encryption must be used to help protect traffic between the Mediation Server and the gateway or private branch exchange (PBX).</span></span>
    
      - <span data-ttu-id="f3427-128">**Необязательно:** Шифрование SRTP будет использоваться, если поставщик услуг или производитель оборудования его поддерживает.</span><span class="sxs-lookup"><span data-stu-id="f3427-128">**Optional:** SRTP encryption will be used if the service provider or equipment manufacturer supports it.</span></span>
    
      - <span data-ttu-id="f3427-129">**Не поддерживается:** Шифрование SRTP не поддерживается поставщиком услуг или производителем оборудования, поэтому не будет использоваться.</span><span class="sxs-lookup"><span data-stu-id="f3427-129">**Not Supported:** SRTP encryption is not supported by the service provider or equipment manufacturer and therefore will not be used.</span></span>

6.  <span data-ttu-id="f3427-130">Убедитесь, что флажок **Разрешить обход мультимедиа** снят.</span><span class="sxs-lookup"><span data-stu-id="f3427-130">Be sure that the **Enable media bypass** check box is cleared.</span></span>

7.  <span data-ttu-id="f3427-p107">Установите флажок **Централизованная обработка мультимедиа**, если существует известная точка терминирования медиаданных (например, шлюз телефонной сети общего пользования (ТСОП), где у точки терминирования такой же IP-адрес, как и у точки терминирования сигналов). Снимите этот флажок, если в магистрали нет известной точки терминирования медиаданных.</span><span class="sxs-lookup"><span data-stu-id="f3427-p107">Select the **Centralized media processing** check box if there is a well-known media termination point (for example, a public switched telephone network (PSTN) gateway where the media termination has the same IP as the signaling termination). Clear this check box if the trunk does not have a well-known media termination point.</span></span>

8.  <span data-ttu-id="f3427-133">Если магистральный узел поддерживает получение запросов SIP на получение запросов SIP от сервера-посредника, установите флажок **Разрешить отправку ссылку на шлюз** .</span><span class="sxs-lookup"><span data-stu-id="f3427-133">If the trunk peer supports receiving SIP REFER requests from the Mediation Server, select the **Enable sending refer to the gateway** check box.</span></span>

9.  <span data-ttu-id="f3427-p108">(Необязательно) Чтобы включить маршрутизацию между магистральными линиями связи, сопоставьте и настройте записи режима работы с ТСОП для этой конфигурации магистральной линии связи. Записи режима работы с ТСОП, связанные с этой конфигурацией магистральной линии связи, будут применены ко всем входящим вызовам через магистральную линию связи, которые начинаются за пределами конечной точки Lync. Чтобы управлять записями режима работы с ТСОП, связанными с конфигурацией магистральной линии связи, используйте один из приведенных ниже методов.</span><span class="sxs-lookup"><span data-stu-id="f3427-p108">(Optional) To enable inter-trunk routing, associate and configure PSTN usage records to this trunk configuration. The PSTN usages associated to this trunk configuration will be applied for all incoming calls through the trunk that is not originating from a Lync endpoint. To manage PSTN usage records associated to a trunk configuration, use one of the following methods:</span></span>
    
      - <span data-ttu-id="f3427-137">Чтобы выбрать одну или несколько записей из списка всех записей использования PSTN, доступных в развертывании корпоративной голосовой связи, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="f3427-137">To select one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="f3427-138">Выделите записи, которые следует связать с этой конфигурацией магистральной линии связи, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f3427-138">Highlight the records you want to associate with this trunk configuration and then click **OK**.</span></span>
    
      - <span data-ttu-id="f3427-139">Чтобы удалить запись режима работы с ТСОП из этой конфигурации магистральной линии связи, выберите эту запись и щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f3427-139">To remove a PSTN usage record from this trunk configuration, select the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="f3427-140">Чтобы определить новую запись режима работы с ТСОП и сопоставить ее с этой конфигурацией магистральной линии связи, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f3427-140">To define a new PSTN usage record and associate it with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="f3427-141">Щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="f3427-141">Click **New**.</span></span>
        
        2.  <span data-ttu-id="f3427-142">В поле **Имя** укажите уникальное описательное имя для записи.</span><span class="sxs-lookup"><span data-stu-id="f3427-142">In the **Name** field, specify a descriptive name for the record that is unique.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="f3427-p110">Имя записи режима работы с ТСОП должно быть уникальным в рамках развертывания корпоративной голосовой связи. После сохранения записи поле <STRONG>Имя</STRONG> изменить невозможно.</span><span class="sxs-lookup"><span data-stu-id="f3427-p110">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="f3427-145">Используйте один из следующих методов для сопоставления и настройки маршрутов для этой записи режима работы с ТСОП:</span><span class="sxs-lookup"><span data-stu-id="f3427-145">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="f3427-146">Чтобы выбрать один или несколько маршрутов из списка доступных маршрутов в развертывании корпоративной голосовой связи, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="f3427-146">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="f3427-147">Выделите маршруты, которые хотите сопоставить с этой записью режима использования ТСОП, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f3427-147">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="f3427-148">Чтобы удалить маршрут из записи режима работы с ТСОП, выберите этот маршрут и щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f3427-148">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="f3427-149">Чтобы определить новый маршрут и сопоставить его с этой записью режима работы с ТСОП, щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="f3427-149">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="f3427-150">Дополнительные сведения см. [в статье Создание маршрута голосовых вызовов в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f3427-150">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="f3427-151">Чтобы изменить маршрут, сопоставленный с этой записью режима работы с ТСОП, выберите маршрут и щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="f3427-151">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="f3427-152">Дополнительную информацию можно узнать [в статье изменение маршрута голосовой связи в Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f3427-152">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="f3427-153">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f3427-153">Click **OK**.</span></span>
    
      - <span data-ttu-id="f3427-154">Чтобы изменить запись режима работы с ТСОП, уже сопоставленную с этой конфигурацией магистральной линии связи, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f3427-154">To edit a PSTN usage record that is already associated with this trunk configuration, do the following:</span></span>
        
        1.  <span data-ttu-id="f3427-155">Выберите запись режима работы с ТСОП, которую требуется изменить, и щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="f3427-155">Select the PSTN usage record you want to edit, and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="f3427-156">Используйте один из следующих методов для сопоставления и настройки маршрутов для этой записи режима работы с ТСОП:</span><span class="sxs-lookup"><span data-stu-id="f3427-156">Use one of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="f3427-157">Чтобы выбрать один или несколько маршрутов из списка доступных маршрутов в развертывании корпоративной голосовой связи, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="f3427-157">To select one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="f3427-158">Выделите маршруты, которые хотите сопоставить с этой записью режима использования ТСОП, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f3427-158">Highlight the routes you want to associate with this PSTN usage record, and click **OK**.</span></span>
            
              - <span data-ttu-id="f3427-159">Чтобы удалить маршрут из записи режима работы с ТСОП, выберите этот маршрут и щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f3427-159">To remove a route from the PSTN usage record, select the route, and click **Remove**.</span></span>
            
              - <span data-ttu-id="f3427-160">Чтобы определить новый маршрут и сопоставить его с этой записью режима работы с ТСОП, щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="f3427-160">To define a new route and associate it to this PSTN usage record, click **New**.</span></span> <span data-ttu-id="f3427-161">Дополнительные сведения см. [в статье Создание маршрута голосовых вызовов в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f3427-161">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="f3427-162">Чтобы изменить маршрут, сопоставленный с этой записью режима работы с ТСОП, выберите маршрут и щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="f3427-162">To edit a route that is associated with this PSTN usage record, select the route, and click **Show details**.</span></span> <span data-ttu-id="f3427-163">Дополнительную информацию можно узнать [в статье изменение маршрута голосовой связи в Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="f3427-163">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="f3427-164">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f3427-164">Click **OK**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f3427-165">Важно связать записи об использовании PSTN в соответствии с одноранговым узлом сервера-посредника, связанным с настраиваемой магистралью.</span><span class="sxs-lookup"><span data-stu-id="f3427-165">It important to associate PSTN usage records according to the Mediation Server peer that is associated to the trunk being configured.</span></span> <span data-ttu-id="f3427-166">Если узел сервера-посредника является шлюзом PSTN или пограничным контроллером сеансов (SBC), настоятельно рекомендуется, чтобы конфигурация магистрали не сопоставлена с записью использования PSTN, которая подключается к назначению PSTN или другим подчиненным системам, подключенным через Lync. Сервер.</span><span class="sxs-lookup"><span data-stu-id="f3427-166">If the Mediation Server peer is a PSTN gateway or a Session Border Controller (SBC), it is strongly recommended that the trunk configuration is not associated to a PSTN usage record that routes to a PSTN destination or any other downstream systems connected via Lync Server.</span></span>

    
    </div>

10. <span data-ttu-id="f3427-p118">Измените расположение записей режима работы с ТСОП, чтобы обеспечить оптимальную производительность. Чтобы изменить расположение записи в списке, выберите соответствующую запись режима работы с ТСОП и щелкните стрелку вверх или стрелку вниз.</span><span class="sxs-lookup"><span data-stu-id="f3427-p118">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, select the PSTN usage record, and click the up or down arrows.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f3427-169">Порядок расположения записей режима работы с ТСОП в списке является важным.</span><span class="sxs-lookup"><span data-stu-id="f3427-169">The order in which PSTN usage records are listed in the trunk configuration is significant.</span></span> <span data-ttu-id="f3427-170">Lync Server выполняет обход списка сверху вниз.</span><span class="sxs-lookup"><span data-stu-id="f3427-170">Lync Server traverses the list from top to down.</span></span>

    
    </div>

11. <span data-ttu-id="f3427-171">Установите флажок **Разрешить блокирование RTP**, чтобы разрешить обход сервера-посредника для клиентов, находящихся за устройством NAT (преобразование сетевых адресов) или брандмауэром, и пограничного контроллера сеансов, поддерживающего блокирование.</span><span class="sxs-lookup"><span data-stu-id="f3427-171">**Enable RTP Latching** should be selected to enable bypass media for clients behind a NAT or firewall and an SBC that supports latching.</span></span>

12. <span data-ttu-id="f3427-172">Чтобы включить отправку сведений о журнале вызовов на узел шлюза сервера-посредника, необходимо **Включить журнал вызовов переадресации** .</span><span class="sxs-lookup"><span data-stu-id="f3427-172">**Enable forward call history** should be selected to enable sending of call history information to the gateway peer of the Mediation Server.</span></span>

13. <span data-ttu-id="f3427-173">**Включить данные о пересылке P-Assert-Identity** необходимо выбрать, чтобы разрешить перенаправление сведений о источнике вызовов Pai между сервером-посредником и стороны шлюза (и наоборот), если они есть.</span><span class="sxs-lookup"><span data-stu-id="f3427-173">**Enable forward P-Asserted-Identity data** should be selected to enable PAI call originator information to be forwarded between the Mediation Server side and gateway side (and vice versa), when present.</span></span>

14. <span data-ttu-id="f3427-174">Установите флажок **Включить таймер отработки отказа внешней маршрутизации**, чтобы включить быструю отработку отказа.</span><span class="sxs-lookup"><span data-stu-id="f3427-174">**Enable outbound routing failover timer** should be selected to enable fast failover.</span></span> <span data-ttu-id="f3427-175">Шлюз, сопоставленный с этой магистралью, может в течение 10 секунд выдать уведомление о том, что он обрабатывает исходящий вызов.</span><span class="sxs-lookup"><span data-stu-id="f3427-175">The gateway associated with this trunk can give notification within 10 seconds that it is processing an outbound call.</span></span> <span data-ttu-id="f3427-176">Перенаправление на другую магистраль произойдет, если это уведомление не получено сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="f3427-176">Rerouting to another trunk will occur if this notification is not received by the Mediation Server.</span></span> <span data-ttu-id="f3427-177">В сетях, где задержка может увеличить время ответа или где на ответ шлюзу требуется более 10 секунд, быструю отработку отказа следует отключить.</span><span class="sxs-lookup"><span data-stu-id="f3427-177">On networks where latency may delay the response time or the gateway takes longer than 10 seconds to respond, the fast failover should be disabled.</span></span>

15. <span data-ttu-id="f3427-178">(Необязательно) Сопоставьте и настройте **правила трансляции вызывающего номера** для магистральной линии связи.</span><span class="sxs-lookup"><span data-stu-id="f3427-178">(Optional) Associate and configure **calling number translation rules** for the trunk.</span></span> <span data-ttu-id="f3427-179">Эти правила применяются к вызывающим номерам для исходящих вызовов</span><span class="sxs-lookup"><span data-stu-id="f3427-179">These translation rules apply to the calling number for outbound calls</span></span>
    
      - <span data-ttu-id="f3427-180">Чтобы выбрать одно или несколько правил из списка всех правил трансляции, доступных в развертывании корпоративной голосовой связи, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="f3427-180">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="f3427-181">В окне **Выбор правил трансляции** выберите правила, которые требуется сопоставить с магистральной линией связи, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f3427-181">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="f3427-182">Чтобы определить новое правило преобразования и сопоставить его с магистралью, нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="f3427-182">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="f3427-183">Дополнительные сведения об определении нового правила приведены в статье [Определение правил преобразования в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="f3427-183">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="f3427-184">Чтобы изменить правило преобразования, которое уже сопоставлено с магистралью, щелкните имя правила, затем нажмите кнопку **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="f3427-184">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="f3427-185">Дополнительные сведения приведены в статье [Определение правил преобразования в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="f3427-185">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="f3427-186">Чтобы скопировать существующее правило преобразования и использовать его в качестве отправной точки для определения нового правила, щелкните имя правила и нажмите кнопку **Копировать**, а затем кнопку **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="f3427-186">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="f3427-187">Дополнительные сведения см. [в статье Определение правил преобразования в Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="f3427-187">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="f3427-188">Чтобы удалить правило преобразования из магистральной линии связи, выделите имя этого правила, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f3427-188">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="защиты" alt="security" /><span data-ttu-id="f3427-190">Примечание о безопасности:</span><span class="sxs-lookup"><span data-stu-id="f3427-190">Security Note:</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="f3427-191">Не сопоставляйте правила преобразования с магистралью, если вы настроили правила преобразования на сопоставленном одноранговом узле, поскольку два правила могут конфликтовать.</span><span class="sxs-lookup"><span data-stu-id="f3427-191">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span></td>
    </tr>
    </tbody>
    </table>
    
    </div>

16. <span data-ttu-id="f3427-p126">(Необязательно) Сопоставьте и настройте **правила трансляции набранного номера** для магистральной линии связи. Эти правила применяются к вызываемым номерам для исходящих вызовов.</span><span class="sxs-lookup"><span data-stu-id="f3427-p126">(Optional) Associate and configure **called number translation rules** for the trunk. The translation rules apply to the called number in an outbound call.</span></span>
    
      - <span data-ttu-id="f3427-194">Чтобы выбрать одно или несколько правил из списка всех правил трансляции, доступных в развертывании корпоративной голосовой связи, нажмите кнопку **выбрать**.</span><span class="sxs-lookup"><span data-stu-id="f3427-194">To choose one or more rules from a list of all translation rules that are available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="f3427-195">В окне **Выбор правил трансляции** выберите правила, которые требуется сопоставить с магистральной линией связи, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f3427-195">In **Select Translation Rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>
    
      - <span data-ttu-id="f3427-196">Чтобы определить новое правило преобразования и сопоставить его с магистралью, нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="f3427-196">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="f3427-197">Дополнительные сведения об определении нового правила приведены в статье [Определение правил преобразования в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="f3427-197">For details about defining a new rule, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="f3427-198">Чтобы изменить правило преобразования, которое уже сопоставлено с магистралью, щелкните имя правила, затем нажмите кнопку **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="f3427-198">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**.</span></span> <span data-ttu-id="f3427-199">Дополнительные сведения приведены в статье [Определение правил преобразования в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="f3427-199">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="f3427-200">Чтобы скопировать существующее правило преобразования и использовать его в качестве отправной точки для определения нового правила, щелкните имя правила и нажмите кнопку **Копировать**, а затем кнопку **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="f3427-200">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**.</span></span> <span data-ttu-id="f3427-201">Дополнительные сведения см. [в статье Определение правил преобразования в Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span><span class="sxs-lookup"><span data-stu-id="f3427-201">For details, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).</span></span>
    
      - <span data-ttu-id="f3427-202">Чтобы удалить правило преобразования из магистральной линии связи, выделите имя этого правила, а затем нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="f3427-202">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="f3427-203">Не сопоставляйте правила преобразования с магистральной линией связи, если вы уже настроили их для связанной одноранговой магистральной линии связи, поскольку эти два правила могут конфликтовать друг с другом.</span><span class="sxs-lookup"><span data-stu-id="f3427-203">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>

    
    </div>

17. <span data-ttu-id="f3427-204">Убедитесь, что правила преобразования магистральной линии упорядочены в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="f3427-204">Make sure that the trunk’s translation rules are arranged in the correct order.</span></span> <span data-ttu-id="f3427-205">Чтобы изменить положение правила в списке, выделите имя правила и нажмите кнопку со стрелкой вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="f3427-205">To change a rule’s position in the list, highlight the rule name, and then click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f3427-206">Lync Server выполняет обход списка правил трансляции сверху вниз и использует первое правило, которое соответствует набранному номеру.</span><span class="sxs-lookup"><span data-stu-id="f3427-206">Lync Server traverses the translation rule list from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="f3427-207">Если вы настраиваете магистраль таким образом, чтобы набираемый номер мог соответствовать нескольким правилам преобразования, убедитесь, что более строгие правила расположены над менее строгими.</span><span class="sxs-lookup"><span data-stu-id="f3427-207">If you configure a trunk so that a dialed number can match more than one translation rule, be sure that the more restrictive rules are sorted above the less restrictive rules.</span></span> <span data-ttu-id="f3427-208">Например, если вы включаете правило преобразования, соответствующее любому 11-значному номеру, и правило преобразования, которое соответствует только 11-значным номерам, начинающимся с +1425, убедитесь, что правило, соответствующее любому 11-значному номеру, располагается <EM>ниже</EM> более строгого правила.</span><span class="sxs-lookup"><span data-stu-id="f3427-208">For example, if you have included a translation rule that matches any 11-digit number and a translation rule that matches only 11-digit numbers that start with +1425, be sure that the rule that matches any 11-digit number is sorted <EM>below</EM> the more restrictive rule.</span></span>

    
    </div>

18. <span data-ttu-id="f3427-209">Закончив настройку магистрали, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f3427-209">When you are finished configuring the trunk, click **OK**.</span></span>

19. <span data-ttu-id="f3427-210">На странице **Конфигурация магистрали** нажмите кнопку **Передать**, а затем щелкните **Передать все**.</span><span class="sxs-lookup"><span data-stu-id="f3427-210">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f3427-211">При каждом создании или изменении конфигурации магистрали необходимо выполнить команду <STRONG>Сохранить все</STRONG>, чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f3427-211">Whenever you create or modify a trunk configuration, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="f3427-212">Дополнительные сведения см в статье <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</A> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="f3427-212">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f3427-213">См. также</span><span class="sxs-lookup"><span data-stu-id="f3427-213">See Also</span></span>


[<span data-ttu-id="f3427-214">Настройка магистрали с обходом сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3427-214">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[<span data-ttu-id="f3427-215">Определение правил преобразования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f3427-215">Defining translation rules in Lync Server 2013</span></span>](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

