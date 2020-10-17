---
title: 'Lync Server 2013: Просмотр сведений об отдельных магистральных магистральных каналах SIP'
description: 'Lync Server 2013: Просмотр сведений об отдельных магистральных магистральных каналах SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about individual SIP trunks
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49733780
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55c2f9fb1df4e916615cf7f95f95ae167d7216ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569615"
---
# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a><span data-ttu-id="b55c3-103">Просмотр сведений об отдельных магистральных магистральных каналах SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b55c3-103">View information about individual SIP trunks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b55c3-104">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="b55c3-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b55c3-105">Магистральные линии SIP используются для подключения телефонной сети Lync Server 2013 для передачи голоса по протоколу IP с телефонной сетью общего пользования.</span><span class="sxs-lookup"><span data-stu-id="b55c3-105">SIP trunks are used to connect Lync Server 2013 Voice over IP phone network with the Public Switched Telephone Network.</span></span> <span data-ttu-id="b55c3-106">В предыдущих версиях продукта магистрали использовались для маршрутизации исходящих звонков с сервера-посредника на шлюз ТСОП, причем для каждого шлюза использовалась только одна магистраль.</span><span class="sxs-lookup"><span data-stu-id="b55c3-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="b55c3-107">Поэтому шлюз ТСОП и магистраль SIP были практически равнозначны.</span><span class="sxs-lookup"><span data-stu-id="b55c3-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="b55c3-108">Для администраторов это означало возможность просмотра сведений об отдельной магистрали SIP путем просмотра сведений о связанном шлюзе ТСОП.</span><span class="sxs-lookup"><span data-stu-id="b55c3-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>

<span data-ttu-id="b55c3-109">Однако в Lync Server 2013 можно назначить несколько магистральных магистральов одному шлюзу PSTN; Это означает, что шлюзы и магистрали больше не являются одними и теми же.</span><span class="sxs-lookup"><span data-stu-id="b55c3-109">In Lync Server 2013, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="b55c3-110">В свою очередь, это означает, что администраторам необходимо использовать новый командлет [Get – CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) для просмотра сведений об отдельной магистральной магистральной сети SIP.</span><span class="sxs-lookup"><span data-stu-id="b55c3-110">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet in order to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="b55c3-111">Командлет Get-CsTrunk можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b55c3-111">The Get-CsTrunk cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b55c3-112">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="b55c3-112">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="b55c3-113">Просмотр сведений обо всех магистральных магистральных каналах SIP</span><span class="sxs-lookup"><span data-stu-id="b55c3-113">To view information for all your SIP trunks</span></span>

  - <span data-ttu-id="b55c3-114">Следующая команда возвращает сведения о всех магистралях SIP, используемых в организации.</span><span class="sxs-lookup"><span data-stu-id="b55c3-114">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="b55c3-115">Просмотр сведений об определенной магистрали SIP</span><span class="sxs-lookup"><span data-stu-id="b55c3-115">To view information for a specific SIP trunk</span></span>

  - <span data-ttu-id="b55c3-116">Эта команда возвращает сведения только о магистрали SIP с идентификатором PstnGateway:192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="b55c3-116">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="b55c3-117">Просмотр сведений о всех магистралях SIP, назначенных пулу</span><span class="sxs-lookup"><span data-stu-id="b55c3-117">Viewing Information for All the SIP Trunks Assigned to a Pool</span></span>

  - <span data-ttu-id="b55c3-118">В этом примере возвращаются сведения о всех магистралях SIP, назначенных пулу atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="b55c3-118">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

