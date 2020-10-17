---
title: 'Lync Server 2013: Добавление политики расположения к сетевому сайту'
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
ms.openlocfilehash: 95ca625746fc38d8cab9c25701a8bf22718e71e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529576"
---
# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a><span data-ttu-id="8e1b5-102">Добавление политики расположения к сетевому сайту в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e1b5-102">Add a location policy to a network site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e1b5-103">_**Последнее изменение темы:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="8e1b5-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="8e1b5-104">В следующих примерах показано, как добавить политику расположения **Redmond** , определенную в разделе [Создание политик расположения в Lync Server 2013](lync-server-2013-create-location-policies.md) на существующий сетевой сайт, и как создать новый сетевой сайт, использующий политику расположения **Redmond** .</span><span class="sxs-lookup"><span data-stu-id="8e1b5-104">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>

<span data-ttu-id="8e1b5-105">Для получения подробных сведений о работе с сетевыми сайтами обратитесь к документации по командной консоли Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="8e1b5-105">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="8e1b5-106">**New — CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="8e1b5-106">**New-CsNetworkSite**</span></span>

  - <span data-ttu-id="8e1b5-107">**Get — CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="8e1b5-107">**Get-CsNetworkSite**</span></span>

  - <span data-ttu-id="8e1b5-108">**Set — CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="8e1b5-108">**Set-CsNetworkSite**</span></span>

  - <span data-ttu-id="8e1b5-109">**Remove — CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="8e1b5-109">**Remove-CsNetworkSite**</span></span>

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="8e1b5-110">Назначение политики местоположения существующему сетевому узлу</span><span class="sxs-lookup"><span data-stu-id="8e1b5-110">To assign a location policy to an existing network site</span></span>

1.  <span data-ttu-id="8e1b5-111">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8e1b5-112">Выполните следующие командлеты для изменения существующего сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-112">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="8e1b5-113">Назначьте политику расположения с меткой **Redmond** существующему сетевому сайту с именем **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-113">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="8e1b5-114">Назначение политики местоположения новому сетевому узлу</span><span class="sxs-lookup"><span data-stu-id="8e1b5-114">To assign a location policy to a new network site</span></span>

1.  <span data-ttu-id="8e1b5-115">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8e1b5-116">Выполните следующий командлет для создания нового сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-116">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="8e1b5-117">Создайте новый сетевой узел в области сети и назначьте ему политику местоположения с меткой **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="8e1b5-117">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>

