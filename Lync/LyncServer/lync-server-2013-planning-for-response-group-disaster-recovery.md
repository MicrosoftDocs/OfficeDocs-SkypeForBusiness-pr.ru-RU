---
title: 'Lync Server 2013: планирование аварийного восстановления для группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for response group disaster recovery
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204699(v=OCS.15)
ms:contentKeyID: 48183482
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70622364349eb83ecbc171cb3d5bf894ba03d3f9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-response-group-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="47341-102">Планирование аварийного восстановления для группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47341-102">Planning for response group disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47341-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="47341-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="47341-104">В этом разделе описаны некоторые способы подготовки групп ответов для аварийного восстановления и обзор процесса аварийного восстановления.</span><span class="sxs-lookup"><span data-stu-id="47341-104">This section describes some ways to prepare response groups for disaster recovery and provides an overview of the disaster recovery process.</span></span>

<div>

## <a name="preparing-for-response-group-disaster-recovery"></a><span data-ttu-id="47341-105">Подготовка к аварийному восстановлению группы ответов</span><span class="sxs-lookup"><span data-stu-id="47341-105">Preparing for Response Group Disaster Recovery</span></span>

<span data-ttu-id="47341-106">При подготовке и выполнении процедур аварийного восстановления следует учитывать следующее:</span><span class="sxs-lookup"><span data-stu-id="47341-106">Keep the following in mind when you prepare for and carry out disaster recovery procedures.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="47341-107">В среде сосуществования для процедур аварийного восстановления, описанных в этом документе, поддерживаются только группы ответов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="47341-107">In a coexistence environment, only the Lync Server 2013 response groups are supported for the disaster recovery procedures described in this document.</span></span>



