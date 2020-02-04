---
title: 'Lync Server 2013: Управление емкостью и обеспечением доступности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity and availability management
ms:assetid: 207a2997-f482-4bee-892d-d2b112294481
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720325(v=OCS.15)
ms:contentKeyID: 63969586
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 169c2e383a1799f5f3ab7ca810de32f86350e51b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-and-availability-management-in-lync-server-2013"></a><span data-ttu-id="76b6c-102">Управление емкостью и доступностью в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76b6c-102">Capacity and availability management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76b6c-103">_**Тема последнего изменения:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="76b6c-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="76b6c-104">Цель управления емкостью и обеспечением доступности — измерение и контроль производительности системы.</span><span class="sxs-lookup"><span data-stu-id="76b6c-104">The purpose of capacity management and availability management is to measure and control system performance.</span></span> <span data-ttu-id="76b6c-105">Мы рекомендуем реализовать процедуры управления емкостью и управления надежностью, чтобы можно было измерять и контролировать производительность системы.</span><span class="sxs-lookup"><span data-stu-id="76b6c-105">We recommend that you implement capacity management and availability management procedures so that you can measure and control system performance.</span></span> <span data-ttu-id="76b6c-106">Вам нужно знать, доступна ли система, и может обрабатывать текущие и прогнозируемые требования, задавая базовые показатели и контролируя систему для поиска тенденций.</span><span class="sxs-lookup"><span data-stu-id="76b6c-106">You have to know whether the system is available and if it can handle the current and the projected demands by setting baselines and monitoring the system to look for trends.</span></span>

<div>

## <a name="capacity-management"></a><span data-ttu-id="76b6c-107">Управление емкостью</span><span class="sxs-lookup"><span data-stu-id="76b6c-107">Capacity management</span></span>

<span data-ttu-id="76b6c-108">Управление производительностью включает в себя планирование, изменение размера и Управление емкостью служб, чтобы гарантировать превышение минимальных уровней производительности, указанных для вашего соглашения об уровне обслуживания.</span><span class="sxs-lookup"><span data-stu-id="76b6c-108">Capacity management involves planning, sizing, and controlling service capacity to help guarantee that the minimum performance levels specified in your SLA are exceeded.</span></span> <span data-ttu-id="76b6c-109">Эффективное Управление емкостью помогает обеспечить предоставление ИТ-услуг по разумным затратам и, тем не менее, отвечать на уровни производительности, определенные в рамках вашего соглашения об уровне обслуживания с помощью клиента.</span><span class="sxs-lookup"><span data-stu-id="76b6c-109">Good capacity management helps ensure that you can provide IT services at a reasonable cost and still meet the levels of performance defined in your SLAs with the client.</span></span> <span data-ttu-id="76b6c-110">Эти условия могут включать в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="76b6c-110">These criteria can include the following:</span></span>

  - <span data-ttu-id="76b6c-111">**Время ответа системы**   . Это измеряемое время, которое система предпринимает для выполнения типичных действий.</span><span class="sxs-lookup"><span data-stu-id="76b6c-111">**System Response Time**   This is the measured time that the system takes to do typical actions.</span></span> <span data-ttu-id="76b6c-112">В качестве примера можно привести время, необходимое для работы роли аудио-и видеофайла для обработки аудио-и видеопотока, время, необходимое для создания и присоединения к Конференции с помощью клиента, а также время, затраченное на обновление во всех клиентах наблюдателей.</span><span class="sxs-lookup"><span data-stu-id="76b6c-112">Examples include the time that is required for the audio/video server role to process audio/video traffic, the time that is required for a client to create and join a conference, or the time taken for presence to be updated in all watcher clients.</span></span>

  - <span data-ttu-id="76b6c-113">**Емкость хранилища —**   это емкость системы хранения, будь то база данных контента, устройство резервного копирования или локальный диск.</span><span class="sxs-lookup"><span data-stu-id="76b6c-113">**Storage Capacity**   This is the capacity of a storage system, whether it is a content database, a backup device, or a local drive.</span></span> <span data-ttu-id="76b6c-114">Пример: максимальный объем дискового пространства, который должен быть указан на сайте, и время, в которое необходимо сохранить резервные копии, прежде чем они будут перезаписаны.</span><span class="sxs-lookup"><span data-stu-id="76b6c-114">Examples include the maximum amount of storage space to be provided per site and the time that backups should be stored before they are overwritten.</span></span>

