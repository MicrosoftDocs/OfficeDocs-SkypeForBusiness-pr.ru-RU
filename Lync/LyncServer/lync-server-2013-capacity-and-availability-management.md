---
title: 'Lync Server 2013: Управление емкостью и доступностью'
description: 'Lync Server 2013: Управление емкостью и доступностью.'
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
ms.openlocfilehash: d498649651f8cfbccc65f5b1b5f010025ac418e7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565155"
---
# <a name="capacity-and-availability-management-in-lync-server-2013"></a><span data-ttu-id="bed77-103">Управление емкостью и доступностью в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bed77-103">Capacity and availability management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bed77-104">_**Последнее изменение темы:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="bed77-104">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="bed77-105">Цель управления емкостью и обеспечением доступности — измерение и контроль производительности системы.</span><span class="sxs-lookup"><span data-stu-id="bed77-105">The purpose of capacity management and availability management is to measure and control system performance.</span></span> <span data-ttu-id="bed77-106">Рекомендуется реализовать процедуры управления емкостью и обеспечения доступности, чтобы можно было измерять и контролировать производительность системы.</span><span class="sxs-lookup"><span data-stu-id="bed77-106">We recommend that you implement capacity management and availability management procedures so that you can measure and control system performance.</span></span> <span data-ttu-id="bed77-107">Необходимо знать, доступна ли система, и может ли она обрабатывать текущие и запланированные требования, устанавливая базовые уровни и отслеживая систему для поиска тенденций.</span><span class="sxs-lookup"><span data-stu-id="bed77-107">You have to know whether the system is available and if it can handle the current and the projected demands by setting baselines and monitoring the system to look for trends.</span></span>

<div>

## <a name="capacity-management"></a><span data-ttu-id="bed77-108">Управление емкостью</span><span class="sxs-lookup"><span data-stu-id="bed77-108">Capacity management</span></span>

<span data-ttu-id="bed77-109">Управление емкостью включает в себя планирование, изменение размеров и Управление емкостью служб, чтобы обеспечить превышение минимальных уровней производительности, указанных в соглашении об уровне обслуживания.</span><span class="sxs-lookup"><span data-stu-id="bed77-109">Capacity management involves planning, sizing, and controlling service capacity to help guarantee that the minimum performance levels specified in your SLA are exceeded.</span></span> <span data-ttu-id="bed77-110">Хорошее управление емкостью помогает обеспечить возможность предоставления ИТ-служб по разумным затратам и по-прежнему соответствовать уровням производительности, определенным в рамках вашего соглашения об уровне обслуживания с клиентом.</span><span class="sxs-lookup"><span data-stu-id="bed77-110">Good capacity management helps ensure that you can provide IT services at a reasonable cost and still meet the levels of performance defined in your SLAs with the client.</span></span> <span data-ttu-id="bed77-111">К этим условиям могут относиться следующие:</span><span class="sxs-lookup"><span data-stu-id="bed77-111">These criteria can include the following:</span></span>

  - <span data-ttu-id="bed77-112">Время отклика **системы**     Это измеряемое время, затраченное системой на выполнение типичных действий.</span><span class="sxs-lookup"><span data-stu-id="bed77-112">**System Response Time**   This is the measured time that the system takes to do typical actions.</span></span> <span data-ttu-id="bed77-113">Примеры включают время, необходимое для работы роли аудио-и видеофайла для обработки аудио-и видеоданных, время, необходимое для создания и присоединения клиента к Конференции, а также время, затрачиваемое на обновление сведений о присутствии для всех клиентов-наблюдателей.</span><span class="sxs-lookup"><span data-stu-id="bed77-113">Examples include the time that is required for the audio/video server role to process audio/video traffic, the time that is required for a client to create and join a conference, or the time taken for presence to be updated in all watcher clients.</span></span>

  - <span data-ttu-id="bed77-114">**Емкость хранилища**     Это емкость системы хранения, независимо от того, является ли она базой данных контента, устройством резервного копирования или локальным диском.</span><span class="sxs-lookup"><span data-stu-id="bed77-114">**Storage Capacity**   This is the capacity of a storage system, whether it is a content database, a backup device, or a local drive.</span></span> <span data-ttu-id="bed77-115">Примеры: максимальный объем дискового пространства, который должен быть указан для каждого сайта, а также время, в течение которого будут храниться резервные копии, прежде чем они будут перезаписаны.</span><span class="sxs-lookup"><span data-stu-id="bed77-115">Examples include the maximum amount of storage space to be provided per site and the time that backups should be stored before they are overwritten.</span></span>

