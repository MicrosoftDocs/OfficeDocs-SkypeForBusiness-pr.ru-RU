---
title: 'Lync Server 2013: контроль допуска звонков на магистральной линии SIP'
description: 'Lync Server 2013: контроль допуска звонков в магистрали SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on a SIP trunk
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398632(v=OCS.15)
ms:contentKeyID: 48184623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3667ef4608b221a1607b6bbe0d89d390cb1dd402
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563165"
---
# <a name="call-admission-control-on-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="f0672-103">Контроль допуска звонков на магистральной линии SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0672-103">Call admission control on a SIP trunk in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0672-104">_**Последнее изменение темы:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="f0672-104">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="f0672-p101">Для развертывания контроля допуска звонков в канал SIP создается сетевой узел, который представляет поставщика услуг Интернет-телефонии (ITSP). Для применения значений политики пропускной способности в канале SIP создается межузловая политика между сетевым узлом в предприятии и сетевым узлом, созданным для представления ITSP.</span><span class="sxs-lookup"><span data-stu-id="f0672-p101">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="f0672-107">На следующем рисунке показан пример развертывания контроля допуска звонков в канале SIP.</span><span class="sxs-lookup"><span data-stu-id="f0672-107">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="f0672-108">**Конфигурация контроля допуска звонков в канале SIP**</span><span class="sxs-lookup"><span data-stu-id="f0672-108">**CAC configuration on a SIP trunk**</span></span>

<span data-ttu-id="f0672-109">![Схема распределения каналов SIP управления допуском звонков](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Схема распределения каналов SIP управления допуском звонков")</span><span class="sxs-lookup"><span data-stu-id="f0672-109">![Call Admission Control SIP Trunking diagram](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Call Admission Control SIP Trunking diagram")</span></span>

<span data-ttu-id="f0672-110">Чтобы настроить контроль допуска звонков в канале SIP, во время развертывания контроля допуска звонков необходимо выполнить следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="f0672-110">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1.  <span data-ttu-id="f0672-111">Создать сетевой узел, представляющий поставщика услуг Интернет-телефонии (ITSP).</span><span class="sxs-lookup"><span data-stu-id="f0672-111">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="f0672-112">Связать этот сетевой узел с соответствующей областью сети и выделить в этом сетевом узле нулевую пропускную способность для аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="f0672-112">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="f0672-113">Подробнее: [Настройка сетевых сайтов для контроля допуска звонков в Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="f0672-113">For details, see [Configure network sites for CAC in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f0672-114">Для ITSP конфигурация этого сетевого узла не функциональна.</span><span class="sxs-lookup"><span data-stu-id="f0672-114">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="f0672-115">Значения политики пропускной способности фактически применяются в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="f0672-115">Bandwidth policy values are actually applied in step 2.</span></span>

    
    </div>

2.  <span data-ttu-id="f0672-116">Создайте межсайтовую связь для магистрали SIP с использованием соответствующих значений параметров для сайта, созданного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="f0672-116">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="f0672-117">Например, используйте имя сетевого сайта в Организации в качестве значения параметра NetworkSiteID1 и сетевой сайт ITSP в качестве значения параметра NetworkSiteID2.</span><span class="sxs-lookup"><span data-stu-id="f0672-117">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="f0672-118">Дополнительные сведения приведены в статье [CREATE Network для межсайтовых политик в Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="f0672-118">For details, see [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="f0672-119">Кроме того, для командлета New-CsNetworkInterSitePolicy обратитесь к документации по командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f0672-119">Also see the Lync Server Management Shell documentation for the New-CsNetworkInterSitePolicy cmdlet.</span></span>

3.  <span data-ttu-id="f0672-120">Получить IP-адрес точки завершения мультимедиа пограничного контроллера сеансов (SCB) у своего поставщика услуг Интернет-телефонии (ITSP).</span><span class="sxs-lookup"><span data-stu-id="f0672-120">Get the IP address of the Session Border Controller’s (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="f0672-121">Добавить этот IP-адрес с маской подсети 32 к сетевому узлу, представляющему ITSP.</span><span class="sxs-lookup"><span data-stu-id="f0672-121">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="f0672-122">Дополнительные сведения см. [в разделе Связывание подсети с сетевым сайтом в Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="f0672-122">For details, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

