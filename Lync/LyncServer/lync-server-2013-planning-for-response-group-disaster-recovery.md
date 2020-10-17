---
title: 'Lync Server 2013: Планирование аварийного восстановления для группы ответа'
description: 'Lync Server 2013: Планирование аварийного восстановления группы ответа.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5294ddf7dbd42d95c5eb17acd6be6a5abc7a5917
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549265"
---
# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="afd26-103">Планирование аварийного восстановления группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afd26-103">Planning for response group disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afd26-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="afd26-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="afd26-105">В этом разделе описываются некоторые способы подготовки групп ответа к аварийному восстановлению и обзор процесса аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="afd26-105">This section describes some ways to prepare response groups for disaster recovery and provides an overview of the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a><span data-ttu-id="afd26-106">Подготовка к аварийному восстановлению группы ответа</span><span class="sxs-lookup"><span data-stu-id="afd26-106">Preparing for Response Group Disaster Recovery</span></span>

<span data-ttu-id="afd26-107">При подготовке и выполнении процедур аварийного восстановления имейте в виду следующее.</span><span class="sxs-lookup"><span data-stu-id="afd26-107">Keep the following in mind when you prepare for and carry out disaster recovery procedures.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="afd26-108">В среде сосуществования для процедур аварийного восстановления, описанных в этом документе, поддерживаются только группы ответа Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="afd26-108">In a coexistence environment, only the Lync Server 2013 response groups are supported for the disaster recovery procedures described in this document.</span></span>



