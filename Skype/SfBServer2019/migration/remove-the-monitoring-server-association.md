---
title: Удаление связи с сервером мониторинга
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
description: Чтобы удалить сервер мониторинга, необходимо изменить или удалить зависимость от связанного пула переднего сервера, сервера переднего сервера, устройства для survivable Branch Appliance и сервера для связи в филиалах. Чтобы удалить зависимость, отредактируете свойства пула переднего сервера, сервера переднего сервера, устройства для survivable branch appliance и survivable Branch Server. После очистки зависимости и удаления сервера в построитель топологий вы будете уведомлены о том, что связанный объект хранения базы данных в построите топологии также будет удален.
ms.openlocfilehash: dafbeb88773330164a5daf2144988d1afb2776a8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753421"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="ad286-105">Удаление связи с сервером мониторинга</span><span class="sxs-lookup"><span data-stu-id="ad286-105">Remove the Monitoring server association</span></span>

<span data-ttu-id="ad286-106">Чтобы удалить сервер мониторинга, необходимо изменить или удалить зависимость от связанного пула переднего сервера, сервера переднего сервера, устройства для связи в филиалах и сервера для связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="ad286-106">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="ad286-107">Чтобы удалить зависимость, отредактируете свойства пула переднего сервера, сервера переднего сервера, устройства для survivable Branch Appliance и сервера survivable Branch Server.</span><span class="sxs-lookup"><span data-stu-id="ad286-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="ad286-108">После очистки зависимости и удаления сервера в построитель топологий вы будете уведомлены о том, что связанный объект хранения базы данных в построите топологии также будет удален.</span><span class="sxs-lookup"><span data-stu-id="ad286-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="ad286-109">Удаление связи с сервером мониторинга</span><span class="sxs-lookup"><span data-stu-id="ad286-109">To remove the Monitoring Server association</span></span>

1. <span data-ttu-id="ad286-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="ad286-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="ad286-111">Перейдите к устаревшему узлу установок.</span><span class="sxs-lookup"><span data-stu-id="ad286-111">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="ad286-112">В построитель топологий разоберем пулы переднего сервера **Enterprise Edition,** серверы переднего сервера **Standard Edition** или сайты филиалов **в** зависимости от того, где определен сервер мониторинга.</span><span class="sxs-lookup"><span data-stu-id="ad286-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Monitoring Server is defined.</span></span>
    
4. <span data-ttu-id="ad286-113">Если с сервером для связи в филиалах связаны, развяйте сайты филиалов, развяйте имя сайта филиала, а затем расширьйте устройства для **survivable Branch Appliances.**</span><span class="sxs-lookup"><span data-stu-id="ad286-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ad286-114">**Устройства для survivable Branch Appliance в** пользовательском интерфейсе применяются как к серверу для survivable Branch Server, так и к устройству для survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="ad286-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="ad286-115">Щелкните правой кнопкой мыши пул, сервер или устройство, связанное с сервером мониторинга, и выберите "Изменить **свойства".**</span><span class="sxs-lookup"><span data-stu-id="ad286-115">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="ad286-116">В **окне "Изменение свойств"** в области **"Общие** связи" сйдите с этого сервера мониторинга и нажмите  >  кнопку  "ОК". </span><span class="sxs-lookup"><span data-stu-id="ad286-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="ad286-117">Повторите предыдущий шаг для любого другого пула, сервера или устройства, связанного с сервером мониторинга.</span><span class="sxs-lookup"><span data-stu-id="ad286-117">Repeat the previous step for any other pool, server, or device associated with the Monitoring Server.</span></span>
    
8. <span data-ttu-id="ad286-118">Щелкните правой кнопкой мыши сервер мониторинга и выберите **"Удалить".**</span><span class="sxs-lookup"><span data-stu-id="ad286-118">Right-click the Monitoring Server, and then click **Delete**.</span></span> 
    
9. <span data-ttu-id="ad286-119">В окне **удаления зависимых хранилищ** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ad286-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="ad286-120">Опубликуйте топологию, проверьте состояние репликации и при необходимости запустите мастер развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ad286-120">Publish the topology, check replication status, and run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