<span data-ttu-id="76b6c-115">Настройка емкости зачастую является единственным вариантом обеспечения доступности достаточных физических ресурсов, таких как место на диске и пропускная способность сети.</span><span class="sxs-lookup"><span data-stu-id="76b6c-115">Adjusting capacity is frequently a case of making sure that enough physical resources are available, such as disk space and network bandwidth.</span></span> <span data-ttu-id="76b6c-116">В приведенной ниже таблице перечислены типичные решения проблем, связанных с производительностью.</span><span class="sxs-lookup"><span data-stu-id="76b6c-116">The following table lists typical resolutions for capacity-related issues.</span></span>

### <a name="typical-resolutions-for-capacity-related-issues"></a><span data-ttu-id="76b6c-117">Типичные решения проблем, связанных с производительностью</span><span class="sxs-lookup"><span data-stu-id="76b6c-117">Typical resolutions for capacity-related issues</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76b6c-118">Ошибка</span><span class="sxs-lookup"><span data-stu-id="76b6c-118">Issue</span></span></th>
<th><span data-ttu-id="76b6c-119">Возможное решение</span><span class="sxs-lookup"><span data-stu-id="76b6c-119">Possible resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76b6c-120">Неудовлетворительные качество звука и видео удаленных пользователей</span><span class="sxs-lookup"><span data-stu-id="76b6c-120">Remote users having poor audio/video performance</span></span></p></td>
<td><p><span data-ttu-id="76b6c-121">Проверьте, доступна ли подходящая пропускная способность для WAN Links, а также в том случае, если качество обслуживания включено и настроено надлежащим образом.</span><span class="sxs-lookup"><span data-stu-id="76b6c-121">Check to see whether appropriate bandwidth is available on the WAN links and if QoS is enabled and appropriately configured.</span></span> <span data-ttu-id="76b6c-122">Проверьте данные QoE.</span><span class="sxs-lookup"><span data-stu-id="76b6c-122">Check QoE data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76b6c-123">Общий ответ среды Lync очень медленный.</span><span class="sxs-lookup"><span data-stu-id="76b6c-123">Overall response of the Lync environment is slow.</span></span></p></td>
<td><p><span data-ttu-id="76b6c-124">Выполнение тестов для проверки того, что существующие серверы переднего плана могут работать с загрузкой.</span><span class="sxs-lookup"><span data-stu-id="76b6c-124">Run tests to check that the existing front-end servers can deal with the load.</span></span> <span data-ttu-id="76b6c-125">Представьте новый сервер переднего плана, если это необходимо. Проверьте значения времени ответа на базу данных SQL и исправьте причины возникновения задержек (например, улучшения дискового ввода-вывода).</span><span class="sxs-lookup"><span data-stu-id="76b6c-125">Introduce a new front-end server if it is needed.Check SQL database response times and fix the causes for the delays (for example, improve disk I/O).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="76b6c-126">Более подробные сведения об устранении неполадок описаны в руководстве по сети Lync Server.</span><span class="sxs-lookup"><span data-stu-id="76b6c-126">Troubleshooting in greater detail is covered in the Lync Server Networking Guide.</span></span>

<span data-ttu-id="76b6c-127">На производительность влияет настройка системы, и они зависят от физических ресурсов, таких как пропускная способность сети.</span><span class="sxs-lookup"><span data-stu-id="76b6c-127">Capacity is affected by system configuration and depends on physical resources such as network bandwidth.</span></span> <span data-ttu-id="76b6c-128">Например, если среда Lync настроена для ежедневного выполнения полного резервного копирования, необходимо соблюдать осторожность, чтобы гарантировать, что эффект на интерактивной производительности, доступ к которой происходил для конечных пользователей, будет минимизирован.</span><span class="sxs-lookup"><span data-stu-id="76b6c-128">For example, if a Lync environment is configured to perform a full backup nightly, care must be taken to help guarantee that the effect on the interactive performance experienced by end-users is minimized.</span></span>

