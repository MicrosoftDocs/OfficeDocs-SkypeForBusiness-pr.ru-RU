---
title: Создание пула VIS в Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Сводка: Создание пула серверов взаимодействия видео в Скайп для Business Server, с помощью построителя топологий.'
ms.openlocfilehash: f284163bc52f4e62c3ec5b1c7966f3c663ee09f7
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20978818"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a><span data-ttu-id="006ef-103">Создание пула VIS в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="006ef-103">Create a VIS pool in Skype for Business Server</span></span>
 
<span data-ttu-id="006ef-104">**Сводка:** Создание пула серверов взаимодействия видео в Скайп для Business Server, с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="006ef-104">**Summary:** Create a Video Interop Server pool in Skype for Business Server using Topology Builder.</span></span>
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a><span data-ttu-id="006ef-105">Создание сервера видеовзаимодействия или пула серверов видеовзаимодействия с помощью построителя топологии</span><span class="sxs-lookup"><span data-stu-id="006ef-105">Create a VIS or VIS pool using Topology Builder</span></span>

1. <span data-ttu-id="006ef-106">Откройте построитель топологии на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="006ef-106">Open Topology Builder on the front end server.</span></span> <span data-ttu-id="006ef-107">В левой области построителя топологий щелкните правой кнопкой мыши **Пулы серверов взаимодействия видео** и выберите **Новый пул серверов взаимодействия видео**.</span><span class="sxs-lookup"><span data-stu-id="006ef-107">From the left pane of Topology Builder, right click on **Video Interop Server Pools** and choose **New Video Interop Server Pool**.</span></span> 
    
2. <span data-ttu-id="006ef-108">Откроется мастер **Создание нового пула сервера видеовзаимодействия**.</span><span class="sxs-lookup"><span data-stu-id="006ef-108">This will open up a **Create a new Video Interop Server Pool** wizard.</span></span> <span data-ttu-id="006ef-109">Укажите полное доменное имя пула для нового сервера взаимодействия видео и выберите **Этот пул имеет один сервер** или **пул с несколькими серверами** , на основании требований, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="006ef-109">Provide the Pool FQDN for the new Video Interop Server and select either **This pool has one server** or **This pool has multiple servers** based on your requirement, then press **Next**.</span></span>
    
    <span data-ttu-id="006ef-110">Если вы хотите развернуть пулу серверов взаимодействия видео для обеспечения высокой доступности, выберите **Этот пул с несколькими серверами**.</span><span class="sxs-lookup"><span data-stu-id="006ef-110">If you want to deploy a Video Interop Server pool to provide high availability, select **This pool has multiple servers**.</span></span> <span data-ttu-id="006ef-111">Помните, что при выборе этого параметра:</span><span class="sxs-lookup"><span data-stu-id="006ef-111">Keep in mind with this option that:</span></span> 
    
    - <span data-ttu-id="006ef-112">Необходимо развернуть балансировку нагрузки DNS для поддержки пулы серверов взаимодействия видео.</span><span class="sxs-lookup"><span data-stu-id="006ef-112">You must deploy DNS load balancing to support Video Interop Server pools.</span></span> 
    
   - <span data-ttu-id="006ef-113">На следующей странице в пункте **Указание компьютеров в пуле** введите в текстовое поле **полное доменное имя компьютера** для каждого сервера и затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="006ef-113">On the next page, for the **Define the computers in this pool** item, enter the **Computer FQDN** of each server in the pool into the text field, and then click **Add**.</span></span> <span data-ttu-id="006ef-114">Повторите этот шаг, чтобы добавить еще один сервер взаимодействия видео в пул.</span><span class="sxs-lookup"><span data-stu-id="006ef-114">Repeat this step to add another Video Interop Server to the pool.</span></span> <span data-ttu-id="006ef-115">Определив все компьютеры в пуле, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="006ef-115">When you have defined all the computers in the pool, press **Next**.</span></span>
    
    <span data-ttu-id="006ef-116">Если вы хотите развернуть только один сервер взаимодействия видео в пуле, так как не требуется высокий уровень доступности, выберите **Этот пул состоит из одного сервера** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="006ef-116">If you want to deploy only one Video Interop Server in the pool because you do not require high availability, then select **This pool has one server** and press **Next**.</span></span>
    
