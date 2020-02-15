---
title: 'Lync Server 2013: Управление качеством обслуживания (QoS)'
ms.reviewer: ''
f1.keywords:
- NOCSH
TOCTitle: Managing Quality of Service (QoS)
author: lanachin
ms.author: v-lanac
ms.manager: serdars
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9b6661bb9e34db11099bc0f1a7526ba23792198
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "41992334"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a><span data-ttu-id="bc35c-102">Управление качеством обслуживания (QoS) в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc35c-102">Managing Quality of Service (QoS) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc35c-103">_**Последнее изменение темы:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="bc35c-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="bc35c-p101">Качество обслуживания (QoS) — это сетевая технология, которая используется в некоторых организациях для обеспечения оптимального качества аудио- и видеосвязи. Качество обслуживания наиболее часто используется в сетях с ограниченной пропускной способностью, в которых большое число сетевых пакетов конкурирует за относительно небольшую доступную пропускную способность. В таких сетях качество обслуживания позволяет назначать более высокие приоритеты пакетам, используемым для передачи аудио- и видеоданных. Назначение пакетам аудио- и видеоданных высокого приоритета позволяет повысить скорость аудио- и видеосвязи и уменьшить задержки по сравнению с сеансами передачи файлов, просмотра веб-страниц или резервного копирования баз данных. По этой причине сетевым пакетам, используемым при передаче файлов или резервном копировании баз данных, назначается приоритет "best effort" (наилучший вариант).</span><span class="sxs-lookup"><span data-stu-id="bc35c-p101">Quality of Service (QoS) is a networking technology used in some organizations to help provide an optimal end-user experience for audio and video communications. QoS is most-commonly used on networks where bandwidth is limited: with a large number of network packets competing for a relatively small amount of available bandwidth, Quality of Service provides a way for administrators to assign higher priorities to packets carrying audio or video data. By giving these packets a higher priority, audio and video communications are likely to complete faster, and with less interruption, than network sessions involving things like file transfers, web browsing, or database backups. That's because network packets used for file transfers or database backups are assigned a "best effort" priority.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bc35c-p102">Обычно качество обслуживания применяется только к сеансам связи во внутренней сети. Реализация качества обслуживания подразумевает настройку серверов и маршрутизаторов для отметки пакетов с использованием определенного способа. Вы не можете быть уверены в том, что качество обслуживания будет поддерживаться в Интернете или других сетях. Даже если в остальных сетях качество обслуживания поддерживается, то это вовсе не означает, что способы настройки качества обслуживания в вашей сети и в других сетях будут совпадать.</span><span class="sxs-lookup"><span data-stu-id="bc35c-p102">As a general rule, Quality of Service applies only to communication sessions on your internal network. When you implement QoS, you configure your servers and routers to support packet marking; however, you configure these devices to support packet marking in a particular manner. You cannot assume that Quality of Service will be supported on the Internet or on other networks. Even if Quality if Service is supported on other networks, there is no guarantee that QoS will be configured the same way that you configured the service on your network.</span></span>



</div>

<span data-ttu-id="bc35c-112">Microsoft Lync Server 2013 не требует качества обслуживания; Если Служба QoS в настоящее время не используется, то перед установкой Lync Server 2013 вам не требуется устанавливать эту службу.</span><span class="sxs-lookup"><span data-stu-id="bc35c-112">Microsoft Lync Server 2013 does not require Quality of Service; if you do not currently use QoS there is no requirement that you install the service before installing Lync Server 2013.</span></span> <span data-ttu-id="bc35c-113">Если в вашей сети возникла значительная потеря пакетов, рекомендуем решить эту проблему, добавив дополнительную пропускную способность.</span><span class="sxs-lookup"><span data-stu-id="bc35c-113">If you experience a considerable amount of packet loss on your network the recommended way to alleviate this problem is to add additional bandwidth.</span></span> <span data-ttu-id="bc35c-114">Если добавление дополнительной полосы пропускания невозможно, то вместо этого может потребоваться реализовать качество обслуживания.</span><span class="sxs-lookup"><span data-stu-id="bc35c-114">If adding more bandwidth is not possible, then you might want to implement Quality of Service instead.</span></span>

