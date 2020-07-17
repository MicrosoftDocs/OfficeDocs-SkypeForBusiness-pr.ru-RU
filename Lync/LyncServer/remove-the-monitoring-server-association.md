---
title: Удаление связи с сервером мониторинга
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the Monitoring server association
ms:assetid: c45b22ae-fc06-484a-a05b-735bd1bb7448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721877(v=OCS.15)
ms:contentKeyID: 49733810
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aa78a49686ca555fdbc26d3ffd4953d88d64a95
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-monitoring-server-association"></a><span data-ttu-id="853fd-102">Удаление связи с сервером мониторинга</span><span class="sxs-lookup"><span data-stu-id="853fd-102">Remove the Monitoring server association</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="853fd-103">_**Последнее изменение темы:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="853fd-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="853fd-104">Для удаления сервера мониторинга необходимо изменить или снять зависимость от связанного пула переднего плана, сервера переднего плана, устройства для обеспечения связи в филиалах и сервера для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="853fd-104">To remove the Monitoring Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="853fd-105">Вы изменяете свойства пула переднего плана, сервера переднего плана, устройства для обеспечения связи в филиалах и сервера для обеспечения связи в филиалах, чтобы удалить зависимость.</span><span class="sxs-lookup"><span data-stu-id="853fd-105">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="853fd-106">После очистки зависимости и удаления сервера в построителе топологий будет выведено уведомление о том, что связанный объект хранилища базы данных в построителе топологий также будет удален.</span><span class="sxs-lookup"><span data-stu-id="853fd-106">After you clear the dependency and delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-monitoring-server-association"></a><span data-ttu-id="853fd-107">Удаление связи с сервером мониторинга</span><span class="sxs-lookup"><span data-stu-id="853fd-107">To remove the Monitoring Server association</span></span>

1.  <span data-ttu-id="853fd-108">Откройте сервер переднего плана Lync Server 2013, откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="853fd-108">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="853fd-109">Перейдите к узлу Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="853fd-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="853fd-110">В построителе топологий разверните **Пулы переднего плана Enterprise Edition**, **серверы переднего плана Standard Edition**или **сайты филиалов**, в зависимости от того, где определен сервер мониторинга.</span><span class="sxs-lookup"><span data-stu-id="853fd-110">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Monitoring Server is defined.</span></span>

4.  <span data-ttu-id="853fd-111">Если имеется связанный сервер филиалов, разверните **сайты филиалов**, разверните имя сайта филиала, а затем разверните узел устройства для обеспечения связи в **филиалах**.</span><span class="sxs-lookup"><span data-stu-id="853fd-111">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="853fd-112">Устройства для обеспечения связи в <STRONG>филиалах</STRONG> в пользовательском интерфейсе применяются как к серверу обеспечения связи в филиалах, так и к устройству для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="853fd-112"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="853fd-113">Щелкните правой кнопкой мыши пул, сервер или устройство, связанное с сервером мониторинга, и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="853fd-113">Right-click the pool, server, or device that is associated with the Monitoring Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="853fd-114">В окне **изменения свойств** на вкладке **Общие** в разделе **Связи** снимите флажок **Associate Monitoring Server** (Связать сервер мониторинга) и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="853fd-114">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Monitoring Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="853fd-115">Повторите предыдущий шаг для любого другого пула, сервера или устройства, связанного с сервером мониторинга.</span><span class="sxs-lookup"><span data-stu-id="853fd-115">Repeat the previous step for any other pool, server or device associated with the Monitoring Server.</span></span>

8.  <span data-ttu-id="853fd-116">Щелкните сервер мониторинга правой кнопкой мыши и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="853fd-116">Right-click the Monitoring Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="853fd-117">В окне **удаления зависимых хранилищ** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="853fd-117">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="853fd-118">Опубликуйте топологию, проверьте состояние репликации и при необходимости запустите мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="853fd-118">Publish the topology, check replication status, and run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

