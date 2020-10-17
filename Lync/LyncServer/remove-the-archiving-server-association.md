---
title: Удаление связи с сервером архивирования
description: Удалите сопоставление сервера архивации.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f6c34e49b0217a8318a83752b3878a7625e5d58
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570225"
---
# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="30b46-103">Удаление связи с сервером архивирования</span><span class="sxs-lookup"><span data-stu-id="30b46-103">Remove the Archiving server association</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30b46-104">_**Последнее изменение темы:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="30b46-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="30b46-105">Чтобы удалить сервер архивации, необходимо изменить или снять зависимость от связанного пула переднего плана, сервера переднего плана, устройства для обеспечения связи в филиалах и сервера для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="30b46-105">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="30b46-106">Вы изменяете свойства пула переднего плана, сервера переднего плана, устройства для обеспечения связи в филиалах и сервера для обеспечения связи в филиалах, чтобы удалить зависимость.</span><span class="sxs-lookup"><span data-stu-id="30b46-106">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="30b46-107">После очистки зависимости и удаления сервера в построителе топологий будет выведено уведомление о том, что связанный объект хранилища базы данных в построителе топологий также будет удален.</span><span class="sxs-lookup"><span data-stu-id="30b46-107">After you clear the dependency and you delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="30b46-108">Удаление привязки сервера архивации</span><span class="sxs-lookup"><span data-stu-id="30b46-108">To remove the Archiving Server association</span></span>

1.  <span data-ttu-id="30b46-109">Откройте сервер переднего плана Lync Server 2013, откройте построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="30b46-109">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="30b46-110">Перейдите к узлу Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="30b46-110">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="30b46-111">В построителе топологий разверните **Пулы переднего плана Enterprise Edition**, **серверы переднего плана Standard Edition**или **сайты филиалов**, в зависимости от того, где определен сервер архивации.</span><span class="sxs-lookup"><span data-stu-id="30b46-111">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Archiving Server is defined.</span></span>

4.  <span data-ttu-id="30b46-112">Если имеется связанный сервер филиалов, разверните **сайты филиалов**, разверните имя сайта филиала, а затем разверните узел устройства для обеспечения связи в **филиалах**.</span><span class="sxs-lookup"><span data-stu-id="30b46-112">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="30b46-113">Устройства для обеспечения связи в <STRONG>филиалах</STRONG> в пользовательском интерфейсе применяются как к серверу обеспечения связи в филиалах, так и к устройству для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="30b46-113"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="30b46-114">Щелкните правой кнопкой мыши пул, сервер или устройство, связанное с сервером архивации, а затем выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="30b46-114">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="30b46-115">В разделе **Edit Properties** (Изменить свойства) выберите **General** (Общие) и в разделе **Associations** (Привязки) снимите флажок **Associate Archiving Server** (Связанный сервер архивации), а затем щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="30b46-115">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="30b46-116">Повторите предыдущий шаг для любого другого пула, сервера или устройства, связанного с сервером архивации, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="30b46-116">Repeat the previous step for any other pool, server or device associated with the Archiving Server that you want to remove.</span></span>

8.  <span data-ttu-id="30b46-117">Щелкните сервер архивации правой кнопкой мыши и выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="30b46-117">Right-click the Archiving Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="30b46-118">В окне **удаления зависимых хранилищ** нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="30b46-118">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="30b46-119">Опубликуйте топологию, проверьте состояние репликации, а затем при необходимости запустите мастер развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="30b46-119">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