<span data-ttu-id="76b6c-129">Управление производительностью — это процесс сохранения мощности системы в пределах приемлемых уровней и устранения указанных ниже проблем.</span><span class="sxs-lookup"><span data-stu-id="76b6c-129">Capacity management is the process of keeping the capacity of a system within acceptable levels and addresses the following issues:</span></span>

  - <span data-ttu-id="76b6c-130">**Передействующее на изменения требований**   к мощности в требованиях должны быть скорректированы для учета изменений, внесенных в системе или в Организации.</span><span class="sxs-lookup"><span data-stu-id="76b6c-130">**Reacting to changes in requirements**   Capacity requirements have to be adjusted to account for changes in the system or the organization.</span></span> <span data-ttu-id="76b6c-131">Например, если в вашей среде требуется реализовать корпоративную голосовую почту, будет очень важнее количество и расположение серверов-посредников и шлюзов для коммутируемой телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="76b6c-131">For example, if your environment decides to implement Enterprise Voice, the number and placement of Mediation Servers and public switched telephone network (PSTN) gateways will be very important.</span></span> <span data-ttu-id="76b6c-132">Если вы собираетесь звонить по протоколу SIP или Direct SIP, Общая схема будет значительно изменяться для обеспечения оптимальной производительности при работе с корпоративной голосовой связью.</span><span class="sxs-lookup"><span data-stu-id="76b6c-132">If you'll be doing Session Initiation Protocol (SIP) trunking or direct SIP, the overall design will be significantly changed to provide the best Enterprise Voice performance.</span></span>

  - <span data-ttu-id="76b6c-133">**Прогнозирование требований**   к будущем. Некоторые требования к мощности изменяют предсказуемо с течением времени.</span><span class="sxs-lookup"><span data-stu-id="76b6c-133">**Predicting future requirements**   Some capacity requirements change predictably over time.</span></span> <span data-ttu-id="76b6c-134">Отслеживая тенденции, вы можете предварительно планировать обновления.</span><span class="sxs-lookup"><span data-stu-id="76b6c-134">By tracking trends you can plan upgrades in advance.</span></span> <span data-ttu-id="76b6c-135">Например, для создания базового плана необходимо отслеживать доступную пропускную способность между различными сайтами Lync.</span><span class="sxs-lookup"><span data-stu-id="76b6c-135">For example, available bandwidth between various Lync sites must be monitored to create a baseline.</span></span> <span data-ttu-id="76b6c-136">Этот базовый план позволит вам предсказать, когда необходимо добавить дополнительную пропускную способность для этих ссылок, так как количество пользователей на этих сайтах увеличится с учетом времени.</span><span class="sxs-lookup"><span data-stu-id="76b6c-136">This baseline will allow you to predict when you have to add more bandwidth to these links as user count in these remote sites increases with time.</span></span>

</div>

<div>

## <a name="availability-management"></a><span data-ttu-id="76b6c-137">Управление обеспечением доступности</span><span class="sxs-lookup"><span data-stu-id="76b6c-137">Availability management</span></span>

<span data-ttu-id="76b6c-138">Управление обеспечением доступности — это процесс, который гарантирует своевременную и экономичную работу любых ИТ – служб, необходимых для клиента.</span><span class="sxs-lookup"><span data-stu-id="76b6c-138">Availability management is the process of making sure that any IT service consistently and cost effectively delivers the level of consistent, reliable service that is required by the customer.</span></span> <span data-ttu-id="76b6c-139">Управление обеспечением доступности — это минимизация потерь на обслуживание и обеспечение выполнения соответствующего действия при потере обслуживания.</span><span class="sxs-lookup"><span data-stu-id="76b6c-139">Availability management deals with minimizing loss of service and with making sure that appropriate action is taken if service is lost.</span></span> <span data-ttu-id="76b6c-140">В среде Lync может возникнуть вопрос того, доступна ли корпоративная голосовая служба, могут ли пользователи присоединяться к запланированным конференциям и т. д.</span><span class="sxs-lookup"><span data-stu-id="76b6c-140">In a Lync environment, you may be concerned about whether the Enterprise Voice service is available, whether users can join scheduled conferences, and so on.</span></span> <span data-ttu-id="76b6c-141">Соглашение об уровне обслуживания определяет приемлемую частоту и продолжительность перерывов, а также позволяет получить определенные периоды, когда система будет недоступна для запланированного обслуживания.</span><span class="sxs-lookup"><span data-stu-id="76b6c-141">An SLA defines an acceptable frequency and length of outages and allows for certain periods when the system is unavailable for planned maintenance.</span></span>

