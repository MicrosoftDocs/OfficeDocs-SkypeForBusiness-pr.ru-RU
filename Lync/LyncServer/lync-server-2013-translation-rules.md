---
title: 'Lync Server 2013: правила преобразования'
description: 'Lync Server 2013: правила преобразования.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65ee21459123ea09f54eb52e65a4d9ecba61c386
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549045"
---
# <a name="translation-rules-in-lync-server-2013"></a><span data-ttu-id="29261-103">Правила преобразования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29261-103">Translation rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29261-104">_**Последнее изменение темы:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="29261-104">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="29261-105">Lync Server 2013 Enterprise Voice требует, чтобы все строки набора номера были нормализованы до формата E. 164 для выполнения обратного просмотра номера (RNL).</span><span class="sxs-lookup"><span data-stu-id="29261-105">Lync Server 2013 Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="29261-106">В Microsoft Lync Server 2010 правила преобразования поддерживаются только для вызываемых номеров.</span><span class="sxs-lookup"><span data-stu-id="29261-106">In Microsoft Lync Server 2010, translation rules are supported only for called numbers.</span></span> <span data-ttu-id="29261-107">В Microsoft Lync Server 2013 правила преобразования также поддерживаются для номеров звонков.</span><span class="sxs-lookup"><span data-stu-id="29261-107">New in Microsoft Lync Server 2013, translation rules are also supported for calling numbers.</span></span> <span data-ttu-id="29261-108">*Магистральный узел* (т.е. соответствующий шлюз, УАТС или канал SIP) может требовать, чтобы номера были в формате местного набора.</span><span class="sxs-lookup"><span data-stu-id="29261-108">The *trunk peer* (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="29261-109">Чтобы преобразовать номера из формата E.164 в формат местного набора, можно определить правила преобразования для работы с URI запроса перед его направлением в магистральный узел.</span><span class="sxs-lookup"><span data-stu-id="29261-109">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="29261-110">Например, можно написать правило преобразования, чтобы заменить +44 в начале строки набора на 0144.</span><span class="sxs-lookup"><span data-stu-id="29261-110">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="29261-111">Выполняя преобразование исходящего маршрута на сервере, можно уменьшить требования к конфигурации в каждом отдельном магистральном узле для трансляции телефонных номеров в формат местного набора.</span><span class="sxs-lookup"><span data-stu-id="29261-111">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="29261-112">При планировании того, какие шлюзы и сколько шлюзов необходимо связать с конкретным кластерным сервером-посредником, может быть удобно группировать магистральные одноранговые узлы с одинаковыми локальными требованиями набора номера.</span><span class="sxs-lookup"><span data-stu-id="29261-112">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="29261-113">Это позволяет уменьшить необходимое количество правил преобразования и сэкономить время, затрачиваемое на их создание.</span><span class="sxs-lookup"><span data-stu-id="29261-113">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="29261-114">Связывание одного или нескольких правил преобразования с конфигурацией магистрали корпоративной голосовой связи следует использовать в качестве альтернативы настройке правил преобразования на одноранговом одноранговом узле.</span><span class="sxs-lookup"><span data-stu-id="29261-114">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="29261-115">Не связывайте правила преобразования с конфигурацией магистрали корпоративной голосовой связи, если вы настроили правила преобразования на одноранговом одноранговом узле, так как эти два правила могут конфликтовать.</span><span class="sxs-lookup"><span data-stu-id="29261-115">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>



</div>

<div>

## <a name="example-translation-rules"></a><span data-ttu-id="29261-116">Примеры правил преобразования</span><span class="sxs-lookup"><span data-stu-id="29261-116">Example Translation Rules</span></span>

