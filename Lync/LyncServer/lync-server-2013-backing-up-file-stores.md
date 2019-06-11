---
title: 'Lync Server 2013: резервное копирование хранилищ файлов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backing up file stores
ms:assetid: 1a7f4e93-aa3d-461e-878e-2c572baa1293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202167(v=OCS.15)
ms:contentKeyID: 51541449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6facef86481e247d1f51d3ec567c8a4ee4bfde8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-file-stores-in-lync-server-2013"></a><span data-ttu-id="33a5f-102">Резервное копирование хранилищ файлов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33a5f-102">Backing up file stores in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33a5f-103">_**Тема последнего изменения:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="33a5f-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="33a5f-104">Резервное копирование хранилищ файлов Lync Server включает в себя все файлы и папки, используемые в компонентах Lync Server.</span><span class="sxs-lookup"><span data-stu-id="33a5f-104">Backing up the Lync Server File Stores includes all the files and folders used by Lync Server components.</span></span>

<div>

## <a name="to-back-up-file-stores"></a><span data-ttu-id="33a5f-105">Создание резервной копии хранилищ файлов</span><span class="sxs-lookup"><span data-stu-id="33a5f-105">To back up File Stores</span></span>

1.  <span data-ttu-id="33a5f-106">Чтобы найти определенные расположения хранилищ файлов на сервере Lync, откройте "Построитель топологии" и просмотрите раздел " **хранилища файлов** ".</span><span class="sxs-lookup"><span data-stu-id="33a5f-106">To find the specific locations of your Lync Server File Stores, open Topology Builder and look in the **File stores** node.</span></span>

2.  <span data-ttu-id="33a5f-107">Используйте средство Robocopy или другую программу управления файловой системой, чтобы скопировать каждое хранилище файлов в\\$Backup хранилище файлов.</span><span class="sxs-lookup"><span data-stu-id="33a5f-107">Use Robocopy or another file system management tool to copy each File Store to $Backup\\filestore.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

