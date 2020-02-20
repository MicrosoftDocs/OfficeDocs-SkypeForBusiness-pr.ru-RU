---
title: 'Lync Server 2013: Настройка диапазонов портов для серверов конференц-связи, приложений и серверов-посредников'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb91667406fe2c4ed292f9b0b6b85e69c2e4e256
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="29881-102">Настройка диапазонов портов в Lync Server 2013 для серверов конференц-связи, приложений и серверов-посредников</span><span class="sxs-lookup"><span data-stu-id="29881-102">Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29881-103">_**Последнее изменение темы:** 2015-04-30_</span><span class="sxs-lookup"><span data-stu-id="29881-103">_**Topic Last Modified:** 2015-04-30_</span></span>

<span data-ttu-id="29881-p101">Чтобы внедрить качества обслуживания, вам необходимо настроить одинаковые диапазоны портов для звука, видео и общего доступа к приложениям на серверах конференций, приложений и серверах-посредниках; кроме того, эти диапазоны портов не должны каким-либо образом накладываться друг на друга. В качестве простого пример представьте, что вы используете порты с 10000 по 10999 для видео на серверах конференций. Это значит, что вы также должны зарезервировать порты с 10000 по 10999 для видео на серверах приложений и серверах-посредниках. В противном случае качество обслуживания будет работать неправильно.</span><span class="sxs-lookup"><span data-stu-id="29881-p101">In order to implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way. To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers. That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers. If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="29881-p102">Аналогичным образом, представьте, что резервируете порты с 10000 по 10999 для видео, а затем резервируете порты с 10500 по 11999 для звука. Это может привести к проблемам с качеством обслуживания, так как эти диапазоны портов накладываются. При использовании качества обслуживания каждая модальность должна иметь уникальный набор портов: если вы используете порты с 10000 по 10999 для видео, то для звука вам необходимо использовать другой диапазон (например, с 11000 по 11999).</span><span class="sxs-lookup"><span data-stu-id="29881-p102">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio. This can create problems for Quality of Service, because the port ranges overlap. With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999 for audio).</span></span>

<span data-ttu-id="29881-111">По умолчанию диапазоны портов звука и видео не перекрываются в Microsoft Lync Server 2013; Однако диапазоны портов, назначаемые совместному использованию приложений, перекрываются с диапазонами портов звука и видео.</span><span class="sxs-lookup"><span data-stu-id="29881-111">By default, audio and video port ranges do not overlap in Microsoft Lync Server 2013; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="29881-112">(В свою очередь, это означает, что ни один из этих диапазонов не уникален.) Вы можете проверить существующие диапазоны портов для серверов конференц-связи, приложений и серверов-посредников, выполнив следующие три команды в консоли управления Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="29881-112">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> <span data-ttu-id="29881-p104">Как вы можете видеть в предыдущих командах, каждому типу портов — для звука, видео и общего доступа к приложениям — назначаются два отдельных значения свойства: начальный порт и число портов. Начальный порт обозначает первый порт, используемый для данной модальности; например, если начальный порт звука равен 50000, значит первым портом, используемым для звукового трафика, является порт 50000. Если число портов звука равно 2 (это недопустимое значение, которое используется здесь исключительно для иллюстрации), значит для звука выделено всего 2 порта. Если начальный порт равен 50000 и доступно всего два порта, значит вторым будет порт 50001 (диапазоны портов должны быть непрерывными). В результате получается диапазон портов для звука с 50000 по 50001 включительно.</span><span class="sxs-lookup"><span data-stu-id="29881-p104">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count. The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000. If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes) that means that only 2 ports are allocated for audio. If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous). As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><span data-ttu-id="29881-118">Обратите внимание на то, что сервер приложений и сервер-посредник поддерживают качество обслуживания только для звука, поэтому изменять порты для видео или общего доступа к приложениям на серверах приложений или серверах-посредниках не нужно.</span><span class="sxs-lookup"><span data-stu-id="29881-118">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>



</div>

