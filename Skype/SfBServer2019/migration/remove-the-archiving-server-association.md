---
title: Удаление связи с сервером архивирования
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Для удаления сервера архивации необходимо изменить или снять зависимость на связанном пуле интерфейсов, сервере переднего плана, работающем устройстве филиала и бесперебойном сервере подразделения. Вы можете изменить свойства пула переднего плана, сервер переднего плана, бесперебойно работающее устройство филиалов и бесперебойный сервер филиала, чтобы удалить зависимость. После очистки зависимости и удаления сервера в построителе топологии вы будете уведомлены о том, что связанный объект хранилища базы данных в построителе топологии также будет удален.
ms.openlocfilehash: d6d7b7f53f9997b17893db079090e1837ce77f4d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244186"
---
# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="e910f-105">Удаление связи с сервером архивирования</span><span class="sxs-lookup"><span data-stu-id="e910f-105">Remove the Archiving server association</span></span>

<span data-ttu-id="e910f-106">Для удаления сервера архивации необходимо изменить или снять зависимость на связанном пуле интерфейсов, сервере переднего плана, работающем устройстве филиала, а также на сервере, который является бесперебойно.</span><span class="sxs-lookup"><span data-stu-id="e910f-106">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="e910f-107">Вы можете изменить свойства пула переднего плана, сервера переднего плана, устройства с бесперебойной ветвью и бесперебойной подсети, чтобы удалить зависимость.</span><span class="sxs-lookup"><span data-stu-id="e910f-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="e910f-108">После очистки зависимости и удаления сервера в построителе топологии вы будете уведомлены о том, что связанный объект хранилища базы данных в построителе топологии также будет удален.</span><span class="sxs-lookup"><span data-stu-id="e910f-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="e910f-109">Удаление сопоставления сервера архивации</span><span class="sxs-lookup"><span data-stu-id="e910f-109">To remove the Archiving Server association</span></span>

1. <span data-ttu-id="e910f-110">На сервере клиентского доступа Skype для бизнеса Server 2019 откройте конфигуратор топологии.</span><span class="sxs-lookup"><span data-stu-id="e910f-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="e910f-111">Перейдите к устаревшему узлу установки.</span><span class="sxs-lookup"><span data-stu-id="e910f-111">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="e910f-112">В построителе топологии разворачивание **пулов переднего плана Enterprise Edition**, **серверов переднего плана Standard Edition**и **сайтов филиалов**в зависимости от того, где определен сервер архивации.</span><span class="sxs-lookup"><span data-stu-id="e910f-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Archiving Server is defined.</span></span>
    
4. <span data-ttu-id="e910f-113">Если у вас есть связанный сервер филиалов, разверните **сайты филиалов**, разверните имя сайта филиала, а затем разверните **бесперебойно управляемые устройства филиалов**.</span><span class="sxs-lookup"><span data-stu-id="e910f-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e910f-114">**Бесперебойно управляемые устройства ветвления** в пользовательском интерфейсе применяются как к бесперебойному, так и к бесперебойному устройству филиала.</span><span class="sxs-lookup"><span data-stu-id="e910f-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="e910f-115">Щелкните правой кнопкой мыши пул, сервер или устройство, связанные с сервером архивации, а затем выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="e910f-115">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="e910f-116">В диалоговом окне **изменение свойств**в разделе **Общие** > **ассоциации**снимите флажок **сопоставить сервер архивации** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e910f-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="e910f-117">Повторите предыдущий шаг для любого другого пула, сервера или устройства, связанного с сервером архивации, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="e910f-117">Repeat the previous step for any other pool, server, or device associated with the Archiving Server that you want to remove.</span></span>
    
8. <span data-ttu-id="e910f-118">Щелкните сервер архивации правой кнопкой мыши и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="e910f-118">Right-click the Archiving Server, and then click **Delete**.</span></span>
    
9. <span data-ttu-id="e910f-119">На вкладке **удалить зависимые магазины**нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e910f-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="e910f-120">Опубликуйте топологию, проверьте состояние репликации, а затем запустите мастер развертывания Skype для бизнеса Server, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="e910f-120">Publish the topology, check replication status, and then run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

