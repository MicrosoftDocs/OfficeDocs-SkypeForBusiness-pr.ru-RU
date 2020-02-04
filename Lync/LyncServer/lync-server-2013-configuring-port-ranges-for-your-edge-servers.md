---
title: 'Lync Server 2013: Настройка диапазонов портов для пограничных серверов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6eddf59f6fe4b2575e0e7d70adddb2e94c90e05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a><span data-ttu-id="18597-102">Настройка диапазонов портов для пограничных серверов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18597-102">Configuring port ranges for your Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18597-103">_**Тема последнего изменения:** 2015-07-24_</span><span class="sxs-lookup"><span data-stu-id="18597-103">_**Topic Last Modified:** 2015-07-24_</span></span>

<span data-ttu-id="18597-104">В пограничных серверах вам не нужно настраивать отдельные диапазоны портов для обмена аудио, видео и приложений. Аналогичным образом диапазоны портов, используемые для пограничных серверов, не должны совпадать с диапазонами портов, используемыми для серверов конференций, приложений и исправлений.</span><span class="sxs-lookup"><span data-stu-id="18597-104">With Edge servers you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="18597-105">Перед тем как приступить к работе с нашим примером, важно перегрузить этот параметр, но мы не рекомендуем менять диапазоны портов, так как это может негативно сказаться на некоторых сценариях, если вы выйдете из диапазона портов 50000.</span><span class="sxs-lookup"><span data-stu-id="18597-105">Before we proceed with our example, it's important to stress that while this option exists, we do recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="18597-106">Например, предположим, что для использования следующих диапазонов портов настроены серверы конференций, приложений и исправлений:</span><span class="sxs-lookup"><span data-stu-id="18597-106">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="18597-107">Тип пакета</span><span class="sxs-lookup"><span data-stu-id="18597-107">Packet Type</span></span></th>
<th><span data-ttu-id="18597-108">Начальный порт</span><span class="sxs-lookup"><span data-stu-id="18597-108">Starting Port</span></span></th>
<th><span data-ttu-id="18597-109">Количество зарезервированных портов</span><span class="sxs-lookup"><span data-stu-id="18597-109">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="18597-110">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="18597-110">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="18597-111">40803</span><span class="sxs-lookup"><span data-stu-id="18597-111">40803</span></span></p></td>
<td><p><span data-ttu-id="18597-112">8348</span><span class="sxs-lookup"><span data-stu-id="18597-112">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18597-113">Голосовая связь</span><span class="sxs-lookup"><span data-stu-id="18597-113">Audio</span></span></p></td>
<td><p><span data-ttu-id="18597-114">49152</span><span class="sxs-lookup"><span data-stu-id="18597-114">49152</span></span></p></td>
<td><p><span data-ttu-id="18597-115">8348</span><span class="sxs-lookup"><span data-stu-id="18597-115">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="18597-116">Видеосвязь</span><span class="sxs-lookup"><span data-stu-id="18597-116">Video</span></span></p></td>
<td><p><span data-ttu-id="18597-117">57500</span><span class="sxs-lookup"><span data-stu-id="18597-117">57500</span></span></p></td>
<td><p><span data-ttu-id="18597-118">8034</span><span class="sxs-lookup"><span data-stu-id="18597-118">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="18597-119"><strong>Итоги</strong></span><span class="sxs-lookup"><span data-stu-id="18597-119"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="18597-120">24730</span><span class="sxs-lookup"><span data-stu-id="18597-120">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="18597-121">Как видите, диапазоны портов для обмена аудио, видео и приложениями начинаются с порта 40803 и включают в себя всего 24732 портов.</span><span class="sxs-lookup"><span data-stu-id="18597-121">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="18597-122">При желании вы можете настроить этот граничный сервер для использования этих общих значений порта, выполнив следующую команду в командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="18597-122">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Lync Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="18597-123">Вы также можете одновременно настроить все пограничные серверы в Организации с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="18597-123">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="18597-124">Вы можете проверить текущие параметры порта для пограничных серверов с помощью командной консоли Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="18597-124">You can verify the current port settings for your Edge Servers by using this Lync Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="18597-125">Пока мы предоставляем эти параметры, мы настоятельно рекомендуем вам оставить все, что нужно для настройки порта.</span><span class="sxs-lookup"><span data-stu-id="18597-125">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

