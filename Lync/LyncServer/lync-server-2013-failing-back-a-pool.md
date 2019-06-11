---
title: 'Lync Server 2013: отработка отказа для пула'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back a pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48184289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cade83015f57e86e08978ac3bfd9fb848dae9563
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-a-pool-in-lync-server-2013"></a><span data-ttu-id="65523-102">Отработка отказа для пула в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65523-102">Failing back a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65523-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="65523-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="65523-104">После того как пул, в котором произошел сбой, перейдет в оперативный режим (то есть Pool1 в этом примере), выполните указанные ниже действия, чтобы восстановить состояние развертывания для обычного рабочего состояния.</span><span class="sxs-lookup"><span data-stu-id="65523-104">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="65523-105">Обратите внимание, что процесс восстановления после сбоя занимает несколько минут.</span><span class="sxs-lookup"><span data-stu-id="65523-105">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="65523-106">Следует исходить из длительности 60 минут для пула, в котором работает 20 000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="65523-106">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

1.  <span data-ttu-id="65523-107">Не изменяйте пользователей, которые изначально были размещены в Pool1, и произошел сбой при переходе на Pool2, введя следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="65523-107">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="65523-108">Никаких других действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="65523-108">No other steps are necessary.</span></span> <span data-ttu-id="65523-109">Если вы отошел сбой на центральном сервере управления, вы можете оставить его в Pool2.</span><span class="sxs-lookup"><span data-stu-id="65523-109">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

