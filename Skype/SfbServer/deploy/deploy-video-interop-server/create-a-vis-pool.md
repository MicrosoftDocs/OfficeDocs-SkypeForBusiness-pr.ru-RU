---
title: Создание пула VIS в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: Сводка. Создание пула серверов видеосвязи в Skype для бизнеса Server с помощью построщика топологий.
ms.openlocfilehash: 7c6f45b232151d99cbce169826c8110cf4a8d494
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802059"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a><span data-ttu-id="21e17-103">Создание пула VIS в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="21e17-103">Create a VIS pool in Skype for Business Server</span></span>
 
<span data-ttu-id="21e17-104">**Сводка:** Создание пула серверов видеосвязи в Skype для бизнеса Server с помощью построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="21e17-104">**Summary:** Create a Video Interop Server pool in Skype for Business Server using Topology Builder.</span></span>
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a><span data-ttu-id="21e17-105">Создание vis или пула VIS с помощью построитель топологий</span><span class="sxs-lookup"><span data-stu-id="21e17-105">Create a VIS or VIS pool using Topology Builder</span></span>

1. <span data-ttu-id="21e17-106">Откройте построитель топологий на сервере переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="21e17-106">Open Topology Builder on the front end server.</span></span> <span data-ttu-id="21e17-107">В левой области построитель топологий щелкните правой кнопкой мыши пулы серверов видеосвязи и выберите "Новый пул серверов  видеосвязи". </span><span class="sxs-lookup"><span data-stu-id="21e17-107">From the left pane of Topology Builder, right click on **Video Interop Server Pools** and choose **New Video Interop Server Pool**.</span></span> 
    
2. <span data-ttu-id="21e17-108">Откроется мастер создания нового пула серверов **видеосвязи.**</span><span class="sxs-lookup"><span data-stu-id="21e17-108">This will open up a **Create a new Video Interop Server Pool** wizard.</span></span> <span data-ttu-id="21e17-109">Удайте FQDN пула для нового сервера  видеосвязи и  выберите либо этот пул имеет один сервер, либо этот пул имеет несколько серверов в зависимости от вашего требования, а затем нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="21e17-109">Provide the Pool FQDN for the new Video Interop Server and select either **This pool has one server** or **This pool has multiple servers** based on your requirement, then press **Next**.</span></span>
    
    <span data-ttu-id="21e17-110">Если вы хотите развернуть пул серверов видеосвязи для обеспечения высокой доступности, выберите этот пул с **несколькими серверами.**</span><span class="sxs-lookup"><span data-stu-id="21e17-110">If you want to deploy a Video Interop Server pool to provide high availability, select **This pool has multiple servers**.</span></span> <span data-ttu-id="21e17-111">Помните о том, что:</span><span class="sxs-lookup"><span data-stu-id="21e17-111">Keep in mind with this option that:</span></span> 
    
    - <span data-ttu-id="21e17-112">Для поддержки пулов серверов видеосвязи необходимо развернуть балансировку нагрузки на DNS.</span><span class="sxs-lookup"><span data-stu-id="21e17-112">You must deploy DNS load balancing to support Video Interop Server pools.</span></span> 
    
   - <span data-ttu-id="21e17-113">На следующей странице  в поле "Определение компьютеров в этом элементе пула" введите в текстовое поле **FQDN** компьютера каждого сервера в пуле и нажмите кнопку **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="21e17-113">On the next page, for the **Define the computers in this pool** item, enter the **Computer FQDN** of each server in the pool into the text field, and then click **Add**.</span></span> <span data-ttu-id="21e17-114">Повторите это шаг, чтобы добавить в пул еще один сервер видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="21e17-114">Repeat this step to add another Video Interop Server to the pool.</span></span> <span data-ttu-id="21e17-115">После определения всех компьютеров в пуле нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="21e17-115">When you have defined all the computers in the pool, press **Next**.</span></span>
    
     <span data-ttu-id="21e17-116">Если требуется развернуть в пуле только один сервер видеосвязи, так как  высокая доступность не требуется, выберите этот пул с одним сервером и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="21e17-116">If you want to deploy only one Video Interop Server in the pool because you do not require high availability, then select **This pool has one server** and press **Next**.</span></span>
    
