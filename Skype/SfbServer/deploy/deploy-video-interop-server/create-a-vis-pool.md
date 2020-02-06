---
title: Создание пула ВИС в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd8c4f7-057f-4360-8e3e-ec29b58f16a8
description: 'Сводка: создание пула серверов для видеосвязи в Skype для бизнеса Server с помощью Topology Builder.'
ms.openlocfilehash: 474752253312b58b87a3d01f445bd93eabdaf203
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798056"
---
# <a name="create-a-vis-pool-in-skype-for-business-server"></a><span data-ttu-id="92010-103">Создание пула ВИС в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="92010-103">Create a VIS pool in Skype for Business Server</span></span>
 
<span data-ttu-id="92010-104">**Сводка:** Создание пула серверов для видеосвязи в Skype для бизнеса Server с помощью Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="92010-104">**Summary:** Create a Video Interop Server pool in Skype for Business Server using Topology Builder.</span></span>
  
### <a name="create-a-vis-or-vis-pool-using-topology-builder"></a><span data-ttu-id="92010-105">Создание сервера видеовзаимодействия или пула серверов видеовзаимодействия с помощью построителя топологии</span><span class="sxs-lookup"><span data-stu-id="92010-105">Create a VIS or VIS pool using Topology Builder</span></span>

1. <span data-ttu-id="92010-106">Откройте построитель топологии на сервере переднего плана.</span><span class="sxs-lookup"><span data-stu-id="92010-106">Open Topology Builder on the front end server.</span></span> <span data-ttu-id="92010-107">В левой области построителя топологии щелкните правой кнопкой мыши **Пулы серверов видеовзаимодействия** и выберите **создать пул серверов для видеовзаимодействия**.</span><span class="sxs-lookup"><span data-stu-id="92010-107">From the left pane of Topology Builder, right click on **Video Interop Server Pools** and choose **New Video Interop Server Pool**.</span></span> 
    
2. <span data-ttu-id="92010-108">Откроется мастер **Создание нового пула сервера видеовзаимодействия**.</span><span class="sxs-lookup"><span data-stu-id="92010-108">This will open up a **Create a new Video Interop Server Pool** wizard.</span></span> <span data-ttu-id="92010-109">Укажите полное доменное имя пула для нового сервера видеовзаимодействия и выберите для него **один сервер** или **этот пул содержит несколько серверов** в соответствии с требованиями и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="92010-109">Provide the Pool FQDN for the new Video Interop Server and select either **This pool has one server** or **This pool has multiple servers** based on your requirement, then press **Next**.</span></span>
    
    <span data-ttu-id="92010-110">Если вы хотите развернуть пул серверов видеовзаимодействия для обеспечения высокой доступности, выберите **этот пул с несколькими серверами**.</span><span class="sxs-lookup"><span data-stu-id="92010-110">If you want to deploy a Video Interop Server pool to provide high availability, select **This pool has multiple servers**.</span></span> <span data-ttu-id="92010-111">Помните, что при выборе этого параметра:</span><span class="sxs-lookup"><span data-stu-id="92010-111">Keep in mind with this option that:</span></span> 
    
    - <span data-ttu-id="92010-112">Для поддержки пулов серверов видеовзаимодействия необходимо развернуть балансировку нагрузки DNS.</span><span class="sxs-lookup"><span data-stu-id="92010-112">You must deploy DNS load balancing to support Video Interop Server pools.</span></span> 
    
   - <span data-ttu-id="92010-113">На следующей странице в пункте **Указание компьютеров в пуле** введите в текстовое поле **полное доменное имя компьютера** для каждого сервера и затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="92010-113">On the next page, for the **Define the computers in this pool** item, enter the **Computer FQDN** of each server in the pool into the text field, and then click **Add**.</span></span> <span data-ttu-id="92010-114">Повторите этот шаг, чтобы добавить еще один сервер видеоконференций в пул.</span><span class="sxs-lookup"><span data-stu-id="92010-114">Repeat this step to add another Video Interop Server to the pool.</span></span> <span data-ttu-id="92010-115">Определив все компьютеры в пуле, нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="92010-115">When you have defined all the computers in the pool, press **Next**.</span></span>
    
     <span data-ttu-id="92010-116">Если вы хотите развернуть только один сервер видеосвязи в пуле, так как вам не требуется высокая доступность, выберите для **этого пула один сервер** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="92010-116">If you want to deploy only one Video Interop Server in the pool because you do not require high availability, then select **This pool has one server** and press **Next**.</span></span>
    
