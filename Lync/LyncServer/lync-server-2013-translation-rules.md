---
title: 'Lync Server 2013: правила перевода'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22b6fbacf068f6a1a388a968989259afec81d17a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a><span data-ttu-id="24a6b-102">Правила перевода в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24a6b-102">Translation rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24a6b-103">_**Тема последнего изменения:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="24a6b-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="24a6b-104">Для Lync Server 2013 Enterprise Voice требуется, чтобы все строки набора номера были нормализованы в формат E. 164 для целей обратного просмотра номера (РНЛ).</span><span class="sxs-lookup"><span data-stu-id="24a6b-104">Lync Server 2013 Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="24a6b-105">В Microsoft Lync Server 2010 правила перевода поддерживаются только для вызываемых номеров.</span><span class="sxs-lookup"><span data-stu-id="24a6b-105">In Microsoft Lync Server 2010, translation rules are supported only for called numbers.</span></span> <span data-ttu-id="24a6b-106">Новые возможности Microsoft Lync Server 2013 для звонков также поддерживаются правила перевода.</span><span class="sxs-lookup"><span data-stu-id="24a6b-106">New in Microsoft Lync Server 2013, translation rules are also supported for calling numbers.</span></span> <span data-ttu-id="24a6b-107">Для *магистрального однорангового узла* (т.е. связанного шлюза, УАТС или SIP-канала) может потребоваться, чтобы номера были в формате местного набора.</span><span class="sxs-lookup"><span data-stu-id="24a6b-107">The *trunk peer* (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="24a6b-108">Чтобы преобразовать номера из формата E.164 в формат местного набора, вы можете установить правила преобразования для работы с URI запроса перед его направлением в магистральный узел.</span><span class="sxs-lookup"><span data-stu-id="24a6b-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="24a6b-109">Например, можно написать правило преобразования, чтобы заменить +44 в начале строки набора на 0144.</span><span class="sxs-lookup"><span data-stu-id="24a6b-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="24a6b-110">Выполняя преобразование исходящего маршрута на сервере, вы можете снизить требования конфигурации в каждом отдельном магистральном узле для трансляции телефонных номеров в формат местного набора.</span><span class="sxs-lookup"><span data-stu-id="24a6b-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="24a6b-111">При планировании выбора шлюзов и количества шлюзов, связанных с определенным кластером серверов обновлений, может быть полезно сгруппировать одноранговые узлы с использованием одинаковых местных требований для набора номера.</span><span class="sxs-lookup"><span data-stu-id="24a6b-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="24a6b-112">Это позволяет сократить количество необходимых правил преобразования и сэкономить время, затрачиваемое на их создание.</span><span class="sxs-lookup"><span data-stu-id="24a6b-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="24a6b-113">Связывание одного или нескольких правил трансляции с конфигурацией магистрали корпоративной голосовой связи следует использовать в качестве альтернативы настройке правил перевода на магистральном одноранговом узле.</span><span class="sxs-lookup"><span data-stu-id="24a6b-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="24a6b-114">Не применяйте правила перевода с конфигурацией корпоративной магистрали, если вы настроили правила трансляции для однорангового канала, так как эти правила могут конфликтовать.</span><span class="sxs-lookup"><span data-stu-id="24a6b-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>



</div>

<div>

## <a name="example-translation-rules"></a><span data-ttu-id="24a6b-115">Примеры правил преобразования</span><span class="sxs-lookup"><span data-stu-id="24a6b-115">Example Translation Rules</span></span>

