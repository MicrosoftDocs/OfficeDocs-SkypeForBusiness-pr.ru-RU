---
title: 'Lync Server 2013: правила преобразования'
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
ms.openlocfilehash: d1576b9c0c7286150c62f1491960bf9beef5d700
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a><span data-ttu-id="57ee9-102">Правила преобразования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="57ee9-102">Translation rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57ee9-103">_**Последнее изменение темы:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="57ee9-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="57ee9-104">Lync Server 2013 Enterprise Voice требует, чтобы все строки набора номера были нормализованы до формата E. 164 для выполнения обратного просмотра номера (RNL).</span><span class="sxs-lookup"><span data-stu-id="57ee9-104">Lync Server 2013 Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="57ee9-105">В Microsoft Lync Server 2010 правила преобразования поддерживаются только для вызываемых номеров.</span><span class="sxs-lookup"><span data-stu-id="57ee9-105">In Microsoft Lync Server 2010, translation rules are supported only for called numbers.</span></span> <span data-ttu-id="57ee9-106">В Microsoft Lync Server 2013 правила преобразования также поддерживаются для номеров звонков.</span><span class="sxs-lookup"><span data-stu-id="57ee9-106">New in Microsoft Lync Server 2013, translation rules are also supported for calling numbers.</span></span> <span data-ttu-id="57ee9-107">*Магистральный узел* (т.е. соответствующий шлюз, УАТС или канал SIP) может требовать, чтобы номера были в формате местного набора.</span><span class="sxs-lookup"><span data-stu-id="57ee9-107">The *trunk peer* (that is, the associated gateway, private branch exchange (PBX), or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="57ee9-108">Чтобы преобразовать номера из формата E.164 в формат местного набора, можно определить правила преобразования для работы с URI запроса перед его направлением в магистральный узел.</span><span class="sxs-lookup"><span data-stu-id="57ee9-108">To translate numbers from E.164 format to a local dialing format, you can define one or more translation rules to manipulate the request URI before you route it to the trunk peer.</span></span> <span data-ttu-id="57ee9-109">Например, можно написать правило преобразования, чтобы заменить +44 в начале строки набора на 0144.</span><span class="sxs-lookup"><span data-stu-id="57ee9-109">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

<span data-ttu-id="57ee9-110">Выполняя преобразование исходящего маршрута на сервере, можно уменьшить требования к конфигурации в каждом отдельном магистральном узле для трансляции телефонных номеров в формат местного набора.</span><span class="sxs-lookup"><span data-stu-id="57ee9-110">By performing outbound route translation on the server, you can reduce the configuration requirements on each individual trunk peer in order to translate phone numbers into a local dialing format.</span></span> <span data-ttu-id="57ee9-111">При планировании того, какие шлюзы и сколько шлюзов необходимо связать с конкретным кластерным сервером-посредником, может быть удобно группировать магистральные одноранговые узлы с одинаковыми локальными требованиями набора номера.</span><span class="sxs-lookup"><span data-stu-id="57ee9-111">When you plan which gateways, and how many gateways, to associate with a specific Mediation Server cluster, it may be useful to group trunk peers with similar local dialing requirements.</span></span> <span data-ttu-id="57ee9-112">Это позволяет уменьшить необходимое количество правил преобразования и сэкономить время, затрачиваемое на их создание.</span><span class="sxs-lookup"><span data-stu-id="57ee9-112">This can reduce the number of required translation rules and the time it takes to write them.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="57ee9-113">Связывание одного или нескольких правил преобразования с конфигурацией магистрали корпоративной голосовой связи следует использовать в качестве альтернативы настройке правил преобразования на одноранговом одноранговом узле.</span><span class="sxs-lookup"><span data-stu-id="57ee9-113">Associating one or more translation rules with an Enterprise Voice trunk configuration should be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="57ee9-114">Не связывайте правила преобразования с конфигурацией магистрали корпоративной голосовой связи, если вы настроили правила преобразования на одноранговом одноранговом узле, так как эти два правила могут конфликтовать.</span><span class="sxs-lookup"><span data-stu-id="57ee9-114">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer, because the two rules might conflict.</span></span>



</div>

<div>

## <a name="example-translation-rules"></a><span data-ttu-id="57ee9-115">Примеры правил преобразования</span><span class="sxs-lookup"><span data-stu-id="57ee9-115">Example Translation Rules</span></span>

<span data-ttu-id="57ee9-116">Следующие примеры правил преобразования показывают, как можно разрабатывать правила на сервере для преобразования номеров из формата E.164 в местный формат для магистрального узла.</span><span class="sxs-lookup"><span data-stu-id="57ee9-116">The following examples of translation rules show how you can develop rules on the server to translate numbers from E.164 format to a local format for the trunk peer.</span></span>

<span data-ttu-id="57ee9-117">Для получения дополнительных сведений о том, как реализовать правила преобразования, ознакомьтесь со статьей [Определение правил преобразования в Lync Server 2013](lync-server-2013-defining-translation-rules.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="57ee9-117">For details about how to implement translation rules, see [Defining translation rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in the Deployment documentation.</span></span>


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
<th><span data-ttu-id="57ee9-118">Описание</span><span class="sxs-lookup"><span data-stu-id="57ee9-118">Description</span></span></th>
<th><span data-ttu-id="57ee9-119">Цифры в начале</span><span class="sxs-lookup"><span data-stu-id="57ee9-119">Starting Digits</span></span></th>
<th><span data-ttu-id="57ee9-120">Длина</span><span class="sxs-lookup"><span data-stu-id="57ee9-120">Length</span></span></th>
<th><span data-ttu-id="57ee9-121">Цифры для удаления</span><span class="sxs-lookup"><span data-stu-id="57ee9-121">Digits to Remove</span></span></th>
<th><span data-ttu-id="57ee9-122">Цифры для добавления</span><span class="sxs-lookup"><span data-stu-id="57ee9-122">Digits to Add</span></span></th>
<th><span data-ttu-id="57ee9-123">Шаблон соответствия</span><span class="sxs-lookup"><span data-stu-id="57ee9-123">Matching Pattern</span></span></th>
<th><span data-ttu-id="57ee9-124">Translation</span><span class="sxs-lookup"><span data-stu-id="57ee9-124">Translation</span></span></th>
<th><span data-ttu-id="57ee9-125">Пример</span><span class="sxs-lookup"><span data-stu-id="57ee9-125">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57ee9-126">Обычный междугородний звонок в США.</span><span class="sxs-lookup"><span data-stu-id="57ee9-126">Conventional long-distance dialing in U.S.</span></span></p>
<p><span data-ttu-id="57ee9-127">(убирается ‘+’)</span><span class="sxs-lookup"><span data-stu-id="57ee9-127">(strip out the ‘+’)</span></span></p></td>
<td><p><span data-ttu-id="57ee9-128">+ 1</span><span class="sxs-lookup"><span data-stu-id="57ee9-128">+1</span></span></p></td>
<td><p><span data-ttu-id="57ee9-129">Точно 12</span><span class="sxs-lookup"><span data-stu-id="57ee9-129">Exactly 12</span></span></p></td>
<td><p><span data-ttu-id="57ee9-130">1,1</span><span class="sxs-lookup"><span data-stu-id="57ee9-130">1</span></span></p></td>
<td><p><span data-ttu-id="57ee9-131">нуль</span><span class="sxs-lookup"><span data-stu-id="57ee9-131">0</span></span></p></td>
<td><p><span data-ttu-id="57ee9-132">^\+(1 \ d{10}) $</span><span class="sxs-lookup"><span data-stu-id="57ee9-132">^\+(1\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="57ee9-133">$1</span><span class="sxs-lookup"><span data-stu-id="57ee9-133">$1</span></span></p></td>
<td><p><span data-ttu-id="57ee9-134">+14255551010 становится 14255551010</span><span class="sxs-lookup"><span data-stu-id="57ee9-134">+14255551010 becomes 14255551010</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57ee9-135">Международный звонок из США</span><span class="sxs-lookup"><span data-stu-id="57ee9-135">U.S. international long-distance dialing</span></span></p>
<p><span data-ttu-id="57ee9-136">(убирается ‘+’ и добавляются цифры 011)</span><span class="sxs-lookup"><span data-stu-id="57ee9-136">(strip out ‘+’ and add 011)</span></span></p></td>
<td><p>+</p></td>
<td><p><span data-ttu-id="57ee9-137">Не менее 11</span><span class="sxs-lookup"><span data-stu-id="57ee9-137">At least 11</span></span></p></td>
<td><p><span data-ttu-id="57ee9-138">1,1</span><span class="sxs-lookup"><span data-stu-id="57ee9-138">1</span></span></p></td>
<td><p><span data-ttu-id="57ee9-139">011</span><span class="sxs-lookup"><span data-stu-id="57ee9-139">011</span></span></p></td>
<td><p><span data-ttu-id="57ee9-140">^\+(\d{9}\d +) $</span><span class="sxs-lookup"><span data-stu-id="57ee9-140">^\+(\d{9}\d+)$</span></span></p></td>
<td><p><span data-ttu-id="57ee9-141">011 $1</span><span class="sxs-lookup"><span data-stu-id="57ee9-141">011$1</span></span></p></td>
<td><p><span data-ttu-id="57ee9-142">+441235551010 становится 011441235551010</span><span class="sxs-lookup"><span data-stu-id="57ee9-142">+441235551010 becomes 011441235551010</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

