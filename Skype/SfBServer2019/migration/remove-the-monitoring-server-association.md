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
description: Для удаления сервера мониторинга необходимо изменить или снять зависимость от связанного пула переднего плана, сервера переднего плана, устройства для обеспечения связи в филиалах и сервера для обеспечения связи в филиалах. Вы изменяете свойства пула переднего плана, сервера переднего плана, устройства для обеспечения связи в филиалах и сервера для обеспечения связи в филиалах, чтобы удалить зависимость. После очистки зависимости и удаления сервера в построителе топологий будет выведено уведомление о том, что связанный объект хранилища базы данных в построителе топологий также будет удален.
ms.openlocfilehash: dafbeb88773330164a5daf2144988d1afb2776a8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753421"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="49b84-105">Удаление связи с сервером мониторинга</span><span class="sxs-lookup"><span data-stu-id="49b84-105">Remove the Monitoring server association</span></span>

<span data-ttu-id="49b84-106">Для удаления сервера мониторинга необходимо изменить или снять зависимость от связанного пула переднего плана, сервера переднего плана, устройства для обеспечения связи в филиалах и сервера для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="49b84-106">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="49b84-107">Вы изменяете свойства пула переднего плана, сервера переднего плана, устройства для обеспечения связи в филиалах и сервера для обеспечения связи в филиалах, чтобы удалить зависимость.</span><span class="sxs-lookup"><span data-stu-id="49b84-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="49b84-108">После очистки зависимости и удаления сервера в построителе топологий будет выведено уведомление о том, что связанный объект хранилища базы данных в построителе топологий также будет удален.</span><span class="sxs-lookup"><span data-stu-id="49b84-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="49b84-109">Удаление связи с сервером мониторинга</span><span class="sxs-lookup"><span data-stu-id="49b84-109">To remove the Monitoring Server association</span></span>

1. <span data-ttu-id="49b84-110">На сервере переднего плана Skype для бизнеса Server 2019 откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="49b84-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="49b84-111">Перейдите к узлу установки прежних версий.</span><span class="sxs-lookup"><span data-stu-id="49b84-111">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="49b84-112">В построителе топологий разверните **Пулы переднего плана Enterprise Edition**, **серверы переднего плана Standard Edition**или **сайты филиалов**в зависимости от того, где определен сервер мониторинга.</span><span class="sxs-lookup"><span data-stu-id="49b84-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Monitoring Server is defined.</span></span>
    
4. <span data-ttu-id="49b84-113">Если имеется связанный сервер филиалов, разверните **сайты филиалов**, разверните имя сайта филиала, а затем разверните узел устройства для обеспечения связи в **филиалах**.</span><span class="sxs-lookup"><span data-stu-id="49b84-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="49b84-114">Устройства для обеспечения связи в **филиалах** в пользовательском интерфейсе применяются как к серверу обеспечения связи в филиалах, так и к устройству для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="49b84-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="49b84-115">Щелкните правой кнопкой мыши пул, сервер или устройство, связанное с сервером мониторинга, и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="49b84-115">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="49b84-116">В диалоговом окне **изменение свойств**в разделе **Общие**  >  **связи**снимите флажок **сопоставить сервер мониторинга** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="49b84-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="49b84-117">Повторите предыдущий шаг для любого другого пула, сервера или устройства, связанного с сервером мониторинга.</span><span class="sxs-lookup"><span data-stu-id="49b84-117">Repeat the previous step for any other pool, server, or device associated with the Monitoring Server.</span></span>
    
8. <span data-ttu-id="49b84-118">Щелкните сервер мониторинга правой кнопкой мыши и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="49b84-118">Right-click the Monitoring Server, and then click **Delete**.</span></span> 
    
9. <span data-ttu-id="49b84-119">В окне **удаления зависимых хранилищ** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="49b84-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="49b84-120">Опубликуйте топологию, проверьте состояние репликации и при необходимости запустите мастер развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="49b84-120">Publish the topology, check replication status, and run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