<span data-ttu-id="24a6b-116">Следующие примеры правил преобразования показывают, как можно разрабатывать правила на сервере для преобразования номеров из формата E.164 в местный формат для магистрального узла.</span><span class="sxs-lookup"><span data-stu-id="24a6b-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="24a6b-117">Подробнее о том, как применять правила перевода, можно найти [в разделе Определение правил перевода в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="24a6b-117">For details about how to implement translation rules, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24a6b-118">Описание</span><span class="sxs-lookup"><span data-stu-id="24a6b-118">Description</span></span></th>
<th><span data-ttu-id="24a6b-119">Цифры в начале</span><span class="sxs-lookup"><span data-stu-id="24a6b-119">Starting Digits</span></span></th>
<th><span data-ttu-id="24a6b-120">Длина</span><span class="sxs-lookup"><span data-stu-id="24a6b-120">Length</span></span></th>
<th><span data-ttu-id="24a6b-121">Цифры для удаления</span><span class="sxs-lookup"><span data-stu-id="24a6b-121">Digits to Remove</span></span></th>
<th><span data-ttu-id="24a6b-122">Цифры для добавления</span><span class="sxs-lookup"><span data-stu-id="24a6b-122">Digits to Add</span></span></th>
<th><span data-ttu-id="24a6b-123">Шаблон соответствия</span><span class="sxs-lookup"><span data-stu-id="24a6b-123">Matching Pattern</span></span></th>
<th><span data-ttu-id="24a6b-124">Преобразование</span><span class="sxs-lookup"><span data-stu-id="24a6b-124">Translation</span></span></th>
<th><span data-ttu-id="24a6b-125">Пример</span><span class="sxs-lookup"><span data-stu-id="24a6b-125">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24a6b-126">Обычный междугородний звонок в США</span><span class="sxs-lookup"><span data-stu-id="24a6b-126">Conventional long-distance dialing in U.S.</span></span></p>
<p><span data-ttu-id="24a6b-127">(убирается ‘+’)</span><span class="sxs-lookup"><span data-stu-id="24a6b-127">(strip out the ‘+’)</span></span></p></td>
<td><p><span data-ttu-id="24a6b-128">+1</span><span class="sxs-lookup"><span data-stu-id="24a6b-128">+1</span></span></p></td>
<td><p><span data-ttu-id="24a6b-129">Ровно 12</span><span class="sxs-lookup"><span data-stu-id="24a6b-129">Exactly 12</span></span></p></td>
<td><p><span data-ttu-id="24a6b-130">1</span><span class="sxs-lookup"><span data-stu-id="24a6b-130">1</span></span></p></td>
<td><p><span data-ttu-id="24a6b-131">до</span><span class="sxs-lookup"><span data-stu-id="24a6b-131">0</span></span></p></td>
<td><p><span data-ttu-id="24a6b-132">^\+(1 \ d{10}) $</span><span class="sxs-lookup"><span data-stu-id="24a6b-132">^\+(1\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="24a6b-133">$1</span><span class="sxs-lookup"><span data-stu-id="24a6b-133">$1</span></span></p></td>
<td><p><span data-ttu-id="24a6b-134">+14255551010 преобразуется в 14255551010</span><span class="sxs-lookup"><span data-stu-id="24a6b-134">+14255551010 becomes 14255551010</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24a6b-135">Международный звонок из США</span><span class="sxs-lookup"><span data-stu-id="24a6b-135">U.S. international long-distance dialing</span></span></p>
<p><span data-ttu-id="24a6b-136">(убирается "+" и добавляются цифры 011)</span><span class="sxs-lookup"><span data-stu-id="24a6b-136">(strip out ‘+’ and add 011)</span></span></p></td>
<td><p>+</p></td>
<td><p><span data-ttu-id="24a6b-137">Не менее 11</span><span class="sxs-lookup"><span data-stu-id="24a6b-137">At least 11</span></span></p></td>
<td><p><span data-ttu-id="24a6b-138">1</span><span class="sxs-lookup"><span data-stu-id="24a6b-138">1</span></span></p></td>
<td><p><span data-ttu-id="24a6b-139">011</span><span class="sxs-lookup"><span data-stu-id="24a6b-139">011</span></span></p></td>
<td><p><span data-ttu-id="24a6b-140">^\+(\d{9}\d +) $</span><span class="sxs-lookup"><span data-stu-id="24a6b-140">^\+(\d{9}\d+)$</span></span></p></td>
<td><p><span data-ttu-id="24a6b-141">011$1</span><span class="sxs-lookup"><span data-stu-id="24a6b-141">011$1</span></span></p></td>
<td><p><span data-ttu-id="24a6b-142">+441235551010 преобразуется в 011441235551010</span><span class="sxs-lookup"><span data-stu-id="24a6b-142">+441235551010 becomes 011441235551010</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

