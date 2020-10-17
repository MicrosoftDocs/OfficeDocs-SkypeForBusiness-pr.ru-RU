---
title: 'Lync Server 2013: Планирование аварийного восстановления для группы ответа'
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
ms.openlocfilehash: 6cc238665ecb0222ded43e438e9f9370b561b85d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530576"
---
# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="c742f-102">Планирование аварийного восстановления группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c742f-102">Planning for response group disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c742f-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c742f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c742f-104">В этом разделе описываются некоторые способы подготовки групп ответа к аварийному восстановлению и обзор процесса аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="c742f-104">This section describes some ways to prepare response groups for disaster recovery and provides an overview of the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a><span data-ttu-id="c742f-105">Подготовка к аварийному восстановлению группы ответа</span><span class="sxs-lookup"><span data-stu-id="c742f-105">Preparing for Response Group Disaster Recovery</span></span>

<span data-ttu-id="c742f-106">При подготовке и выполнении процедур аварийного восстановления имейте в виду следующее.</span><span class="sxs-lookup"><span data-stu-id="c742f-106">Keep the following in mind when you prepare for and carry out disaster recovery procedures.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c742f-107">В среде сосуществования для процедур аварийного восстановления, описанных в этом документе, поддерживаются только группы ответа Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c742f-107">In a coexistence environment, only the Lync Server 2013 response groups are supported for the disaster recovery procedures described in this document.</span></span>



