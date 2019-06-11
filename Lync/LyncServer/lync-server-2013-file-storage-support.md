---
title: 'Lync Server 2013: поддержка хранения файлов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3025534aecb45f230e986016e839af07fe1406cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a><span data-ttu-id="7ac8b-102">Поддержка хранения файлов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ac8b-102">File storage support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ac8b-103">_**Тема последнего изменения:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="7ac8b-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="7ac8b-104">Lync Server 2013 использует одно и то же хранилище файлов для хранения всех файлов.</span><span class="sxs-lookup"><span data-stu-id="7ac8b-104">Lync Server 2013 uses the same file store for all file storage.</span></span> <span data-ttu-id="7ac8b-105">Поддержка хранения файлов включает следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="7ac8b-105">File storage support includes the following:</span></span>

  - <span data-ttu-id="7ac8b-106">Файловый общий доступ на запоминающем устройстве (DAS) или в сети хранения данных (SAN), включая распределенную файловую систему (DFS), а также на резервный массив независимых дисков (RAID) для хранения файлов.</span><span class="sxs-lookup"><span data-stu-id="7ac8b-106">A file share on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS), and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="7ac8b-107">Дополнительные сведения о требованиях к хранению можно найти в статьях [технические требования к серверам переднего плана,](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) обмену мгновенными сообщениями и сведениям 2013 о присутствии в lync Server 2013, а также [о требованиях к оборудованию](lync-server-2013-hardware-and-software-requirements-for-the-director.md) и программному обеспечению содержатся.</span><span class="sxs-lookup"><span data-stu-id="7ac8b-107">For details about storage requirements, see [Technical requirements for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) and [Hardware and software requirements for the Director in Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) in the Planning documentation.</span></span> <span data-ttu-id="7ac8b-108">Подробные сведения о DFS для операционной системы Windows Server 2008 можно найти в пошаговом руководстве по DFS для Windows Server 2008 по адресу [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835).</span><span class="sxs-lookup"><span data-stu-id="7ac8b-108">For details about DFS for Windows Server 2008 operating system, see the DFS Step-by-Step Guide for Windows Server 2008 at [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835).</span></span>

  - <span data-ttu-id="7ac8b-109">Общий кластер для общего доступа к файлам.</span><span class="sxs-lookup"><span data-stu-id="7ac8b-109">A shared cluster for the file share.</span></span> <span data-ttu-id="7ac8b-110">Если вы пользуетесь общим кластером, вы должны использовать кластерные серверы под управлением Windows Server 2008 или Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="7ac8b-110">If you use a shared cluster, you should use cluster servers running Windows Server 2008 or Windows Server 2008 R2.</span></span> <span data-ttu-id="7ac8b-111">Использование серверов кластера, работающих под управлением более ранней версии Windows, может привести к проблемам с разрешениями, которые не позволяют получить доступ к некоторым функциям.</span><span class="sxs-lookup"><span data-stu-id="7ac8b-111">Using cluster servers running an older version of Windows may result in permission issues that prevent some features from being available.</span></span> <span data-ttu-id="7ac8b-112">Для создания общих файловых ресурсов используйте администратор кластеров.</span><span class="sxs-lookup"><span data-stu-id="7ac8b-112">Use the Cluster Administrator to create the file shares.</span></span> <span data-ttu-id="7ac8b-113">Подробнее об использовании администратора кластера можно найти в [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899)статье 284838 базы знаний Майкрософт, посвященной созданию общего файлового файла кластера сервера с помощью Cluster. exe.</span><span class="sxs-lookup"><span data-stu-id="7ac8b-113">For details about using the Cluster Administrator, see Microsoft Knowledge Base article 284838, "How to Create a Server Cluster File Share with Cluster.exe" at [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

