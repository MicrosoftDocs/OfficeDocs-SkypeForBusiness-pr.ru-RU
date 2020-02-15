---
title: 'Lync Server 2013: Планирование аварийного восстановления парковки вызовов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Call Park disaster recovery
ms:assetid: f7cf3958-177b-4340-a864-35a6f44d6d88
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205395(v=OCS.15)
ms:contentKeyID: 48185867
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74aec0a6fe0edc288dfaae57a146c52cf9a0babe
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-park-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="c2dbe-102">Планирование аварийного восстановления парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2dbe-102">Planning for Call Park disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2dbe-103">_**Последнее изменение темы:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="c2dbe-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="c2dbe-104">В этом разделе описываются некоторые способы подготовки приложения парковки вызовов для аварийного восстановления и некоторые соображения для процесса аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="c2dbe-104">This section describes some ways to prepare the Call Park application for disaster recovery and some considerations for the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-call-park-disaster-recovery"></a><span data-ttu-id="c2dbe-105">Подготовка к аварийному восстановлению приостановки вызовов</span><span class="sxs-lookup"><span data-stu-id="c2dbe-105">Preparing for Call Park Disaster Recovery</span></span>

<span data-ttu-id="c2dbe-106">Имейте в виду следующее при подготовке и проведении процедур аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="c2dbe-106">Keep the following in mind when preparing for and carrying out disaster recovery procedures.</span></span>

  - <span data-ttu-id="c2dbe-107">Планируйте аварийное восстановление в ходе планирования мощности.</span><span class="sxs-lookup"><span data-stu-id="c2dbe-107">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="c2dbe-108">Для емкости аварийного восстановления каждый пул в связанном пуле должен иметь возможность обрабатывать рабочие нагрузки служб парковки вызовов в обоих пулах.</span><span class="sxs-lookup"><span data-stu-id="c2dbe-108">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of the Call Park services in both pools.</span></span> <span data-ttu-id="c2dbe-109">Подробнее о планировании мощности приостановки вызовов можно узнать [в статье Планирование мощности для парковки вызовов в Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span><span class="sxs-lookup"><span data-stu-id="c2dbe-109">For details about Call Park capacity planning, see [Capacity planning for Call Park in Lync Server 2013](lync-server-2013-capacity-planning-for-call-park.md).</span></span>

  - <span data-ttu-id="c2dbe-110">В ходе аварийного восстановления пользователи, которые были перенаправлены в резервный пул в рамках процесса аварийного переключения, используют службу парковки вызовов, выполняемую в резервном пуле.</span><span class="sxs-lookup"><span data-stu-id="c2dbe-110">During disaster recovery, users who have been redirected to the backup pool as part of the failover process use the Call Park service running in the backup pool.</span></span> <span data-ttu-id="c2dbe-111">Таким образом, для поддержки парковки вызовов во время аварийного восстановления необходимо, чтобы приложение парковки вызовов было развернуто и включено как в основном пуле, так и в резервном пуле.</span><span class="sxs-lookup"><span data-stu-id="c2dbe-111">Therefore, support for Call Park during disaster recovery requires the Call Park application to be deployed and enabled in both the primary pool and the backup pool.</span></span>

  - <span data-ttu-id="c2dbe-112">В каждом пуле должен иметься действительный диапазон номеров орбит для пользователей, которые размещаются в этом пуле, чтобы обеспечить парковку вызовов.</span><span class="sxs-lookup"><span data-stu-id="c2dbe-112">Each pool must have a valid range of orbit numbers for users who are homed in that pool to use for parking calls.</span></span>

  - <span data-ttu-id="c2dbe-113">Всегда храните отдельную резервную копию всех настроенных музыкальных файлов на удержании, которые были отправлены для парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="c2dbe-113">Always keep a separate backup copy of any customized music on hold that has been uploaded for Call Park.</span></span> <span data-ttu-id="c2dbe-114">Резервные копии этих файлов не входят в состав процесса аварийного восстановления Lync Server 2013 и будут потеряны, если загруженные в пул файлы повреждены, повреждены или удалены.</span><span class="sxs-lookup"><span data-stu-id="c2dbe-114">These files are not backed up as part of the Lync Server 2013 disaster recovery process and will be lost if the files uploaded to the pool are damaged, corrupted, or erased.</span></span>

</div>

<div>

## <a name="call-park-disaster-recovery-considerations"></a><span data-ttu-id="c2dbe-115">Вопросы аварийного восстановления парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="c2dbe-115">Call Park Disaster Recovery Considerations</span></span>

<span data-ttu-id="c2dbe-116">Можно определить только один набор параметров конфигурации приложения парковки вызовов и один настроенный звуковой файл музыки при удержании для каждого пула.</span><span class="sxs-lookup"><span data-stu-id="c2dbe-116">You can define only one set of Call Park application configuration settings and one customized music-on-hold audio file per pool.</span></span> <span data-ttu-id="c2dbe-117">Эти параметры включают пороговое значение времени ожидания, музыку при удержании, максимальное количество попыток ответа на вызовы и URI времени ожидания.</span><span class="sxs-lookup"><span data-stu-id="c2dbe-117">These settings include the timeout threshold, music on hold, maximum call pickup attempts, and timeout URI.</span></span> <span data-ttu-id="c2dbe-118">Чтобы просмотреть эти параметры конфигурации, запустите командлет **Get – CsCpsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="c2dbe-118">To view these configuration settings, run the **Get-CsCpsConfiguration** cmdlet.</span></span> <span data-ttu-id="c2dbe-119">Сведения о командлете **Get – CsCpsConfiguration** можно найти в статье [Get – CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span><span class="sxs-lookup"><span data-stu-id="c2dbe-119">For details about the **Get-CsCpsConfiguration** cmdlet, see [Get-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsCpsConfiguration).</span></span>

<span data-ttu-id="c2dbe-120">Во время аварийного восстановления Приостановка вызовов использует приложение парковки вызовов в резервном пуле, поэтому не выполняется резервное копирование параметров в основном пуле.</span><span class="sxs-lookup"><span data-stu-id="c2dbe-120">During disaster recovery, Call Park uses the Call Park application in the backup pool, so settings in the primary pool are not backed up.</span></span> <span data-ttu-id="c2dbe-121">Если основной пул восстановить невозможно и вы разворачиваете новый пул для замены основного пула, параметры из основного пула теряются и необходимо изменить параметры парковки вызовов и все настроенные звуковые файлы музыки для хранения в новом пуле.</span><span class="sxs-lookup"><span data-stu-id="c2dbe-121">If the primary pool can't be recovered and you deploy a new pool to replace the primary pool, the settings from the primary pool are lost, and you need to reconfigure the Call Park settings and any customized music-on-hold audio files in the new pool.</span></span>

<span data-ttu-id="c2dbe-122">При развертывании нового пула с другим полным доменным именем (FQDN) для замены основного пула необходимо переназначить все диапазоны орбит парковки вызовов, связанные с основным пулом, на полное доменное имя нового пула.</span><span class="sxs-lookup"><span data-stu-id="c2dbe-122">If you deploy a new pool with a different fully qualified domain name (FQDN) to replace the primary pool, you need to reassign all the Call Park orbit ranges that were associated with the primary pool to the FQDN of the new pool.</span></span> <span data-ttu-id="c2dbe-123">Чтобы переназначить диапазоны орбиты в новый пул, можно использовать либо панель управления Lync Server, либо командлет **Set – CsCallParkOrbit** .</span><span class="sxs-lookup"><span data-stu-id="c2dbe-123">To reassign orbit ranges to the new pool, you can use either Lync Server Control Panel or the **Set-CsCallParkOrbit** cmdlet.</span></span> <span data-ttu-id="c2dbe-124">Дополнительные сведения о командлете **Set – CsCallParkOrbit** см. в разделе [Set – CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span><span class="sxs-lookup"><span data-stu-id="c2dbe-124">For details about the **Set-CsCallParkOrbit** cmdlet, see [Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

