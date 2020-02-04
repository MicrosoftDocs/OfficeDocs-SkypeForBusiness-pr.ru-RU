---
title: 'Lync Server 2013: восстановление хранилища файлов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a file store
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202180(v=OCS.15)
ms:contentKeyID: 51541491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c013159de83d258273e381dd54556bcceec056f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a><span data-ttu-id="9f531-102">Восстановление хранилища файлов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9f531-102">Restoring a file store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f531-103">_**Тема последнего изменения:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="9f531-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="9f531-104">Хранилища файлов для выпуска Standard Edition обычно находятся на сервере Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9f531-104">File Stores for Standard Edition are typically located on the Standard Edition server.</span></span> <span data-ttu-id="9f531-105">Хранилища файлов Enterprise Edition обычно находятся на файловом сервере или кластере.</span><span class="sxs-lookup"><span data-stu-id="9f531-105">File Stores for Enterprise Edition are typically located on a file server or cluster.</span></span> <span data-ttu-id="9f531-106">Ниже описана процедура восстановления хранилища файлов.</span><span class="sxs-lookup"><span data-stu-id="9f531-106">The following procedure describes how to restore a File Store.</span></span>

<div>

## <a name="to-restore-a-file-store"></a><span data-ttu-id="9f531-107">Восстановление хранилища файлов</span><span class="sxs-lookup"><span data-stu-id="9f531-107">To restore a File Store</span></span>

1.  <span data-ttu-id="9f531-108">Если хранилище файлов не удается, скопируйте соответствующее хранилище файлов из $Backup\\ в хранилище файлов на файловом сервере или стандартном сервере выпуске, а затем предоставьте к ней общий доступ.</span><span class="sxs-lookup"><span data-stu-id="9f531-108">If a File Store fails, copy the appropriate File Store from $Backup\\ to the File Store location on the file server or Standard Edition server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="9f531-109">Путь и имя файла для восстановленного хранилища файлов должны совпадать с заархивированным хранилищем файлов, чтобы компоненты, использующие эти файлы, могли получать к ним доступ.</span><span class="sxs-lookup"><span data-stu-id="9f531-109">The path and file name for the restored File Store should be exactly the same as the backed up File Store, so that components that use the files can access them.</span></span>

    
    </div>

2.  <span data-ttu-id="9f531-110">При необходимости задайте списки управления доступом (ACL) для хранилища файлов.</span><span class="sxs-lookup"><span data-stu-id="9f531-110">If necessary, set the access control lists (ACLs) for the File Store.</span></span> <span data-ttu-id="9f531-111">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9f531-111">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9f531-112">Этот шаг необходимо выполнить только в том случае, если в процессе восстановления не выполнялась построитель топологии.</span><span class="sxs-lookup"><span data-stu-id="9f531-112">You need to perform this step only if you have not otherwise run Topology Builder during your restoration process.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

