---
title: Удаление связи с сервером архивирования
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Чтобы удалить сервер архивации, необходимо изменить или удалить зависимость от связанного пула переднего сервера, сервера переднего сервера, устройства для survivable Branch Appliance и сервера для связи в филиалах. Чтобы удалить зависимость, отредактируете свойства пула переднего сервера, сервера переднего сервера, устройства для survivable branch appliance и survivable Branch Server. После очистки зависимости и удаления сервера в построитель топологий вы будете уведомлены о том, что связанный объект хранения базы данных в построите топологии также будет удален.
ms.openlocfilehash: bba21dadc70f5c9f62fea5073ef5bf815c8b35a1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752141"
---
# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="e2814-105">Удаление связи с сервером архивирования</span><span class="sxs-lookup"><span data-stu-id="e2814-105">Remove the Archiving server association</span></span>

<span data-ttu-id="e2814-106">Чтобы удалить сервер архивации, необходимо изменить или удалить зависимость от связанного пула переднего сервера, сервера переднего сервера, устройства для survivable Branch Appliance и сервера для связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="e2814-106">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="e2814-107">Чтобы удалить зависимость, отредактируете свойства пула переднего сервера, сервера переднего сервера, устройства для survivable Branch Appliance и сервера survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="e2814-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="e2814-108">После очистки зависимости и удаления сервера в построитель топологий вы будете уведомлены о том, что связанный объект хранения базы данных в построите топологии также будет удален.</span><span class="sxs-lookup"><span data-stu-id="e2814-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="e2814-109">Удаление привязки сервера архивации</span><span class="sxs-lookup"><span data-stu-id="e2814-109">To remove the Archiving Server association</span></span>

1. <span data-ttu-id="e2814-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="e2814-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="e2814-111">Перейдите к устаревшему узлу установки.</span><span class="sxs-lookup"><span data-stu-id="e2814-111">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="e2814-112">В построителье топологий развявите пулы переднего сервера **Enterprise Edition,** серверы переднего сервера **Standard Edition** или сайты филиалов **в** зависимости от того, где определен сервер архива.</span><span class="sxs-lookup"><span data-stu-id="e2814-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Archiving Server is defined.</span></span>
    
4. <span data-ttu-id="e2814-113">Если у вас есть связанный сервер для survivable Branch Server, развяйте сайты филиалов, развяйте имя сайта филиала, а затем расширьйте устройства для **survivable Branch Appliances.**</span><span class="sxs-lookup"><span data-stu-id="e2814-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e2814-114">**Устройства для survivable Branch Appliance в** пользовательском интерфейсе применяются как к серверу для survivable Branch Server, так и к устройству для survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="e2814-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="e2814-115">Щелкните правой кнопкой мыши пул, сервер или устройство, связанное с сервером архива, и выберите "Изменить **свойства".**</span><span class="sxs-lookup"><span data-stu-id="e2814-115">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="e2814-116">В **окне "Изменение свойств"** в области **"Общие** связи" сйдите с этого сервера, а затем  >  нажмите кнопку "ОК".  </span><span class="sxs-lookup"><span data-stu-id="e2814-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="e2814-117">Повторите предыдущий шаг для любого другого пула, сервера или устройства, связанного с сервером архива, который необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="e2814-117">Repeat the previous step for any other pool, server, or device associated with the Archiving Server that you want to remove.</span></span>
    
8. <span data-ttu-id="e2814-118">Щелкните правой кнопкой мыши сервер архива и выберите **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="e2814-118">Right-click the Archiving Server, and then click **Delete**.</span></span>
    
9. <span data-ttu-id="e2814-119">В окне **удаления зависимых хранилищ** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e2814-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="e2814-120">Опубликуйте топологию, проверьте состояние репликации и при необходимости запустите мастер развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e2814-120">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