<span data-ttu-id="bed77-116">Настройка емкости часто позволяет убедиться, что доступно достаточное количество физических ресурсов, таких как дисковое пространство и пропускная способность сети.</span><span class="sxs-lookup"><span data-stu-id="bed77-116">Adjusting capacity is frequently a case of making sure that enough physical resources are available, such as disk space and network bandwidth.</span></span> <span data-ttu-id="bed77-117">В приведенной ниже таблице перечислены типичные решения проблем, связанных с емкостью.</span><span class="sxs-lookup"><span data-stu-id="bed77-117">The following table lists typical resolutions for capacity-related issues.</span></span>

### <a name="typical-resolutions-for-capacity-related-issues"></a><span data-ttu-id="bed77-118">Типичное решение проблем, связанных с емкостью</span><span class="sxs-lookup"><span data-stu-id="bed77-118">Typical resolutions for capacity-related issues</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bed77-119">Проблема</span><span class="sxs-lookup"><span data-stu-id="bed77-119">Issue</span></span></th>
<th><span data-ttu-id="bed77-120">Возможное решение</span><span class="sxs-lookup"><span data-stu-id="bed77-120">Possible resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bed77-121">Удаленные пользователи с низкой производительностью звука и видео</span><span class="sxs-lookup"><span data-stu-id="bed77-121">Remote users having poor audio/video performance</span></span></p></td>
<td><p><span data-ttu-id="bed77-122">Проверьте наличие соответствующей пропускной способности в каналах WAN и в том случае, если качество обслуживания включено и соответствующим образом настроено.</span><span class="sxs-lookup"><span data-stu-id="bed77-122">Check to see whether appropriate bandwidth is available on the WAN links and if QoS is enabled and appropriately configured.</span></span> <span data-ttu-id="bed77-123">Проверьте данные QoE.</span><span class="sxs-lookup"><span data-stu-id="bed77-123">Check QoE data.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bed77-124">Общий отклик среды Lync работает медленнее.</span><span class="sxs-lookup"><span data-stu-id="bed77-124">Overall response of the Lync environment is slow.</span></span></p></td>
<td><p><span data-ttu-id="bed77-125">Запустите тесты, чтобы проверить, могут ли существующие серверы переднего плана работать с этой нагрузкой.</span><span class="sxs-lookup"><span data-stu-id="bed77-125">Run tests to check that the existing front-end servers can deal with the load.</span></span> <span data-ttu-id="bed77-126">Познакомьтесь с новым сервером переднего плана, если это необходимо. Проверьте время отклика базы данных SQL и устраните причины задержек (например, улучшите дисковые операции ввода-вывода).</span><span class="sxs-lookup"><span data-stu-id="bed77-126">Introduce a new front-end server if it is needed.Check SQL database response times and fix the causes for the delays (for example, improve disk I/O).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bed77-127">Более подробное устранение неполадок описано в руководстве сетевого руководства по Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bed77-127">Troubleshooting in greater detail is covered in the Lync Server Networking Guide.</span></span>

<span data-ttu-id="bed77-128">На производительность влияет конфигурация системы и зависит от физических ресурсов, таких как пропускная способность сети.</span><span class="sxs-lookup"><span data-stu-id="bed77-128">Capacity is affected by system configuration and depends on physical resources such as network bandwidth.</span></span> <span data-ttu-id="bed77-129">Например, если среда Lync настроена для ежедневного выполнения полного резервного копирования, следует соблюдать осторожность, чтобы повысить производительность работы конечных пользователей.</span><span class="sxs-lookup"><span data-stu-id="bed77-129">For example, if a Lync environment is configured to perform a full backup nightly, care must be taken to help guarantee that the effect on the interactive performance experienced by end-users is minimized.</span></span>

