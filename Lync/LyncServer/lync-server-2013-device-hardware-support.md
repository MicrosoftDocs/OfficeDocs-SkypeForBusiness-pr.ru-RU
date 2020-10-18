---
title: Lync Server 2013 — поддержка оборудования устройств
description: 'Lync Server 2013: поддержка оборудования устройств.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device hardware support
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412908(v=OCS.15)
ms:contentKeyID: 48185222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd03936d35fbc3a639a3ba4596a4357e8e379719
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575665"
---
# <a name="device-hardware-support-in-lync-server-2013"></a><span data-ttu-id="942d3-103">Аппаратная поддержка устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="942d3-103">Device hardware support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="942d3-104">_**Последнее изменение темы:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="942d3-104">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="942d3-105">Перед развертыванием IP-телефонов и аналоговых устройств необходимо рассмотреть особые конфигурации оборудования.</span><span class="sxs-lookup"><span data-stu-id="942d3-105">Specific hardware configurations must be in place before you deploy IP phones and analog devices.</span></span>

<span data-ttu-id="942d3-106">IP-телефоны с Lync Phone Edition поддерживают обнаружение уровня связи Protocol-Media обнаружение конечных точек (LLDP-MED) и Power over Ethernet (ПОЕ).</span><span class="sxs-lookup"><span data-stu-id="942d3-106">IP phones running Lync Phone Edition support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) and Power over Ethernet (PoE).</span></span><span data-ttu-id="942d3-107">Чтобы воспользоваться преимуществами протокола LLDP-MED, коммутатор должен поддерживать IEEE802.1AB и ANSI/TIA-1057.</span><span class="sxs-lookup"><span data-stu-id="942d3-107"> To take advantage of LLDP-MED, the switch must support IEEE802.1AB and ANSI/TIA-1057.</span></span> <span data-ttu-id="942d3-108">Чтобы воспользоваться преимуществами протокола PoE, коммутатор должен поддерживать PoE802.3AF или 802.3at.</span><span class="sxs-lookup"><span data-stu-id="942d3-108">To take advantage of PoE, the switch must support PoE802.3AF or 802.3at.</span></span>

<span data-ttu-id="942d3-109">Для включения LLDP-MED администратор должен включить LLDP с помощью консоли коммутатора и задать политику сети LLDP-MED с правильным ИД виртуальной локальной сети для голосовых служб.</span><span class="sxs-lookup"><span data-stu-id="942d3-109">To enable LLDP-MED, the administrator must enable LLDP by using the switch console window and set the LLDP-MED network policy with the correct voice VLAN ID.</span></span>

<span data-ttu-id="942d3-110">Кроме того, если в развертывании используются аналоговые устройства, необходимо настроить аналоговый шлюз для использования Lync Server, а шлюз должен быть одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="942d3-110">In addition, if your deployment includes analog devices, you must configure the analog gateway to use Lync Server, and the gateway must be one of the following:</span></span>

  - <span data-ttu-id="942d3-111">Аналоговый телефонный адаптер (ATA)</span><span class="sxs-lookup"><span data-stu-id="942d3-111">An analog telephone adapter (ATA)</span></span>

  - <span data-ttu-id="942d3-112">Аналоговый шлюз ТСОП</span><span class="sxs-lookup"><span data-stu-id="942d3-112">A PSTN analog gateway</span></span>

  - <span data-ttu-id="942d3-113">Устройство для обеспечения связи в филиалах, которое содержит аналоговый шлюз ТСОП</span><span class="sxs-lookup"><span data-stu-id="942d3-113">A Survivable Branch Appliance that includes a PSTN analog gateway</span></span>

  - <span data-ttu-id="942d3-114">Устройство для обеспечения связи в филиалах, которое содержит шлюз ТСОП, взаимодействующий с аналоговым телефонным адаптером</span><span class="sxs-lookup"><span data-stu-id="942d3-114">A Survivable Branch Appliance that includes a PSTN gateway that communicates with an ATA</span></span>

<span data-ttu-id="942d3-115">Чтобы узнать, как настроить аналоговый шлюз, ознакомьтесь со статьей "Планирование развертывания аналоговых устройств" [https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537) в библиотеке TechNet для Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="942d3-115">To learn how to configure an analog gateway, see "Planning to Deploy Analog Devices" at [https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="942d3-116">(Аналоговые устройства работают аналогичным образом в Lync Server 2013, как в Lync Server 2010.)</span><span class="sxs-lookup"><span data-stu-id="942d3-116">(Analog devices work the same way in Lync Server 2013 as they do in Lync Server 2010.)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="942d3-117">Вы можете настроить коммутатор для службы Enhanced 9-1-1 (E9-1-1), если он поддерживает эту службу.</span><span class="sxs-lookup"><span data-stu-id="942d3-117">You can configure the switch for Enhanced 9-1-1 (E9-1-1), if the switch supports this.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