3. <span data-ttu-id="21e17-117">Выберите пул следующего прыжка или fe в выпадаемом списке и нажмите **кнопку "Далее".**</span><span class="sxs-lookup"><span data-stu-id="21e17-117">Select the next hop pool/FE from the drop-down list and press **Next**.</span></span>
    
4. <span data-ttu-id="21e17-118">Выберите пул для связи с VIS и нажмите кнопку **"Готово".**</span><span class="sxs-lookup"><span data-stu-id="21e17-118">Select an Edge Pool to associate with the VIS and press **Finish**.</span></span>
    
5. <span data-ttu-id="21e17-119">Установите порт TCP или TLS.</span><span class="sxs-lookup"><span data-stu-id="21e17-119">Set a TCP or TLS port.</span></span>
    
    <span data-ttu-id="21e17-120">Выберите только что добавленный сервер видеосвязи в левой области построитель топологий, щелкните его правой кнопкой мыши и выберите "Изменить **свойства".**</span><span class="sxs-lookup"><span data-stu-id="21e17-120">Select the newly added Video Interop Server from the left pane of Topology Builder, right click it and choose **Edit Properties**.</span></span> <span data-ttu-id="21e17-121">В включить или обновить TCP-порт или TLS по вашему требованию и выберите **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="21e17-121">Enable or Update the TCP or TLS port per your requirement and choose **OK**.</span></span> <span data-ttu-id="21e17-122">Хотя по умолчанию добавлен TLS, только TCP был полностью протестирован с помощью Cisco Unified Communications Manager (CallManager или CUCM).</span><span class="sxs-lookup"><span data-stu-id="21e17-122">Although by default TLS is added, only TCP has been fully tested with Cisco Unified Communications Manager (CallManager, or CUCM).</span></span>
    
6. <span data-ttu-id="21e17-123">Добавление видео шлюза.</span><span class="sxs-lookup"><span data-stu-id="21e17-123">Add a video gateway.</span></span> <span data-ttu-id="21e17-124">Для этого разберем общие компоненты, щелкните правой кнопкой **мыши** видео шлюзы и выберите **"Новый видео шлюз".**</span><span class="sxs-lookup"><span data-stu-id="21e17-124">To do this, Expand Shared Components, right click on **Video Gateways** and select **New Video Gateway**.</span></span>
    
7. <span data-ttu-id="21e17-125">Укадать FQDN или IP-адрес видео шлюза.</span><span class="sxs-lookup"><span data-stu-id="21e17-125">Provide the video gateway FQDN or IP address.</span></span> <span data-ttu-id="21e17-126">Видео шлюз может быть в поддомене или другом домене.</span><span class="sxs-lookup"><span data-stu-id="21e17-126">The video gateway could be in a subdomain or a different domain.</span></span> <span data-ttu-id="21e17-127">CUCM, используемый VTCs системы, выступает в качестве видео шлюза.</span><span class="sxs-lookup"><span data-stu-id="21e17-127">The CUCM used by your system's VTCs serves as a video gateway.</span></span>
    
8. <span data-ttu-id="21e17-128">При необходимости выберите IPv4 или IPv6.</span><span class="sxs-lookup"><span data-stu-id="21e17-128">Select either IPv4 or IPv6 as appropriate.</span></span> <span data-ttu-id="21e17-129">Можно использовать все настроенные IP-адреса или ограничить использование службы выбранными IP-адресами.</span><span class="sxs-lookup"><span data-stu-id="21e17-129">You can use all configured IP addresses or limit service usage to selected IP addresses.</span></span>
    
9. <span data-ttu-id="21e17-130">Выберите порт прослушивания видео шлюза.</span><span class="sxs-lookup"><span data-stu-id="21e17-130">Select the listening port of the video gateway.</span></span> <span data-ttu-id="21e17-131">Выберите транспортный протокол (TCP или TLS) и привяжем его к серверу видеосвязи, настроенного для видеомакторной магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="21e17-131">Select the Transport protocol (TCP or TLS) and associate it with a Video Interop Server which is set up for a video SIP trunk.</span></span> <span data-ttu-id="21e17-132">Транспортный протокол для видео шлюза должен соответствовать транспортному протоколу, настроенного для VIS.</span><span class="sxs-lookup"><span data-stu-id="21e17-132">The Transport Protocol for the video gateway should match the Transport Protocol configured for the VIS.</span></span>
    
