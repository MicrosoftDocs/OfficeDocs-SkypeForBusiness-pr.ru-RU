---
title: 'Lync Server 2013: Настройка регионов сети для CAC'
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
ms.openlocfilehash: d80a5ec8d02376ae084f1973f47690259cac364d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758377"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a><span data-ttu-id="867c8-102">Настройка регионов сети для CAC в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="867c8-102">Configure network regions for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="867c8-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="867c8-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="867c8-104">Если вы уже создали регионы сети для E9-1 или мультимедиа, вы можете изменить существующие сетевые регионы, добавив параметры, специфические для управления допуском звонков (CAC), с помощью командлета <STRONG>Set-кснетворкрегион</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="867c8-104">If you have already created network regions for E9-1-1 or media bypass, you can modify the existing network regions by adding settings specific to call admission control (CAC) by using the <STRONG>Set-CsNetworkRegion</STRONG> cmdlet.</span></span> <span data-ttu-id="867c8-105">Пример, посвященный изменению сетевого региона, можно найти <A href="lync-server-2013-create-or-modify-a-network-region.md">в разделе Создание или изменение сетевого региона в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="867c8-105">For an example of how to modify a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="867c8-106">*Регионы сетей* — это сетевые разветвители и одинарные кости, которые используются при настройке CAC, E9-1-1 и мультимедийного обхода.</span><span class="sxs-lookup"><span data-stu-id="867c8-106">*Network regions* are the network hubs or backbones that are used in configuring CAC, E9-1-1, and media bypass.</span></span> <span data-ttu-id="867c8-107">Используйте описанную ниже процедуру для создания областей сети, которые выравниваются по сетевым областям в примере использования CAC в топологии сети.</span><span class="sxs-lookup"><span data-stu-id="867c8-107">Use the following procedure to create network regions that align to network regions in the example network topology for CAC.</span></span> <span data-ttu-id="867c8-108">Пример топологии сети вы можете найти в статье [пример. сбор требований для управления допуском звонков в Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="867c8-108">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="867c8-109">Пример топологии сети для CAC состоит из трех регионов: Северная Америка, EMEA и APAC.</span><span class="sxs-lookup"><span data-stu-id="867c8-109">The example network topology for CAC has three regions: North America, EMEA, and APAC.</span></span> <span data-ttu-id="867c8-110">Каждый регион имеет указанный центральный сайт.</span><span class="sxs-lookup"><span data-stu-id="867c8-110">Each region has a specified central site.</span></span> <span data-ttu-id="867c8-111">Для региона Северной Америки указанный центральный сайт называется Чикаго.</span><span class="sxs-lookup"><span data-stu-id="867c8-111">For the North America region, the designated central site is named CHICAGO.</span></span> <span data-ttu-id="867c8-112">Ниже приведен пример использования командлета **New-кснетворкрегион** для создания области для Северной Америки.</span><span class="sxs-lookup"><span data-stu-id="867c8-112">The following procedure shows an example of how you can use the **New-CsNetworkRegion** cmdlet to create the North America region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="867c8-113">В описанной ниже процедуре для создания сетевого региона используется Командная консоль Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="867c8-113">In the following procedure, Lync Server Management Shell is used to create a network region.</span></span> <span data-ttu-id="867c8-114">Дополнительные сведения об использовании панели управления Lync Server для создания сетевого региона можно найти <A href="lync-server-2013-create-or-modify-a-network-region.md">в разделе Создание или изменение сетевого региона в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="867c8-114">For details about using Lync Server Control Panel to create a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a><span data-ttu-id="867c8-115">Создание сетевого региона для управления допуском звонков</span><span class="sxs-lookup"><span data-stu-id="867c8-115">To create a network region for call admission control</span></span>

1.  <span data-ttu-id="867c8-116">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="867c8-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="867c8-117">Для каждого региона, который необходимо создать, выполните командлет **New-кснетворкрегион** .</span><span class="sxs-lookup"><span data-stu-id="867c8-117">For each region that you need to create, run the **New-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="867c8-118">Например, чтобы создать регион для Северной Америки, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="867c8-118">For example, to create the North America region, run:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  <span data-ttu-id="867c8-119">Повторите шаг 2, чтобы создать сетевые регионы, EMEA и APAC.</span><span class="sxs-lookup"><span data-stu-id="867c8-119">Repeat step 2 to create the network regions, EMEA and APAC.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

