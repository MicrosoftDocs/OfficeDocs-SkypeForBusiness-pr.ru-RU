---
title: 'Lync Server 2013: восстановление содержимого конференций с помощью службы резервного копирования'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring conference contents using the Backup Service
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49733620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 873ca354ca592eb6bc317b579a0a6f5008e6a172
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="ce9f4-102">Восстановление содержимого конференций с помощью службы резервного копирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce9f4-102">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce9f4-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ce9f4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ce9f4-104">Если сведения о конференции, хранящиеся в хранилище файлов в пуле переднего плана, становятся недоступными.</span><span class="sxs-lookup"><span data-stu-id="ce9f4-104">If the conference information stored in the file store of a Front End pool becomes unavailable.</span></span> <span data-ttu-id="ce9f4-105">Эти данные необходимо восстановить таким образом, чтобы пользователи, расположенные в пуле, сохраняли свои данные на Конференции.</span><span class="sxs-lookup"><span data-stu-id="ce9f4-105">you must restore this information so that users homed on the pool retain their conference data.</span></span> <span data-ttu-id="ce9f4-106">Если пул переднего плана, который потерял данные конференции, связан с другим пулом переднего плана, вы можете восстановить данные с помощью службы резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="ce9f4-106">If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="ce9f4-107">Кроме того, вы должны выполнить эту задачу в случае сбоя всего пула, после чего вы должны переключиться между пользователями в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="ce9f4-107">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool.</span></span> <span data-ttu-id="ce9f4-108">Если эти пользователи не переносятся в исходный пул, необходимо выполнить описанные ниже действия, чтобы снова скопировать содержимое конференции в первоначальный пул.</span><span class="sxs-lookup"><span data-stu-id="ce9f4-108">When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="ce9f4-109">Предположим, что Pool1 связан с Pool2, а данные конференции в Pool1 теряются.</span><span class="sxs-lookup"><span data-stu-id="ce9f4-109">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="ce9f4-110">Вы можете использовать следующий командлет для вызова службы резервного копирования для восстановления содержимого:</span><span class="sxs-lookup"><span data-stu-id="ce9f4-110">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="ce9f4-111">Восстановление содержимого конференции может занять некоторое время в зависимости от его размера.</span><span class="sxs-lookup"><span data-stu-id="ce9f4-111">Restoring the conference contents may take some time, depending on their size.</span></span> <span data-ttu-id="ce9f4-112">Вы можете проверить состояние процесса с помощью следующего командлета:</span><span class="sxs-lookup"><span data-stu-id="ce9f4-112">You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="ce9f4-113">Процесс выполняется, если этот командлет возвращает значение стабильного состояния для модуля конференции с данными.</span><span class="sxs-lookup"><span data-stu-id="ce9f4-113">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

