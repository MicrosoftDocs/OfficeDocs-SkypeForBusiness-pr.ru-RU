---
title: 'Lync Server 2013: Добавление политики расположения к сетевому сайту'
description: 'Lync Server 2013: Добавление политики расположения к сетевому сайту.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a location policy to a network site
ms:assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425936(v=OCS.15)
ms:contentKeyID: 48183980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20f71d3144e2ef730de5dae46be16138b5d36c42
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567925"
---
# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a><span data-ttu-id="46cc9-103">Добавление политики расположения к сетевому сайту в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46cc9-103">Add a location policy to a network site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46cc9-104">_**Последнее изменение темы:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="46cc9-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="46cc9-105">В следующих примерах показано, как добавить политику расположения **Redmond** , определенную в разделе [Создание политик расположения в Lync Server 2013](lync-server-2013-create-location-policies.md) на существующий сетевой сайт, и как создать новый сетевой сайт, использующий политику расположения **Redmond** .</span><span class="sxs-lookup"><span data-stu-id="46cc9-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>

<span data-ttu-id="46cc9-106">Для получения подробных сведений о работе с сетевыми сайтами обратитесь к документации по командной консоли Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="46cc9-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="46cc9-107">**New — CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="46cc9-107">**New-CsNetworkSite**</span></span>

  - <span data-ttu-id="46cc9-108">**Get — CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="46cc9-108">**Get-CsNetworkSite**</span></span>

  - <span data-ttu-id="46cc9-109">**Set — CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="46cc9-109">**Set-CsNetworkSite**</span></span>

  - <span data-ttu-id="46cc9-110">**Remove — CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="46cc9-110">**Remove-CsNetworkSite**</span></span>

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="46cc9-111">Назначение политики местоположения существующему сетевому узлу</span><span class="sxs-lookup"><span data-stu-id="46cc9-111">To assign a location policy to an existing network site</span></span>

1.  <span data-ttu-id="46cc9-112">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="46cc9-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="46cc9-113">Выполните следующие командлеты для изменения существующего сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="46cc9-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="46cc9-114">Назначьте политику расположения с меткой **Redmond** существующему сетевому сайту с именем **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="46cc9-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="46cc9-115">Назначение политики местоположения новому сетевому узлу</span><span class="sxs-lookup"><span data-stu-id="46cc9-115">To assign a location policy to a new network site</span></span>

1.  <span data-ttu-id="46cc9-116">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="46cc9-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="46cc9-117">Выполните следующий командлет для создания нового сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="46cc9-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="46cc9-118">Создайте новый сетевой узел в области сети и назначьте ему политику местоположения с меткой **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="46cc9-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>

