---
title: 'Lync Server 2013: контроль допуска звонков на канале SIP'
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
ms.openlocfilehash: ab8196070bbb7992aed915cf188d67e95912524a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-a-sip-trunk-in-lync-server-2013"></a><span data-ttu-id="75598-102">Контроль допуска звонков на канале SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75598-102">Call admission control on a SIP trunk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75598-103">_**Тема последнего изменения:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="75598-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="75598-p101">Для развертывания контроля допуска звонков в магистрали SIP создается сетевой сайт, который представляет поставщика услуг интернет-телефонии (ITSP). Для применения значений политики пропускной способности в магистрали SIP создается межсайтовая политика между сетевым сайтом на предприятии и сетевым сайтом, созданным для представления ITSP.</span><span class="sxs-lookup"><span data-stu-id="75598-p101">To deploy call admission control (CAC) on a SIP trunk, you create a network site to represent the Internet telephony service provider (ITSP). To apply bandwidth policy values on the SIP trunk, you create an inter-site policy between the network site in your enterprise and the network site that you create to represent the ITSP.</span></span>

<span data-ttu-id="75598-106">На следующем рисунке показан пример развертывания контроля допуска звонков в магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="75598-106">The following figure shows an example CAC deployment on a SIP trunk.</span></span>

<span data-ttu-id="75598-107">**Конфигурация контроля допуска звонков в магистрали SIP**</span><span class="sxs-lookup"><span data-stu-id="75598-107">**CAC configuration on a SIP trunk**</span></span>

<span data-ttu-id="75598-108">![Контроль допуска звонков с распределением каналов SIP (схема)](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Контроль допуска звонков с распределением каналов SIP (схема)")</span><span class="sxs-lookup"><span data-stu-id="75598-108">![Call Admission Control SIP Trunking diagram](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Call Admission Control SIP Trunking diagram")</span></span>

<span data-ttu-id="75598-109">Чтобы настроить контроль допуска звонков в магистрали SIP, во время развертывания контроля допуска звонков необходимо выполнить следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="75598-109">To configure CAC on a SIP trunk, you will have to perform the following tasks during CAC deployment:</span></span>

1.  <span data-ttu-id="75598-110">Создать сетевой сайт для представления поставщика услуг интернет-телефонии (ITSP).</span><span class="sxs-lookup"><span data-stu-id="75598-110">Create a network site to represent the ITSP.</span></span> <span data-ttu-id="75598-111">Вписать этот сетевой сайт в соответствующий сетевую область и выделить для этого сетевого сайта нулевую пропускную способность для аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="75598-111">Associate the network site to an appropriate network region, and allocate bandwidth of zero for audio and video for this network site.</span></span> <span data-ttu-id="75598-112">Подробности можно найти [в разделе Настройка сайтов сети для CAC в среде Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="75598-112">For details, see [Configure network sites for CAC in Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) in the Deployment documentation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="75598-113">Для ITSP конфигурация этого сетевого сайта не функциональна.</span><span class="sxs-lookup"><span data-stu-id="75598-113">For the ITSP, this network site configuration is not functional.</span></span> <span data-ttu-id="75598-114">Значения политики пропускной способности фактически применяются в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="75598-114">Bandwidth policy values are actually applied in step 2.</span></span>

    
    </div>

2.  <span data-ttu-id="75598-115">Создать межсайтовую связь для магистрали SIP с помощью соответствующих значений параметров для сайта, созданного на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="75598-115">Create an inter-site link for the SIP trunk using the relevant parameter values for the site you created in step 1.</span></span> <span data-ttu-id="75598-116">Например, можно указать имя этого сетевого сайта на предприятии в качестве значения параметра NetworkSiteID1, а имя сетевого сайта ITSP — в качестве значения параметра NetworkSiteID2.</span><span class="sxs-lookup"><span data-stu-id="75598-116">For example, use the name of the network site in your enterprise as the value of the NetworkSiteID1 parameter, and the ITSP network site as the value of the NetworkSiteID2 parameter.</span></span> <span data-ttu-id="75598-117">Дополнительные сведения можно найти [в разделе Создание политик межсетевого соединения в Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="75598-117">For details, see [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="75598-118">Дополнительные сведения о командлете New-Кснетворкинтерситеполици можно найти в документации по командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="75598-118">Also see the Lync Server Management Shell documentation for the New-CsNetworkInterSitePolicy cmdlet.</span></span>

3.  <span data-ttu-id="75598-119">Получить IP-адрес оконечной точки мультимедиа (MTP) пограничного контроллера сеансов (SCB) у своего поставщика услуг интернет-телефонии (ITSP).</span><span class="sxs-lookup"><span data-stu-id="75598-119">Get the IP address of the Session Border Controller’s (SCB) Media Termination Point from your ITSP.</span></span> <span data-ttu-id="75598-120">Добавить этот IP-адрес с маской подсети 32 к сетевому сайту, представляющему ITSP.</span><span class="sxs-lookup"><span data-stu-id="75598-120">Add that IP address with a subnet mask of 32 to the network site that represents the ITSP.</span></span> <span data-ttu-id="75598-121">Дополнительные сведения можно найти [в разделе Связывание подсети с сетевым сайтом в Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="75598-121">For details, see [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