<span data-ttu-id="76b6c-142">Если вам нужно предоставлять отчеты для управления сведениями о доступности систем или при наличии финансовых или других санкций, связанных с отсутствующими целевыми объектами доступности, необходимо записать данные о доступности.</span><span class="sxs-lookup"><span data-stu-id="76b6c-142">If you have to provide reports to your management about the availability of systems, or if you have financial or other penalties associated with missing availability targets, you must record availability data.</span></span> <span data-ttu-id="76b6c-143">Даже если у вас нет подобных формальных требований, рекомендуется по крайней мере знать, как часто система завершилась сбоем за определенный период времени.</span><span class="sxs-lookup"><span data-stu-id="76b6c-143">Even if you do not have such formal requirements, it is a good idea to at least know how frequently a system has failed in a certain time period.</span></span> <span data-ttu-id="76b6c-144">Например, доступность системы за последние 12 месяцев и время, затраченное на восстановление после каждой ошибки.</span><span class="sxs-lookup"><span data-stu-id="76b6c-144">For example, system availability in the last 12 months and how long it took to recover from each failure.</span></span> <span data-ttu-id="76b6c-145">Эта информация поможет вам измерять и улучшать эффективность работы группы в ответ на сбой системы.</span><span class="sxs-lookup"><span data-stu-id="76b6c-145">This information will help you measure and improve your team’s effectiveness in responding to a system failure.</span></span> <span data-ttu-id="76b6c-146">Кроме того, он может предоставить вам полезные сведения, если у вас есть спорный вопрос.</span><span class="sxs-lookup"><span data-stu-id="76b6c-146">It can also give you useful information if there is a dispute.</span></span>

<span data-ttu-id="76b6c-147">Меры, связанные с обеспечением доступности, описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="76b6c-147">Measures related to availability are as follows:</span></span>

  - <span data-ttu-id="76b6c-148">**Доступность**   это обычно выражается в том случае, если вы можете получить доступ к системе или службе по сравнению со временем, на которое она не работает.</span><span class="sxs-lookup"><span data-stu-id="76b6c-148">**Availability**   This is typically expressed as the time that a system or service can be accessed compared to the time that it is down.</span></span> <span data-ttu-id="76b6c-149">Обычно оно выражается в процентах.</span><span class="sxs-lookup"><span data-stu-id="76b6c-149">It is typically expressed as a percentage.</span></span> <span data-ttu-id="76b6c-150">(Могут отображаться ссылки на три девяти или пять девяти).</span><span class="sxs-lookup"><span data-stu-id="76b6c-150">(You may see references to “three nines” or “five nines”.</span></span> <span data-ttu-id="76b6c-151">Они ссылаются на 99,9% и 99,999 процента доступности.)</span><span class="sxs-lookup"><span data-stu-id="76b6c-151">These refer to 99.9 percent or 99.999 percent availability.)</span></span>

  - <span data-ttu-id="76b6c-152">**Надежность**   . это мера времени между сбоями системы и иногда измеряется (среднее) время между сбоями (MTBF).</span><span class="sxs-lookup"><span data-stu-id="76b6c-152">**Reliability**   This is a measure of the time between failures of a system and is sometimes expressed as mean (or average) time between failures (MTBF).</span></span>

  - <span data-ttu-id="76b6c-153">**Время восстановления**   это время, затраченное на восстановление службы после возникновения сбоя, которое часто выражается как среднее время восстановления (мттр).</span><span class="sxs-lookup"><span data-stu-id="76b6c-153">**Time to Repair**   This is the time taken to recover a service after a failure has occurred and is often expressed as mean (meaning average) time to repair (MTTR).</span></span>

<span data-ttu-id="76b6c-154">Доступность, надежность и время восстановления связаны следующим образом:</span><span class="sxs-lookup"><span data-stu-id="76b6c-154">Availability, reliability, and time to repair are related as follows:</span></span>

