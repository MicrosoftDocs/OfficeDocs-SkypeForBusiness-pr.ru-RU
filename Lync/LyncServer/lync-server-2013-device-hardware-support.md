---
title: 'Lync Server 2013: поддержка аппаратных устройств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device hardware support
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412908(v=OCS.15)
ms:contentKeyID: 48185222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da92e5f8d37ae5112ccea2d2b33f7f2b0186dfcf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a><span data-ttu-id="6e177-102">Поддержка аппаратных устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e177-102">Device hardware support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e177-103">_**Тема последнего изменения:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="6e177-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="6e177-104">Перед развертыванием IP-телефонов и аналоговых устройств необходимо установить определенные конфигурации оборудования.</span><span class="sxs-lookup"><span data-stu-id="6e177-104">Specific hardware configurations must be in place before you deploy IP phones and analog devices.</span></span>

<span data-ttu-id="6e177-105">IP-телефоны, поддерживающие Lync Phone Edition протокол обнаружения уровня связи — обнаружение конечной точки мультимедиа (LLDP-MED) и Power over Ethernet (PoE).</span><span class="sxs-lookup"><span data-stu-id="6e177-105">IP phones running Lync Phone Edition support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) and Power over Ethernet (PoE).</span></span><span data-ttu-id="6e177-106">Чтобы воспользоваться преимуществами LLDP-MED, коммутатор должен поддерживать IEEE 802.1 AB и ANSI/Тиа-1057.</span><span class="sxs-lookup"><span data-stu-id="6e177-106"> To take advantage of LLDP-MED, the switch must support IEEE802.1AB and ANSI/TIA-1057.</span></span> <span data-ttu-id="6e177-107">Чтобы воспользоваться преимуществами PoE, коммутатор должен поддерживать PoE 802.3 AF или 802.3 по адресу.</span><span class="sxs-lookup"><span data-stu-id="6e177-107">To take advantage of PoE, the switch must support PoE802.3AF or 802.3at.</span></span>

<span data-ttu-id="6e177-108">Чтобы включить LLDP-MED, администратор должен включить LLDP с помощью окна переключения консоли и настройте сетевую политику LLDP-MED с правильным ИДЕНТИФИКАТОРом виртуальной ЛС для голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="6e177-108">To enable LLDP-MED, the administrator must enable LLDP by using the switch console window and set the LLDP-MED network policy with the correct voice VLAN ID.</span></span>

<span data-ttu-id="6e177-109">Кроме того, если в развертывании используются аналоговые устройства, необходимо настроить аналоговый шлюз для использования Lync Server, а шлюз должен быть одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="6e177-109">In addition, if your deployment includes analog devices, you must configure the analog gateway to use Lync Server, and the gateway must be one of the following:</span></span>

  - <span data-ttu-id="6e177-110">Аналоговый телефонный адаптер (ATA)</span><span class="sxs-lookup"><span data-stu-id="6e177-110">An analog telephone adapter (ATA)</span></span>

  - <span data-ttu-id="6e177-111">Аналоговый шлюз PSTN</span><span class="sxs-lookup"><span data-stu-id="6e177-111">A PSTN analog gateway</span></span>

  - <span data-ttu-id="6e177-112">Бесперебойно работающее устройство филиалов, включающее аналоговый шлюз PSTN</span><span class="sxs-lookup"><span data-stu-id="6e177-112">A Survivable Branch Appliance that includes a PSTN analog gateway</span></span>

  - <span data-ttu-id="6e177-113">Бесперебойно работающее устройство филиалов, которое включает шлюз PSTN, взаимодействующий с ATA.</span><span class="sxs-lookup"><span data-stu-id="6e177-113">A Survivable Branch Appliance that includes a PSTN gateway that communicates with an ATA</span></span>

<span data-ttu-id="6e177-114">Сведения о настройке аналогового шлюза можно найти в статье Планирование развертывания аналоговых устройств на сайте [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) Lync Server 2010 в библиотеке TechNet.</span><span class="sxs-lookup"><span data-stu-id="6e177-114">To learn how to configure an analog gateway, see "Planning to Deploy Analog Devices" at [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="6e177-115">(Аналоговые устройства работают аналогичным образом в Lync Server 2013, как это делается в Lync Server 2010.)</span><span class="sxs-lookup"><span data-stu-id="6e177-115">(Analog devices work the same way in Lync Server 2013 as they do in Lync Server 2010.)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6e177-116">Вы можете настроить переключатель для улучшенной 9-1-1 (E9-1-1), если она поддерживается коммутатором.</span><span class="sxs-lookup"><span data-stu-id="6e177-116">You can configure the switch for Enhanced 9-1-1 (E9-1-1), if the switch supports this.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

