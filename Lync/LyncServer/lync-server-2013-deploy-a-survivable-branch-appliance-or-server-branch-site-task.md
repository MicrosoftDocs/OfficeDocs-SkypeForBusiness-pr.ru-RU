---
title: Развертывание устройства для обеспечения связи в филиалах или задачи сайта филиала
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy a Survivable Branch Appliance or Server - branch site task
ms:assetid: 7989ba29-0419-46dd-892c-4ad3238afd56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398599(v=OCS.15)
ms:contentKeyID: 48184586
ms.date: 10/29/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a06cbb4322a1e25b24e94140ceeaa4d89a9cd826
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-a-survivable-branch-appliance-or-server-with-lync-server-2013---branch-site-task"></a><span data-ttu-id="ab9b5-102">Развертывание устройства или сервера для обеспечения связи в филиалах с помощью Lync Server 2013 — задача сайта филиала</span><span class="sxs-lookup"><span data-stu-id="ab9b5-102">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab9b5-103">_**Последнее изменение темы:** 2014-10-28_</span><span class="sxs-lookup"><span data-stu-id="ab9b5-103">_**Topic Last Modified:** 2014-10-28_</span></span>

<span data-ttu-id="ab9b5-104">Выполните одну из двух процедур, описанных в этом разделе, на сайте филиала после успешного выполнения задач по [развертыванию устройства или сервера для обеспечения связи в филиалах с задачами Lync server 2013-Central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="ab9b5-104">Perform one of the two procedures described in this topic at the branch site, after successfully completing the tasks in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md).</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="ab9b5-105">Чтобы выполнить эту процедуру, необходимо быть членом группы RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="ab9b5-105">To perform this procedure, you must be a member of the RTCUniversalSBATechnicians group.</span></span>



</div>

<div>

## <a name="to-deploy-the-survivable-branch-appliance"></a><span data-ttu-id="ab9b5-106">Развертывание устройства для обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="ab9b5-106">To deploy the Survivable Branch Appliance</span></span>

  - <span data-ttu-id="ab9b5-107">Развертывание устройства для обеспечения связи в филиалах включено поставщиком устройства для обеспечения связи в филиалах через пользовательский веб-интерфейс.</span><span class="sxs-lookup"><span data-stu-id="ab9b5-107">Survivable Branch Appliance deployment is enabled by the Survivable Branch Appliance vendor through a web user interface (UI).</span></span> <span data-ttu-id="ab9b5-108">Сведения о развертывании устройства для обеспечения связи в филиалах можно найти в документации к поставщику устройства для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="ab9b5-108">For information about deploying the Survivable Branch Appliance, see your Survivable Branch Appliance vendor documentation.</span></span>

</div>

<div>

## <a name="to-deploy-the-survivable-branch-server"></a><span data-ttu-id="ab9b5-109">Развертывание сервера для обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="ab9b5-109">To deploy the Survivable Branch Server</span></span>

  - <span data-ttu-id="ab9b5-110">Установите Lync Server 2013 на компьютере под управлением Windows Server 2008 R2, Windows Server 2012 или Windows Server 2012 R2, точно так же, как при установке любой другой роли сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ab9b5-110">Install Lync Server 2013 on a computer running Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2, just as you would install any other Lync Server 2013 server role.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="ab9b5-111">Сведения об установке Lync Server содержатся в документации по развертыванию <A href="lync-server-2013-deploying-lync-server.md">Lync server 2013</A> .</span><span class="sxs-lookup"><span data-stu-id="ab9b5-111">For information about installing Lync Server, see <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="ab9b5-112">**Следующий шаг**: [Настройка пользователей для обеспечения устойчивости сайта филиала в Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="ab9b5-112">**Next step**: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ab9b5-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ab9b5-113">See Also</span></span>


[<span data-ttu-id="ab9b5-114">Приложение а: использование командлетов для развертывания устройства для обеспечения связи в филиалах в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab9b5-114">Appendix A: Using cmdlets to deploy a Survivable Branch Appliance in Lync Server 2013</span></span>](lync-server-2013-appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