<span data-ttu-id="76b6c-155">**Доступность = (MTBF – мттр)/MTBF**   (например, если сервер не проходит две попытки в течение шести месяцев и недоступен в среднем на 20 минут), MTBF составляет три месяца или 90 дня, а мттр — 20 минут.</span><span class="sxs-lookup"><span data-stu-id="76b6c-155">**Availability = (MTBF – MTTR) / MTBF**   For example, if a server fails two times over a six-month period and is unavailable for an average of 20 minutes, the MTBF is three months or 90 days and the MTTR is 20 minutes.</span></span> <span data-ttu-id="76b6c-156">Таким образом, доступность = (90 дней – 20 минут)/90 дней = 99,985%.</span><span class="sxs-lookup"><span data-stu-id="76b6c-156">Therefore, Availability = (90 days – 20 minutes) / 90 days = 99.985 percent.</span></span>

<span data-ttu-id="76b6c-157">Управление обеспечением доступности — это процесс, который гарантирует, что доступность развернута и сохраняется в параметрах, определенных в SLA.</span><span class="sxs-lookup"><span data-stu-id="76b6c-157">Availability management is the process of making sure that availability is maximized and kept within the parameters that are defined in SLAs.</span></span> <span data-ttu-id="76b6c-158">Управление обеспечением доступности включает следующие процессы:</span><span class="sxs-lookup"><span data-stu-id="76b6c-158">Availability management includes the following processes:</span></span>

  - <span data-ttu-id="76b6c-159">**Наблюдение за**     анализом времени и время, в течение которого недоступна служба.</span><span class="sxs-lookup"><span data-stu-id="76b6c-159">**Monitoring**    Examining when and for how long services are unavailable.</span></span>

  - <span data-ttu-id="76b6c-160">**Данные о доступности отчетов**   должны регулярно предоставляться для управления, пользователей и рабочих групп.</span><span class="sxs-lookup"><span data-stu-id="76b6c-160">**Reporting**   Availability figures should be regularly provided to management, users, and operations teams.</span></span> <span data-ttu-id="76b6c-161">Эти отчеты должны выявлять тенденции и определять области, которые прекрасно работают, и области, требующие внимания.</span><span class="sxs-lookup"><span data-stu-id="76b6c-161">These reports should highlight trends and identify areas that are doing well and areas that require attention.</span></span> <span data-ttu-id="76b6c-162">Отчет должен суммировать соответствие требованиям с целями, заданными в SLA.</span><span class="sxs-lookup"><span data-stu-id="76b6c-162">The report should summarize compliance with targets set in the SLAs.</span></span>

  - <span data-ttu-id="76b6c-163">**Улучшение**   если доступность не соответствует конечным объектам, определенным в соглашениях об уровне обслуживания или тенденция к снижению доступности, процесс управления сведениями о доступности должен планировать шаги.</span><span class="sxs-lookup"><span data-stu-id="76b6c-163">**Improvement**   If availability does not meet targets that are defined in the SLAs or where the trend is toward reduced availability, the availability management process should plan remedial steps.</span></span> <span data-ttu-id="76b6c-164">Это должно включать работу с другими ответственными группами, чтобы вычислить причины нарушения и спланировать повторяющиеся действия, чтобы не допустить повторения перерывов.</span><span class="sxs-lookup"><span data-stu-id="76b6c-164">This should include working with other responsible teams to highlight reasons for outages and to plan remedial actions to prevent a recurrence of the outages.</span></span>

<span data-ttu-id="76b6c-165">Измерения емкости и доступности — это повторяющиеся задачи, которые лучше всего подходят для автоматизированных средств и сценариев, таких как Microsoft System Center Operations Manager (прежнее название — Microsoft Operations Manager), которое рассматривается ниже в этом документе.</span><span class="sxs-lookup"><span data-stu-id="76b6c-165">Capacity and availability measurements are repetitive tasks that are ideally suited to automated tools and scripts such as Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which is discussed later in this document.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="76b6c-166">См. также</span><span class="sxs-lookup"><span data-stu-id="76b6c-166">See Also</span></span>


[<span data-ttu-id="76b6c-167">Мониторинг сервера Lync Server 2013 с помощью System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="76b6c-167">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