3. <span data-ttu-id="92010-117">Выберите пул следующего перехода или сервер переднего плана из раскрывающегося списка и нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="92010-117">Select the next hop pool/FE from the drop-down list and press **Next**.</span></span>
    
4. <span data-ttu-id="92010-118">Выберите пограничный пул для связи с сервером видеовзаимодействия и нажмите **Готово**.</span><span class="sxs-lookup"><span data-stu-id="92010-118">Select an Edge Pool to associate with the VIS and press **Finish**.</span></span>
    
5. <span data-ttu-id="92010-119">Выберите порт TCP или TLS.</span><span class="sxs-lookup"><span data-stu-id="92010-119">Set a TCP or TLS port.</span></span>
    
    <span data-ttu-id="92010-120">Выберите недавно добавленный сервер видеовзаимодействия в левой области построителя топологии, щелкните его правой кнопкой мыши и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="92010-120">Select the newly added Video Interop Server from the left pane of Topology Builder, right click it and choose **Edit Properties**.</span></span> <span data-ttu-id="92010-121">В зависимости от ваших требований включите или отключите порт TCP или TLS и нажмите **OK**.</span><span class="sxs-lookup"><span data-stu-id="92010-121">Enable or Update the TCP or TLS port per your requirement and choose **OK**.</span></span> <span data-ttu-id="92010-122">Несмотря на то, что добавляется TLS по умолчанию, только протокол TCP был полностью протестирован с помощью диспетчера единой системы обмена сообщениями Cisco (Каллманажер или КУКМ).</span><span class="sxs-lookup"><span data-stu-id="92010-122">Although by default TLS is added, only TCP has been fully tested with Cisco Unified Communications Manager (CallManager, or CUCM).</span></span>
    
6. <span data-ttu-id="92010-p106">Добавьте видеошлюз. Для этого разверните узел общих компонентов, щелкните правой кнопкой мыши элемент **Видеошлюзы** и выберите **Новый видеошлюз**.</span><span class="sxs-lookup"><span data-stu-id="92010-p106">Add a video gateway. To do this, Expand Shared Components, right click on **Video Gateways** and select **New Video Gateway**.</span></span>
    
7. <span data-ttu-id="92010-p107">Укажите полное доменное имя или IP-адрес видеошлюза. Видеошлюз может находиться в дочернем или в другом домене. CUCM, который используется вашими системами видеоконференций (VTC), выступает в роли видеошлюза.</span><span class="sxs-lookup"><span data-stu-id="92010-p107">Provide the video gateway FQDN or IP address. The video gateway could be in a subdomain or a different domain. The CUCM used by your system's VTCs serves as a video gateway.</span></span>
    
8. <span data-ttu-id="92010-p108">Выберите протокол IPv4 или IPv6 в зависимости от требований. Можно выбрать все настроенные IP-адреса или ограничить выбранными IP-адресами использование со стороны службы.</span><span class="sxs-lookup"><span data-stu-id="92010-p108">Select either IPv4 or IPv6 as appropriate. You can use all configured IP addresses or limit service usage to selected IP addresses.</span></span>
    
9. <span data-ttu-id="92010-130">Выберите порт прослушивания видеошлюза.</span><span class="sxs-lookup"><span data-stu-id="92010-130">Select the listening port of the video gateway.</span></span> <span data-ttu-id="92010-131">Выберите транспортный протокол (TCP или TLS) и свяжите его с сервером видеосвязи, настроенным для канала видеосвязи по каналу SIP.</span><span class="sxs-lookup"><span data-stu-id="92010-131">Select the Transport protocol (TCP or TLS) and associate it with a Video Interop Server which is set up for a video SIP trunk.</span></span> <span data-ttu-id="92010-132">Транспортный протокол для видеошлюза должен соответствовать транспортному протоколу, который настроен для сервера VIS.</span><span class="sxs-lookup"><span data-stu-id="92010-132">The Transport Protocol for the video gateway should match the Transport Protocol configured for the VIS.</span></span>
    
