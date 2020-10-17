---
title: 'Lync Server 2013: Проверка физической среды'
description: 'Lync Server 2013: проверьте физическую среду.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Performing physical environmental checks
ms:assetid: 153aee5e-3adf-4dbf-bf41-53e4fba51fb0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720558(v=OCS.15)
ms:contentKeyID: 63969582
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d963485b109e0afdf21b3a9085fa28884dfc3100
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543555"
---
# <a name="performing-physical-environmental-checks"></a><span data-ttu-id="cf092-103">Выполнение проверки физической среды</span><span class="sxs-lookup"><span data-stu-id="cf092-103">Performing physical environmental checks</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf092-104">_**Последнее изменение темы:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="cf092-104">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="cf092-105">Прежде чем проверять производительность, доступность и функциональные возможности развертывания Lync Server 2013, следует проверить физическую среду.</span><span class="sxs-lookup"><span data-stu-id="cf092-105">Before checking the performance, availability, and functionality of the Lync Server 2013 deployment, you should check the physical environment.</span></span> <span data-ttu-id="cf092-106">Например, температура для помещения на сервер может быть меньше или может потребоваться замена сетевого кабеля.</span><span class="sxs-lookup"><span data-stu-id="cf092-106">For example, the server room temperature might have to be lowered, or a network cable might have to be replaced.</span></span> <span data-ttu-id="cf092-107">Для достижения лучших результатов выполните следующие физические проверки среды:</span><span class="sxs-lookup"><span data-stu-id="cf092-107">For best results, perform the following physical environmental inspections:</span></span>

  - <span data-ttu-id="cf092-108">**Физические меры безопасности**     Физическая защита безопасности, например блокировки, двери и комнаты с ограниченным доступом, должна быть защищена.</span><span class="sxs-lookup"><span data-stu-id="cf092-108">**Physical security measures**   Physical security protection such as locks, doors, and restricted-access rooms must be secured.</span></span> <span data-ttu-id="cf092-109">Проверьте наличие неавторизованных и принудительных записей и признаки повреждений оборудования.</span><span class="sxs-lookup"><span data-stu-id="cf092-109">Check for any unauthorized and forced entries and signs of equipment damage.</span></span>

  - <span data-ttu-id="cf092-110">**Температура и влажность**     Высокая температура, плохой поток воздуха и влажность могут привести к оверхеат компонентов оборудования.</span><span class="sxs-lookup"><span data-stu-id="cf092-110">**Temperature and humidity**   High temperature, poor air flow, and humidity can cause hardware components to overheat.</span></span> <span data-ttu-id="cf092-111">Проверьте температуру и влажность, чтобы убедиться, что системы окружающей среды, такие как перегрев и Воздушный Кондиционер, могут поддерживать приемлемые условия и работать в соответствии с требованиями производителя оборудования.</span><span class="sxs-lookup"><span data-stu-id="cf092-111">Check temperature and humidity to help to make sure that the environmental systems such as heating and air conditioning can maintain acceptable conditions and function within the hardware manufacturer's specifications.</span></span> <span data-ttu-id="cf092-112">Когда новое оборудование было недавно установлено, также проверьте, что воздушный поток как к серверу, так и к нему не соответствует спецификации производителя.</span><span class="sxs-lookup"><span data-stu-id="cf092-112">When new equipment has recently been installed, also check that air flow both to and from the servers is unimpeded and meets manufacturer spec.</span></span>

  - <span data-ttu-id="cf092-113">**Устройства и компоненты**     Организация Lync Server 2013 использует работающую физическую сеть и связанное с ним оборудование.</span><span class="sxs-lookup"><span data-stu-id="cf092-113">**Devices and components**   The Lync Server 2013 organization relies on a functioning physical network and related hardware.</span></span> <span data-ttu-id="cf092-114">Убедитесь, что маршрутизаторы, коммутаторы, концентраторы, физические Кабели и соединители функционируют.</span><span class="sxs-lookup"><span data-stu-id="cf092-114">Make sure that routers, switches, hubs, physical cables, and connectors are operational.</span></span>

<span data-ttu-id="cf092-115">Сведения о том, как выполнять эти проверки, будут сильно зависеть от сайта установки и выбранного оборудования сервера.</span><span class="sxs-lookup"><span data-stu-id="cf092-115">The specifics on how to perform these checks will depend greatly on your installation site and the server hardware that was chosen.</span></span> <span data-ttu-id="cf092-116">Когда вы впервые выполняете эту проверку, ознакомьтесь с документацией по оборудованию и запишите необходимые параметры для дальнейших ссылок.</span><span class="sxs-lookup"><span data-stu-id="cf092-116">The first time that you perform this check, refer to the hardware documentation and note the desired parameters for future reference.</span></span>

### <a name="desired-server-space-environment"></a><span data-ttu-id="cf092-117">Требуемая среда серверного пространства</span><span class="sxs-lookup"><span data-stu-id="cf092-117">Desired server space environment</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf092-118">Параметр</span><span class="sxs-lookup"><span data-stu-id="cf092-118">Parameter</span></span></th>
<th><span data-ttu-id="cf092-119">Требуемое значение или диапазон</span><span class="sxs-lookup"><span data-stu-id="cf092-119">Desired value or range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf092-120">Рабочая</span><span class="sxs-lookup"><span data-stu-id="cf092-120">Temperature</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf092-121">Хранени</span><span class="sxs-lookup"><span data-stu-id="cf092-121">Humidity</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf092-122">Передние стороны серверов</span><span class="sxs-lookup"><span data-stu-id="cf092-122">Front of server faces</span></span></p></td>
<td><p><span data-ttu-id="cf092-123">Активные проходы/холодный проход</span><span class="sxs-lookup"><span data-stu-id="cf092-123">Hot aisle / cold aisle</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf092-124">Нехватка нехватки зазоров</span><span class="sxs-lookup"><span data-stu-id="cf092-124">Unimpeded exhaust clearance</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

