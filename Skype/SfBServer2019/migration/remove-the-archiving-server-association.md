---
title: Удаление ассоциации сервера архивирования
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Чтобы удалить сервер архивации, необходимо изменить или снимите зависимость на связанный с ним пул переднего плана, сервер переднего плана, для обеспечения связи в филиалах и устройства для обеспечения связи в филиалах. Изменение свойств пула переднего плана сервера переднего плана, для обеспечения связи в филиалах и устройства для обеспечения связи в филиалах, удалить зависимость. После того как очистить зависимости и удаление сервера в построителе топологий, будут уведомлены связанного объекта базы данных хранилища в построителе топологий также будут удалены.
ms.openlocfilehash: 7438145f5822de8f95e881f114983fdb9351d4b9
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028875"
---
# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="2cef3-105">Удаление ассоциации сервера архивирования</span><span class="sxs-lookup"><span data-stu-id="2cef3-105">Remove the Archiving server association</span></span>

<span data-ttu-id="2cef3-106">Чтобы удалить сервер архивации, необходимо изменить или снимите зависимость от связанного переднего плана пула, сервер переднего плана, для обеспечения связи в филиалах и устройства для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="2cef3-106">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="2cef3-107">Изменение свойств пула переднего плана, сервер переднего плана, для обеспечения связи в филиалах и устройства для обеспечения связи в филиалах для удаления зависимости.</span><span class="sxs-lookup"><span data-stu-id="2cef3-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="2cef3-108">После того как очистить зависимости и удаление сервера в построителе топологий будут уведомлены связанного объекта базы данных хранилища в построителе топологий также будут удалены.</span><span class="sxs-lookup"><span data-stu-id="2cef3-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="2cef3-109">Удаление привязки сервера архивации</span><span class="sxs-lookup"><span data-stu-id="2cef3-109">To remove the Archiving Server association</span></span>

1. <span data-ttu-id="2cef3-110">На Скайп для сервера переднего плана Business Server 2019 откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="2cef3-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="2cef3-111">Перейдите к узлу установки прежних версий.</span><span class="sxs-lookup"><span data-stu-id="2cef3-111">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="2cef3-112">В построителе топологий разверните **Пулы переднего плана Enterprise Edition**, **Стандартный выпуск сервера переднего плана**или **сайтов филиалов**, в зависимости от того, где определяется сервера архивирование.</span><span class="sxs-lookup"><span data-stu-id="2cef3-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Archiving Server is defined.</span></span>
    
4. <span data-ttu-id="2cef3-113">Если у вас есть связанного сервера для обеспечения связи в филиалах, разверните узел **сайты филиалов**, разверните имя сайта филиала и затем разверните узел **Для обеспечения связи в филиалах**.</span><span class="sxs-lookup"><span data-stu-id="2cef3-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2cef3-114">**Для обеспечения связи в филиалах** в интерфейсе пользователя применяется для обеспечения связи в филиалах и устройства для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="2cef3-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="2cef3-115">Щелкните правой кнопкой мыши пул, сервер или устройство, связанное с сервера архивации и выберите команду **Изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="2cef3-115">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="2cef3-116">В окне **Изменение свойств**на вкладке **Общие** > **связей**, снимите флажок **Связать сервера архивации** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2cef3-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="2cef3-117">Повторите предыдущий шаг для пула, сервер или устройство, связанное с сервера архивирование, которую требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="2cef3-117">Repeat the previous step for any other pool, server, or device associated with the Archiving Server that you want to remove.</span></span>
    
8. <span data-ttu-id="2cef3-118">Щелкните правой кнопкой мыши сервер архивации и нажмите кнопку **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="2cef3-118">Right-click the Archiving Server, and then click **Delete**.</span></span>
    
9. <span data-ttu-id="2cef3-119">В **Окне удаления зависимых хранилищ**нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="2cef3-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="2cef3-120">Опубликуйте топологию, проверьте состояние репликации и запустите Скайп для мастера развертывания сервера Business при необходимости.</span><span class="sxs-lookup"><span data-stu-id="2cef3-120">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