<span data-ttu-id="bed77-130">Управление емкостью — это процесс поддержания мощности системы на допустимых уровнях и устранение следующих проблем:</span><span class="sxs-lookup"><span data-stu-id="bed77-130">Capacity management is the process of keeping the capacity of a system within acceptable levels and addresses the following issues:</span></span>

  - <span data-ttu-id="bed77-131">**Реагирование на изменения в требованиях**     Требования к емкости необходимо изменить для учета изменений в системе или в Организации.</span><span class="sxs-lookup"><span data-stu-id="bed77-131">**Reacting to changes in requirements**   Capacity requirements have to be adjusted to account for changes in the system or the organization.</span></span> <span data-ttu-id="bed77-132">Например, если ваша среда решает внедрить корпоративную голосовую связь, будет очень важна количество и расположение серверов-посредников и шлюзов телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="bed77-132">For example, if your environment decides to implement Enterprise Voice, the number and placement of Mediation Servers and public switched telephone network (PSTN) gateways will be very important.</span></span> <span data-ttu-id="bed77-133">Если вы будете совершать магистраль протокола SIP или Direct SIP, Общая структура будет значительно изменена, чтобы обеспечить оптимальную производительность корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="bed77-133">If you'll be doing Session Initiation Protocol (SIP) trunking or direct SIP, the overall design will be significantly changed to provide the best Enterprise Voice performance.</span></span>

  - <span data-ttu-id="bed77-134">**Прогнозирование будущих требований**     Некоторые требования к емкости изменяются предсказуемым образом с течением времени.</span><span class="sxs-lookup"><span data-stu-id="bed77-134">**Predicting future requirements**   Some capacity requirements change predictably over time.</span></span> <span data-ttu-id="bed77-135">Отслеживая тенденции, вы можете заранее спланировать обновления.</span><span class="sxs-lookup"><span data-stu-id="bed77-135">By tracking trends you can plan upgrades in advance.</span></span> <span data-ttu-id="bed77-136">Например, для создания базового плана необходимо отслеживать доступную полосу пропускания между различными сайтами Lync.</span><span class="sxs-lookup"><span data-stu-id="bed77-136">For example, available bandwidth between various Lync sites must be monitored to create a baseline.</span></span> <span data-ttu-id="bed77-137">Этот базовый план позволит предсказать, когда вам потребуется увеличить пропускную способность для этих ссылок, так как количество пользователей на этих удаленных сайтах возрастает с учетом времени.</span><span class="sxs-lookup"><span data-stu-id="bed77-137">This baseline will allow you to predict when you have to add more bandwidth to these links as user count in these remote sites increases with time.</span></span>

</div>

<div>

## <a name="availability-management"></a><span data-ttu-id="bed77-138">Управление доступностью</span><span class="sxs-lookup"><span data-stu-id="bed77-138">Availability management</span></span>

<span data-ttu-id="bed77-139">Управление доступом — это процесс, позволяющий гарантировать, что все ИТ-службы постоянно и экономически эффективно обеспечивают уровень согласованной и надежной службы, которая необходима для клиента.</span><span class="sxs-lookup"><span data-stu-id="bed77-139">Availability management is the process of making sure that any IT service consistently and cost effectively delivers the level of consistent, reliable service that is required by the customer.</span></span> <span data-ttu-id="bed77-140">Управление обеспечением доступности заключается в минимизации потери обслуживания и обеспечении выполнения соответствующих действий в случае потери службы.</span><span class="sxs-lookup"><span data-stu-id="bed77-140">Availability management deals with minimizing loss of service and with making sure that appropriate action is taken if service is lost.</span></span> <span data-ttu-id="bed77-141">В среде Lync может возникнуть вопрос о том, доступна ли служба корпоративной голосовой связи, могут ли пользователи присоединяться к запланированным конференциям и т. д.</span><span class="sxs-lookup"><span data-stu-id="bed77-141">In a Lync environment, you may be concerned about whether the Enterprise Voice service is available, whether users can join scheduled conferences, and so on.</span></span> <span data-ttu-id="bed77-142">Соглашение об уровне обслуживания определяет приемлемую частоту и продолжительность простоя и разрешает определенные периоды, когда система недоступна для запланированного обслуживания.</span><span class="sxs-lookup"><span data-stu-id="bed77-142">An SLA defines an acceptable frequency and length of outages and allows for certain periods when the system is unavailable for planned maintenance.</span></span>