3. <span data-ttu-id="006ef-117">Выберите пул следующего перехода или сервер переднего плана из раскрывающегося списка и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="006ef-117">Select the next hop pool/FE from the drop-down list and press **Next**.</span></span>
    
4. <span data-ttu-id="006ef-118">Выберите пограничный пул для связи с сервером видеовзаимодействия и нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="006ef-118">Select an Edge Pool to associate with the VIS and press **Finish**.</span></span>
    
5. <span data-ttu-id="006ef-119">Выберите порт TCP или TLS.</span><span class="sxs-lookup"><span data-stu-id="006ef-119">Set a TCP or TLS port.</span></span>
    
    <span data-ttu-id="006ef-120">Выберите только что добавленный сервер взаимодействия видео в левой панели построителя топологий, щелкните его правой кнопкой мыши и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="006ef-120">Select the newly added Video Interop Server from the left pane of Topology Builder, right click it and choose **Edit Properties**.</span></span> <span data-ttu-id="006ef-121">В зависимости от ваших требований включите или отключите порт TCP или TLS и нажмите **OK**.</span><span class="sxs-lookup"><span data-stu-id="006ef-121">Enable or Update the TCP or TLS port per your requirement and choose **OK**.</span></span> <span data-ttu-id="006ef-122">Несмотря на то, что по умолчанию добавляется TLS, только TCP полностью протестировано Cisco объединенных коммуникаций диспетчером (CallManager или CUCM).</span><span class="sxs-lookup"><span data-stu-id="006ef-122">Although by default TLS is added, only TCP has been fully tested with Cisco Unified Communications Manager (CallManager, or CUCM).</span></span>
    
6. <span data-ttu-id="006ef-p106">Добавьте видеошлюз. Для этого разверните узел общих компонентов, щелкните правой кнопкой мыши элемент **Видеошлюзы** и выберите **Новый видеошлюз**.</span><span class="sxs-lookup"><span data-stu-id="006ef-p106">Add a video gateway. To do this, Expand Shared Components, right click on **Video Gateways** and select **New Video Gateway**.</span></span>
    
7. <span data-ttu-id="006ef-p107">Укажите полное доменное имя или IP-адрес видеошлюза. Видеошлюз может находиться в дочернем или в другом домене. CUCM, который используется вашими системами видеоконференций (VTC), выступает в роли видеошлюза.</span><span class="sxs-lookup"><span data-stu-id="006ef-p107">Provide the video gateway FQDN or IP address. The video gateway could be in a subdomain or a different domain. The CUCM used by your system's VTCs serves as a video gateway.</span></span>
    
8. <span data-ttu-id="006ef-p108">Выберите протокол IPv4 или IPv6 в зависимости от требований. Можно выбрать все настроенные IP-адреса или ограничить выбранными IP-адресами использование со стороны службы.</span><span class="sxs-lookup"><span data-stu-id="006ef-p108">Select either IPv4 or IPv6 as appropriate. You can use all configured IP addresses or limit service usage to selected IP addresses.</span></span>
    
9. <span data-ttu-id="006ef-130">Выберите порт прослушивания видеошлюза.</span><span class="sxs-lookup"><span data-stu-id="006ef-130">Select the listening port of the video gateway.</span></span> <span data-ttu-id="006ef-131">Выберите транспортный протокол (TCP или TLS) и связать его с видео взаимодействия сервера, который настроен для видео канала SIP.</span><span class="sxs-lookup"><span data-stu-id="006ef-131">Select the Transport protocol (TCP or TLS) and associate it with a Video Interop Server which is set up for a video SIP trunk.</span></span> <span data-ttu-id="006ef-132">Транспортный протокол для видеошлюза должен соответствовать транспортному протоколу, который настроен для сервера VIS.</span><span class="sxs-lookup"><span data-stu-id="006ef-132">The Transport Protocol for the video gateway should match the Transport Protocol configured for the VIS.</span></span>
    
