---
title: Удаление связи с сервером мониторинга
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the Monitoring server association
ms:assetid: c45b22ae-fc06-484a-a05b-735bd1bb7448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721877(v=OCS.15)
ms:contentKeyID: 49733810
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f26a809056674c231212db3f824a2ecb7ce7ecd1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="4661e-102">Удаление связи с сервером мониторинга</span><span class="sxs-lookup"><span data-stu-id="4661e-102">Remove the Monitoring server association</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4661e-103">_**Тема последнего изменения:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="4661e-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="4661e-104">Для удаления сервера мониторинга необходимо изменить или снять зависимость на связанном пуле интерфейсов, сервере переднего плана, работающем устройстве филиала и бесперебойном сервере подразделения.</span><span class="sxs-lookup"><span data-stu-id="4661e-104">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="4661e-105">Вы можете изменить свойства пула переднего плана, сервер переднего плана, бесперебойно работающее устройство филиалов и бесперебойный сервер филиала, чтобы удалить зависимость.</span><span class="sxs-lookup"><span data-stu-id="4661e-105">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="4661e-106">После очистки зависимости и удаления сервера в построителе топологии вы будете уведомлены о том, что связанный объект хранилища базы данных в построителе топологии также будет удален.</span><span class="sxs-lookup"><span data-stu-id="4661e-106">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="4661e-107">Удаление сопоставления сервера мониторинга</span><span class="sxs-lookup"><span data-stu-id="4661e-107">To remove the Monitoring Server association</span></span>

1.  <span data-ttu-id="4661e-108">Откройте сервер клиентского доступа Lync Server 2013, откройте построитель топологии.</span><span class="sxs-lookup"><span data-stu-id="4661e-108">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="4661e-109">Перейдите на узел Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4661e-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="4661e-110">В построителе топологии разворачивание **пулов переднего плана Enterprise Edition**, **серверов переднего плана Standard Edition**и **сайтов филиалов**в зависимости от того, где определен сервер мониторинга.</span><span class="sxs-lookup"><span data-stu-id="4661e-110">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Monitoring Server is defined.</span></span>

4.  <span data-ttu-id="4661e-111">Если у вас есть связанный сервер филиалов, разверните **сайты филиалов**, разверните имя сайта филиала, а затем разверните **бесперебойно управляемые устройства филиалов**.</span><span class="sxs-lookup"><span data-stu-id="4661e-111">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4661e-112"><STRONG>Бесперебойно управляемые устройства ветвления</STRONG> в пользовательском интерфейсе применяются как к бесперебойному, так и к бесперебойному устройству филиала.</span><span class="sxs-lookup"><span data-stu-id="4661e-112"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="4661e-113">Щелкните правой кнопкой мыши пул, сервер или устройство, связанные с сервером мониторинга, и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="4661e-113">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="4661e-114">В диалоговом окне **изменение свойств**в разделе **Общие**в группе **сопоставления**снимите флажок **сопоставить сервер мониторинга** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4661e-114">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="4661e-115">Повторите предыдущий шаг для любого другого пула, сервера или устройства, связанного с сервером мониторинга.</span><span class="sxs-lookup"><span data-stu-id="4661e-115">Repeat the previous step for any other pool, server or device associated with the Monitoring Server.</span></span>

8.  <span data-ttu-id="4661e-116">Щелкните сервер мониторинга правой кнопкой мыши и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="4661e-116">Right-click the Monitoring Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="4661e-117">На вкладке **удалить зависимые магазины**нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4661e-117">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="4661e-118">Опубликуйте топологию, проверьте состояние репликации и запустите мастер развертывания Lync Server, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="4661e-118">Publish the topology, check replication status, and run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