<span data-ttu-id="bed77-143">Если необходимо предоставить отчеты для управления сведениями о доступности систем, или если у вас есть финансовые или другие штрафы, связанные с отсутствующими целевыми объектами доступности, необходимо записать данные о доступности.</span><span class="sxs-lookup"><span data-stu-id="bed77-143">If you have to provide reports to your management about the availability of systems, or if you have financial or other penalties associated with missing availability targets, you must record availability data.</span></span> <span data-ttu-id="bed77-144">Даже если у вас нет таких формальных требований, рекомендуется по крайней мере знать, как часто в системе произошел сбой за определенный период времени.</span><span class="sxs-lookup"><span data-stu-id="bed77-144">Even if you do not have such formal requirements, it is a good idea to at least know how frequently a system has failed in a certain time period.</span></span> <span data-ttu-id="bed77-145">Например, доступность системы за последние 12 месяцев и время, затрачиваемое на восстановление после каждого сбоя.</span><span class="sxs-lookup"><span data-stu-id="bed77-145">For example, system availability in the last 12 months and how long it took to recover from each failure.</span></span> <span data-ttu-id="bed77-146">Эта информация поможет вам измерять и улучшать эффективность команды в ответ на сбой системы.</span><span class="sxs-lookup"><span data-stu-id="bed77-146">This information will help you measure and improve your team’s effectiveness in responding to a system failure.</span></span> <span data-ttu-id="bed77-147">Кроме того, вы можете предоставить вам полезную информацию, если у вас есть спорный вопрос.</span><span class="sxs-lookup"><span data-stu-id="bed77-147">It can also give you useful information if there is a dispute.</span></span>

<span data-ttu-id="bed77-148">Показатели, относящиеся к доступности, приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="bed77-148">Measures related to availability are as follows:</span></span>

  - <span data-ttu-id="bed77-149">**Доступность**     Как правило, это значение времени, в течение которого можно получить доступ к системе или службе по сравнению со временем, когда она не работает.</span><span class="sxs-lookup"><span data-stu-id="bed77-149">**Availability**   This is typically expressed as the time that a system or service can be accessed compared to the time that it is down.</span></span> <span data-ttu-id="bed77-150">Обычно он выражается в процентах.</span><span class="sxs-lookup"><span data-stu-id="bed77-150">It is typically expressed as a percentage.</span></span> <span data-ttu-id="bed77-151">(Могут отображаться ссылки на «три девяти» или «пять девяти».</span><span class="sxs-lookup"><span data-stu-id="bed77-151">(You may see references to “three nines” or “five nines”.</span></span> <span data-ttu-id="bed77-152">Они ссылаются на 99,9 процентов или 99,999 процента доступности.)</span><span class="sxs-lookup"><span data-stu-id="bed77-152">These refer to 99.9 percent or 99.999 percent availability.)</span></span>

  - <span data-ttu-id="bed77-153">**Надежность**     Это мера времени между сбоями системы и иногда выражается как среднее (или среднее) время между сбоями (MTBF).</span><span class="sxs-lookup"><span data-stu-id="bed77-153">**Reliability**   This is a measure of the time between failures of a system and is sometimes expressed as mean (or average) time between failures (MTBF).</span></span>

  - <span data-ttu-id="bed77-154">**Время для восстановления**     Это время, затраченное на восстановление службы после сбоя и часто выраженное средним значением времени восстановления (MTTR).</span><span class="sxs-lookup"><span data-stu-id="bed77-154">**Time to Repair**   This is the time taken to recover a service after a failure has occurred and is often expressed as mean (meaning average) time to repair (MTTR).</span></span>

<span data-ttu-id="bed77-155">Доступность, надежность и время восстановления связаны следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bed77-155">Availability, reliability, and time to repair are related as follows:</span></span>

