---
title: 'Lync Server 2013: Настройка расположения резервной копии'
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
ms.openlocfilehash: 2ee86d2cf3d68b65c03e851980b21fb0293c5362
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509746"
---
# <a name="setting-up-a-backup-location-for-lync-server-2013"></a><span data-ttu-id="f6a17-102">Настройка расположения резервной копии для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6a17-102">Setting up a backup location for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6a17-103">_**Последнее изменение темы:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="f6a17-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="f6a17-104">Перед началом работы с первой резервной копией Lync Server настройте оборудование и программное обеспечение, необходимое для хранения и обслуживания резервных копий.</span><span class="sxs-lookup"><span data-stu-id="f6a17-104">Before you take your first backup of Lync Server, set up the hardware and software that you need in order to store and maintain the backups.</span></span> <span data-ttu-id="f6a17-105">Вам необходимо получить доступ к мультимедиа и содержимому, если это необходимо, и предоставить сетевое подключение между каждым сервером для резервного копирования и резервным носителем.</span><span class="sxs-lookup"><span data-stu-id="f6a17-105">You need to obtain access to the media and content, as appropriate, and provide network connectivity between each server to be backed up and the backup media.</span></span> <span data-ttu-id="f6a17-106">В стратегии резервного копирования и восстановления определяется используемый носитель и расположение.</span><span class="sxs-lookup"><span data-stu-id="f6a17-106">The media and location that you use should be defined in your backup and restoration strategy.</span></span> <span data-ttu-id="f6a17-107">Место, используемое для регулярного резервного копирования, может быть локальным или удаленным, но оно должно быть безопасным и доступно как для резервного копирования, так и для восстановления.</span><span class="sxs-lookup"><span data-stu-id="f6a17-107">The location that you use for regular backups can be local or remote, but it must be secure, and it must be accessible for both backup and restoration.</span></span> <span data-ttu-id="f6a17-108">Мы рекомендуем использовать удаленное расположение для защиты от разрушительного события на основном сайте.</span><span class="sxs-lookup"><span data-stu-id="f6a17-108">We recommend using a remote location to protect against a catastrophic event at your primary site.</span></span>

<span data-ttu-id="f6a17-109">После настройки и тестирования отдельных компонентов проверьте доступность резервных копий на каждом сервере.</span><span class="sxs-lookup"><span data-stu-id="f6a17-109">After you set up and test the individual components, verify accessibility to the backups from each server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

