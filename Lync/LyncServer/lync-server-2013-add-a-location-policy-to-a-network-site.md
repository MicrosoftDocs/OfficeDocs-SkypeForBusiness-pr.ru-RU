---
title: 'Lync Server 2013: Добавление политики расположения на сайт сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add a location policy to a network site
ms:assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425936(v=OCS.15)
ms:contentKeyID: 48183980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9ee6b5ba89cef592e137104df9e80d9373b5f02
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a><span data-ttu-id="d2b7f-102">Добавление политики расположения на сайт сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2b7f-102">Add a location policy to a network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2b7f-103">_**Тема последнего изменения:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="d2b7f-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="d2b7f-104">В следующих примерах показано, как добавить политику расположения в **Редмонде** , определенную в разделе [Создание политик расположения в Lync Server 2013](lync-server-2013-create-location-policies.md) , на существующий сайт сети и как создать новый сайт сети, использующий политику расположения в **Редмонде** .</span><span class="sxs-lookup"><span data-stu-id="d2b7f-104">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>

<span data-ttu-id="d2b7f-105">Дополнительные сведения о работе с сетевыми сайтами можно найти в документации по оболочке Lync Server Management Shell для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="d2b7f-105">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="d2b7f-106">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="d2b7f-106">**New-CsNetworkSite**</span></span>

  - <span data-ttu-id="d2b7f-107">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="d2b7f-107">**Get-CsNetworkSite**</span></span>

  - <span data-ttu-id="d2b7f-108">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="d2b7f-108">**Set-CsNetworkSite**</span></span>

  - <span data-ttu-id="d2b7f-109">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="d2b7f-109">**Remove-CsNetworkSite**</span></span>

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="d2b7f-110">Назначение политики местоположения существующему сетевому узлу</span><span class="sxs-lookup"><span data-stu-id="d2b7f-110">To assign a location policy to an existing network site</span></span>

1.  <span data-ttu-id="d2b7f-111">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d2b7f-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d2b7f-112">Выполните следующие командлеты для изменения существующего сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="d2b7f-112">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="d2b7f-113">Назначьте политику расположения с меткой **Redmond** существующему сетевому сайту с именем **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="d2b7f-113">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="d2b7f-114">Назначение политики местоположения новому сетевому узлу</span><span class="sxs-lookup"><span data-stu-id="d2b7f-114">To assign a location policy to a new network site</span></span>

1.  <span data-ttu-id="d2b7f-115">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d2b7f-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d2b7f-116">Выполните следующий командлет для создания нового сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="d2b7f-116">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="d2b7f-117">Создайте новый сетевой сайт в области сети и назначьте ему политику расположения с меткой **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="d2b7f-117">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>

