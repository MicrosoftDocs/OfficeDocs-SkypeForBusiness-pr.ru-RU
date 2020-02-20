---
title: 'Lync Server 2013: Приложение A: использование командлетов для развертывания устройства для обеспечения связи в филиалах'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Appendix A: Using cmdlets to deploy a Survivable Branch Appliance'
ms:assetid: 796a26cf-7ec9-453b-8757-6153a6dd86c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398598(v=OCS.15)
ms:contentKeyID: 48184569
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 107bc5f9b39b1d62db0cba6960b60307c82831fb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance-in-lync-server-2013"></a><span data-ttu-id="15971-102">Приложение а: использование командлетов для развертывания устройства для обеспечения связи в филиалах в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15971-102">Appendix A: Using cmdlets to deploy a Survivable Branch Appliance in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15971-103">_**Последнее изменение темы:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="15971-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="15971-104">В этом разделе описывается, как развернуть устройство для обеспечения связи в филиалах с помощью командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="15971-104">This topic describes how to deploy a Survivable Branch Appliance using the Lync Server Management Shell.</span></span> <span data-ttu-id="15971-105">Выполните эту процедуру на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="15971-105">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-deploy-a-survivable-branch-appliance-remotely"></a><span data-ttu-id="15971-106">Удаленное развертывание устройства для обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="15971-106">To deploy a Survivable Branch Appliance remotely</span></span>

1.  <span data-ttu-id="15971-107">Чтобы добавить новый сайт филиала, выполните процедуру, описанную в разделе [Добавление сайтов филиалов в топологию в Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md) .</span><span class="sxs-lookup"><span data-stu-id="15971-107">Follow the procedure in [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md) to add a new branch site.</span></span>

2.  <span data-ttu-id="15971-108">Присоедините узел филиала к домену.</span><span class="sxs-lookup"><span data-stu-id="15971-108">Join the branch site to the domain.</span></span>

3.  <span data-ttu-id="15971-109">Добавьте группу RTCUniversalSBATechnicians в локальную группу администраторов.</span><span class="sxs-lookup"><span data-stu-id="15971-109">Add the RTCUniversalSBATechnicians group to the local Administrators group.</span></span>

4.  <span data-ttu-id="15971-110">Перезапустите сервер и войдите в систему в качестве члена группы RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="15971-110">Restart the server, and log on to it as a member of the RTCUniversalSBATechnicians group.</span></span>

5.  <span data-ttu-id="15971-111">В командной консоли Lync Server введите следующие команды, заменив заполнители на правильные сведения для вашей организации:</span><span class="sxs-lookup"><span data-stu-id="15971-111">In the Lync Server Management Shell, type the following commands, replacing the placeholders with the correct information for your organization:</span></span>
    
        Export-CsConfiguration -FileName C:\CSConfig.zip
        Import-CsConfiguration -LocalStore -FileName C:\CSConfig.zip -Verbose
        Enable-CSReplica -Verbose
        Enable-CsComputer -Verbose
        Request-CsCertificate -New -Type default -CA <YourCA> -Verbose
        Set-CsCertificate -Type Default -Thumbprint <YourCertThumbprint>
        Start-cswindowsservice -verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

