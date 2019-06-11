---
title: 'Lync Server 2013: создание политик межсайтовой сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6309b27ddedb37c2c38e7d40e74e427f61b904a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-intersite-policies-in-lync-server-2013"></a><span data-ttu-id="97638-102">Создание политик межсайтовой сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97638-102">Create network intersite policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97638-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="97638-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="97638-104">*Политика* межсетевое соединение определяет ограничения пропускной способности между сайтами, которые имеют прямые WAN-ссылки между ними.</span><span class="sxs-lookup"><span data-stu-id="97638-104">A *network intersite policy* defines bandwidth limitations between sites that have direct WAN links between them.</span></span>

<span data-ttu-id="97638-105">Дополнительные сведения можно найти в документации по оболочке управления Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="97638-105">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="97638-106">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="97638-106">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="97638-107">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="97638-107">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="97638-108">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="97638-108">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="97638-109">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="97638-109">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> <span data-ttu-id="97638-110">Политика межсетевого сайта требуется <EM>только</EM> в том случае, если имеется прямая перекрестная связь между двумя сетевыми сайтами.</span><span class="sxs-lookup"><span data-stu-id="97638-110">A network intersite policy is required <EM>only</EM> if there is a direct cross link between two network sites.</span></span>



</div>

<span data-ttu-id="97638-111">В примере в Северной Америке для топологии есть прямая связь между сайтами Рено и Альбукерке.</span><span class="sxs-lookup"><span data-stu-id="97638-111">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="97638-112">Для этих двух сайтов требуется межсайтовая политика, которая применяет соответствующий профиль политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="97638-112">These two sites require an intersite policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="97638-113">В следующем примере используется профиль ссылки\_20Mb.</span><span class="sxs-lookup"><span data-stu-id="97638-113">The following example applies the 20Mb\_Link profile.</span></span>

<div>

## <a name="to-create-a-network-intersite-policy"></a><span data-ttu-id="97638-114">Создание политики межсетевого соединения</span><span class="sxs-lookup"><span data-stu-id="97638-114">To create a network intersite policy</span></span>

1.  <span data-ttu-id="97638-115">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="97638-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="97638-116">Запустите командлет New-Кснетворкинтерситеполици, чтобы создать политики межсетевого сайта и применить соответствующий профиль политики пропускной способности для двух сайтов с прямой перекрестной связью.</span><span class="sxs-lookup"><span data-stu-id="97638-116">Run the New-CsNetworkInterSitePolicy cmdlet to create network intersite policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="97638-117">Например, выполните командлет:</span><span class="sxs-lookup"><span data-stu-id="97638-117">For example, run:</span></span>
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  <span data-ttu-id="97638-118">При необходимости повторите шаг 2, чтобы создать политики межсетевого сайта для всех пар сетевых сайтов, имеющих прямую перекрестную ссылку.</span><span class="sxs-lookup"><span data-stu-id="97638-118">Repeat step 2 as needed to create network intersite policies for all network sites pairs that have a direct cross link.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

