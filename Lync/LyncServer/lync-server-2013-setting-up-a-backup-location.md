---
title: 'Lync Server 2013: Настройка расположения для резервного копирования'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up a backup location
ms:assetid: 006732eb-3d44-414d-8010-227a855caa93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202158(v=OCS.15)
ms:contentKeyID: 51541440
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 723bcbc2aeaae5264645d824a9b10a939b6770ab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-a-backup-location-for-lync-server-2013"></a><span data-ttu-id="a2d29-102">Настройка расположения резервной копии для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a2d29-102">Setting up a backup location for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2d29-103">_**Тема последнего изменения:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="a2d29-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="a2d29-104">Прежде чем приступить к первой резервной копии Lync Server, настройте оборудование и программное обеспечение, которое требуется для хранения и обслуживания резервных копий.</span><span class="sxs-lookup"><span data-stu-id="a2d29-104">Before you take your first backup of Lync Server, set up the hardware and software that you need in order to store and maintain the backups.</span></span> <span data-ttu-id="a2d29-105">Вам необходимо получить доступ к носителю и контенту, если это уместно, и предоставить сетевое подключение между каждым из них для резервного копирования и резервного носителя.</span><span class="sxs-lookup"><span data-stu-id="a2d29-105">You need to obtain access to the media and content, as appropriate, and provide network connectivity between each server to be backed up and the backup media.</span></span> <span data-ttu-id="a2d29-106">Используемые вами мультимедиа и расположение следует определять в стратегии резервного копирования и восстановления.</span><span class="sxs-lookup"><span data-stu-id="a2d29-106">The media and location that you use should be defined in your backup and restoration strategy.</span></span> <span data-ttu-id="a2d29-107">Расположение, используемое для регулярного резервного копирования, может быть локальным или удаленным, но оно должно быть защищено, и оно должно быть доступно и для резервного копирования, и для восстановления.</span><span class="sxs-lookup"><span data-stu-id="a2d29-107">The location that you use for regular backups can be local or remote, but it must be secure, and it must be accessible for both backup and restoration.</span></span> <span data-ttu-id="a2d29-108">Мы рекомендуем использовать удаленное расположение для защиты от разрушительных событий на основном сайте.</span><span class="sxs-lookup"><span data-stu-id="a2d29-108">We recommend using a remote location to protect against a catastrophic event at your primary site.</span></span>

<span data-ttu-id="a2d29-109">После того как вы настроили и проверите отдельные компоненты, проверьте доступность резервных копий на каждом сервере.</span><span class="sxs-lookup"><span data-stu-id="a2d29-109">After you set up and test the individual components, verify accessibility to the backups from each server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

