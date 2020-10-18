---
title: 'Lync Server 2013: Установка сертификата на узел-наблюдатель, расположенный снаружи сети периметра'
description: 'Lync Server 2013: Установка сертификата на узел-наблюдатель, расположенный снаружи сети периметра.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing a certificate on a watcher node located outside the perimeter network
ms:assetid: 825c9c02-1951-4d7a-a25e-a313a85333f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688113(v=OCS.15)
ms:contentKeyID: 49733711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66f40886e9784b5bd4182a60b955745b5daf2034
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574035"
---
# <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network-of-lync-server-2013"></a><span data-ttu-id="d744e-103">Установка сертификата на узел-наблюдатель, расположенный вне сети периметра Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d744e-103">Installing a certificate on a watcher node located outside the perimeter network of Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d744e-104">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="d744e-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="d744e-105">Агенты System Center Operations Manager, работающие в сети периметра (например, на пограничном сервере Lync Server), вне Организации (например, узла-наблюдателя внешней искусственной транзакции) или на границе доверия доменных служб Active Directory, могут требовать настройки сервера шлюза System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="d744e-105">System Center Operations Manager agents running in a perimeter network (such as a Lync Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory Domain Services trust boundary, might require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="d744e-106">Эта роль сервера позволяет агентам без отношения доверия с корневым сервером управления создавать предупреждения.</span><span class="sxs-lookup"><span data-stu-id="d744e-106">This server role allows agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="d744e-107">Дополнительные сведения см. в разделе "Управление серверами шлюза в Operations Manager 2007" в библиотеке TechNet System Center Operations Manager по адресу [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703) .</span><span class="sxs-lookup"><span data-stu-id="d744e-107">For details, see "Managing Gateway Servers in Operations Manager 2007" in the System Center Operations Manager TechNet Library at [https://go.microsoft.com/fwlink/p/?LinkId=268703](https://go.microsoft.com/fwlink/p/?linkid=268703).</span></span>

<span data-ttu-id="d744e-108">Если вы развертываете агент в одном из этих расположений, вам также потребуется запросить и настроить сертификат, который позволяет узлу-наблюдателю отправлять оповещения в System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="d744e-108">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="d744e-109">Чтобы упростить этот процесс, группа разработчиков Operations Manager создала набор вспомогательных программ, позволяющих запрашивать и устанавливать нужный тип сертификата на компьютера узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="d744e-109">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="d744e-110">Для получения дополнительных сведений и загрузки этих служебных программ просмотрите статью "получение сертификатов для агентов, не присоединенных к домену", с помощью мастера создания сертификатов, по адресу [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421) .</span><span class="sxs-lookup"><span data-stu-id="d744e-110">For details, and to download these utilities, see the "Obtaining Certificates for Non-Domain Joined Agents Made Easy With Certificate Generation Wizard" blog article at [https://go.microsoft.com/fwlink/p/?LinkId=267421](https://go.microsoft.com/fwlink/p/?linkid=267421).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

