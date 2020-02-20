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
ms.openlocfilehash: c3aab42110bf1bf8eaafcebeddcd3acd168a80e4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a><span data-ttu-id="923db-102">Восстановление содержимого конференций с помощью службы резервного копирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="923db-102">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="923db-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="923db-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="923db-p101">Если сведения о конференциях, содержащиеся в хранилище файлов на интерфейсном пуле, становятся недоступными, необходимо восстановить эти сведения, чтобы пользователи, размещенные в пуле, сохранили свои данные конференций. Если интерфейсный пул, утративший данные конференций, объединен в пару с другим интерфейсным пулом, можно использовать службу резервного копирования для восстановления данных.</span><span class="sxs-lookup"><span data-stu-id="923db-p101">If the conference information stored in the file store of a Front End pool becomes unavailable. you must restore this information so that users homed on the pool retain their conference data. If the Front End pool which has lost conference data is paired with another Front End pool, you can use the Backup Service to restore the data.</span></span>

<span data-ttu-id="923db-p102">Необходимо также выполнить эту задачу, если вследствие сбоя не работает весь пул и необходимо перенести его пользователей в резервный пул. При восстановлении пользователей в исходном пуле необходимо использовать эту процедуру для копирования контента конференций обратно в исходный пул.</span><span class="sxs-lookup"><span data-stu-id="923db-p102">You must also perform this task if an entire pool has failed and you have to fail over its users to a backup pool. When these users are failed back over to their original pool, you must use this procedure to copy their conference content back to their original pool as well.</span></span>

<span data-ttu-id="923db-109">Предположим, что пул1 объединен с пулом2, а данные конференций в пуле1 утрачены.</span><span class="sxs-lookup"><span data-stu-id="923db-109">Assume that Pool1 is paired with Pool2, and the conference data in Pool1 is lost.</span></span> <span data-ttu-id="923db-110">Можно использовать следующий командлет для вызова службы резервного копирования для восстановления содержимого:</span><span class="sxs-lookup"><span data-stu-id="923db-110">You can use the following cmdlet to invoke the Backup Service to restore the contents:</span></span>

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="923db-p104">Восстановление содержимого конференций может занять некоторое время в зависимости от размера. Можно использовать приведенный ниже командлет для проверки состояния процесса:</span><span class="sxs-lookup"><span data-stu-id="923db-p104">Restoring the conference contents may take some time, depending on their size. You can use the following cmdlet to check the process status:</span></span>

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

<span data-ttu-id="923db-113">Процесс завершается, когда этот командлет возвращает значение Steady State для данных в модуле конференций.</span><span class="sxs-lookup"><span data-stu-id="923db-113">The process is done when this cmdlet returns a value of Steady State for the data conference module.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