<span data-ttu-id="bc35c-115">Lync Server 2013 обеспечивает полную поддержку качества обслуживания: это означает, что Организации, которые уже используют QoS, могут легко интегрировать Lync Server с существующей сетевой инфраструктурой.</span><span class="sxs-lookup"><span data-stu-id="bc35c-115">Lync Server 2013 offers full support for Quality of Service: that means that organizations that are already using QoS can easily integrate Lync Server into their existing network infrastructure.</span></span> <span data-ttu-id="bc35c-116">Для этого необходимо выполнить следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="bc35c-116">In order to do this you must perform the following tasks:</span></span>

  - <span data-ttu-id="bc35c-117">[Включение качества обслуживания в Lync Server 2013 для устройств, не основанных на Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span><span class="sxs-lookup"><span data-stu-id="bc35c-117">[Enabling QoS in Lync Server 2013 for devices that are not based on Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md).</span></span> <span data-ttu-id="bc35c-118">По умолчанию качество обслуживания отключено для компьютеров и других устройств (например, iPhones), работающих под управлением ОС, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="bc35c-118">By default, QoS is disabled for computers and other devices (such as iPhones) that run other operating systems.</span></span> <span data-ttu-id="bc35c-119">Несмотря на то что вы можете использовать Lync Server для включения и отключения качества обслуживания для устройств, обычно невозможно использовать продукт для изменения кодов DSCP, используемых этими устройствами.</span><span class="sxs-lookup"><span data-stu-id="bc35c-119">Although you can use Lync Server to enable and disable Quality of Service for devices, you typically cannot use the product to modify the DSCP codes used by these devices.</span></span>

  - <span data-ttu-id="bc35c-120">[Настройка диапазонов портов в Lync Server 2013 для серверов конференц-связи, приложений и серверов-посредников](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span><span class="sxs-lookup"><span data-stu-id="bc35c-120">[Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="bc35c-121">Вам необходимо зарезервировать уникальный набор портов для разных типов пакетов, например аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="bc35c-121">You must reserve a unique set of ports for different packet types, such as audio and video.</span></span> <span data-ttu-id="bc35c-122">В Lync Server 2013 вы не включаете и не отключаете качество обслуживания, скажем, присвоив свойству значение true или false.</span><span class="sxs-lookup"><span data-stu-id="bc35c-122">With Lync Server 2013 you do not enable or disable Quality of Service by, say, setting a property value to True or to False.</span></span> <span data-ttu-id="bc35c-123">Вместо этого для включения качества обслуживания необходимо настроить диапазоны портов и затем создать и применить групповую политику.</span><span class="sxs-lookup"><span data-stu-id="bc35c-123">Instead, you enable Quality of Service by configuring port ranges and then creating and applying Group Policy.</span></span> <span data-ttu-id="bc35c-124">Если впоследствии вы не захотите использовать качество обслуживания, то для его "отключения" достаточно удалить соответствующие объекты групповой политики.</span><span class="sxs-lookup"><span data-stu-id="bc35c-124">If you later decide not to use QoS you can “disable” Quality of Service simply by removing the appropriate Group Policy objects.</span></span>

  - <span data-ttu-id="bc35c-125">[Настройка диапазонов портов для пограничных серверов в Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md).</span><span class="sxs-lookup"><span data-stu-id="bc35c-125">[Configuring port ranges for your Edge Servers in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md).</span></span> <span data-ttu-id="bc35c-126">Вы можете использовать на пограничных серверах и остальных серверах одни и те же диапазоны портов, хотя это необязательно.</span><span class="sxs-lookup"><span data-stu-id="bc35c-126">Although not required, you can configure your Edge servers to use the same port ranges as your other servers.</span></span>

  - <span data-ttu-id="bc35c-127">[Настройка диапазонов портов для клиентов Microsoft Lync в Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md).</span><span class="sxs-lookup"><span data-stu-id="bc35c-127">[Configuring port ranges for your Microsoft Lync clients in Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md).</span></span> <span data-ttu-id="bc35c-128">Эти диапазоны портов применяются только к клиентским компьютерам и обычно не совпадают с диапазонами портов, заданными на серверах.</span><span class="sxs-lookup"><span data-stu-id="bc35c-128">These port ranges apply only to client computers and are typically not the same as the port ranges configured on your servers.</span></span>

  - <span data-ttu-id="bc35c-129">[Настройка политики качества обслуживания в Lync Server 2013 для серверов конференц-связи, приложений и серверов-посредников](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span><span class="sxs-lookup"><span data-stu-id="bc35c-129">[Configuring a Quality of Service policy in Lync Server 2013 for your Conferencing, Application, and Mediation servers](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md).</span></span> <span data-ttu-id="bc35c-130">Эти политики определяют коды DSCP, которые применяются к разным типам пакетов.</span><span class="sxs-lookup"><span data-stu-id="bc35c-130">These policies determine the DSCP codes that are applied to different packet types.</span></span>

  - <span data-ttu-id="bc35c-131">[Настройка политики качества обслуживания для пограничных серверов аудио-и видеоданных в Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md).</span><span class="sxs-lookup"><span data-stu-id="bc35c-131">[Configuring a Quality of Service policy for your A/V Edge Servers in Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md).</span></span> <span data-ttu-id="bc35c-132">Это следует делать только для внутренней стороны пограничных серверов.</span><span class="sxs-lookup"><span data-stu-id="bc35c-132">This should only be done for the internal side of your Edge servers.</span></span> <span data-ttu-id="bc35c-133">Это связано с тем, что служба качества обслуживания предназначена для внутренней сети, а не для Интернета.</span><span class="sxs-lookup"><span data-stu-id="bc35c-133">That's because Quality of Service is designed for use on your internal network and not on the Internet.</span></span>

  - <span data-ttu-id="bc35c-134">[Настройка политик качества обслуживания в Lync Server 2013 для клиентов, работающих под управлением Windows 7 или Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md).</span><span class="sxs-lookup"><span data-stu-id="bc35c-134">[Configuring Quality of Service policies in Lync Server 2013 for clients running on Windows 7 or Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md).</span></span> <span data-ttu-id="bc35c-135">Обратите внимание, что Microsoft Lync Server 2013 не поддерживает QoS для других операционных систем Windows, таких как Windows Vista или Windows XP.</span><span class="sxs-lookup"><span data-stu-id="bc35c-135">Note that Microsoft Lync Server 2013 does not support QoS for other Windows operating systems, such as Windows Vista or Windows XP.</span></span>

  - <span data-ttu-id="bc35c-136">[Настройка качества обслуживания на устройствах Microsoft Lync Phone Edition в Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md).</span><span class="sxs-lookup"><span data-stu-id="bc35c-136">[Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md).</span></span> <span data-ttu-id="bc35c-137">По умолчанию качество обслуживания включено для устройств Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="bc35c-137">By default, QoS is enabled for Lync Phone Edition devices.</span></span> <span data-ttu-id="bc35c-138">Однако может потребоваться изменение значения DSCP по умолчанию, чтобы все пакеты аудиоданных в организации использовали один и тот же код DSCP.</span><span class="sxs-lookup"><span data-stu-id="bc35c-138">However, you might want to change the default DSCP value in order to ensure that all audio packets in your organization use the same DSCP code.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bc35c-139">Если вы используете Microsoft Windows Server 2012 или Windows Server 2012 R2, вам может потребоваться новый набор командлетов Windows PowerShell, доступных для управления качеством обслуживания на этой платформе.</span><span class="sxs-lookup"><span data-stu-id="bc35c-139">If you are using Microsoft Windows Server 2012 or Windows Server 2012 R2 you might be interested in the new set of Windows PowerShell cmdlets available for managing Quality of Service on that platform.</span></span> <span data-ttu-id="bc35c-140">Для получения дополнительных сведений обратитесь к командлетам сетевого качества обслуживания в Windows PowerShell [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)на сайте.</span><span class="sxs-lookup"><span data-stu-id="bc35c-140">For more information, see Network Quality of Service Cmdlets in Windows PowerShell at [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps).</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

