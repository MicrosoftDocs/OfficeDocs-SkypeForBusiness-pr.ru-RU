---
title: Удаление связи с сервером мониторинга
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Для удаления сервера мониторинга необходимо изменить или снять зависимость на связанном пуле интерфейсов, сервере переднего плана, работающем устройстве филиала и бесперебойном сервере подразделения. Вы можете изменить свойства пула переднего плана, сервер переднего плана, бесперебойно работающее устройство филиалов и бесперебойный сервер филиала, чтобы удалить зависимость. После очистки зависимости и удаления сервера в построителе топологии вы будете уведомлены о том, что связанный объект хранилища базы данных в построителе топологии также будет удален.
ms.openlocfilehash: 366bb67815df99542b893e9ced79c1fc1f0e3e9f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301099"
---
# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="bde78-105">Удаление связи с сервером мониторинга</span><span class="sxs-lookup"><span data-stu-id="bde78-105">Remove the Monitoring server association</span></span>

<span data-ttu-id="bde78-106">Для удаления сервера мониторинга необходимо изменить или снять зависимость на связанном пуле интерфейсов, сервере переднего плана, работающем устройстве филиала и бесперебойном сервере филиала.</span><span class="sxs-lookup"><span data-stu-id="bde78-106">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server.</span></span> <span data-ttu-id="bde78-107">Вы можете изменить свойства пула переднего плана, сервера переднего плана, устройства с бесперебойной ветвью и бесперебойной подсети, чтобы удалить зависимость.</span><span class="sxs-lookup"><span data-stu-id="bde78-107">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance, and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="bde78-108">После очистки зависимости и удаления сервера в построителе топологии вы будете уведомлены о том, что связанный объект хранилища базы данных в построителе топологии также будет удален.</span><span class="sxs-lookup"><span data-stu-id="bde78-108">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>
  
### <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="bde78-109">Удаление сопоставления сервера мониторинга</span><span class="sxs-lookup"><span data-stu-id="bde78-109">To remove the Monitoring Server association</span></span>

1. <span data-ttu-id="bde78-110">На сервере клиентского доступа Skype для бизнеса Server 2019 откройте конфигуратор топологии.</span><span class="sxs-lookup"><span data-stu-id="bde78-110">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="bde78-111">Перейдите к узлу устаревшие установки.</span><span class="sxs-lookup"><span data-stu-id="bde78-111">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="bde78-112">В построителе топологии разворачивание **пулов переднего плана Enterprise Edition**, **серверов переднего плана Standard Edition**и **сайтов филиалов**в зависимости от того, где определен сервер мониторинга.</span><span class="sxs-lookup"><span data-stu-id="bde78-112">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, depending on where the Monitoring Server is defined.</span></span>
    
4. <span data-ttu-id="bde78-113">Если у вас есть связанный сервер филиалов, разверните **сайты филиалов**, разверните имя сайта филиала, а затем разверните **бесперебойно управляемые устройства филиалов**.</span><span class="sxs-lookup"><span data-stu-id="bde78-113">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bde78-114">**Бесперебойно управляемые устройства ветвления** в пользовательском интерфейсе применяются как к бесперебойному, так и к бесперебойному устройству филиала.</span><span class="sxs-lookup"><span data-stu-id="bde78-114">**Survivable Branch Appliances** in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span> 
  
5. <span data-ttu-id="bde78-115">Щелкните правой кнопкой мыши пул, сервер или устройство, связанные с сервером мониторинга, и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="bde78-115">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>
    
6. <span data-ttu-id="bde78-116">В диалоговом окне **изменение свойств**в разделе **Общие** > **ассоциации**снимите флажок **сопоставить сервер мониторинга** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bde78-116">In **Edit Properties**, under **General** > **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>
    
7. <span data-ttu-id="bde78-117">Повторите предыдущий шаг для любого другого пула, сервера или устройства, связанного с сервером мониторинга.</span><span class="sxs-lookup"><span data-stu-id="bde78-117">Repeat the previous step for any other pool, server, or device associated with the Monitoring Server.</span></span>
    
8. <span data-ttu-id="bde78-118">Щелкните сервер мониторинга правой кнопкой мыши и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="bde78-118">Right-click the Monitoring Server, and then click **Delete**.</span></span> 
    
9. <span data-ttu-id="bde78-119">На вкладке **удалить зависимые магазины**нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bde78-119">On **Delete Dependent Stores**, click **OK**.</span></span>
    
10. <span data-ttu-id="bde78-120">Опубликуйте топологию, проверьте состояние репликации и запустите мастер развертывания Skype для бизнеса Server по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="bde78-120">Publish the topology, check replication status, and run the Skype for Business Server Deployment Wizard as needed.</span></span> 
    