<span data-ttu-id="29881-119">При выполнении предыдущих трех команд вы увидите, что значения портов по умолчанию для Lync Server 2013 настроены следующим образом:</span><span class="sxs-lookup"><span data-stu-id="29881-119">If you run the preceding three commands you'll see that the default port values for Lync Server 2013 are configured like this:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29881-120">Свойство</span><span class="sxs-lookup"><span data-stu-id="29881-120">Property</span></span></th>
<th><span data-ttu-id="29881-121">Сервер конференций</span><span class="sxs-lookup"><span data-stu-id="29881-121">Conferencing Server</span></span></th>
<th><span data-ttu-id="29881-122">Сервер приложений</span><span class="sxs-lookup"><span data-stu-id="29881-122">Application Server</span></span></th>
<th><span data-ttu-id="29881-123">Сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="29881-123">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29881-124">аудиопортстарт</span><span class="sxs-lookup"><span data-stu-id="29881-124">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="29881-125">49152</span><span class="sxs-lookup"><span data-stu-id="29881-125">49152</span></span></p></td>
<td><p><span data-ttu-id="29881-126">49152</span><span class="sxs-lookup"><span data-stu-id="29881-126">49152</span></span></p></td>
<td><p><span data-ttu-id="29881-127">49152</span><span class="sxs-lookup"><span data-stu-id="29881-127">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29881-128">аудиопорткаунт</span><span class="sxs-lookup"><span data-stu-id="29881-128">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="29881-129">8348</span><span class="sxs-lookup"><span data-stu-id="29881-129">8348</span></span></p></td>
<td><p><span data-ttu-id="29881-130">8348</span><span class="sxs-lookup"><span data-stu-id="29881-130">8348</span></span></p></td>
<td><p><span data-ttu-id="29881-131">8348</span><span class="sxs-lookup"><span data-stu-id="29881-131">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29881-132">видеопортстарт</span><span class="sxs-lookup"><span data-stu-id="29881-132">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="29881-133">57501</span><span class="sxs-lookup"><span data-stu-id="29881-133">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29881-134">видеопорткаунт</span><span class="sxs-lookup"><span data-stu-id="29881-134">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="29881-135">8034</span><span class="sxs-lookup"><span data-stu-id="29881-135">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29881-136">аппликатионшарингпортстарт</span><span class="sxs-lookup"><span data-stu-id="29881-136">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="29881-137">49152</span><span class="sxs-lookup"><span data-stu-id="29881-137">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29881-138">аппликатионшарингпорткаунт</span><span class="sxs-lookup"><span data-stu-id="29881-138">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="29881-139">16383</span><span class="sxs-lookup"><span data-stu-id="29881-139">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="29881-140">Как отмечалось ранее, при настройке портов Lync Server для QoS необходимо убедиться в том, что: 1) параметры звукового порта идентичны на серверах конференц-связи, приложений и серверов-посредников; и, 2) диапазоны портов не перекрываются.</span><span class="sxs-lookup"><span data-stu-id="29881-140">As noted previously, when configuring Lync Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="29881-141">Если вы внимательнее посмотрите на предыдущую таблицу, то заметите, что диапазоны портов одинаковы для всех трех типов серверов.</span><span class="sxs-lookup"><span data-stu-id="29881-141">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="29881-142">Например, в качестве начального порта звука на сервере каждого типа установлен порт 49152, а общее число портов, зарезервированных для звука, также одинаково на каждом из серверов — 8348.</span><span class="sxs-lookup"><span data-stu-id="29881-142">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="29881-143">Однако диапазоны портов накладываются: порты звука — как и порты для общего доступа к приложениям — начинаются с порта 49152.</span><span class="sxs-lookup"><span data-stu-id="29881-143">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="29881-144">Чтобы обеспечить оптимальное использование качества обслуживания, настройку для общего доступа к приложениям следует изменить на использование уникального диапазона портов.</span><span class="sxs-lookup"><span data-stu-id="29881-144">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="29881-145">Например, вы могли бы настроить для общего доступа к приложениям начальный порт 40803 с общим количеством портов 8348.</span><span class="sxs-lookup"><span data-stu-id="29881-145">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="29881-146">(Почему 8348 портов?</span><span class="sxs-lookup"><span data-stu-id="29881-146">(Why 8348 ports?</span></span> <span data-ttu-id="29881-147">Если вы добавляете эти значения вместе — 40803 + 8348 — это означает, что общий доступ к приложениям будет использовать порты 40803 через порт 49150.</span><span class="sxs-lookup"><span data-stu-id="29881-147">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="29881-148">Поскольку порты для звука начинаются только с порта 49152, наложение диапазонов портов будет устранено.)</span><span class="sxs-lookup"><span data-stu-id="29881-148">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="29881-p106">После выбора нового диапазона портов для общего доступа к приложениям вы можете внести такое изменение с помощью командлета Set-CsConferencingServer. Это изменение не требуется вносить для серверов приложений или серверов-посредников, так как они не обрабатывают трафик общего доступа к приложениям. Значения портов на этих серверах требуется изменить только в том случае, если решили переназначить порты, используемые для трафика звука.</span><span class="sxs-lookup"><span data-stu-id="29881-p106">After you have selected the new port range for application sharing you can make your change by using the Set-CsConferencingServer cmdlet. This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic. You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="29881-152">Чтобы изменить значения портов для общего доступа к приложениям на одном сервере конференций, выполните команду, подобную следующей, в командной консоли Lync Server:</span><span class="sxs-lookup"><span data-stu-id="29881-152">To modify the port values for application sharing on a single Conferencing server run a command similar to this from within the Lync Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="29881-153">Если вы хотите внести эти изменения на всех серверах конференций, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="29881-153">If you want to make these changes on all your Conferencing servers you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="29881-154">После изменения параметров портов вам необходимо остановить и перезапустить каждую из служб, затрагиваемых этими изменениями.</span><span class="sxs-lookup"><span data-stu-id="29881-154">After changing port settings you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="29881-p107">Серверы конференций, серверы приложений и серверы-посредники необязательно должны использовать строго одинаковый диапазон портов, единственным неукоснительным требованием является задание уникальных диапазонов портов на всех серверах. Однако задание одного набора портов на всех серверах упрощает администрирование.</span><span class="sxs-lookup"><span data-stu-id="29881-p107">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers. However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