10. <span data-ttu-id="92010-133">Видеомагистраль SIP будет добавлена после выполнения указанного выше действия.</span><span class="sxs-lookup"><span data-stu-id="92010-133">A corresponding SIP Video trunk is added after the above step is completed.</span></span> <span data-ttu-id="92010-134">Щелкните правой кнопкой мыши видеомагистраль SIP и выберите добавленную вами магистраль.</span><span class="sxs-lookup"><span data-stu-id="92010-134">Right click on the SIP Video Trunk, and select the trunk that was just added.</span></span> <span data-ttu-id="92010-135">Вы можете изменить имя канала видеосвязи, связанного сервера видеосвязи, транспортного протокола SIP и портового устройства.</span><span class="sxs-lookup"><span data-stu-id="92010-135">The video SIP Trunk name, associated Video Interop Server, SIP Transport protocol and port can all be changed.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="92010-136">Сервер видеосвязи поддерживает магистральные каналы 1: N.</span><span class="sxs-lookup"><span data-stu-id="92010-136">A Video Interop Server supports 1:N trunks.</span></span> <span data-ttu-id="92010-137">Таким образом, можно добавить несколько каналов связи, которые связаны с одним сервером видеосвязи, где каждый канал завершает работу на другом видеошлюзе.</span><span class="sxs-lookup"><span data-stu-id="92010-137">Hence multiple trunks can be added, which are associated with a single Video Interop Server, where each trunk terminates on a different Video Gateway.</span></span> <span data-ttu-id="92010-138">Ограничение заключается в том, что конкретный шлюз имеет одну и только одну магистральную плату, которая может быть определена для развертывания в среде Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="92010-138">The limitation is that a particular Video Gateway has one and only one trunk that can be defined to the Skype for Business Server deployment.</span></span>
  
11. <span data-ttu-id="92010-139">Опубликуйте документ с топологией так, как описано в разделе [Создание и публикация новой топологии в Skype для бизнеса Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span><span class="sxs-lookup"><span data-stu-id="92010-139">Publish the Topology Document as described in [Create and publish new topology in Skype for Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="92010-140">Для улучшения устойчивости может потребоваться настроить второй сервер видеоконференций или пул ВИС или пул переднего плана для резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="92010-140">To improve resiliency, you may want to configure a second Video Interop Server or VIS pool, or a backup Front End pool.</span></span> <span data-ttu-id="92010-141">Дополнительные сведения см. в разделе [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency).</span><span class="sxs-lookup"><span data-stu-id="92010-141">See [Resiliency mechanisms](../../plan-your-deployment/video-interop-server.md#resiliency) for more information.</span></span>
  
<span data-ttu-id="92010-142">На этом этапе все задачи, выполняемые с помощью построителя топологии, завершены.</span><span class="sxs-lookup"><span data-stu-id="92010-142">All tasks performed using Topology Builder should now be complete.</span></span> <span data-ttu-id="92010-143">Перейдите к установке программного обеспечения на новом сервере или серверах VIS.</span><span class="sxs-lookup"><span data-stu-id="92010-143">Proceed to installing the software on the new VIS server or servers.</span></span>
## <a name="see-also"></a><span data-ttu-id="92010-144">См. также</span><span class="sxs-lookup"><span data-stu-id="92010-144">See also</span></span>

[<span data-ttu-id="92010-145">Развертывание роли сервера ВИС в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="92010-145">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)

[<span data-ttu-id="92010-146">Планирование сервера видеосвязи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="92010-146">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  
[<span data-ttu-id="92010-147">Создание и публикация новой топологии в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="92010-147">Create and publish new topology in Skype for Business Server 2015</span></span>](../../deploy/install/create-and-publish-new-topology.md)