10. <span data-ttu-id="21e17-133">Соответствующая видеомаголь SIP добавляется после завершения вышеуказанного шага.</span><span class="sxs-lookup"><span data-stu-id="21e17-133">A corresponding SIP Video trunk is added after the above step is completed.</span></span> <span data-ttu-id="21e17-134">Щелкните правой кнопкой мыши видеомакторную магистраль SIP и выберите только что добавленную магистраль.</span><span class="sxs-lookup"><span data-stu-id="21e17-134">Right click on the SIP Video Trunk, and select the trunk that was just added.</span></span> <span data-ttu-id="21e17-135">Имя видеоМАПК, связанный сервер видеосвязи, транспортный протокол SIP и порт можно изменить.</span><span class="sxs-lookup"><span data-stu-id="21e17-135">The video SIP Trunk name, associated Video Interop Server, SIP Transport protocol and port can all be changed.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="21e17-136">Сервер видеосвязи поддерживает магистрали 1:N.</span><span class="sxs-lookup"><span data-stu-id="21e17-136">A Video Interop Server supports 1:N trunks.</span></span> <span data-ttu-id="21e17-137">Поэтому можно добавить несколько магистральных магистральных магистрали, связанных с одним сервером видеосвязи, где каждая магистраль завершается на другом видео шлюзе.</span><span class="sxs-lookup"><span data-stu-id="21e17-137">Hence multiple trunks can be added, which are associated with a single Video Interop Server, where each trunk terminates on a different Video Gateway.</span></span> <span data-ttu-id="21e17-138">The limitation is that a particular Video Gateway has one and only one trunk that can be defined to the Skype for Business Server deployment.</span><span class="sxs-lookup"><span data-stu-id="21e17-138">The limitation is that a particular Video Gateway has one and only one trunk that can be defined to the Skype for Business Server deployment.</span></span>
  
11. <span data-ttu-id="21e17-139">Опубликуйте документ топологии, как описано в документе "Создание и публикация [новой топологии" в Skype для бизнеса Server 2015.](../../deploy/install/create-and-publish-new-topology.md)</span><span class="sxs-lookup"><span data-stu-id="21e17-139">Publish the Topology Document as described in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="21e17-140">Для повышения устойчивости может потребоваться настройка второго сервера видеосвязи или пула VIS или резервного пула переднего сервера.</span><span class="sxs-lookup"><span data-stu-id="21e17-140">To improve resiliency, you may want to configure a second Video Interop Server or VIS pool, or a backup Front End pool.</span></span> <span data-ttu-id="21e17-141">Дополнительные [сведения см. в](../../plan-your-deployment/video-interop-server.md#resiliency) механизмах устойчивости.</span><span class="sxs-lookup"><span data-stu-id="21e17-141">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
<span data-ttu-id="21e17-142">Все задачи, выполняемые с помощью построитель топологий, должны быть завершены.</span><span class="sxs-lookup"><span data-stu-id="21e17-142">All tasks performed using Topology Builder should now be complete.</span></span> <span data-ttu-id="21e17-143">Переходите к установке программного обеспечения на новом сервере или серверах VIS.</span><span class="sxs-lookup"><span data-stu-id="21e17-143">Proceed to installing the software on the new VIS server or servers.</span></span>
## <a name="see-also"></a><span data-ttu-id="21e17-144">См. также</span><span class="sxs-lookup"><span data-stu-id="21e17-144">See also</span></span>

[<span data-ttu-id="21e17-145">Развертывание роли сервера VIS в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="21e17-145">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)

[<span data-ttu-id="21e17-146">Планирование сервера видеосвязи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="21e17-146">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  
[<span data-ttu-id="21e17-147">Создание и публикация новой топологии в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="21e17-147">Create and publish new topology in Skype for Business Server 2015</span></span>](../../deploy/install/create-and-publish-new-topology.md)
