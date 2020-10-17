---
title: 'Lync Server 2013: создание политик межсайтовой сети'
description: 'Lync Server 2013: создание политик межсайтовой сети.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9666efcb9c6da459a8e50eeae66cd1a513b46f65
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562275"
---
# <a name="create-network-intersite-policies-in-lync-server-2013"></a><span data-ttu-id="11d95-103">Создание межсайтовых политик для сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11d95-103">Create network intersite policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11d95-104">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="11d95-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="11d95-105">*Межузловая сетевая политика* задает ограничения пропускной способности между узлами, соединенными прямыми подключениями по глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="11d95-105">A *network intersite policy* defines bandwidth limitations between sites that have direct WAN links between them.</span></span>

<span data-ttu-id="11d95-106">Для получения дополнительных сведений обратитесь к документации по командной консоли Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="11d95-106">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="11d95-107">New — CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="11d95-107">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="11d95-108">Get — CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="11d95-108">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="11d95-109">Set — CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="11d95-109">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="11d95-110">Remove — CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="11d95-110">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> <span data-ttu-id="11d95-111">Межузловая сетевая политика требуется <EM>только</EM> в том случае, если между двумя сетевыми узлами есть прямое соединение.</span><span class="sxs-lookup"><span data-stu-id="11d95-111">A network intersite policy is required <EM>only</EM> if there is a direct cross link between two network sites.</span></span>



</div>

<span data-ttu-id="11d95-112">В примере области "Северная Америка" топологии существует прямая ссылка между сайтами Рино и Альбукерке.</span><span class="sxs-lookup"><span data-stu-id="11d95-112">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="11d95-113">Для этих двух сайтов требуется межсайтовая политика, которая применяет соответствующий профиль политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="11d95-113">These two sites require an intersite policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="11d95-114">В следующем примере применяется \_ профиль канала 20Mb.</span><span class="sxs-lookup"><span data-stu-id="11d95-114">The following example applies the 20Mb\_Link profile.</span></span>

<div>

## <a name="to-create-a-network-intersite-policy"></a><span data-ttu-id="11d95-115">Создание межузловой сетевой политики</span><span class="sxs-lookup"><span data-stu-id="11d95-115">To create a network intersite policy</span></span>

1.  <span data-ttu-id="11d95-116">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="11d95-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="11d95-p102">Чтобы создать межузловые сетевые политики и применить соответствующий профиль политики пропускной способности для двух узлов с прямым соединением, выполните командлет New-CsNetworkInterSitePolicy. Пример:</span><span class="sxs-lookup"><span data-stu-id="11d95-p102">Run the New-CsNetworkInterSitePolicy cmdlet to create network intersite policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link. For example, run:</span></span>
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  <span data-ttu-id="11d95-119">Повторите шаг 2 для всех пар сетевых узлов, имеющих прямое соединение.</span><span class="sxs-lookup"><span data-stu-id="11d95-119">Repeat step 2 as needed to create network intersite policies for all network sites pairs that have a direct cross link.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

