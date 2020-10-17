---
title: 'Lync Server 2013: планирование и настройка IPv6'
description: 'Lync Server 2013: планирование и настройка IPv6.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for and configuring IPv6
ms:assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204624(v=OCS.15)
ms:contentKeyID: 48183236
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c63268bd92fc9d3b683cfa05ab49f01ea56d6ba
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554365"
---
# <a name="planning-for-and-configuring-ipv6-in-lync-server-2013"></a><span data-ttu-id="730fe-103">Планирование и настройка IPv6 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="730fe-103">Planning for and configuring IPv6 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="730fe-104">_**Последнее изменение темы:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="730fe-104">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="730fe-105">Lync Server 2013 включает поддержку адресов IP версии 6 (IPv6), а также продолжает поддержку адресов IP версии 4 (IPv4).</span><span class="sxs-lookup"><span data-stu-id="730fe-105">Lync Server 2013 includes support for IP version 6 (IPv6) addresses, along with continued support of IP version 4 (IPv4) addresses.</span></span> <span data-ttu-id="730fe-106">Адреса IPv4 — 32-разрядные адреса, которые позволяют компьютеру осуществлять взаимодействие через Интернет.</span><span class="sxs-lookup"><span data-stu-id="730fe-106">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="730fe-107">В связи с увеличением числа устройств по всему миру доступные IPv4-адреса исходящиеся. В связи с этим многие новые устройства перемещаются на адреса IPv6.</span><span class="sxs-lookup"><span data-stu-id="730fe-107">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span> <span data-ttu-id="730fe-108">Адреса IPv6 выполняют ту же задачу, что и адреса IPv4 (с некоторыми дополнительными возможностями), но вместо использования 32 бит в адресах IPv6 используется 128 бит.</span><span class="sxs-lookup"><span data-stu-id="730fe-108">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="730fe-109">Это не только предоставляет новый набор адресов, но существенно увеличивает их количество.</span><span class="sxs-lookup"><span data-stu-id="730fe-109">This provides not only a new set of addresses, but also a much larger number of them.</span></span> <span data-ttu-id="730fe-110">Типичный адрес IPv4 выглядит следующим образом: 192.0.2.235, в то время как адрес IPv6 выглядит следующим образом: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span><span class="sxs-lookup"><span data-stu-id="730fe-110">A typical IPv4 address looks something like this: 192.0.2.235, whereas an IPv6 address looks like this: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span></span> <span data-ttu-id="730fe-111">Изменение форматирования и функциональных возможностей для устройств, использующих IPv6-адреса, требует нескольких рекомендаций по развертыванию и настройке в установке Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="730fe-111">The change in formatting and functionality for devices that use IPv6 addresses requires several deployment and configuration considerations in your Lync Server 2013 installation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="730fe-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="730fe-112">In This Section</span></span>

  - [<span data-ttu-id="730fe-113">Обзор типов IP-адресов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="730fe-113">Overview of IP address types for Lync Server 2013</span></span>](lync-server-2013-overview-of-ip-address-types.md)

  - [<span data-ttu-id="730fe-114">Технические требования для IPv6 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="730fe-114">Technical requirements for IPv6 in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-ipv6.md)

  - [<span data-ttu-id="730fe-115">Вопросы миграции и сосуществования для IPv6 в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="730fe-115">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>](lync-server-2013-migration-and-coexistence-considerations-for-ipv6.md)

  - [<span data-ttu-id="730fe-116">Настройка типов IP-адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="730fe-116">Configure IP address types in Lync Server 2013</span></span>](lync-server-2013-configure-ip-address-types.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

