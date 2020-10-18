---
title: 'Lync Server 2013: Настройка областей сети для контроля допуска звонков'
description: 'Lync Server 2013: Настройка областей сети для CAC.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f016e0c943963ea4ce9739bd486c6996da502e73
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577565"
---
# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a><span data-ttu-id="ab5b5-103">Настройка сетевых регионов для CAC в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab5b5-103">Configure network regions for CAC in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab5b5-104">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ab5b5-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ab5b5-105">Если области сети для E9-1-1 или обхода сервера-посредника уже созданы, измените эти существующие области, добавив параметры, относящиеся к контролю допуска звонков, с помощью командлета <STRONG>Set-CsNetworkRegion</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-105">If you have already created network regions for E9-1-1 or media bypass, you can modify the existing network regions by adding settings specific to call admission control (CAC) by using the <STRONG>Set-CsNetworkRegion</STRONG> cmdlet.</span></span> <span data-ttu-id="ab5b5-106">Пример, посвященный изменению области сети, представлен <A href="lync-server-2013-create-or-modify-a-network-region.md">в статье Создание или изменение области сети в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-106">For an example of how to modify a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="ab5b5-107">*Области сети* — это сетевые концентраторы или магистрали, используемые в конфигурациях контроля допуска звонков, E9-1-1 и обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-107">*Network regions* are the network hubs or backbones that are used in configuring CAC, E9-1-1, and media bypass.</span></span> <span data-ttu-id="ab5b5-108">Используйте следующие процедуры для создания областей сети, которые совмещаются с областями сети в примере топологии сети для контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-108">Use the following procedure to create network regions that align to network regions in the example network topology for CAC.</span></span> <span data-ttu-id="ab5b5-109">Пример сетевой топологии представлен в статье [Пример: сбор требований для контроля допуска звонков в Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-109">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="ab5b5-110">В этом примере топологии сети для контроля допуска звонков имеется три области: North America (Северная Америка), EMEA (Европа, Ближний Восток и Африка) и APAC (азиатско-тихоокеанский регион).</span><span class="sxs-lookup"><span data-stu-id="ab5b5-110">The example network topology for CAC has three regions: North America, EMEA, and APAC.</span></span> <span data-ttu-id="ab5b5-111">Каждая область имеет свой центральный сайт.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-111">Each region has a specified central site.</span></span> <span data-ttu-id="ab5b5-112">Для области Северной Америки (NorthAmerica) назначенный центральный сайт называется CHICAGO.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-112">For the North America region, the designated central site is named CHICAGO.</span></span> <span data-ttu-id="ab5b5-113">В следующей процедуре показано, как можно создать область NorthAmerica с помощью командлета **New-CsNetworkRegion**.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-113">The following procedure shows an example of how you can use the **New-CsNetworkRegion** cmdlet to create the North America region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ab5b5-114">В следующей процедуре для создания области сети используется Командная консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-114">In the following procedure, Lync Server Management Shell is used to create a network region.</span></span> <span data-ttu-id="ab5b5-115">Дополнительные сведения о создании области сети с помощью панели управления Lync Server можно найти <A href="lync-server-2013-create-or-modify-a-network-region.md">в статье Создание или изменение области сети в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-115">For details about using Lync Server Control Panel to create a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a><span data-ttu-id="ab5b5-116">Создание области сети для контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="ab5b5-116">To create a network region for call admission control</span></span>

1.  <span data-ttu-id="ab5b5-117">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="ab5b5-118">Выполните командлет **New-CsNetworkRegion** для каждой области, которую требуется создать.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-118">For each region that you need to create, run the **New-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="ab5b5-119">Например, чтобы создать область NorthAmerica, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ab5b5-119">For example, to create the North America region, run:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  <span data-ttu-id="ab5b5-120">Повторите действие 2 для создания областей сети EMEA и APAC.</span><span class="sxs-lookup"><span data-stu-id="ab5b5-120">Repeat step 2 to create the network regions, EMEA and APAC.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