<span data-ttu-id="bed77-156">**Доступность = (MTBF – MTTR)/MTBF**     Например, если сервер отказывается два раза за шесть месяцев и недоступен в среднем в 20 минут, MTBF составляет три месяца или 90 дней, а MTTR — 20 минут.</span><span class="sxs-lookup"><span data-stu-id="bed77-156">**Availability = (MTBF – MTTR) / MTBF**   For example, if a server fails two times over a six-month period and is unavailable for an average of 20 minutes, the MTBF is three months or 90 days and the MTTR is 20 minutes.</span></span> <span data-ttu-id="bed77-157">Таким образом, доступность = (90 дней – 20 минут)/90 дней = 99,985 процентов.</span><span class="sxs-lookup"><span data-stu-id="bed77-157">Therefore, Availability = (90 days – 20 minutes) / 90 days = 99.985 percent.</span></span>

<span data-ttu-id="bed77-158">Управление обеспечением доступности — это процесс, позволяющий убедиться, что доступность развернута и хранится в параметрах, определенных в SLA.</span><span class="sxs-lookup"><span data-stu-id="bed77-158">Availability management is the process of making sure that availability is maximized and kept within the parameters that are defined in SLAs.</span></span> <span data-ttu-id="bed77-159">Управление доступностьми состоит из следующих процессов:</span><span class="sxs-lookup"><span data-stu-id="bed77-159">Availability management includes the following processes:</span></span>

  - <span data-ttu-id="bed77-160">**Мониторинг**     Анализ времени и времени недоступности служб.</span><span class="sxs-lookup"><span data-stu-id="bed77-160">**Monitoring**    Examining when and for how long services are unavailable.</span></span>

  - <span data-ttu-id="bed77-161">**Создание отчетов**     Данные о доступности должны быть регулярно предоставлены управлению, пользователям и операционным группам.</span><span class="sxs-lookup"><span data-stu-id="bed77-161">**Reporting**   Availability figures should be regularly provided to management, users, and operations teams.</span></span> <span data-ttu-id="bed77-162">Эти отчеты должны выделять тенденции и определять области, которые хорошо работают, и области, требующие внимания.</span><span class="sxs-lookup"><span data-stu-id="bed77-162">These reports should highlight trends and identify areas that are doing well and areas that require attention.</span></span> <span data-ttu-id="bed77-163">Отчет должен обобщеть соответствие целям с целями, установленными в SLA.</span><span class="sxs-lookup"><span data-stu-id="bed77-163">The report should summarize compliance with targets set in the SLAs.</span></span>

  - <span data-ttu-id="bed77-164">**Улучшение**     Если доступность не соответствует целевым объектам, определенным в SLA, или тенденция к снижению доступности, процесс управления доступностью должен спланировать действия по выпуску носителей.</span><span class="sxs-lookup"><span data-stu-id="bed77-164">**Improvement**   If availability does not meet targets that are defined in the SLAs or where the trend is toward reduced availability, the availability management process should plan remedial steps.</span></span> <span data-ttu-id="bed77-165">Это должно включать в себя работу с другими ответственными командами, чтобы выделить причины простоев и спланировать действия по выпуску, чтобы избежать повторения простоев.</span><span class="sxs-lookup"><span data-stu-id="bed77-165">This should include working with other responsible teams to highlight reasons for outages and to plan remedial actions to prevent a recurrence of the outages.</span></span>

<span data-ttu-id="bed77-166">Измерения емкости и доступности — это повторяющиеся задачи, которые идеально подходят для автоматизированных средств и сценариев, таких как Microsoft System Center Operations Manager (ранее Microsoft Operations Manager), которые рассматриваются далее в этом документе.</span><span class="sxs-lookup"><span data-stu-id="bed77-166">Capacity and availability measurements are repetitive tasks that are ideally suited to automated tools and scripts such as Microsoft System Center Operations Manager (formerly Microsoft Operations Manager), which is discussed later in this document.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bed77-167">См. также</span><span class="sxs-lookup"><span data-stu-id="bed77-167">See Also</span></span>


[<span data-ttu-id="bed77-168">Мониторинг Lync Server 2013 с помощью System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="bed77-168">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

