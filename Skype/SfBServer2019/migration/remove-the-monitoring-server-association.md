---
title: Удаление связи с сервером мониторинга
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Чтобы удалить сервер мониторинга, необходимо изменить или снимите зависимость на связанный с ним пул переднего плана, сервер переднего плана, для обеспечения связи в филиалах и устройства для обеспечения связи в филиалах. Изменение свойств пула переднего плана сервера переднего плана, для обеспечения связи в филиалах и устройства для обеспечения связи в филиалах, удалить зависимость. После того как очистить зависимости и удаление сервера в построителе топологий будут уведомлены связанного объекта базы данных хранилища в построителе топологий также будут удалены.
ms.openlocfilehash: 854e95969d08d14d626bb374073091ae4ae39630
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892704"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="54673-105">Удаление связи с сервером мониторинга</span><span class="sxs-lookup"><span data-stu-id="54673-105">Remove the Monitoring server association</span></span>

<span data-ttu-id="54673-106">Чтобы удалить сервер мониторинга, необходимо изменить или снимите зависимость от связанного переднего плана пула, сервер переднего плана, для обеспечения связи в филиалах и устройства для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="54673-106">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="54673-107">Изменение свойств пула переднего плана, сервер переднего плана, для обеспечения связи в филиалах и устройства для обеспечения связи в филиалах для удаления зависимости.</span><span class="sxs-lookup"><span data-stu-id="54673-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="54673-108">После того как очистить зависимости и удаление сервера в построителе топологий будут уведомлены связанного объекта базы данных хранилища в построителе топологий также будут удалены.</span><span class="sxs-lookup"><span data-stu-id="54673-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="54673-109">Для удаления связи с сервером мониторинга</span><span class="sxs-lookup"><span data-stu-id="54673-109">To remove the Monitoring Server association</span></span>

1. <span data-ttu-id="54673-110">На Скайп для сервера переднего плана Business Server 2019 откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="54673-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="54673-111">Перейдите к узлу устанавливает прежних версий.</span><span class="sxs-lookup"><span data-stu-id="54673-111">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="54673-112">В построителе топологий разверните **Пулы переднего плана Enterprise Edition**, **Стандартный выпуск сервера переднего плана**или **сайтов филиалов**, в зависимости от того, где определяется сервера мониторинга.</span><span class="sxs-lookup"><span data-stu-id="54673-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Monitoring Server is defined.</span></span>
    
4. <span data-ttu-id="54673-113">Если у вас есть связанного сервера для обеспечения связи в филиалах, разверните узел **сайты филиалов**, разверните имя сайта филиала и затем разверните узел **Для обеспечения связи в филиалах**.</span><span class="sxs-lookup"><span data-stu-id="54673-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="54673-114">**Для обеспечения связи в филиалах** в интерфейсе пользователя применяется для обеспечения связи в филиалах и устройства для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="54673-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="54673-115">Щелкните правой кнопкой мыши пул, сервер или устройство, связанное с сервера мониторинга и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="54673-115">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="54673-116">В окне **Изменение свойств**на вкладке **Общие** > **связей**, снимите флажок **Связать сервер мониторинга** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="54673-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="54673-117">Повторите предыдущий шаг для пула, сервер или устройство, связанное с сервером мониторинга.</span><span class="sxs-lookup"><span data-stu-id="54673-117">Repeat the previous step for any other pool, server, or device associated with the Monitoring Server.</span></span>
    
8. <span data-ttu-id="54673-118">Щелкните правой кнопкой мыши сервер мониторинга и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="54673-118">Right-click the Monitoring Server, and then click **Delete**.</span></span> 
    
9. <span data-ttu-id="54673-119">В **Окне удаления зависимых хранилищ**нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="54673-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="54673-120">Опубликуйте топологию, проверьте состояние репликации и при необходимости запустите мастер развертывания Business Server Скайп.</span><span class="sxs-lookup"><span data-stu-id="54673-120">Publish the topology, check replication status, and run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