</div>

  - <span data-ttu-id="c742f-108">Планируйте аварийное восстановление в ходе планирования мощности.</span><span class="sxs-lookup"><span data-stu-id="c742f-108">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="c742f-109">Для емкости аварийного восстановления каждый пул в связанном пуле должен иметь возможность обрабатывать рабочие нагрузки всех групп ответа в обоих пулах.</span><span class="sxs-lookup"><span data-stu-id="c742f-109">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of all the response groups in both pools.</span></span> <span data-ttu-id="c742f-110">Подробнее о планировании мощности группы ответа можно узнать [в статье Планирование мощности для группы ответа в Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="c742f-110">For details about Response Group capacity planning, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span></span>

  - <span data-ttu-id="c742f-111">Создайте стандартные резервные копии всех конфигураций группы ответа во всех пулах переднего плана, где вы развернули приложение группы ответа с помощью процедуры экспорта, описанной в этом документе.</span><span class="sxs-lookup"><span data-stu-id="c742f-111">Take regular backup copies of all the response group configurations in all the Front End pools where you deployed the Response Group application by using the export procedure described in this document.</span></span> <span data-ttu-id="c742f-112">Для получения дополнительных сведений см. [процедуры аварийного восстановления группы ответа в Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c742f-112">For details, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span> <span data-ttu-id="c742f-113">Резервные копии следует хранить в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="c742f-113">Keep the backup copies in a safe location.</span></span>

  - <span data-ttu-id="c742f-114">Сохраните отдельную резервную копию всех исходных файлов, которые использовались для приложения группы ответа, включая записи и файлы для хранения музыки.</span><span class="sxs-lookup"><span data-stu-id="c742f-114">Keep a separate backup copy of all the original audio files you used for the Response Group application, including any recordings and music-on-hold files.</span></span> <span data-ttu-id="c742f-115">Храните файлы резервных копий в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="c742f-115">Keep the backup files in a safe location.</span></span>

  - <span data-ttu-id="c742f-116">При аварийном восстановлении Lync Server 2013 все параметры группы ответа должны иметь уникальные имена во всем развертывании.</span><span class="sxs-lookup"><span data-stu-id="c742f-116">For Lync Server 2013 disaster recovery, all Response Group settings must have unique names across your deployment.</span></span> <span data-ttu-id="c742f-117">Это требование относится к рабочим процессам, очередям, группам агентов, наборам праздников и часам бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c742f-117">This requirement applies to workflows, queues, agent groups, holiday sets, and hours of business.</span></span> <span data-ttu-id="c742f-118">Необходимо убедиться, что это требование выполнено, когда основной и резервный пулы по-прежнему активны, и до того, как необходимо инициировать какую-либо процедуру отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="c742f-118">You should verify that this requirement is met when the primary and backup pools are still active, and before you need to initiate any failover procedure.</span></span> <span data-ttu-id="c742f-119">Если при импорте данных группы ответа в резервный пул возникли конфликты имен, Импорт завершается неудачей.</span><span class="sxs-lookup"><span data-stu-id="c742f-119">If you encounter name conflicts while importing response group data to the backup pool, the import fails.</span></span> <span data-ttu-id="c742f-120">Чтобы выполнить процедуру импорта и отработки отказа, необходимо устранить конфликты имен, переопределив объект группы ответа в резервном пуле, или с помощью командлета **Import-CsRgsConfiguration** с параметром – ресолвенамеконфликтс, чтобы автоматически разрешить конфликт, добавив уникальный идентификационный номер в объект группы ответа.</span><span class="sxs-lookup"><span data-stu-id="c742f-120">To complete the import and failover procedure, you need to resolve the name conflicts by renaming the response group object in the backup pool or by using the **Import-CsRgsConfiguration** cmdlet with the –ResolveNameConflicts parameter to automatically resolve the conflict by appending a unique identifying number to the response group object.</span></span>

  - <span data-ttu-id="c742f-121">Как правило, рекомендуется выполнять ежедневное резервное копирование, но если у вас большой объем изменений, можно запланировать более частые резервные копии.</span><span class="sxs-lookup"><span data-stu-id="c742f-121">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="c742f-122">Объем данных, которые можно потерять в случае аварии, зависит от частоты резервного копирования, а также частоты и объема изменений.</span><span class="sxs-lookup"><span data-stu-id="c742f-122">The amount of information you can lose in the event of a disaster depends on the frequency of your backups, as well as the frequency and volume of changes.</span></span>

  - <span data-ttu-id="c742f-123">Можно импортировать группы ответа в резервный пул перед выполнением аварийной или резервной операции.</span><span class="sxs-lookup"><span data-stu-id="c742f-123">It is possible to import response groups to a backup pool before a disaster or failover operation occurs.</span></span> <span data-ttu-id="c742f-124">Импорт групп ответа в продвижение сокращает время простоя, так как служба группы ответа Lync Server может быть восстановлена в резервном пуле, как только вызовы направляются в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="c742f-124">Importing response groups in advance reduces downtime, because the Lync Server Response Group service can be restored in the backup pool as soon as calls are routed to the backup pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c742f-125">Приложение группы ответа не может получить доступ к агентам, размещенным в неактивном пуле, пока отработка отказа не завершена.</span><span class="sxs-lookup"><span data-stu-id="c742f-125">The Response Group application cannot reach any agents homed in an inactive pool until failover is complete.</span></span> <span data-ttu-id="c742f-126">В течение этого времени приложение группы ответа обрабатывает вызовы, как если бы эти агенты были недоступны.</span><span class="sxs-lookup"><span data-stu-id="c742f-126">During this time, the Response Group application processes calls as if those agents are unavailable.</span></span>

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a><span data-ttu-id="c742f-127">Процесс аварийного восстановления группы ответа</span><span class="sxs-lookup"><span data-stu-id="c742f-127">Response Group Disaster Recovery Process</span></span>

<span data-ttu-id="c742f-128">В случае аварии вы можете восстановить группы ответа, используя один из следующих подходов к восстановлению:</span><span class="sxs-lookup"><span data-stu-id="c742f-128">In the event of a disaster, you can recover response groups by using either of the following recovery approaches:</span></span>

  - <span data-ttu-id="c742f-129">Отработка отказа в резервном пуле и восстановление исходного пула.</span><span class="sxs-lookup"><span data-stu-id="c742f-129">Fail over to a backup pool and then fail back to the original pool.</span></span>

  - <span data-ttu-id="c742f-130">Отработка отказа для резервного копирования в резервный пул, создание нового пула с другим полным доменным именем (FQDN), а затем импорт групп ответа в новый пул.</span><span class="sxs-lookup"><span data-stu-id="c742f-130">Fail over to a backup pool, create a new pool with a different fully qualified domain name (FQDN), and then import the response groups to the new pool.</span></span>

<span data-ttu-id="c742f-131">На этапе отработки отказа в процессе аварийного восстановления группы ответа находятся в двух пулах: основном (который недоступен) и резервном.</span><span class="sxs-lookup"><span data-stu-id="c742f-131">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="c742f-132">Группы ответа в обоих пулах имеют одинаковое имя и владельца (основной пул), но разные родительские объекты.</span><span class="sxs-lookup"><span data-stu-id="c742f-132">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span>

<span data-ttu-id="c742f-133">При восстановлении путем создания нового пула с другим полным доменным именем необходимо назначить новый пул владельцем групп ответа при их импорте.</span><span class="sxs-lookup"><span data-stu-id="c742f-133">When you recover by creating a new pool with a different FQDN, you need to assign the new pool as the owner of the response groups when you import them.</span></span> <span data-ttu-id="c742f-134">Владелец групп ответа остается в исходном пуле до тех пор, пока не будет явно переназначено владение с помощью параметра – Овервритеовнер с помощью командлета **Import-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="c742f-134">Ownership of response groups remains with the original pool unless or until you explicitly reassign ownership by using the –OverwriteOwner parameter with the **Import-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c742f-135">Кроме того, необходимо использовать параметр – Овервритеовнер, если вы перестроили пул во время восстановления (то есть, что база данных группы ответа пуста), независимо от того, используется ли такое же полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="c742f-135">You also need to use the –OverwriteOwner parameter if you rebuilt the pool during the recovery (that is, the Response Group database is empty), whether or not you use the same FQDN.</span></span> <span data-ttu-id="c742f-136">Нет необходимости использовать параметр – Овервритеовнер, если вы не перестраивать пул, но этот параметр можно использовать при импорте групп ответа обратно в основной пул.</span><span class="sxs-lookup"><span data-stu-id="c742f-136">You do not need to use the –OverwriteOwner parameter if you did not rebuild the pool, but it is permissible to use this parameter whenever you import response groups back to the primary pool.</span></span>



</div>

<span data-ttu-id="c742f-137">Для каждого пула можно определить только один набор параметров конфигурации группы ответа уровня приложения.</span><span class="sxs-lookup"><span data-stu-id="c742f-137">You can define only one set of application-level Response Group configuration settings per pool.</span></span> <span data-ttu-id="c742f-138">Эти параметры включают используемую по умолчанию конфигурацию хранения музыки, а также стандартный звуковой файл с музыкой по умолчанию, период отсрочки агента удерживаемого абонента и контекстную конфигурацию вызова.</span><span class="sxs-lookup"><span data-stu-id="c742f-138">These settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="c742f-139">Чтобы просмотреть эти параметры конфигурации, запустите командлет **Get – CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="c742f-139">To view these configuration settings, run the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="c742f-140">Сведения о командлете **Get – CsRgsConfiguration** можно найти в статье [Get – CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span><span class="sxs-lookup"><span data-stu-id="c742f-140">For details about the **Get-CsRgsConfiguration** cmdlet, see [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span></span>

<span data-ttu-id="c742f-141">Эти параметры уровня приложения можно перенести из одного пула в другой с помощью командлета **Import-CsRgsConfiguration** с параметром – реплацеексистингсеттингс, но это переопределяет параметры в целевом пуле.</span><span class="sxs-lookup"><span data-stu-id="c742f-141">You can transfer these application-level settings from one pool to another by using the **Import-CsRgsConfiguration** cmdlet with the –ReplaceExistingSettings parameter, but doing so overrides the settings in the destination pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c742f-142">Это ограничение для переноса параметров в другой пул имеет значение true только для параметров уровня приложения и музыкальных файлов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c742f-142">This constraint about transferring settings to another pool is true only for the application-level settings and the default music-on-hold audio file.</span></span> <span data-ttu-id="c742f-143">Она не применяется к группам агентов, очередям, рабочим процессам, рабочим часам и наборам праздников.</span><span class="sxs-lookup"><span data-stu-id="c742f-143">It does not apply to agent groups, queues, workflows, business hours, and holiday sets.</span></span>



</div>

<span data-ttu-id="c742f-144">Если вы не хотите заменять параметры уровня приложения в резервном пуле во время аварии, и основной пул восстановить невозможно, параметры уровня приложения из основного пула будут утрачены.</span><span class="sxs-lookup"><span data-stu-id="c742f-144">If you don't want to replace the application-level settings in the backup pool during a disaster and the primary pool can't be recovered, the application-level settings from the primary pool will be lost.</span></span> <span data-ttu-id="c742f-145">Если необходимо создать новый пул для замены основного пула в ходе восстановления с таким же полным доменным именем или с другим полным доменным именем, вы не сможете восстановить исходные параметры на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="c742f-145">If you need to create a new pool to replace the primary pool during recovery, either with the same FQDN or with a different FQDN, you can't recover the original application-level settings.</span></span> <span data-ttu-id="c742f-146">В этом случае необходимо настроить новый пул с использованием этих параметров и включить звуковой файл с музыкой для сохранения.</span><span class="sxs-lookup"><span data-stu-id="c742f-146">In this case, you need to configure the new pool with these settings and include the music-on-hold audio file.</span></span>

<span data-ttu-id="c742f-147">Если вы решили использовать командлет **Import – CsRgsConfiguration** для переноса параметров уровня приложения из основного пула в резервный пул во время аварии, вы можете перенести параметры из резервного пула в новый пул во время восстановления, как это было передано из основного пула в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="c742f-147">If you decide to use the **Import-CsRgsConfiguration** cmdlet to transfer application-level settings from the primary pool to the backup pool during a disaster, you can then transfer the settings from the backup pool to the new pool during recovery in the same way that you transferred them from the primary pool to the backup pool.</span></span>

<span data-ttu-id="c742f-148">В следующей таблице представлен обзор действий, необходимых для восстановления групп ответа.</span><span class="sxs-lookup"><span data-stu-id="c742f-148">The following table is an overview of the steps involved in recovering response groups.</span></span>

<span data-ttu-id="c742f-149">Для получения дополнительных сведений о выполнении этих шагов обратитесь к разделу [процедуры аварийного восстановления группы ответа в Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c742f-149">For details about performing these steps, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span>

### <a name="response-group-disaster-recovery-steps"></a><span data-ttu-id="c742f-150">Этапы аварийного восстановления группы ответа</span><span class="sxs-lookup"><span data-stu-id="c742f-150">Response Group Disaster Recovery Steps</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c742f-151">Этап</span><span class="sxs-lookup"><span data-stu-id="c742f-151">Phase</span></span></th>
<th><span data-ttu-id="c742f-152">Действия</span><span class="sxs-lookup"><span data-stu-id="c742f-152">Steps</span></span></th>
<th><span data-ttu-id="c742f-153">Необходимые группы и роли</span><span class="sxs-lookup"><span data-stu-id="c742f-153">Required groups and roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c742f-154">Перед отключением</span><span class="sxs-lookup"><span data-stu-id="c742f-154">Before outage</span></span></p></td>
<td><p><span data-ttu-id="c742f-155">При необходимости выполните командлет <strong>Export-CsRgsConfiguration</strong> , чтобы создать резервные копии всех конфигураций группы ответа во всех пулах переднего плана, где развернуто приложение группы ответа.</span><span class="sxs-lookup"><span data-stu-id="c742f-155">On a routine basis, run the <strong>Export-CsRgsConfiguration</strong> cmdlet to create backups of all Response Group configurations in all Front End pools where Response Group application is deployed.</span></span></p></td>
<td><p><span data-ttu-id="c742f-156">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c742f-156">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="c742f-157">ксреспонсеграупадминистратор</span><span class="sxs-lookup"><span data-stu-id="c742f-157">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c742f-158">Во время сбоя</span><span class="sxs-lookup"><span data-stu-id="c742f-158">During outage</span></span></p></td>
<td><p><span data-ttu-id="c742f-159">Выполните командлет <strong>Import – CsRgsConfiguration</strong> для импорта конфигурации службы группы ответа Lync Server из основного пула в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="c742f-159">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the backed up Lync Server Response Group service configuration from the primary pool to the backup pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c742f-160">Используйте параметр – Реплацеексистингсеттингс, если требуется заменить параметры группы ответа уровня приложения в резервном пуле на параметры из основного пула.</span><span class="sxs-lookup"><span data-stu-id="c742f-160">Use the –ReplaceExistingSettings parameter if you want to replace application-level Response Group settings in the backup pool with the settings from the primary pool.</span></span> <span data-ttu-id="c742f-161">Если не перенести параметры уровня приложения из основного пула в резервный пул, а основной пул восстановить невозможно, параметры из основного пула будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="c742f-161">If you do not transfer the application-level settings from the primary pool to the backup pool, and the primary pool can't be recovered, you will lose the settings from the primary pool.</span></span>


</div></td>
<td><p><span data-ttu-id="c742f-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c742f-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="c742f-163">ксреспонсеграупадминистратор</span><span class="sxs-lookup"><span data-stu-id="c742f-163">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c742f-164">После импорта</span><span class="sxs-lookup"><span data-stu-id="c742f-164">After importing</span></span></p></td>
<td><p><span data-ttu-id="c742f-165">Выполните командлеты группы ответа с параметром – ShowAll (для отображения всех групп ответа) или параметр – Owner (для отображения только импортированных групп ответа), чтобы убедиться в том, что все конфигурации группы ответа были импортированы в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="c742f-165">Run Response Group cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were imported to the backup pool.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="c742f-166">Если вы не используете параметр – ShowAll или параметр – owner, группы ответа, импортированные в резервный пул, не будут отображаться в результатах, возвращенных командлетами.</span><span class="sxs-lookup"><span data-stu-id="c742f-166">If you do not use either the –ShowAll parameter or the –Owner parameter, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>


</div>
<p><span data-ttu-id="c742f-167">Выполните следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="c742f-167">Run the following cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="c742f-168"><strong>Get — CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="c742f-168"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="c742f-169"><strong>Get — CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="c742f-169"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="c742f-170"><strong>Get — CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="c742f-170"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="c742f-171"><strong>Get — CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="c742f-171"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="c742f-172"><strong>Get — CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="c742f-172"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c742f-173">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c742f-173">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="c742f-174">ксреспонсеграупадминистратор</span><span class="sxs-lookup"><span data-stu-id="c742f-174">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c742f-175">После отработки отказа</span><span class="sxs-lookup"><span data-stu-id="c742f-175">After failover</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c742f-176">Установите тестовый вызов группы ответа, которая была импортирована в резервный пул, и убедитесь, что вызов обрабатывается правильно.</span><span class="sxs-lookup"><span data-stu-id="c742f-176">Place a test call to a response group that was imported to the backup pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="c742f-177">Все формальные агенты должны снова войти в свои формальные группы в резервном пуле.</span><span class="sxs-lookup"><span data-stu-id="c742f-177">All formal agents must sign in again to their formal groups on backup pool.</span></span></p></li>
<li><p><span data-ttu-id="c742f-178">Управление изменениями конфигурации:</span><span class="sxs-lookup"><span data-stu-id="c742f-178">Manage configuration changes:</span></span></p>
<p><span data-ttu-id="c742f-179">Группы ответа в резервном пуле, импортированные в резервный пул или принадлежащие резервному пулу, могут быть изменены как обычно во время сбоя.</span><span class="sxs-lookup"><span data-stu-id="c742f-179">Response groups in the backup pool, whether imported to the backup pool or owned by the backup pool, can be modified as usual during the outage.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="c742f-180">Для управления группами ответа, импортированными в резервный пул, необходимо использовать командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c742f-180">You must use Lync Server Management Shell to manage the response groups that you imported to the backup pool.</span></span> <span data-ttu-id="c742f-181">Вы не можете использовать панель управления Lync Server для управления этими группами ответа, пока они находятся в резервном пуле.</span><span class="sxs-lookup"><span data-stu-id="c742f-181">You cannot use Lync Server Control Panel to manage these response groups while they are in the backup pool.</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="c742f-182">Недоступно</span><span class="sxs-lookup"><span data-stu-id="c742f-182">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c742f-183">После восстановления до восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="c742f-183">After recovery, before failback</span></span></p></td>
<td><p><span data-ttu-id="c742f-184">Выполните командлет <strong>Export-CsRgsConfiguration</strong> , указав параметр-Source в качестве резервного пула, и параметр – owner в качестве основного пула для экспорта групп ответа, принадлежащих основному пулу, из резервного пула.</span><span class="sxs-lookup"><span data-stu-id="c742f-184">Run the <strong>Export-CsRgsConfiguration</strong> cmdlet specifying the -Source parameter as the backup pool and the –Owner parameter as the primary pool to export the response groups owned by the primary pool from the backup pool.</span></span></p></td>
<td><p><span data-ttu-id="c742f-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c742f-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="c742f-186">ксреспонсеграупадминистратор</span><span class="sxs-lookup"><span data-stu-id="c742f-186">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c742f-187">После восстановления размещения</span><span class="sxs-lookup"><span data-stu-id="c742f-187">After failback</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c742f-188">Выполните командлет <strong>Import – CsRgsConfiguration</strong> , чтобы импортировать группы ответа обратно в основной пул.</span><span class="sxs-lookup"><span data-stu-id="c742f-188">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the response groups back to the primary pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c742f-189">Если основной пул восстановить невозможно и вы развернете новый пул, чтобы заменить его, используйте параметр – Реплацеексистингсеттингс для переноса параметров уровня приложения из резервного пула в новый пул.</span><span class="sxs-lookup"><span data-stu-id="c742f-189">If the primary pool can't be recovered and you deploy a new pool to replace it, use the –ReplaceExistingSettings parameter to transfer the application-level settings from the backup pool to the new pool.</span></span> <span data-ttu-id="c742f-190">Если вы не переносите параметры из резервного пула, новый пул будет использовать параметры по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c742f-190">If you do not transfer the settings from the backup pool, the new pool will use the default settings.</span></span>


</div></li>
<li><p><span data-ttu-id="c742f-191">Выполните следующие командлеты с параметром – ShowAll (для отображения всех групп ответа) или параметр – Owner (для отображения только импортированных групп ответа), чтобы убедиться, что все конфигурации группы ответа успешно импортированы обратно в основной пул:</span><span class="sxs-lookup"><span data-stu-id="c742f-191">Run the following cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were successfully imported back to the primary pool:</span></span></p>
<ul>
<li><p><span data-ttu-id="c742f-192"><strong>Get — CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="c742f-192"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="c742f-193"><strong>Get — CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="c742f-193"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="c742f-194"><strong>Get — CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="c742f-194"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="c742f-195"><strong>Get — CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="c742f-195"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="c742f-196"><strong>Get — CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="c742f-196"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="c742f-197">Поместите тестовый вызов в группу ответа, которая была импортирована обратно в основной пул, и убедитесь, что вызов обрабатывается правильно.</span><span class="sxs-lookup"><span data-stu-id="c742f-197">Place a test call to a response group that was imported back to the primary pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="c742f-198">При необходимости выполните командлет <strong>Export-CsRgsConfiguration</strong> в резервном пуле с параметром – ремовикспортедконфигуратион, чтобы удалить из резервного пула группы ответа, принадлежащие основному пулу.</span><span class="sxs-lookup"><span data-stu-id="c742f-198">Optionally, run the <strong>Export-CsRgsConfiguration</strong> cmdlet on the backup pool with the –RemoveExportedConfiguration parameter to remove the response groups owned by the primary pool from the backup pool.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c742f-199">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="c742f-199">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="c742f-200">ксреспонсеграупадминистратор</span><span class="sxs-lookup"><span data-stu-id="c742f-200">CsResponseGroupAdministrator</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