10. <span data-ttu-id="006ef-133">Видеомагистраль SIP будет добавлена после выполнения указанного выше действия.</span><span class="sxs-lookup"><span data-stu-id="006ef-133">A corresponding SIP Video trunk is added after the above step is completed.</span></span> <span data-ttu-id="006ef-134">Щелкните правой кнопкой мыши видеомагистраль SIP и выберите добавленную вами магистраль.</span><span class="sxs-lookup"><span data-stu-id="006ef-134">Right click on the SIP Video Trunk, and select the trunk that was just added.</span></span> <span data-ttu-id="006ef-135">Видео имя SIP-магистрали, связанного сервера видео взаимодействия, SIP-транспортный протокол и порт можно изменить.</span><span class="sxs-lookup"><span data-stu-id="006ef-135">The video SIP Trunk name, associated Video Interop Server, SIP Transport protocol and port can all be changed.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="006ef-136">Сервер взаимодействия видео поддерживает магистральных линий связи 1: n.</span><span class="sxs-lookup"><span data-stu-id="006ef-136">A Video Interop Server supports 1:N trunks.</span></span> <span data-ttu-id="006ef-137">Поэтому несколько магистралей можно добавлять, которой связаны с одним сервером взаимодействия видео, где каждой магистрали завершает на разных шлюза видео.</span><span class="sxs-lookup"><span data-stu-id="006ef-137">Hence multiple trunks can be added, which are associated with a single Video Interop Server, where each trunk terminates on a different Video Gateway.</span></span> <span data-ttu-id="006ef-138">Ограничение — конкретного шлюза видео на наличие одного и только одного линии связи, который может быть определен для Скайп для развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="006ef-138">The limitation is that a particular Video Gateway has one and only one trunk that can be defined to the Skype for Business Server deployment.</span></span>
  
11. <span data-ttu-id="006ef-139">Публикация в документе топологии, как описано в статье [создания и публикации новой топологии в Скайп для Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="006ef-139">Publish the Topology Document as described in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="006ef-140">Чтобы повысить устойчивость, может потребоваться настроить второй сервер взаимодействия видео или VIS пула или в резервный пул переднего плана.</span><span class="sxs-lookup"><span data-stu-id="006ef-140">To improve resiliency, you may want to configure a second Video Interop Server or VIS pool, or a backup Front End pool.</span></span> <span data-ttu-id="006ef-141">Дополнительные сведения см. в разделе [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency).</span><span class="sxs-lookup"><span data-stu-id="006ef-141">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
<span data-ttu-id="006ef-p113">На этом этапе все задачи, выполняемые с помощью построителя топологии, завершены. Перейдите к установке программного обеспечения на новом сервере или серверах VIS.</span><span class="sxs-lookup"><span data-stu-id="006ef-p113">All tasks performed using Topology Builder should now be complete. Proceed to installing the software on the new VIS server or servers.</span></span>
## <a name="see-also"></a><span data-ttu-id="006ef-144">См. также</span><span class="sxs-lookup"><span data-stu-id="006ef-144">See also</span></span>

[<span data-ttu-id="006ef-145">Развертывание VIS серверной роли в Скайп for Business Server</span><span class="sxs-lookup"><span data-stu-id="006ef-145">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)

[<span data-ttu-id="006ef-146">Планирование для видео взаимодействия сервера в Скайп Business Server</span><span class="sxs-lookup"><span data-stu-id="006ef-146">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  
[<span data-ttu-id="006ef-147">Создание и публикация новой топологии в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="006ef-147">Create and publish new topology in Skype for Business Server 2015</span></span>](../../deploy/install/create-and-publish-new-topology.md)