<span data-ttu-id="29261-117">Следующие примеры правил преобразования показывают, как можно разрабатывать правила на сервере для преобразования номеров из формата E.164 в местный формат для магистрального узла.</span><span class="sxs-lookup"><span data-stu-id="29261-117">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="29261-118">Для получения дополнительных сведений о том, как реализовать правила преобразования, ознакомьтесь со статьей [Определение правил преобразования в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="29261-118">For details about how to implement translation rules, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>


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
<th><span data-ttu-id="29261-119">Описание</span><span class="sxs-lookup"><span data-stu-id="29261-119">Description</span></span></th>
<th><span data-ttu-id="29261-120">Цифры в начале</span><span class="sxs-lookup"><span data-stu-id="29261-120">Starting Digits</span></span></th>
<th><span data-ttu-id="29261-121">Длина</span><span class="sxs-lookup"><span data-stu-id="29261-121">Length</span></span></th>
<th><span data-ttu-id="29261-122">Цифры для удаления</span><span class="sxs-lookup"><span data-stu-id="29261-122">Digits to Remove</span></span></th>
<th><span data-ttu-id="29261-123">Цифры для добавления</span><span class="sxs-lookup"><span data-stu-id="29261-123">Digits to Add</span></span></th>
<th><span data-ttu-id="29261-124">Шаблон соответствия</span><span class="sxs-lookup"><span data-stu-id="29261-124">Matching Pattern</span></span></th>
<th><span data-ttu-id="29261-125">Translation</span><span class="sxs-lookup"><span data-stu-id="29261-125">Translation</span></span></th>
<th><span data-ttu-id="29261-126">Пример</span><span class="sxs-lookup"><span data-stu-id="29261-126">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29261-127">Обычный междугородний звонок в США.</span><span class="sxs-lookup"><span data-stu-id="29261-127">Conventional long-distance dialing in U.S.</span></span></p>
<p><span data-ttu-id="29261-128">(убирается ‘+’)</span><span class="sxs-lookup"><span data-stu-id="29261-128">(strip out the ‘+’)</span></span></p></td>
<td><p><span data-ttu-id="29261-129">+ 1</span><span class="sxs-lookup"><span data-stu-id="29261-129">+1</span></span></p></td>
<td><p><span data-ttu-id="29261-130">Точно 12</span><span class="sxs-lookup"><span data-stu-id="29261-130">Exactly 12</span></span></p></td>
<td><p><span data-ttu-id="29261-131">1,1</span><span class="sxs-lookup"><span data-stu-id="29261-131">1</span></span></p></td>
<td><p><span data-ttu-id="29261-132">нуль</span><span class="sxs-lookup"><span data-stu-id="29261-132">0</span></span></p></td>
<td><p><span data-ttu-id="29261-133">^\+(1 \ d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="29261-133">^\+(1\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="29261-134">$1</span><span class="sxs-lookup"><span data-stu-id="29261-134">$1</span></span></p></td>
<td><p><span data-ttu-id="29261-135">+14255551010 становится 14255551010</span><span class="sxs-lookup"><span data-stu-id="29261-135">+14255551010 becomes 14255551010</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29261-136">Международный звонок из США</span><span class="sxs-lookup"><span data-stu-id="29261-136">U.S. international long-distance dialing</span></span></p>
<p><span data-ttu-id="29261-137">(убирается ‘+’ и добавляются цифры 011)</span><span class="sxs-lookup"><span data-stu-id="29261-137">(strip out ‘+’ and add 011)</span></span></p></td>
<td><p>+</p></td>
<td><p><span data-ttu-id="29261-138">Не менее 11</span><span class="sxs-lookup"><span data-stu-id="29261-138">At least 11</span></span></p></td>
<td><p><span data-ttu-id="29261-139">1,1</span><span class="sxs-lookup"><span data-stu-id="29261-139">1</span></span></p></td>
<td><p><span data-ttu-id="29261-140">011</span><span class="sxs-lookup"><span data-stu-id="29261-140">011</span></span></p></td>
<td><p><span data-ttu-id="29261-141">^\+(\d {9} \d +) $</span><span class="sxs-lookup"><span data-stu-id="29261-141">^\+(\d{9}\d+)$</span></span></p></td>
<td><p><span data-ttu-id="29261-142">011 $1</span><span class="sxs-lookup"><span data-stu-id="29261-142">011$1</span></span></p></td>
<td><p><span data-ttu-id="29261-143">+441235551010 становится 011441235551010</span><span class="sxs-lookup"><span data-stu-id="29261-143">+441235551010 becomes 011441235551010</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

