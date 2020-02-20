---
title: Удаление связи сервера архивации
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec4cf011f96174f921ddbbbe814d21ec2280a2e5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="c4feb-102">Удаление связи сервера архивации</span><span class="sxs-lookup"><span data-stu-id="c4feb-102">Remove the Archiving server association</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4feb-103">_**Последнее изменение темы:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="c4feb-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="c4feb-104">Чтобы удалить сервер архивации, необходимо изменить или снять зависимость от связанного пула переднего плана, сервера переднего плана, устройства для обеспечения связи в филиалах и сервера для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="c4feb-104">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="c4feb-105">Вы изменяете свойства пула переднего плана, сервера переднего плана, устройства для обеспечения связи в филиалах и сервера для обеспечения связи в филиалах, чтобы удалить зависимость.</span><span class="sxs-lookup"><span data-stu-id="c4feb-105">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="c4feb-106">После очистки зависимости и удаления сервера в построителе топологий будет выведено уведомление о том, что связанный объект хранилища базы данных в построителе топологий также будет удален.</span><span class="sxs-lookup"><span data-stu-id="c4feb-106">After you clear the dependency and you delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="c4feb-107">Удаление привязки сервера архивации</span><span class="sxs-lookup"><span data-stu-id="c4feb-107">To remove the Archiving Server association</span></span>

1.  <span data-ttu-id="c4feb-108">Откройте сервер переднего плана Lync Server 2013, откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="c4feb-108">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="c4feb-109">Перейдите к узлу Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c4feb-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="c4feb-110">В построителе топологий разверните **Пулы переднего плана Enterprise Edition**, **серверы переднего плана Standard Edition**или **сайты филиалов**, в зависимости от того, где определен сервер архивации.</span><span class="sxs-lookup"><span data-stu-id="c4feb-110">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Archiving Server is defined.</span></span>

4.  <span data-ttu-id="c4feb-111">Если имеется связанный сервер филиалов, разверните **сайты филиалов**, разверните имя сайта филиала, а затем разверните узел устройства для обеспечения связи в **филиалах**.</span><span class="sxs-lookup"><span data-stu-id="c4feb-111">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c4feb-112">Устройства для обеспечения связи в <STRONG>филиалах</STRONG> в пользовательском интерфейсе применяются как к серверу обеспечения связи в филиалах, так и к устройству для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="c4feb-112"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="c4feb-113">Щелкните правой кнопкой мыши пул, сервер или устройство, связанное с сервером архивации, а затем выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="c4feb-113">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="c4feb-114">В разделе **Edit Properties** (Изменить свойства) выберите **General** (Общие) и в разделе **Associations** (Привязки) снимите флажок **Associate Archiving Server** (Связанный сервер архивации), а затем щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c4feb-114">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="c4feb-115">Повторите предыдущий шаг для любого другого пула, сервера или устройства, связанного с сервером архивации, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="c4feb-115">Repeat the previous step for any other pool, server or device associated with the Archiving Server that you want to remove.</span></span>

8.  <span data-ttu-id="c4feb-116">Щелкните сервер архивации правой кнопкой мыши и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="c4feb-116">Right-click the Archiving Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="c4feb-117">В окне **удаления зависимых хранилищ** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c4feb-117">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="c4feb-118">Опубликуйте топологию, проверьте состояние репликации, а затем при необходимости запустите мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c4feb-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