</div>

  - <span data-ttu-id="47341-108">Планирование аварийного восстановления при планировании производственных мощностей.</span><span class="sxs-lookup"><span data-stu-id="47341-108">Plan for disaster recovery when you do your capacity planning.</span></span> <span data-ttu-id="47341-109">Для производительности аварийного восстановления каждый пул в Объединенном пуле должен иметь возможность обрабатывать рабочие нагрузки всех групп ответов в обоих пулах.</span><span class="sxs-lookup"><span data-stu-id="47341-109">For disaster recovery capacity, each pool in a paired pool should be able to handle the workloads of all the response groups in both pools.</span></span> <span data-ttu-id="47341-110">Подробные сведения о планировании мощности групп ответов можно найти [в разделе Планирование ресурсов для группы ответа в Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="47341-110">For details about Response Group capacity planning, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).</span></span>

  - <span data-ttu-id="47341-111">Регулярно заполните резервные копии всех конфигураций групп ответа во всех пулах интерфейсов, в которых вы развернули приложение группы ответа с помощью процедуры экспорта, описанной в этом документе.</span><span class="sxs-lookup"><span data-stu-id="47341-111">Take regular backup copies of all the response group configurations in all the Front End pools where you deployed the Response Group application by using the export procedure described in this document.</span></span> <span data-ttu-id="47341-112">Дополнительные сведения можно найти [в разделе процедуры аварийного восстановления группы ответа в Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="47341-112">For details, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span> <span data-ttu-id="47341-113">Храните резервные копии в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="47341-113">Keep the backup copies in a safe location.</span></span>

  - <span data-ttu-id="47341-114">Храните резервные копии всех исходных аудиофайлов, которые вы использовали для приложения группы ответа, включая любые записи и файлы на удержании музыки.</span><span class="sxs-lookup"><span data-stu-id="47341-114">Keep a separate backup copy of all the original audio files you used for the Response Group application, including any recordings and music-on-hold files.</span></span> <span data-ttu-id="47341-115">Храните архивные файлы в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="47341-115">Keep the backup files in a safe location.</span></span>

  - <span data-ttu-id="47341-116">Для Lync Server 2013 с аварийным восстановлением все параметры группы ответа должны иметь уникальные имена в рамках развертывания.</span><span class="sxs-lookup"><span data-stu-id="47341-116">For Lync Server 2013 disaster recovery, all Response Group settings must have unique names across your deployment.</span></span> <span data-ttu-id="47341-117">Это требование относится к рабочим процессам, очередям, группам агентов, наборам праздников и часам бизнеса.</span><span class="sxs-lookup"><span data-stu-id="47341-117">This requirement applies to workflows, queues, agent groups, holiday sets, and hours of business.</span></span> <span data-ttu-id="47341-118">Убедитесь в том, что это требование выполняется, когда основной пул и пулы резервных копий по-прежнему активны, а перед тем, как вы захотите инициировать резервную процедуру.</span><span class="sxs-lookup"><span data-stu-id="47341-118">You should verify that this requirement is met when the primary and backup pools are still active, and before you need to initiate any failover procedure.</span></span> <span data-ttu-id="47341-119">Если при импорте данных группы ответа в пул резервных копий возникло конфликт имен, импорт завершится сбоем.</span><span class="sxs-lookup"><span data-stu-id="47341-119">If you encounter name conflicts while importing response group data to the backup pool, the import fails.</span></span> <span data-ttu-id="47341-120">Чтобы завершить импорт и отработку отказа, необходимо устранить конфликты имен, переименование объекта группы ответа в пуле резервных копий, или с помощью командлета **Import-ксргсконфигуратион** с параметром – ресолвенамеконфликтс автоматически. Устраните конфликт, добавив уникальный идентификационный номер к объекту группы ответа.</span><span class="sxs-lookup"><span data-stu-id="47341-120">To complete the import and failover procedure, you need to resolve the name conflicts by renaming the response group object in the backup pool or by using the **Import-CsRgsConfiguration** cmdlet with the –ResolveNameConflicts parameter to automatically resolve the conflict by appending a unique identifying number to the response group object.</span></span>

  - <span data-ttu-id="47341-121">Как правило, мы рекомендуем выполнять ежедневные архивации, но если у вас много изменений, вам может понадобиться запланировать более частые резервные копии.</span><span class="sxs-lookup"><span data-stu-id="47341-121">In general, we recommend that you perform daily backups, but if you have a high volume of changes, you might want to schedule more frequent backups.</span></span> <span data-ttu-id="47341-122">Объем данных, которые можно потерять в случае аварии, зависит от частоты резервных копий, а также частоты и объема изменений.</span><span class="sxs-lookup"><span data-stu-id="47341-122">The amount of information you can lose in the event of a disaster depends on the frequency of your backups, as well as the frequency and volume of changes.</span></span>

  - <span data-ttu-id="47341-123">Вы можете импортировать группы ответа в пул резервных копий перед выполнением аварийной или резервной операции.</span><span class="sxs-lookup"><span data-stu-id="47341-123">It is possible to import response groups to a backup pool before a disaster or failover operation occurs.</span></span> <span data-ttu-id="47341-124">Импорт групп ответа в заранее сокращает время простоя, так как служба группы ответа Lync Server может быть восстановлена в пуле резервного копирования сразу после того, как звонки пересылаются в пул резервных копий.</span><span class="sxs-lookup"><span data-stu-id="47341-124">Importing response groups in advance reduces downtime, because the Lync Server Response Group service can be restored in the backup pool as soon as calls are routed to the backup pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="47341-125">Приложение группы ответа не может связаться ни с одним агентом в неактивном пуле, пока не завершится отработка отказа.</span><span class="sxs-lookup"><span data-stu-id="47341-125">The Response Group application cannot reach any agents homed in an inactive pool until failover is complete.</span></span> <span data-ttu-id="47341-126">В течение этого времени приложение "группа ответа" обрабатывает звонки так, как если бы эти агенты были недоступны.</span><span class="sxs-lookup"><span data-stu-id="47341-126">During this time, the Response Group application processes calls as if those agents are unavailable.</span></span>

    
    </div>

</div>

<div>

## <a name="response-group-disaster-recovery-process"></a><span data-ttu-id="47341-127">Процесс аварийного восстановления группы ответов</span><span class="sxs-lookup"><span data-stu-id="47341-127">Response Group Disaster Recovery Process</span></span>

<span data-ttu-id="47341-128">В случае аварии вы можете восстановить группы ответа, используя один из указанных ниже подходов к восстановлению.</span><span class="sxs-lookup"><span data-stu-id="47341-128">In the event of a disaster, you can recover response groups by using either of the following recovery approaches:</span></span>

  - <span data-ttu-id="47341-129">Отработка отказа в резервной копии пула, после чего он не будет восстановлен в исходном пуле.</span><span class="sxs-lookup"><span data-stu-id="47341-129">Fail over to a backup pool and then fail back to the original pool.</span></span>

  - <span data-ttu-id="47341-130">Отработка отказа в резервной копии пула, создание нового пула с другим полным доменным именем (FQDN), а затем импорт групп ответа в новый пул.</span><span class="sxs-lookup"><span data-stu-id="47341-130">Fail over to a backup pool, create a new pool with a different fully qualified domain name (FQDN), and then import the response groups to the new pool.</span></span>

<span data-ttu-id="47341-131">На этапе восстановления после сбоя в аварийном восстановлении группы ответа находятся в нескольких пулах: в основном пуле (который недоступен) и в пуле резервных копий.</span><span class="sxs-lookup"><span data-stu-id="47341-131">During the failover phase of disaster recovery, the response groups reside in multiple pools: in the primary pool (which is unavailable) and in the backup pool.</span></span> <span data-ttu-id="47341-132">Группы ответа в обоих пулах имеют одинаковое имя и одного и того же владельца (основного пула), но у них разные родители.</span><span class="sxs-lookup"><span data-stu-id="47341-132">The response groups in both pools have the same name and the same owner (the primary pool), but they have different parents.</span></span>

<span data-ttu-id="47341-133">При восстановлении путем создания нового пула с другим полным доменным именем необходимо назначить новый пул владельцем групп ответа при импорте.</span><span class="sxs-lookup"><span data-stu-id="47341-133">When you recover by creating a new pool with a different FQDN, you need to assign the new pool as the owner of the response groups when you import them.</span></span> <span data-ttu-id="47341-134">Владелец групп ответов остается в исходном пуле, если только вы не переназначьте владение с помощью параметра – Овервритеовнер с командлетом **Import-ксргсконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="47341-134">Ownership of response groups remains with the original pool unless or until you explicitly reassign ownership by using the –OverwriteOwner parameter with the **Import-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="47341-135">Кроме того, вы также можете использовать параметр – Овервритеовнер, если вы перестроили пул во время восстановления (то есть она пуста), независимо от того, используется ли это полное доменное имя.</span><span class="sxs-lookup"><span data-stu-id="47341-135">You also need to use the –OverwriteOwner parameter if you rebuilt the pool during the recovery (that is, the Response Group database is empty), whether or not you use the same FQDN.</span></span> <span data-ttu-id="47341-136">Если вы не перестроены в пул, вам не нужно использовать параметр – Овервритеовнер, но этот параметр можно использовать при импорте групп ответа обратно в основной пул.</span><span class="sxs-lookup"><span data-stu-id="47341-136">You do not need to use the –OverwriteOwner parameter if you did not rebuild the pool, but it is permissible to use this parameter whenever you import response groups back to the primary pool.</span></span>



</div>

<span data-ttu-id="47341-137">Вы можете задать только один набор параметров конфигурации группы ответов на уровне приложения для каждого пула.</span><span class="sxs-lookup"><span data-stu-id="47341-137">You can define only one set of application-level Response Group configuration settings per pool.</span></span> <span data-ttu-id="47341-138">Эти параметры включают стандартную конфигурацию сохранения музыки, используемую по умолчанию в качестве звукового файла для сохранения музыки, агент рингбакк льготный период и контекстную конфигурацию вызова.</span><span class="sxs-lookup"><span data-stu-id="47341-138">These settings include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="47341-139">Чтобы просмотреть эти параметры конфигурации, запустите командлет **Get-ксргсконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="47341-139">To view these configuration settings, run the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="47341-140">Дополнительные сведения о командлете **Get-ксргсконфигуратион** можно найти в [статьях Get-ксргсконфигуратион](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span><span class="sxs-lookup"><span data-stu-id="47341-140">For details about the **Get-CsRgsConfiguration** cmdlet, see [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).</span></span>

<span data-ttu-id="47341-141">Вы можете перенести эти параметры уровня приложения из одного пула в другой с помощью командлета **Import-ксргсконфигуратион** с параметром – реплацеексистингсеттингс, но это переопределит параметры в целевом пуле.</span><span class="sxs-lookup"><span data-stu-id="47341-141">You can transfer these application-level settings from one pool to another by using the **Import-CsRgsConfiguration** cmdlet with the –ReplaceExistingSettings parameter, but doing so overrides the settings in the destination pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="47341-142">Это ограничение для перемещения параметров в другой пул имеет значение true только для параметров уровня приложения и звукового файла, используемого по умолчанию при хранении музыки.</span><span class="sxs-lookup"><span data-stu-id="47341-142">This constraint about transferring settings to another pool is true only for the application-level settings and the default music-on-hold audio file.</span></span> <span data-ttu-id="47341-143">Это не относится к группам агентов, очередям, рабочим процессам, часам и наборам праздников.</span><span class="sxs-lookup"><span data-stu-id="47341-143">It does not apply to agent groups, queues, workflows, business hours, and holiday sets.</span></span>



</div>

<span data-ttu-id="47341-144">Если вы не хотите заменять параметры уровня приложения в пуле резервных копий во время аварии, и основной пул невозможно восстановить, параметры уровня приложения из основного пула будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="47341-144">If you don't want to replace the application-level settings in the backup pool during a disaster and the primary pool can't be recovered, the application-level settings from the primary pool will be lost.</span></span> <span data-ttu-id="47341-145">Если необходимо создать новый пул для замены основного пула при восстановлении с таким же полным доменным именем или с другим полным доменным именем, вы не сможете восстановить исходные параметры уровня приложения.</span><span class="sxs-lookup"><span data-stu-id="47341-145">If you need to create a new pool to replace the primary pool during recovery, either with the same FQDN or with a different FQDN, you can't recover the original application-level settings.</span></span> <span data-ttu-id="47341-146">В этом случае необходимо настроить новый пул с помощью этих параметров и добавить звуковой файл для сохранения музыки.</span><span class="sxs-lookup"><span data-stu-id="47341-146">In this case, you need to configure the new pool with these settings and include the music-on-hold audio file.</span></span>

<span data-ttu-id="47341-147">Если вы решили использовать командлет **Import-ксргсконфигуратион** для переноса параметров уровня приложения из основного пула в пул резервных копий во время аварии, вы можете перенести настройки из пула резервных копий в новый пул в том же так, как вы перенесли их из основного пула в пул резервных копий.</span><span class="sxs-lookup"><span data-stu-id="47341-147">If you decide to use the **Import-CsRgsConfiguration** cmdlet to transfer application-level settings from the primary pool to the backup pool during a disaster, you can then transfer the settings from the backup pool to the new pool during recovery in the same way that you transferred them from the primary pool to the backup pool.</span></span>

<span data-ttu-id="47341-148">В таблице ниже приведены инструкции по восстановлению групп ответа.</span><span class="sxs-lookup"><span data-stu-id="47341-148">The following table is an overview of the steps involved in recovering response groups.</span></span>

<span data-ttu-id="47341-149">Дополнительные сведения о выполнении этих действий можно найти [в разделе процедуры аварийного восстановления группы ответа в Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="47341-149">For details about performing these steps, see [Response group disaster recovery procedures in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).</span></span>

### <a name="response-group-disaster-recovery-steps"></a><span data-ttu-id="47341-150">Инструкции по аварийному восстановлению группы ответа</span><span class="sxs-lookup"><span data-stu-id="47341-150">Response Group Disaster Recovery Steps</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47341-151">Этап</span><span class="sxs-lookup"><span data-stu-id="47341-151">Phase</span></span></th>
<th><span data-ttu-id="47341-152">Шаги</span><span class="sxs-lookup"><span data-stu-id="47341-152">Steps</span></span></th>
<th><span data-ttu-id="47341-153">Необходимые группы и роли</span><span class="sxs-lookup"><span data-stu-id="47341-153">Required groups and roles</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47341-154">Перед отключением</span><span class="sxs-lookup"><span data-stu-id="47341-154">Before outage</span></span></p></td>
<td><p><span data-ttu-id="47341-155">С помощью командлета <strong>Export-ксргсконфигуратион</strong> можно создавать резервные копии всех конфигураций групп ответа во всех пулах интерфейсных служб, в которых развернуто приложение группы ответа.</span><span class="sxs-lookup"><span data-stu-id="47341-155">On a routine basis, run the <strong>Export-CsRgsConfiguration</strong> cmdlet to create backups of all Response Group configurations in all Front End pools where Response Group application is deployed.</span></span></p></td>
<td><p><span data-ttu-id="47341-156">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="47341-156">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="47341-157">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="47341-157">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47341-158">Во время отключения</span><span class="sxs-lookup"><span data-stu-id="47341-158">During outage</span></span></p></td>
<td><p><span data-ttu-id="47341-159">Запустите командлет <strong>Import-ксргсконфигуратион</strong> , чтобы импортировать из резервной копии конфигурации службы ответов на Lync Server из основного пула в пул резервных копий.</span><span class="sxs-lookup"><span data-stu-id="47341-159">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the backed up Lync Server Response Group service configuration from the primary pool to the backup pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="47341-160">Используйте параметр – Реплацеексистингсеттингс, если вы хотите заменить параметры группы ответа уровня приложения в пуле резервного копирования на параметры из основного пула.</span><span class="sxs-lookup"><span data-stu-id="47341-160">Use the –ReplaceExistingSettings parameter if you want to replace application-level Response Group settings in the backup pool with the settings from the primary pool.</span></span> <span data-ttu-id="47341-161">Если вы не переносите параметры уровня приложения из основного пула в пул резервных копий, и основной пул восстановить невозможно, параметры из основного пула будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="47341-161">If you do not transfer the application-level settings from the primary pool to the backup pool, and the primary pool can't be recovered, you will lose the settings from the primary pool.</span></span>


</div></td>
<td><p><span data-ttu-id="47341-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="47341-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="47341-163">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="47341-163">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47341-164">После импорта</span><span class="sxs-lookup"><span data-stu-id="47341-164">After importing</span></span></p></td>
<td><p><span data-ttu-id="47341-165">Запустите командлеты группы ответа с параметром – Шовалл (для отображения всех групп ответа) или параметр – владелец (чтобы отобразить только импортированные группы ответов), чтобы убедиться в том, что все конфигурации группы ответа были импортированы в резервный пул.</span><span class="sxs-lookup"><span data-stu-id="47341-165">Run Response Group cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were imported to the backup pool.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="47341-166">Если вы не используете либо параметр – Шовалл, либо параметр – владелец, группы ответа, импортированные в пул резервных копий, не будут указаны в результатах, возвращенных командлетами.</span><span class="sxs-lookup"><span data-stu-id="47341-166">If you do not use either the –ShowAll parameter or the –Owner parameter, the response groups that you imported to the backup pool will not be listed in the results returned by the cmdlets.</span></span>


</div>
<p><span data-ttu-id="47341-167">Выполните следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="47341-167">Run the following cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="47341-168"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="47341-168"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="47341-169"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="47341-169"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="47341-170"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="47341-170"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="47341-171"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="47341-171"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="47341-172"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="47341-172"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="47341-173">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="47341-173">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="47341-174">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="47341-174">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47341-175">После перехода на другой ресурс</span><span class="sxs-lookup"><span data-stu-id="47341-175">After failover</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="47341-176">Наведите тестовый звонок в группу ответа, которая была импортирована в пул резервных копий, и убедитесь, что звонок обрабатывается должным образом.</span><span class="sxs-lookup"><span data-stu-id="47341-176">Place a test call to a response group that was imported to the backup pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="47341-177">Все формальные агенты должны повторно входить в их формальные группы в пуле резервных копий.</span><span class="sxs-lookup"><span data-stu-id="47341-177">All formal agents must sign in again to their formal groups on backup pool.</span></span></p></li>
<li><p><span data-ttu-id="47341-178">Управление изменениями конфигурации.</span><span class="sxs-lookup"><span data-stu-id="47341-178">Manage configuration changes:</span></span></p>
<p><span data-ttu-id="47341-179">Группы ответа в пуле резервных копий, импортированные в резервную копию или принадлежащую пулу резервных копий, можно изменять в обычном режиме простоя.</span><span class="sxs-lookup"><span data-stu-id="47341-179">Response groups in the backup pool, whether imported to the backup pool or owned by the backup pool, can be modified as usual during the outage.</span></span></p>
<div>

> [!IMPORTANT]  
> <span data-ttu-id="47341-180">Вы должны использовать командную консоль Lync Server для управления группами ответов, которые вы импортировали в пул резервных копий.</span><span class="sxs-lookup"><span data-stu-id="47341-180">You must use Lync Server Management Shell to manage the response groups that you imported to the backup pool.</span></span> <span data-ttu-id="47341-181">Вы не можете использовать панель управления Lync Server для управления этими группами ответа, пока они находятся в пуле резервных копий.</span><span class="sxs-lookup"><span data-stu-id="47341-181">You cannot use Lync Server Control Panel to manage these response groups while they are in the backup pool.</span></span>


</div></li>
</ul></td>
<td><p><span data-ttu-id="47341-182">Н/Д</span><span class="sxs-lookup"><span data-stu-id="47341-182">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47341-183">После восстановления перед восстановлением после сбоя</span><span class="sxs-lookup"><span data-stu-id="47341-183">After recovery, before failback</span></span></p></td>
<td><p><span data-ttu-id="47341-184">Запустите командлет <strong>Export-ксргсконфигуратион</strong> , указав параметр-Source в качестве пула резервных копий, и параметр – владелец в качестве основного пула для экспорта групп ответов, принадлежащих основным пулам из пула резервных копий.</span><span class="sxs-lookup"><span data-stu-id="47341-184">Run the <strong>Export-CsRgsConfiguration</strong> cmdlet specifying the -Source parameter as the backup pool and the –Owner parameter as the primary pool to export the response groups owned by the primary pool from the backup pool.</span></span></p></td>
<td><p><span data-ttu-id="47341-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="47341-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="47341-186">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="47341-186">CsResponseGroupAdministrator</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47341-187">После восстановления после сбоя</span><span class="sxs-lookup"><span data-stu-id="47341-187">After failback</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="47341-188">Запустите командлет <strong>Import-ксргсконфигуратион</strong> , чтобы импортировать группы ответа обратно в основной пул.</span><span class="sxs-lookup"><span data-stu-id="47341-188">Run the <strong>Import-CsRgsConfiguration</strong> cmdlet to import the response groups back to the primary pool.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="47341-189">Если основной пул не поддается восстановлению и вы развертываете новый пул для его замены, используйте параметр – Реплацеексистингсеттингс для переноса параметров уровня приложения из пула резервных копий в новый пул.</span><span class="sxs-lookup"><span data-stu-id="47341-189">If the primary pool can't be recovered and you deploy a new pool to replace it, use the –ReplaceExistingSettings parameter to transfer the application-level settings from the backup pool to the new pool.</span></span> <span data-ttu-id="47341-190">Если вы не переносяте параметры из пула резервных копий, для нового пула будут использоваться параметры по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="47341-190">If you do not transfer the settings from the backup pool, the new pool will use the default settings.</span></span>


</div></li>
<li><p><span data-ttu-id="47341-191">Выполните следующие командлеты с параметром – Шовалл (для отображения всех групп ответа) или параметр – владелец (для отображения только импортированных групп ответа), чтобы убедиться в том, что все конфигурации группы ответа успешно импортированы в основной пул.</span><span class="sxs-lookup"><span data-stu-id="47341-191">Run the following cmdlets with either the –ShowAll parameter (to display all response groups) or the –Owner parameter (to display only imported response groups) to verify that all response group configurations were successfully imported back to the primary pool:</span></span></p>
<ul>
<li><p><span data-ttu-id="47341-192"><strong>Get-CsRgsWorkflow</strong></span><span class="sxs-lookup"><span data-stu-id="47341-192"><strong>Get-CsRgsWorkflow</strong></span></span></p></li>
<li><p><span data-ttu-id="47341-193"><strong>Get-CsRgsQueue</strong></span><span class="sxs-lookup"><span data-stu-id="47341-193"><strong>Get-CsRgsQueue</strong></span></span></p></li>
<li><p><span data-ttu-id="47341-194"><strong>Get-CsRgsAgentGroup</strong></span><span class="sxs-lookup"><span data-stu-id="47341-194"><strong>Get-CsRgsAgentGroup</strong></span></span></p></li>
<li><p><span data-ttu-id="47341-195"><strong>Get-CsRgsHoursOfBusiness</strong></span><span class="sxs-lookup"><span data-stu-id="47341-195"><strong>Get-CsRgsHoursOfBusiness</strong></span></span></p></li>
<li><p><span data-ttu-id="47341-196"><strong>Get-CsRgsHolidaySet</strong></span><span class="sxs-lookup"><span data-stu-id="47341-196"><strong>Get-CsRgsHolidaySet</strong></span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="47341-197">Наведите тестовый звонок в группу ответа, которая была импортирована обратно в основной пул, и убедитесь, что звонок обрабатывается должным образом.</span><span class="sxs-lookup"><span data-stu-id="47341-197">Place a test call to a response group that was imported back to the primary pool and verify that the call is handled correctly.</span></span></p></li>
<li><p><span data-ttu-id="47341-198">При необходимости выполните командлет <strong>Export-ксргсконфигуратион</strong> в пуле резервных копий с параметром – ремовикспортедконфигуратион, чтобы удалить группы ответов, принадлежащие основным пулам из пула резервных копий.</span><span class="sxs-lookup"><span data-stu-id="47341-198">Optionally, run the <strong>Export-CsRgsConfiguration</strong> cmdlet on the backup pool with the –RemoveExportedConfiguration parameter to remove the response groups owned by the primary pool from the backup pool.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="47341-199">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="47341-199">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="47341-200">CsResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="47341-200">CsResponseGroupAdministrator</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

