---
title: 'Lync Server 2013: Просмотр сведений о сетевом интерфейсе'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network interface information
ms:assetid: e7dbb1ec-62b3-48be-a419-c493df5740e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721916(v=OCS.15)
ms:contentKeyID: 49733850
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7dab87bd6397d8473dfff8158b8c6eaa15988f37
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-network-interface-information-in-lync-server-2013"></a><span data-ttu-id="9d734-102">Просмотр сведений о сетевом интерфейсе в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9d734-102">Viewing network interface information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d734-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="9d734-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="9d734-104">Вы можете просматривать сведения о сетевом интерфейсе с помощью Windows PowerShell и командлета **Get – CsNetworkInterface** .</span><span class="sxs-lookup"><span data-stu-id="9d734-104">You can view network interface information by using Windows PowerShell and the **Get-CsNetworkInterface** cmdlet.</span></span> <span data-ttu-id="9d734-105">Этот командлет можно выполнить из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9d734-105">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9d734-106">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="9d734-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-interface-information"></a><span data-ttu-id="9d734-107">Просмотр сведений о сетевом интерфейсе</span><span class="sxs-lookup"><span data-stu-id="9d734-107">To view network interface information</span></span>

  - <span data-ttu-id="9d734-108">Чтобы просмотреть сведения о сетевом интерфейсе, введите следующую команду в командной консоли Lync Server, а затем нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="9d734-108">To view network interface information, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkInterface
    
    <span data-ttu-id="9d734-109">Эта команда возвращает сведения, подобные приведенным ниже, для каждого сетевого интерфейса:</span><span class="sxs-lookup"><span data-stu-id="9d734-109">This command returns information similar to the following for each network interface:</span></span>
    
        Identity              : dc.vdomain.com/Primary/1
        ComputerFqdn          : dc.vdomain.com
        IPAddress             : 0.0.0.0
        IPv6Address           :
        Interface             : Primary
        InterfaceNumber       : 1
        ConfiguredFqdn        :
        ConfiguredIPAddress   :
        ConfiguredIPv6Address :
    
    <span data-ttu-id="9d734-110">Дополнительные сведения см. в разделе [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span><span class="sxs-lookup"><span data-stu-id="9d734-110">For details, see [Get-CsNetworkInterface](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterface).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

