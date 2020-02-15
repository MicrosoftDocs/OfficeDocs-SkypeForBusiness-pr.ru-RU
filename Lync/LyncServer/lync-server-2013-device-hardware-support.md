---
title: Lync Server 2013 — поддержка оборудования устройств
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
ms.openlocfilehash: e0b4b0f24523044169ae3274ae4d0ff16ae9ff67
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a><span data-ttu-id="f55e7-102">Аппаратная поддержка устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f55e7-102">Device hardware support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f55e7-103">_**Последнее изменение темы:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="f55e7-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="f55e7-104">Перед развертыванием IP-телефонов и аналоговых устройств необходимо рассмотреть особые конфигурации оборудования.</span><span class="sxs-lookup"><span data-stu-id="f55e7-104">Specific hardware configurations must be in place before you deploy IP phones and analog devices.</span></span>

<span data-ttu-id="f55e7-105">IP-телефоны с поддержкой Lync Phone Edition протокол обнаружения уровня связи — обнаружение конечных точек мультимедиа (LLDP-MED) и Power over Ethernet (ПОЕ).</span><span class="sxs-lookup"><span data-stu-id="f55e7-105">IP phones running Lync Phone Edition support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) and Power over Ethernet (PoE).</span></span><span data-ttu-id="f55e7-106">Чтобы воспользоваться преимуществами протокола LLDP-MED, коммутатор должен поддерживать IEEE802.1AB и ANSI/TIA-1057.</span><span class="sxs-lookup"><span data-stu-id="f55e7-106"> To take advantage of LLDP-MED, the switch must support IEEE802.1AB and ANSI/TIA-1057.</span></span> <span data-ttu-id="f55e7-107">Чтобы воспользоваться преимуществами протокола PoE, коммутатор должен поддерживать PoE802.3AF или 802.3at.</span><span class="sxs-lookup"><span data-stu-id="f55e7-107">To take advantage of PoE, the switch must support PoE802.3AF or 802.3at.</span></span>

<span data-ttu-id="f55e7-108">Для включения LLDP-MED администратор должен включить LLDP с помощью консоли коммутатора и задать политику сети LLDP-MED с правильным ИД виртуальной локальной сети для голосовых служб.</span><span class="sxs-lookup"><span data-stu-id="f55e7-108">To enable LLDP-MED, the administrator must enable LLDP by using the switch console window and set the LLDP-MED network policy with the correct voice VLAN ID.</span></span>

<span data-ttu-id="f55e7-109">Кроме того, если в развертывании используются аналоговые устройства, необходимо настроить аналоговый шлюз для использования Lync Server, а шлюз должен быть одним из следующих:</span><span class="sxs-lookup"><span data-stu-id="f55e7-109">In addition, if your deployment includes analog devices, you must configure the analog gateway to use Lync Server, and the gateway must be one of the following:</span></span>

  - <span data-ttu-id="f55e7-110">Аналоговый телефонный адаптер (ATA)</span><span class="sxs-lookup"><span data-stu-id="f55e7-110">An analog telephone adapter (ATA)</span></span>

  - <span data-ttu-id="f55e7-111">Аналоговый шлюз ТСОП</span><span class="sxs-lookup"><span data-stu-id="f55e7-111">A PSTN analog gateway</span></span>

  - <span data-ttu-id="f55e7-112">Устройство для обеспечения связи в филиалах, которое содержит аналоговый шлюз ТСОП</span><span class="sxs-lookup"><span data-stu-id="f55e7-112">A Survivable Branch Appliance that includes a PSTN analog gateway</span></span>

  - <span data-ttu-id="f55e7-113">Устройство для обеспечения связи в филиалах, которое содержит шлюз ТСОП, взаимодействующий с аналоговым телефонным адаптером</span><span class="sxs-lookup"><span data-stu-id="f55e7-113">A Survivable Branch Appliance that includes a PSTN gateway that communicates with an ATA</span></span>

<span data-ttu-id="f55e7-114">Чтобы узнать, как настроить аналоговый шлюз, ознакомьтесь со статьей "Планирование развертывания аналоговых устройств [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) " в библиотеке TechNet для Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f55e7-114">To learn how to configure an analog gateway, see "Planning to Deploy Analog Devices" at [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="f55e7-115">(Аналоговые устройства работают аналогичным образом в Lync Server 2013, как в Lync Server 2010.)</span><span class="sxs-lookup"><span data-stu-id="f55e7-115">(Analog devices work the same way in Lync Server 2013 as they do in Lync Server 2010.)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f55e7-116">Вы можете настроить коммутатор для службы Enhanced 9-1-1 (E9-1-1), если он поддерживает эту службу.</span><span class="sxs-lookup"><span data-stu-id="f55e7-116">You can configure the switch for Enhanced 9-1-1 (E9-1-1), if the switch supports this.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

