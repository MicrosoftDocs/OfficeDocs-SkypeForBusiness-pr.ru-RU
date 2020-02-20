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
ms.openlocfilehash: b5b2d730181426d5b23463816d13a6f3b0e502b0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146922"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a>Аппаратная поддержка устройств в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-12-14_

Перед развертыванием IP-телефонов и аналоговых устройств необходимо рассмотреть особые конфигурации оборудования.

IP-телефоны с поддержкой Lync Phone Edition протокол обнаружения уровня связи — обнаружение конечных точек мультимедиа (LLDP-MED) и Power over Ethernet (ПОЕ).Чтобы воспользоваться преимуществами протокола LLDP-MED, коммутатор должен поддерживать IEEE802.1AB и ANSI/TIA-1057. Чтобы воспользоваться преимуществами протокола PoE, коммутатор должен поддерживать PoE802.3AF или 802.3at.

Для включения LLDP-MED администратор должен включить LLDP с помощью консоли коммутатора и задать политику сети LLDP-MED с правильным ИД виртуальной локальной сети для голосовых служб.

Кроме того, если в развертывании используются аналоговые устройства, необходимо настроить аналоговый шлюз для использования Lync Server, а шлюз должен быть одним из следующих:

  - Аналоговый телефонный адаптер (ATA)

  - Аналоговый шлюз ТСОП

  - Устройство для обеспечения связи в филиалах, которое содержит аналоговый шлюз ТСОП

  - Устройство для обеспечения связи в филиалах, которое содержит шлюз ТСОП, взаимодействующий с аналоговым телефонным адаптером

Чтобы узнать, как настроить аналоговый шлюз, ознакомьтесь со статьей "Планирование развертывания аналоговых устройств [https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537) " в библиотеке TechNet для Lync Server 2010. (Аналоговые устройства работают аналогичным образом в Lync Server 2013, как в Lync Server 2010.)

<div>


> [!IMPORTANT]  
> Вы можете настроить коммутатор для службы Enhanced 9-1-1 (E9-1-1), если он поддерживает эту службу.



</div>

</div>

<span> </span>

</div>

</div>

</div>

