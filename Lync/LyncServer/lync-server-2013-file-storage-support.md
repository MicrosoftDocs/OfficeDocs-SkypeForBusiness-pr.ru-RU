---
title: Поддержка хранения файлов в Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bba71468c9797ad52cd01e163c726f779f43aea9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028500"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a><span data-ttu-id="7240e-102">Поддержка хранения файлов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7240e-102">File storage support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7240e-103">_**Последнее изменение темы:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="7240e-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="7240e-104">Lync Server 2013 использует одно и то же хранилище файлов для всех хранилищ файлов.</span><span class="sxs-lookup"><span data-stu-id="7240e-104">Lync Server 2013 uses the same file store for all file storage.</span></span> <span data-ttu-id="7240e-105">Поддержка хранения файлов включает следующее.</span><span class="sxs-lookup"><span data-stu-id="7240e-105">File storage support includes the following:</span></span>

  - <span data-ttu-id="7240e-106">Файловый ресурс общего доступа либо в непосредственно подключенной системе хранения (DAS — direct attached storage), либо в сети хранения данных (SAN), включая распределенную файловую систему (DFS) и массив RAID для хранения файлов.</span><span class="sxs-lookup"><span data-stu-id="7240e-106">A file share on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS), and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="7240e-107">Дополнительные сведения о требованиях к хранению приведены [в статье технические требования к серверам переднего плана, обмену мгновенными сообщениями и сведениям о присутствии в Lync server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) , а [также требованиях к оборудованию и программному обеспечению для директора в Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md)</span><span class="sxs-lookup"><span data-stu-id="7240e-107">For details about storage requirements, see [Technical requirements for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) and [Hardware and software requirements for the Director in Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) in the Planning documentation.</span></span> <span data-ttu-id="7240e-108">Подробнее о распределенной файловой системе для Windows Server 2008 можно узнать в статье Пошаговое руководство по DFS для Windows Server 2008 по [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)адресу.</span><span class="sxs-lookup"><span data-stu-id="7240e-108">For details about DFS for Windows Server 2008 operating system, see the DFS Step-by-Step Guide for Windows Server 2008 at [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835).</span></span>

  - <span data-ttu-id="7240e-109">Общий кластер для этого файлового ресурса общего доступа.</span><span class="sxs-lookup"><span data-stu-id="7240e-109">A shared cluster for the file share.</span></span> <span data-ttu-id="7240e-110">Если используется общий кластер, то серверы кластера должны работать под управлением Windows Server 2008 или Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="7240e-110">If you use a shared cluster, you should use cluster servers running Windows Server 2008 or Windows Server 2008 R2.</span></span> <span data-ttu-id="7240e-111">Использование серверов кластера, работающих под управлением более ранней версии Windows, может привести к проблемам с разрешениями, которые не позволяют получить доступ к некоторым функциям.</span><span class="sxs-lookup"><span data-stu-id="7240e-111">Using cluster servers running an older version of Windows may result in permission issues that prevent some features from being available.</span></span> <span data-ttu-id="7240e-112">Создавать файловые ресурсы общего доступа можно с помощью администратора кластера.</span><span class="sxs-lookup"><span data-stu-id="7240e-112">Use the Cluster Administrator to create the file shares.</span></span> <span data-ttu-id="7240e-113">Сведения об использовании администратора кластера содержатся в [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899)статье базы знаний Майкрософт 284838, "как создать файловый ресурс кластера серверов с помощью Cluster. exe.</span><span class="sxs-lookup"><span data-stu-id="7240e-113">For details about using the Cluster Administrator, see Microsoft Knowledge Base article 284838, "How to Create a Server Cluster File Share with Cluster.exe" at [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