</div>

  - <span data-ttu-id="afd26-109">Планируйте аварийное восстановление в ходе планирования мощности.</span><span class="sxs-lookup"><span data-stu-id="afd26-109">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="afd26-110">Для емкости аварийного восстановления каждый пул в связанном пуле должен иметь возможность обрабатывать рабочие нагрузки всех групп ответа в обоих пулах.</span><span class="sxs-lookup"><span data-stu-id="afd26-110">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of all the response groups in both pools.</span></span> <span data-ttu-id="afd26-111">Подробнее о планировании мощности группы ответа можно узнать [в статье Планирование мощности для группы ответа в Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="afd26-111">For details about Response Group capacity planning, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span></span>

  - <span data-ttu-id="afd26-112">Создайте стандартные резервные копии всех конфигураций группы ответа во всех пулах переднего плана, где вы развернули приложение группы ответа с помощью процедуры экспорта, описанной в этом документе.</span><span class="sxs-lookup"><span data-stu-id="afd26-112">Take regular backup copies of all the response group configurations in all the Front End pools where you deployed the Response Group application by using the export procedure described in this document.</span></span> <span data-ttu-id="afd26-113">Для получения дополнительных сведений см. [процедуры аварийного восстановления группы ответа в Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="afd26-113">For details, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span> <span data-ttu-id="afd26-114">Резервные копии следует хранить в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="afd26-114">Keep the backup copies in a safe location.</span></span>

  - <span data-ttu-id="afd26-115">Сохраните отдельную резервную копию всех исходных файлов, которые использовались для приложения группы ответа, включая записи и файлы для хранения музыки.</span><span class="sxs-lookup"><span data-stu-id="afd26-115">Keep a separate backup copy of all the original audio files you used for the Response Group application, including any recordings and music-on-hold files.</span></span> <span data-ttu-id="afd26-116">Храните файлы резервных копий в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="afd26-116">Keep the backup files in a safe location.</span></span>

  - <span data-ttu-id="afd26-117">При аварийном восстановлении Lync Server 2013 все параметры группы ответа должны иметь уникальные имена во всем развертывании.</span><span class="sxs-lookup"><span data-stu-id="afd26-117">For Lync Server 2013 disaster recovery, all Response Group settings must have unique names across your deployment.</span></span> <span data-ttu-id="afd26-118">Это требование относится к рабочим процессам, очередям, группам агентов, наборам праздников и часам бизнеса.</span><span class="sxs-lookup"><span data-stu-id="afd26-118">This requirement applies to workflows, queues, agent groups, holiday sets, and hours of business.</span></span> <span data-ttu-id="afd26-119">Необходимо убедиться, что это требование выполнено, когда основной и резервный пулы по-прежнему активны, и до того, как необходимо инициировать какую-либо процедуру отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="afd26-119">You should verify that this requirement is met when the primary and backup pools are still active, and before you need to initiate any failover procedure.</span></span> <span data-ttu-id="afd26-120">Если при импорте данных группы ответа в резервный пул возникли конфликты имен, Импорт завершается неудачей.</span><span class="sxs-lookup"><span data-stu-id="afd26-120">If you encounter name conflicts while importing response group data to the backup pool, the import fails.</span></span> <span data-ttu-id="afd26-121">Чтобы выполнить процедуру импорта и отработки отказа, необходимо устранить конфликты имен, переопределив объект группы ответа в резервном пуле, или с помощью командлета **Import-CsRgsConfiguration** с параметром – ресолвенамеконфликтс, чтобы автоматически разрешить конфликт, добавив уникальный идентификационный номер в объект группы ответа.</span><span class="sxs-lookup"><span data-stu-id="afd26-121">To complete the import and failover procedure, you need to resolve the name conflicts by renaming the response group object in the backup pool or by using the **Import-CsRgsConfiguration** cmdlet with the –ResolveNameConflicts parameter to automatically resolve the conflict by appending a unique identifying number to the response group object.</span></span>

  - <span data-ttu-id="afd26-122">Как правило, рекомендуется выполнять ежедневное резервное копирование, но если у вас большой объем изменений, можно запланировать более частые резервные копии.</span><span class="sxs-lookup"><span data-stu-id="afd26-122">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="afd26-123">Объем данных, которые можно потерять в случае аварии, зависит от частоты резервного копирования, а также частоты и объема изменений.</span><span class="sxs-lookup"><span data-stu-id="afd26-123">The amount of information you can lose in the event of a disaster depends on the frequency of your backups, as well as the frequency and volume of changes.</span></span>

  - <span data-ttu-id="afd26-124">Можно импортировать группы ответа в резервный пул перед выполнением аварийной или резервной операции.</span><span class="sxs-lookup"><span data-stu-id="afd26-124">It is possible to import response groups to a backup pool before a disaster or failover operation occurs.</span></span> <span data-ttu-id="afd26-125">Импорт групп ответа в продвижение сокращает время простоя, так как служба группы ответа Lync Server может быть восстановлена в резервном пуле, как только вызовы направляются в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="afd26-125">Importing response groups in advance reduces downtime, because the Lync Server Response Group service can be restored in the backup pool as soon as calls are routed to the backup pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="afd26-126">Приложение группы ответа не может получить доступ к агентам, размещенным в неактивном пуле, пока отработка отказа не завершена.</span><span class="sxs-lookup"><span data-stu-id="afd26-126">The Response Group application cannot reach any agents homed in an inactive pool until failover is complete.</span></span> <span data-ttu-id="afd26-127">В течение этого времени приложение группы ответа обрабатывает вызовы, как если бы эти агенты были недоступны.</span><span class="sxs-lookup"><span data-stu-id="afd26-127">During this time, the Response Group application processes calls as if those agents are unavailable.</span></span>

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a><span data-ttu-id="afd26-128">Процесс аварийного восстановления группы ответа</span><span class="sxs-lookup"><span data-stu-id="afd26-128">Response Group Disaster Recovery Process</span></span>

<span data-ttu-id="afd26-129">В случае аварии вы можете восстановить группы ответа, используя один из следующих подходов к восстановлению:</span><span class="sxs-lookup"><span data-stu-id="afd26-129">In the event of a disaster, you can recover response groups by using either of the following recovery approaches:</span></span>

  - <span data-ttu-id="afd26-130">Отработка отказа в резервном пуле и восстановление исходного пула.</span><span class="sxs-lookup"><span data-stu-id="afd26-130">Fail over to a backup pool and then fail back to the original pool.</span></span>

  - <span data-ttu-id="afd26-131">Отработка отказа для резервного копирования в резервный пул, создание нового пула с другим полным доменным именем (FQDN), а затем импорт групп ответа в новый пул.</span><span class="sxs-lookup"><span data-stu-id="afd26-131">Fail over to a backup pool, create a new pool with a different fully qualified domain name (FQDN), and then import the response groups to the new pool.</span></span>

<span data-ttu-id="afd26-132">На этапе отработки отказа в процессе аварийного восстановления группы ответа находятся в двух пулах: основном (который недоступен) и резервном.</span><span class="sxs-lookup"><span data-stu-id="afd26-132">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="afd26-133">Группы ответа в обоих пулах имеют одинаковое имя и владельца (основной пул), но разные родительские объекты.</span><span class="sxs-lookup"><span data-stu-id="afd26-133">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span>

<span data-ttu-id="afd26-134">При восстановлении путем создания нового пула с другим полным доменным именем необходимо назначить новый пул владельцем групп ответа при их импорте.</span><span class="sxs-lookup"><span data-stu-id="afd26-134">When you recover by creating a new pool with a different FQDN, you need to assign the new pool as the owner of the response groups when you import them.</span></span> <span data-ttu-id="afd26-135">Владелец групп ответа остается в исходном пуле до тех пор, пока не будет явно переназначено владение с помощью параметра – Овервритеовнер с помощью командлета **Import-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="afd26-135">Ownership of response groups remains with the original pool unless or until you explicitly reassign ownership by using the –OverwriteOwner parameter with the **Import-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="afd26-136">Кроме того, необходимо использовать параметр – Овервритеовнер, если вы перестроили пул во время восстановления (то есть, что база данных группы ответа пуста), независимо от того, используется ли такое же полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="afd26-136">You also need to use the –OverwriteOwner parameter if you rebuilt the pool during the recovery (that is, the Response Group database is empty), whether or not you use the same FQDN.</span></span> <span data-ttu-id="afd26-137">Нет необходимости использовать параметр – Овервритеовнер, если вы не перестраивать пул, но этот параметр можно использовать при импорте групп ответа обратно в основной пул.</span><span class="sxs-lookup"><span data-stu-id="afd26-137">You do not need to use the –OverwriteOwner parameter if you did not rebuild the pool, but it is permissible to use this parameter whenever you import response groups back to the primary pool.</span></span>



</div>

<span data-ttu-id="afd26-138">Для каждого пула можно определить только один набор параметров конфигурации группы ответа уровня приложения.</span><span class="sxs-lookup"><span data-stu-id="afd26-138">You can define only one set of application-level Response Group configuration settings per pool.</span></span> <span data-ttu-id="afd26-139">Эти параметры включают используемую по умолчанию конфигурацию хранения музыки, а также стандартный звуковой файл с музыкой по умолчанию, период отсрочки агента удерживаемого абонента и контекстную конфигурацию вызова.</span><span class="sxs-lookup"><span data-stu-id="afd26-139">These settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="afd26-140">Чтобы просмотреть эти параметры конфигурации, запустите командлет **Get – CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="afd26-140">To view these configuration settings, run the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="afd26-141">Сведения о командлете **Get – CsRgsConfiguration** можно найти в статье [Get – CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span><span class="sxs-lookup"><span data-stu-id="afd26-141">For details about the **Get-CsRgsConfiguration** cmdlet, see [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span></span>

<span data-ttu-id="afd26-142">Эти параметры уровня приложения можно перенести из одного пула в другой с помощью командлета **Import-CsRgsConfiguration** с параметром – реплацеексистингсеттингс, но это переопределяет параметры в целевом пуле.</span><span class="sxs-lookup"><span data-stu-id="afd26-142">You can transfer these application-level settings from one pool to another by using the **Import-CsRgsConfiguration** cmdlet with the –ReplaceExistingSettings parameter, but doing so overrides the settings in the destination pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="afd26-143">Это ограничение для переноса параметров в другой пул имеет значение true только для параметров уровня приложения и музыкальных файлов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="afd26-143">This constraint about transferring settings to another pool is true only for the application-level settings and the default music-on-hold audio file.</span></span> <span data-ttu-id="afd26-144">Она не применяется к группам агентов, очередям, рабочим процессам, рабочим часам и наборам праздников.</span><span class="sxs-lookup"><span data-stu-id="afd26-144">It does not apply to agent groups, queues, workflows, business hours, and holiday sets.</span></span>



</div>

<span data-ttu-id="afd26-145">Если вы не хотите заменять параметры уровня приложения в резервном пуле во время аварии, и основной пул восстановить невозможно, параметры уровня приложения из основного пула будут утрачены.</span><span class="sxs-lookup"><span data-stu-id="afd26-145">If you don't want to replace the application-level settings in the backup pool during a disaster and the primary pool can't be recovered, the application-level settings from the primary pool will be lost.</span></span> <span data-ttu-id="afd26-146">Если необходимо создать новый пул для замены основного пула в ходе восстановления с таким же полным доменным именем или с другим полным доменным именем, вы не сможете восстановить исходные параметры на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="afd26-146">If you need to create a new pool to replace the primary pool during recovery, either with the same FQDN or with a different FQDN, you can't recover the original application-level settings.</span></span> <span data-ttu-id="afd26-147">В этом случае необходимо настроить новый пул с использованием этих параметров и включить звуковой файл с музыкой для сохранения.</span><span class="sxs-lookup"><span data-stu-id="afd26-147">In this case, you need to configure the new pool with these settings and include the music-on-hold audio file.</span></span>

<span data-ttu-id="afd26-148">Если вы решили использовать командлет **Import – CsRgsConfiguration** для переноса параметров уровня приложения из основного пула в резервный пул во время аварии, вы можете перенести параметры из резервного пула в новый пул во время восстановления, как это было передано из основного пула в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="afd26-148">If you decide to use the **Import-CsRgsConfiguration** cmdlet to transfer application-level settings from the primary pool to the backup pool during a disaster, you can then transfer the settings from the backup pool to the new pool during recovery in the same way that you transferred them from the primary pool to the backup pool.</span></span>

<span data-ttu-id="afd26-149">В следующей таблице представлен обзор действий, необходимых для восстановления групп ответа.</span><span class="sxs-lookup"><span data-stu-id="afd26-149">The following table is an overview of the steps involved in recovering response groups.</span></span>

<span data-ttu-id="afd26-150">Для получения дополнительных сведений о выполнении этих шагов обратитесь к разделу [процедуры аварийного восстановления группы ответа в Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="afd26-150">For details about performing these steps, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span>

### <a name="response-group-disaster-recovery-steps"></a><span data-ttu-id="afd26-151">Этапы аварийного восстановления группы ответа</span><span class="sxs-lookup"><span data-stu-id="afd26-151">Response Group Disaster Recovery Steps</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="afd26-152">Этап</span><span class="sxs-lookup"><span data-stu-id="afd26-152">Phase</span></span></th>
<th><span data-ttu-id="afd26-153">Действия</span><span class="sxs-lookup"><span data-stu-id="afd26-153">Steps</span></span></th>
<th><span data-ttu-id="afd26-154">Необходимые группы и роли</span><span class="sxs-lookup"><span data-stu-id="afd26-154">Required groups and roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="afd26-155">Перед отключением</span><span class="sxs-lookup"><span data-stu-id="afd26-155">Before outage</span></span></p></td>
<td><p><span data-ttu-id="afd26-156">При необходимости выполните командлет <strong>Export-CsRgsConfiguration</strong> , чтобы создать резервные копии всех конфигураций группы ответа во всех пулах переднего плана, где развернуто приложение группы ответа.</span><span class="sxs-lookup"><span data-stu-id="afd26-156">On a routine basis, run the <strong>Export-CsRgsConfiguration</strong> cmdlet to create backups of all Response Group configurations in all Front End pools where Response Group application is deployed.</span></span></p></td>
<td><p><span data-ttu-id="afd26-157">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="afd26-157">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="afd26-158">ксреспонсеграупадминистратор</span><span class="sxs-lookup"><span data-stu-id="afd26-158">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afd26-159">Во время сбоя</span><span class="sxs-lookup"><span data-stu-id="afd26-159">During outage</span></span></p></td>
<td><p><span data-ttu-id="afd26-160">Выполните командлет <strong>Import – CsRgsConfiguration</strong> для импорта конфигурации службы группы ответа Lync Server из основного пула в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="afd26-160">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the backed up Lync Server Response Group service configuration from the primary pool to the backup pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="afd26-161">Используйте параметр – Реплацеексистингсеттингс, если требуется заменить параметры группы ответа уровня приложения в резервном пуле на параметры из основного пула.</span><span class="sxs-lookup"><span data-stu-id="afd26-161">Use the –ReplaceExistingSettings parameter if you want to replace application-level Response Group settings in the backup pool with the settings from the primary pool.</span></span> <span data-ttu-id="afd26-162">Если не перенести параметры уровня приложения из основного пула в резервный пул, а основной пул восстановить невозможно, параметры из основного пула будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="afd26-162">If you do not transfer the application-level settings from the primary pool to the backup pool, and the primary pool can't be recovered, you will lose the settings from the primary pool.</span></span>


</div></td>
<td><p><span data-ttu-id="afd26-163">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="afd26-163">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="afd26-164">ксреспонсеграупадминистратор</span><span class="sxs-lookup"><span data-stu-id="afd26-164">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afd26-165">После импорта</span><span class="sxs-lookup"><span data-stu-id="afd26-165">After importing</span></span></p></td>
<td><p><span data-ttu-id="afd26-166">Выполните командлеты группы ответа с параметром – ShowAll (для отображения всех групп ответа) или параметр – Owner (для отображения только импортированных групп ответа), чтобы убедиться в том, что все конфигурации группы ответа были импортированы в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="afd26-166">Run Response Group cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were imported to the backup pool.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="afd26-167">Если вы не используете параметр – ShowAll или параметр – owner, группы ответа, импортированные в резервный пул, не будут отображаться в результатах, возвращенных командлетами.</span><span class="sxs-lookup"><span data-stu-id="afd26-167">If you do not use either the –ShowAll parameter or the –Owner parameter, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>


</div>
<p><span data-ttu-id="afd26-168">Выполните следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="afd26-168">Run the following cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="afd26-169"><strong>Get — CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="afd26-169"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="afd26-170"><strong>Get — CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="afd26-170"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="afd26-171"><strong>Get — CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="afd26-171"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="afd26-172"><strong>Get — CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="afd26-172"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="afd26-173"><strong>Get — CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="afd26-173"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="afd26-174">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="afd26-174">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="afd26-175">ксреспонсеграупадминистратор</span><span class="sxs-lookup"><span data-stu-id="afd26-175">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afd26-176">После отработки отказа</span><span class="sxs-lookup"><span data-stu-id="afd26-176">After failover</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="afd26-177">Установите тестовый вызов группы ответа, которая была импортирована в резервный пул, и убедитесь, что вызов обрабатывается правильно.</span><span class="sxs-lookup"><span data-stu-id="afd26-177">Place a test call to a response group that was imported to the backup pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="afd26-178">Все формальные агенты должны снова войти в свои формальные группы в резервном пуле.</span><span class="sxs-lookup"><span data-stu-id="afd26-178">All formal agents must sign in again to their formal groups on backup pool.</span></span></p></li>
<li><p><span data-ttu-id="afd26-179">Управление изменениями конфигурации:</span><span class="sxs-lookup"><span data-stu-id="afd26-179">Manage configuration changes:</span></span></p>
<p><span data-ttu-id="afd26-180">Группы ответа в резервном пуле, импортированные в резервный пул или принадлежащие резервному пулу, могут быть изменены как обычно во время сбоя.</span><span class="sxs-lookup"><span data-stu-id="afd26-180">Response groups in the backup pool, whether imported to the backup pool or owned by the backup pool, can be modified as usual during the outage.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="afd26-181">Для управления группами ответа, импортированными в резервный пул, необходимо использовать командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="afd26-181">You must use Lync Server Management Shell to manage the response groups that you imported to the backup pool.</span></span> <span data-ttu-id="afd26-182">Вы не можете использовать панель управления Lync Server для управления этими группами ответа, пока они находятся в резервном пуле.</span><span class="sxs-lookup"><span data-stu-id="afd26-182">You cannot use Lync Server Control Panel to manage these response groups while they are in the backup pool.</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="afd26-183">Недоступно</span><span class="sxs-lookup"><span data-stu-id="afd26-183">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afd26-184">После восстановления до восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="afd26-184">After recovery, before failback</span></span></p></td>
<td><p><span data-ttu-id="afd26-185">Выполните командлет <strong>Export-CsRgsConfiguration</strong> , указав параметр-Source в качестве резервного пула, и параметр – owner в качестве основного пула для экспорта групп ответа, принадлежащих основному пулу, из резервного пула.</span><span class="sxs-lookup"><span data-stu-id="afd26-185">Run the <strong>Export-CsRgsConfiguration</strong> cmdlet specifying the -Source parameter as the backup pool and the –Owner parameter as the primary pool to export the response groups owned by the primary pool from the backup pool.</span></span></p></td>
<td><p><span data-ttu-id="afd26-186">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="afd26-186">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="afd26-187">ксреспонсеграупадминистратор</span><span class="sxs-lookup"><span data-stu-id="afd26-187">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afd26-188">После восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="afd26-188">After failback</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="afd26-189">Выполните командлет <strong>Import – CsRgsConfiguration</strong> , чтобы импортировать группы ответа обратно в основной пул.</span><span class="sxs-lookup"><span data-stu-id="afd26-189">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the response groups back to the primary pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="afd26-190">Если основной пул восстановить невозможно и вы развернете новый пул, чтобы заменить его, используйте параметр – Реплацеексистингсеттингс для переноса параметров уровня приложения из резервного пула в новый пул.</span><span class="sxs-lookup"><span data-stu-id="afd26-190">If the primary pool can't be recovered and you deploy a new pool to replace it, use the –ReplaceExistingSettings parameter to transfer the application-level settings from the backup pool to the new pool.</span></span> <span data-ttu-id="afd26-191">Если вы не переносите параметры из резервного пула, новый пул будет использовать параметры по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="afd26-191">If you do not transfer the settings from the backup pool, the new pool will use the default settings.</span></span>


</div></li>
<li><p><span data-ttu-id="afd26-192">Выполните следующие командлеты с параметром – ShowAll (для отображения всех групп ответа) или параметр – Owner (для отображения только импортированных групп ответа), чтобы убедиться, что все конфигурации группы ответа успешно импортированы обратно в основной пул:</span><span class="sxs-lookup"><span data-stu-id="afd26-192">Run the following cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were successfully imported back to the primary pool:</span></span></p>
<ul>
<li><p><span data-ttu-id="afd26-193"><strong>Get — CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="afd26-193"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="afd26-194"><strong>Get — CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="afd26-194"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="afd26-195"><strong>Get — CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="afd26-195"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="afd26-196"><strong>Get — CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="afd26-196"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="afd26-197"><strong>Get — CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="afd26-197"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="afd26-198">Поместите тестовый вызов в группу ответа, которая была импортирована обратно в основной пул, и убедитесь, что вызов обрабатывается правильно.</span><span class="sxs-lookup"><span data-stu-id="afd26-198">Place a test call to a response group that was imported back to the primary pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="afd26-199">При необходимости выполните командлет <strong>Export-CsRgsConfiguration</strong> в резервном пуле с параметром – ремовикспортедконфигуратион, чтобы удалить из резервного пула группы ответа, принадлежащие основному пулу.</span><span class="sxs-lookup"><span data-stu-id="afd26-199">Optionally, run the <strong>Export-CsRgsConfiguration</strong> cmdlet on the backup pool with the –RemoveExportedConfiguration parameter to remove the response groups owned by the primary pool from the backup pool.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="afd26-200">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="afd26-200">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="afd26-201">ксреспонсеграупадминистратор</span><span class="sxs-lookup"><span data-stu-id="afd26-201">CsResponseGroupAdministrator</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

