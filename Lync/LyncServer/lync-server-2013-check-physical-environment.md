---
title: 'Lync Server 2013: проверьте физическую среду'
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
ms.openlocfilehash: 8838e5d3dfd1e3590f7988102f187c49114fc233
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734009"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="performing-physical-environmental-checks"></a><span data-ttu-id="ae77d-102">Выполнение физических проверок окружающей среды</span><span class="sxs-lookup"><span data-stu-id="ae77d-102">Performing physical environmental checks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae77d-103">_**Тема последнего изменения:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="ae77d-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="ae77d-104">Прежде чем проверять производительность, доступность и функциональные возможности развертывания Lync Server 2013, необходимо проверить физическую среду.</span><span class="sxs-lookup"><span data-stu-id="ae77d-104">Before checking the performance, availability, and functionality of the Lync Server 2013 deployment, you should check the physical environment.</span></span> <span data-ttu-id="ae77d-105">Например, может потребоваться уменьшить температуру в комнате сервера или заменить сетевой кабель.</span><span class="sxs-lookup"><span data-stu-id="ae77d-105">For example, the server room temperature might have to be lowered, or a network cable might have to be replaced.</span></span> <span data-ttu-id="ae77d-106">Для достижения наилучших результатов выполните следующие физические проверки среды.</span><span class="sxs-lookup"><span data-stu-id="ae77d-106">For best results, perform the following physical environmental inspections:</span></span>

  - <span data-ttu-id="ae77d-107">**Физическая безопасность**   , например блокировки, дверцы и ограниченные комнаты доступа, должны обеспечивать защиту.</span><span class="sxs-lookup"><span data-stu-id="ae77d-107">**Physical security measures**   Physical security protection such as locks, doors, and restricted-access rooms must be secured.</span></span> <span data-ttu-id="ae77d-108">Проверьте наличие неавторизованных и принудительных операций и признаки повреждений оборудования.</span><span class="sxs-lookup"><span data-stu-id="ae77d-108">Check for any unauthorized and forced entries and signs of equipment damage.</span></span>

  - <span data-ttu-id="ae77d-109">\*\*\*\* Высокая температура и влажность при высокой температуре, плохом потоке воздуха и влажности могут привести к тому, что аппаратные компоненты оверхеат.   </span><span class="sxs-lookup"><span data-stu-id="ae77d-109">**Temperature and humidity**   High temperature, poor air flow, and humidity can cause hardware components to overheat.</span></span> <span data-ttu-id="ae77d-110">Проверьте температуру и влажности, чтобы убедиться в том, что системы окружающей среды, такие как нагревательные и воздушные условия, могут поддерживать приемлемые условия и работать в соответствии с требованиями производителя оборудования.</span><span class="sxs-lookup"><span data-stu-id="ae77d-110">Check temperature and humidity to help to make sure that the environmental systems such as heating and air conditioning can maintain acceptable conditions and function within the hardware manufacturer's specifications.</span></span> <span data-ttu-id="ae77d-111">После установки нового оборудования также убедитесь, что воздушный поток как к серверу, так и от него не соответствует спецификации изготовителя.</span><span class="sxs-lookup"><span data-stu-id="ae77d-111">When new equipment has recently been installed, also check that air flow both to and from the servers is unimpeded and meets manufacturer spec.</span></span>

  - <span data-ttu-id="ae77d-112">**Устройства и компоненты**   . Организация Lync Server 2013 использует работающую физическую сеть и связанное с ним оборудование.</span><span class="sxs-lookup"><span data-stu-id="ae77d-112">**Devices and components**   The Lync Server 2013 organization relies on a functioning physical network and related hardware.</span></span> <span data-ttu-id="ae77d-113">Убедитесь, что на маршрутизаторах, коммутаторах, концентраторах, физических кабелях и соединительных линиях работают.</span><span class="sxs-lookup"><span data-stu-id="ae77d-113">Make sure that routers, switches, hubs, physical cables, and connectors are operational.</span></span>

<span data-ttu-id="ae77d-114">Сведения о том, как выполнять эти проверки, будут сильно зависеть от вашего сайта установки и выбранного оборудования сервера.</span><span class="sxs-lookup"><span data-stu-id="ae77d-114">The specifics on how to perform these checks will depend greatly on your installation site and the server hardware that was chosen.</span></span> <span data-ttu-id="ae77d-115">При первом выполнении этой проверки ознакомьтесь с документацией оборудования и запишите необходимые параметры для использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="ae77d-115">The first time that you perform this check, refer to the hardware documentation and note the desired parameters for future reference.</span></span>

### <a name="desired-server-space-environment"></a><span data-ttu-id="ae77d-116">Нужная среда сервера</span><span class="sxs-lookup"><span data-stu-id="ae77d-116">Desired server space environment</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ae77d-117">Параметр</span><span class="sxs-lookup"><span data-stu-id="ae77d-117">Parameter</span></span></th>
<th><span data-ttu-id="ae77d-118">Нужное значение или диапазон</span><span class="sxs-lookup"><span data-stu-id="ae77d-118">Desired value or range</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae77d-119">Допустим</span><span class="sxs-lookup"><span data-stu-id="ae77d-119">Temperature</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae77d-120">Зарегистрирован</span><span class="sxs-lookup"><span data-stu-id="ae77d-120">Humidity</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae77d-121">Лицевой стороной сервера</span><span class="sxs-lookup"><span data-stu-id="ae77d-121">Front of server faces</span></span></p></td>
<td><p><span data-ttu-id="ae77d-122">Горячий проход/холодный проход</span><span class="sxs-lookup"><span data-stu-id="ae77d-122">Hot aisle / cold aisle</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae77d-123">Нехватка зазоров</span><span class="sxs-lookup"><span data-stu-id="ae77d-123">Unimpeded exhaust clearance</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

