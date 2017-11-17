---
title: "Аудиоконференции в Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Практическое руководство по развертыванию Аудиоконференций в Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: d38112015929a3491386146dd0920d81919a8a66
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2017
---
<a name="audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="fb018-103">Аудиоконференции в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fb018-103">Audio Conferencing in Microsoft Teams</span></span>
=====================================

> [!IMPORTANT]
> <span data-ttu-id="fb018-104">Служба Аудиоконференций находится на этапе общедоступной предварительной версии.</span><span class="sxs-lookup"><span data-stu-id="fb018-104">Audio conferencing is in public preview.</span></span> <span data-ttu-id="fb018-105">Она доступна ранним последователям и клиентам с предварительной версией и может изменяться при выпуске или обновлении.</span><span class="sxs-lookup"><span data-stu-id="fb018-105">It's available to Early Adopters (EA) and preview customers and could change as it is released or updated.</span></span>

<span data-ttu-id="fb018-106">Служба Аудиоконференций в Office 365 (ранее она называлась конференц-связью по ТСОП) позволяет участникам присоединяться к вашим собраниям с любого телефона.</span><span class="sxs-lookup"><span data-stu-id="fb018-106">Audio Conferencing in Office 365 (formerly known as PSTN Conferencing) allows participants to join your meetings from any telephone.</span></span> <span data-ttu-id="fb018-107">Теперь она доступна в Microsoft Teams на этапе общедоступной предварительной версии и позволяет пользователям присоединяться к собраниям Teams с помощью телефонов.</span><span class="sxs-lookup"><span data-stu-id="fb018-107">This feature is now available in Microsoft Teams, in public preview, allowing users to join Teams meetings using their phones.</span></span> <span data-ttu-id="fb018-108">Приведенное здесь практическое руководство содержит пошаговое описание цикла взаимодействия с клиентом Office 365 FastTrack для аудиоконференций — выработка концепции, адаптация и извлечение выгоды.</span><span class="sxs-lookup"><span data-stu-id="fb018-108">The practical guidance in this article steps you through the Office 365 FastTrack customer journey framework for Audio Conferencing - Envision, Onboard, and Drive value.</span></span>

<span data-ttu-id="fb018-109">Ниже указано, что именно вы получаете вместе с [Аудиоконференциями](https://go.microsoft.com/fwlink/?linkid=858992) в Office 365.</span><span class="sxs-lookup"><span data-stu-id="fb018-109">Here's what you get with [Audio Conferencing](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.</span></span>

> [!NOTE]
> <span data-ttu-id="fb018-110">Служба Аудиоконференций поддерживает как Teams, так и Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="fb018-110">Audio Conferencing supports both Teams and Skype for Business Online.</span></span> <span data-ttu-id="fb018-111">Сейчас существующий Центр администрирования Skype для бизнеса и удаленная оболочка PowerShell предоставляют административные интерфейсы для управления Аудиоконференциями.</span><span class="sxs-lookup"><span data-stu-id="fb018-111">Currently, the existing Skype for Business Admin center and remote PowerShell provide the administrative interfaces to manage Audio Conferencing.</span></span>


|  |  |
|---------|---------|
|  <iframe width="350" height="200" src="https://www.youtube.com/embed/AGPvaW4Vg0o" frameborder="0" allowfullscreen></iframe>   | |

<span data-ttu-id="fb018-112">Выработка концепции <a name="Envision_AudioConferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="fb018-112">Envision <a name="Envision_AudioConferencing"> </a></span></span>
=========

<span data-ttu-id="fb018-113">Стадия выработки концепции формирует основу для цикла взаимодействия с клиентом Office 365 и применяется ко всем рабочим нагрузкам, таким как Аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="fb018-113">The Envision phase provides the foundation for the Office 365 customer journey and is applicable to all workloads such as Audio Conferencing.</span></span>

<span data-ttu-id="fb018-114">На этой стадии определяются бизнес-цели и собираются имеющие отношение к проекту заинтересованные лица, а конечной его целью является создание:</span><span class="sxs-lookup"><span data-stu-id="fb018-114">In this phase, business goals are captured, with relevant project stakeholders assembled, to ultimately deliver:</span></span>

-   <span data-ttu-id="fb018-115">высокоуровневого плана достижения успеха, содержащего варианты бизнес-использования, ключевых заинтересованных лиц, задачи и ключевые результаты (OKR), ключевые показатели успешности (KSI), риски, оценку среды, готовность к освоению и план работ;</span><span class="sxs-lookup"><span data-stu-id="fb018-115">a high-level success plan that contains business use cases, key stakeholders, objectives and key results (OKRs), key success indicators (KSIs), risks, environmental assessment, adoption readiness, and operational plan.</span></span>

-   <span data-ttu-id="fb018-116">затем подробного плана реализации аудиоконференций для достижения требуемого конечного состояния.</span><span class="sxs-lookup"><span data-stu-id="fb018-116">and subsequently, a detailed Audio Conferencing technical implementation plan to achieve the desired end state.</span></span>

<a name="define-business-use-cases-for-audio-conferencing"></a><span data-ttu-id="fb018-117">Определение вариантов бизнес-использования для аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="fb018-117">Define business use cases for Audio Conferencing</span></span>
------------------------------------------------

<span data-ttu-id="fb018-118">Аудиоконференции предоставляют организациям дополнительные точки входа на запланированные собрания и позволяют участникам присоединяться к ним по ТСОП с помощью набора номера со стационарных телефонов, УАТС или мобильных телефонов.</span><span class="sxs-lookup"><span data-stu-id="fb018-118">Audio Conferencing provides organizations with additional entry points to any scheduled meetings by allowing meeting participants to join via PSTN by dialing in using traditional landline, PBX, or mobile phones.</span></span>

<span data-ttu-id="fb018-119">Это удобно, когда организатор или участники не находятся за компьютером либо подключения к данным недоступны или недостаточно ненадежны для обеспечения голосовой связи, например при нахождении в удаленной области с нестабильным подключением к мобильной сети для передачи данных, при подключении к бесплатной общедоступной службе Wi-Fi с ограниченной пропускной способностью, а также когда участники собрания предпочитают подключиться к собранию через удобную для них телефонную конечную точку.</span><span class="sxs-lookup"><span data-stu-id="fb018-119">This is useful when the organizer or participants are not in front of a computer, or when data connections are unavailable or unreliable to support voice communications—such as when in a remote area with spotty mobile data coverage, or if connected to a free, public Wi-Fi service with limited bandwidth, or when meeting participants prefer to dial in to the meeting using telephony endpoint readily accessible to them.</span></span>

<span data-ttu-id="fb018-120">На этом этапе ключевые заинтересованные лица проекта определят варианты бизнес-использования, обосновывающие внедрение аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-120">In this step, core project stakeholders will define business use cases that support the implementation of Audio Conferencing.</span></span>

<span data-ttu-id="fb018-121">В рамках этой процедуры требуется определить и задокументировать ожидаемые и измеримые бизнес-результаты, а также указать следующее:</span><span class="sxs-lookup"><span data-stu-id="fb018-121">Business use cases are meant to define and document the expected and measurable business outcomes, and include the following:</span></span>

-   <span data-ttu-id="fb018-122">Описание текущего бизнес-процесса.</span><span class="sxs-lookup"><span data-stu-id="fb018-122">Description of current business process.</span></span>

-   <span data-ttu-id="fb018-123">Трудности, связанные с текущим бизнес-процессом.</span><span class="sxs-lookup"><span data-stu-id="fb018-123">Challenges with existing business process defined.</span></span>

-   <span data-ttu-id="fb018-124">Каким образом технология позволяет преодолеть эти трудности.</span><span class="sxs-lookup"><span data-stu-id="fb018-124">How technology can help overcome these challenges.</span></span>

-   <span data-ttu-id="fb018-125">Измеримые бизнес-результаты, ожидаемые в случае преодоления этих трудностей.</span><span class="sxs-lookup"><span data-stu-id="fb018-125">The expected and measurable business outcome if these challenges are overcome.</span></span>

<table>
<tbody>
<tr class="header">
<th align="left"><p><img src="media/audio_conferencing_image2.png" /></p></th>
<td align="left"><p><span data-ttu-id="fb018-126"><strong>Описание текущего бизнес-процесса</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-126"><strong>Description of current business process</strong></span></span></p>
<p><span data-ttu-id="fb018-127">В настоящее время компания Contoso использует службы конференц-связи по ТСОП, предоставляемые ведущим местным поставщиком телефонии, и оплачивает внутренние собрания и собрания с внешними сторонами поминутно.</span><span class="sxs-lookup"><span data-stu-id="fb018-127">Contoso currently relies on PSTN conferencing services provided by the incumbent local telephony provider chargeable by meeting minutes for internal meetings and meetings involving external parties.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="media/audio_conferencing_image3.png" /></p></td>
<td align="left"><p><span data-ttu-id="fb018-128"><strong>Трудности, связанные с текущим бизнес-процессом</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-128"><strong>Challenges with existing business process</strong></span></span></p>
<p><span data-ttu-id="fb018-129">На имеющуюся службу конференц-связи по ТСОП компания Contoso тратит около 1 миллиона долларов США в год, при этом 75 % затрат связано с внутренними собраниями.</span><span class="sxs-lookup"><span data-stu-id="fb018-129">Contoso spends roughly USD 1 million per year for the current PSTN conferencing service, with 75% of the cost incurred for internal meetings.</span></span></p>
<p><span data-ttu-id="fb018-130">Использование традиционных телефонных конечных точек для присоединения к собраниям, проводимым посредством службы конференц-связи по ТСОП, не согласуется с планами организации по внедрению Teams в качестве современной платформы для взаимодействия и совместной работы.</span><span class="sxs-lookup"><span data-stu-id="fb018-130">The use of traditional telephony endpoints to join the meetings hosted by the PSTN conferencing service is not aligned with the plan for the organization to adopt Teams as modern communications and collaboration platform.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><img src="media/audio_conferencing_image4.png" /></p></td>
<td align="left"><p><span data-ttu-id="fb018-131"><strong>Каким образом технология позволяет преодолеть эти трудности</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-131"><strong>How technology can overcome these challenges</strong></span></span></p>
<p><span data-ttu-id="fb018-132">После внедрения современной платформы для взаимодействия и совместной работы Microsoft Teams внутренние пользователи смогут присоединяться к собраниям с помощью своих компьютеров, оснащенных оптимизированными гарнитурами, и устройств для конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="fb018-132">With the adoption of Microsoft Teams as modern communications and collaboration platform, internal users are expected to primarily join meetings using their PCs equipped with optimized headsets and meeting room devices.</span></span> <span data-ttu-id="fb018-133">Служба Аудиоконференций позволит присоединяться внешним участникам, а также обеспечит поддержку в ситуациях, когда внутренним участникам неудобно использовать голосовую связь через компьютер.</span><span class="sxs-lookup"><span data-stu-id="fb018-133">Audio Conferencing service will be available to support external participants or to support situations where the use of PC audio is not favorable for the internal participants.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="media/audio_conferencing_image5.png" /></p></td>
<td align="left"><p><span data-ttu-id="fb018-134"><strong>Ожидаемые и измеримые бизнес-результаты</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-134"><strong>Expected, measurable, business outcomes</strong></span></span></p>
<p><span data-ttu-id="fb018-135">Переход на современную платформу Teams в сочетании с использованием службы Аудиоконференций позволит значительно сократить затраты — Contoso планирует тратить всего около 20 % от стоимости службы конференц-связи по ТСОП в год.</span><span class="sxs-lookup"><span data-stu-id="fb018-135">The move to Teams as modern communications and collaboration platform, combined with Audio Conferencing service, will greatly reduce the cost to deliver the PSTN conferencing service to the point that Contoso is expected to only spend approximately 20% of the annual cost of the existing PSTN conferencing service.</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fb018-136">_Табл. 1. Пример варианта бизнес-использования_</span><span class="sxs-lookup"><span data-stu-id="fb018-136">_Table 1 Business use case example_</span></span>


<span data-ttu-id="fb018-137">Кроме определения вариантов бизнес-использования, прояснение ситуации с организационной средой и сроками по проекту на этом этапе помогает продвинуться дальше по стадии выработки концепции.</span><span class="sxs-lookup"><span data-stu-id="fb018-137">In addition to defining the business use cases, having a clarity around the organizational scope and project timelines at this step helps move onto the next step of the Envision phase.</span></span>

<a name="identify-key-stakeholders"></a><span data-ttu-id="fb018-138">Определение ключевых заинтересованных лиц</span><span class="sxs-lookup"><span data-stu-id="fb018-138">Identify key stakeholders</span></span>
-------------------------

<span data-ttu-id="fb018-139">Описанные на предыдущем этапе варианты бизнес-использования включают в себя организационную среду для внедрения службы Аудиоконференций. Взяв эти данные за основу, можно определить комплексный спектр заинтересованных лиц, чтобы привлечь к работе над проектом подходящих сотрудников.</span><span class="sxs-lookup"><span data-stu-id="fb018-139">The business use cases defined in the previous step will include organizational scope of Audio Conferencing implementation, and based on that, the comprehensive stakeholder matrix can be completed to include the right people to be involved in the project.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fb018-140">Должность</span><span class="sxs-lookup"><span data-stu-id="fb018-140">Role</span></span></th>
<th align="left"><span data-ttu-id="fb018-141">Описание</span><span class="sxs-lookup"><span data-stu-id="fb018-141">Description</span></span></th>
<th align="left"><span data-ttu-id="fb018-142">Имя, контактные данные и расположение</span><span class="sxs-lookup"><span data-stu-id="fb018-142">Name, contact information, location</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-143"><strong>Ответственный спонсор проекта</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-143"><strong>Project Executive Sponsor</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="fb018-144">Последняя инстанция в отношении проведения работ и отчетности по проекту</span><span class="sxs-lookup"><span data-stu-id="fb018-144">Ultimate authority and accountability for the project and delivery on project objectives</span></span></li>
<li><span data-ttu-id="fb018-145">Помогает в разрешении вопросов, эскалированных начальником проектной группы</span><span class="sxs-lookup"><span data-stu-id="fb018-145">Help resolve issues escalated by Project Lead</span></span></li>
<li><span data-ttu-id="fb018-146">Курирует распространение информации о целях проекта в организации</span><span class="sxs-lookup"><span data-stu-id="fb018-146">Sponsors communication within the company about project goals</span></span></li>
<li><span data-ttu-id="fb018-147">Отвечает за принятие ключевых стратегических решений</span><span class="sxs-lookup"><span data-stu-id="fb018-147">Responsible for making key strategic decisions</span></span></li>
<li><span data-ttu-id="fb018-148">Отвечает за доступность требуемых ресурсов и бюджет</span><span class="sxs-lookup"><span data-stu-id="fb018-148">Responsible for availability of required resources and budget</span></span></p>
<li><span data-ttu-id="fb018-149">Проводит квартальные обзоры коммерческой деятельности</span><span class="sxs-lookup"><span data-stu-id="fb018-149">Leading Quarterly Business Reviews (QBR)</span></span></li>
<li><span data-ttu-id="fb018-150">Отвечает за утверждение и поддержку информационной кампании</span><span class="sxs-lookup"><span data-stu-id="fb018-150">Buy-In and support of awareness campaign effort</span></span></li>
<li><span data-ttu-id="fb018-151">Выступает в качестве куратора проекта при развертывании программы</span><span class="sxs-lookup"><span data-stu-id="fb018-151">Serving as the Project Sponsor to the program rollout</span></span></li></ul></td>
<td align="left"><span data-ttu-id="fb018-152">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-152">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-153"><strong>Начальник проектной группы</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-153"><strong>Project Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="fb018-154">Управляет и руководит проектной группой</span><span class="sxs-lookup"><span data-stu-id="fb018-154">Managing and leading project team</span></span></li>
<li><span data-ttu-id="fb018-155">Координирует работу партнеров и команд, вовлеченных в проект</span><span class="sxs-lookup"><span data-stu-id="fb018-155">Coordinates partners and working teams engaged in the project</span></span></li>
<li><span data-ttu-id="fb018-156">Отвечает за составление и реализацию планов проекта для достижения квартальных ключевых результатов</span><span class="sxs-lookup"><span data-stu-id="fb018-156">Accountable for creating and managing project plans to meet quarterly key results</span></span></li>
<li><span data-ttu-id="fb018-157">Разрешает кросс-функциональные вопросы</span><span class="sxs-lookup"><span data-stu-id="fb018-157">Resolving cross-functional issues</span></span></li>
<li><span data-ttu-id="fb018-158">Держит кураторов проекта в курсе событий</span><span class="sxs-lookup"><span data-stu-id="fb018-158">Providing regular updates to the project sponsors</span></span></li>
<li><span data-ttu-id="fb018-159">Интегрирует аспекты освоения в комплексный план проекта</span><span class="sxs-lookup"><span data-stu-id="fb018-159">Incorporating Adoption aspects into the all-up project plan</span></span></li>
<li><span data-ttu-id="fb018-160">Проводит ежемесячные обзоры коммерческой и операционной деятельности, включаемые в состав квартальных обзоров коммерческой деятельности</span><span class="sxs-lookup"><span data-stu-id="fb018-160">Leading Monthly Business and Operational Reviews (MBR), contributing to Quarterly Business Reviews</span></span></li></ul></td>
<td align="left"><span data-ttu-id="fb018-161">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-161">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-162"><strong>Руководитель/архитектор по совместной работе</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-162"><strong>Collaboration Lead/Architect</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="fb018-163">Отвечает за реализацию стратегии совместной работы, определенной руководством организации</span><span class="sxs-lookup"><span data-stu-id="fb018-163">Responsible for execution on collaboration strategy defined by company executives</span></span></li>
<li><span data-ttu-id="fb018-164">Анализирует и отбирает для организации продукты по обеспечению совместной работы, соответствующие бизнес-целям</span><span class="sxs-lookup"><span data-stu-id="fb018-164">Analyzing and choosing collaboration products for the company that meets business goals</span></span></li>
<li><span data-ttu-id="fb018-165">Отвечает за проектирование функционирования продуктов по обеспечению совместной работы</span><span class="sxs-lookup"><span data-stu-id="fb018-165">Responsible for the design of the operations for collaboration products</span></span></li>
<li><span data-ttu-id="fb018-166">Определяет модель работы и поддержки</span><span class="sxs-lookup"><span data-stu-id="fb018-166">Defines operation and support model</span></span></li>
<li><span data-ttu-id="fb018-167">Участвует в ежемесячных и квартальных обзорах коммерческой деятельности</span><span class="sxs-lookup"><span data-stu-id="fb018-167">Contributing to Monthly and Quarterly Business Reviews</span></span></li><ul></td>
<td align="left"><span data-ttu-id="fb018-168">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-168">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-169"><strong>Консультант</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-169"><strong>Consultant</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="fb018-170">Отвечает за службы настройки</span><span class="sxs-lookup"><span data-stu-id="fb018-170">Responsible for configuration services</span></span></li>
<li><span data-ttu-id="fb018-171">Участвует в разработке общей архитектуры решения</span><span class="sxs-lookup"><span data-stu-id="fb018-171">Contributes in overall solution architecture</span></span></li></ul></td>
<td align="left"><span data-ttu-id="fb018-172">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-172">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-173"><strong>Руководитель проекта</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-173"><strong>Project Manager</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="fb018-174">Разрабатывает и корректирует план проекта</span><span class="sxs-lookup"><span data-stu-id="fb018-174">Developing and maintaining project plan</span></span></li>
<li><span data-ttu-id="fb018-175">Следит за тем, чтобы конечный результат соответствовал плану и бюджету проекта</span><span class="sxs-lookup"><span data-stu-id="fb018-175">Managing project deliverables in line with project plan and budget</span></span></li>
<li><span data-ttu-id="fb018-176">Регистрирует и обрабатывает вопросы по проекту, включая эскалации</span><span class="sxs-lookup"><span data-stu-id="fb018-176">Recording and managing project issues, including escalations</span></span></li>
<li><span data-ttu-id="fb018-177">Еженедельно проводит планерки</span><span class="sxs-lookup"><span data-stu-id="fb018-177">Conducting weekly stand up calls</span></span></li>
<li><span data-ttu-id="fb018-178">Взаимодействует с ответственными спонсорами проекта и держит их в курсе событий</span><span class="sxs-lookup"><span data-stu-id="fb018-178">Liaises with, and provides updates to project executive sponsors</span></span></li>
<li><span data-ttu-id="fb018-179">Сотрудничает с архитектором, чтобы определить подход к управлению изменениями и составить планы взаимодействия</span><span class="sxs-lookup"><span data-stu-id="fb018-179">Working with the Architect to define the Change Management approach and Communication Plans</span></span></li></ul></td>
<td align="left"><span data-ttu-id="fb018-180">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-180">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-181"><strong>Специалист по управлению изменениями/освоению</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-181"><strong>Change Management/Adoption Specialist</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="fb018-182">На стадии исследования предоставляет входные данные о процессах освоения и обучения</span><span class="sxs-lookup"><span data-stu-id="fb018-182">Provide input on Discovery phase into adoption and training processes</span></span></li>
<li><span data-ttu-id="fb018-183">Участвует в рабочем совещании по стратегии освоения</span><span class="sxs-lookup"><span data-stu-id="fb018-183">Participate in adoption strategy workshop</span></span></li>
<li><span data-ttu-id="fb018-184">Отвечает за разработку стратегии освоения</span><span class="sxs-lookup"><span data-stu-id="fb018-184">Developing and responsible for adoption strategy</span></span></li>
<li><span data-ttu-id="fb018-185">Разрабатывает и реализует план взаимодействия</span><span class="sxs-lookup"><span data-stu-id="fb018-185">Developing and executing communication plan</span></span></li>
<li><span data-ttu-id="fb018-186">Отвечает за обучение пользователей</span><span class="sxs-lookup"><span data-stu-id="fb018-186">Responsible for delivering trainings to end users</span></span></li>
<li><span data-ttu-id="fb018-187">Собирает отзывы и проводит опросы</span><span class="sxs-lookup"><span data-stu-id="fb018-187">Collect feedback and conduct surveys</span></span></li></ul></td>
<td align="left"><span data-ttu-id="fb018-188">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-188">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-189"><strong>Руководитель по сетям</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-189"><strong>Network Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="fb018-190">На стадии исследования предоставляет входные данные о структуре сети</span><span class="sxs-lookup"><span data-stu-id="fb018-190">Providing input on Discovery phase into network design</span></span></li>
<li><span data-ttu-id="fb018-191">Участвует в планировании в рамках рабочего совещаниях по выработке концепции</span><span class="sxs-lookup"><span data-stu-id="fb018-191">Participating in planning during Envisioning workshop</span></span></li>
<li><span data-ttu-id="fb018-192">Координирует работу команды по сетям во время реализации проекта</span><span class="sxs-lookup"><span data-stu-id="fb018-192">Coordinates work of networking team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="fb018-193">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-193">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-194"><strong>Руководитель по безопасности</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-194"><strong>Security Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="fb018-195">На стадии исследования предоставляет входные данные о структуре и процессах безопасности</span><span class="sxs-lookup"><span data-stu-id="fb018-195">Providing input on Discovery phase into security design and processes</span></span></li>
<li><span data-ttu-id="fb018-196">Участвует в планировании в рамках рабочего совещаниях по выработке концепции</span><span class="sxs-lookup"><span data-stu-id="fb018-196">Participating in planning during Envisioning workshop</span></span></li>
<li><span data-ttu-id="fb018-197">Координирует работу команды по безопасности во время реализации проекта</span><span class="sxs-lookup"><span data-stu-id="fb018-197">Coordinates work of security team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="fb018-198">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-198">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-199"><strong>Руководитель по телефонии</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-199"><strong>Telephony Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="fb018-200">На стадии исследования предоставляет входные данные о структуре телефонии</span><span class="sxs-lookup"><span data-stu-id="fb018-200">Providing input on Discovery phase into telephony design</span></span></li>
<li><span data-ttu-id="fb018-201">Участвует в планировании в рамках рабочего совещаниях по выработке концепции</span><span class="sxs-lookup"><span data-stu-id="fb018-201">Participating in planning during envisioning workshop</span></span></li>
<li><span data-ttu-id="fb018-202">Координирует работу команды по телефонии во время реализации проекта</span><span class="sxs-lookup"><span data-stu-id="fb018-202">Coordinates work of telephony team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="fb018-203">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-203">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-204"><strong>Руководитель по настольным системам</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-204"><strong>Desktop Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="fb018-205">На стадии исследования предоставляет входные данные о клиентах и процессе обновления</span><span class="sxs-lookup"><span data-stu-id="fb018-205">Providing input on Discovery phase into clients and update process</span></span></li>
<li><span data-ttu-id="fb018-206">Участвует в планировании в рамках рабочего совещаниях по выработке концепции</span><span class="sxs-lookup"><span data-stu-id="fb018-206">Participating in planning during envisioning workshop</span></span></li>
<li><span data-ttu-id="fb018-207">Координирует работу команды по настольным системам во время реализации проекта</span><span class="sxs-lookup"><span data-stu-id="fb018-207">Coordinates work of desktop team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="fb018-208">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-208">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-209"><strong>Руководитель службы технической поддержки</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-209"><strong>Support/Help Desk Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="fb018-210">На стадии исследования предоставляет входные данные о принципах и модели поддержки</span><span class="sxs-lookup"><span data-stu-id="fb018-210">Providing input on Discovery phase into operational and support model</span></span></li>
<li><span data-ttu-id="fb018-211">Участвует в планировании в рамках рабочего совещаниях по выработке концепции</span><span class="sxs-lookup"><span data-stu-id="fb018-211">Participating in planning during envisioning workshop</span></span></li>
<li><span data-ttu-id="fb018-212">Участвует в планировании модели поддержки</span><span class="sxs-lookup"><span data-stu-id="fb018-212">Participating into support model planning</span></span></li>
<li><span data-ttu-id="fb018-213">Координирует работу команд/ресурсов поддержки во время реализации проекта</span><span class="sxs-lookup"><span data-stu-id="fb018-213">Coordinates work of support teams/resources during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="fb018-214">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-214">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-215"><strong>Представители подразделения</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-215"><strong>Business Unit Representatives</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="fb018-216">Участвуют в составлении руководств и материалов по освоению для конечных пользователей</span><span class="sxs-lookup"><span data-stu-id="fb018-216">Contribute in End User based adoption guides and materials</span></span></li>
<li><span data-ttu-id="fb018-217">Участвуют в определении и рассмотрении вариантов бизнес-использования</span><span class="sxs-lookup"><span data-stu-id="fb018-217">Contribute to and review Business Use Cases</span></span></li></ul></td>
<td align="left"><span data-ttu-id="fb018-218">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-218">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-219"><strong>Руководитель по развертыванию</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-219"><strong>Deployment Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="fb018-220">Следит за соблюдением предварительных требований для развертывания</span><span class="sxs-lookup"><span data-stu-id="fb018-220">Ensure that deployment prerequisites are met</span></span></li>
<li><span data-ttu-id="fb018-221">Взаимодействует с ресурсами клиентов для проведения мероприятий по подготовке и развертыванию</span><span class="sxs-lookup"><span data-stu-id="fb018-221">Engage customer resources to engage on prepare and deploy stage activities</span></span></li>
<li><span data-ttu-id="fb018-222">Участвует в собраниях для определения состояния подготовки и развертывания</span><span class="sxs-lookup"><span data-stu-id="fb018-222">Participate in meetings to review prepare and deploy status</span></span></li></ul></td>
<td align="left"><span data-ttu-id="fb018-223">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-223">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-224"><strong>ИТ-администраторы</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-224"><strong>IT Admins</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="fb018-225">ИТ-специалисты, помогающие спланировать и провести тесты</span><span class="sxs-lookup"><span data-stu-id="fb018-225">IT Pros responsible for assistance with test planning and execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="fb018-226">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-226">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-227"><strong>Владелец службы</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-227"><strong>Service Owner</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="fb018-228">Полностью отвечает за работу службы Аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="fb018-228">Is responsible for the operation of the Audio Conferencing service all up</span></span></li>
<li><span data-ttu-id="fb018-229">Владеет службой Аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="fb018-229">Owner of Audio Conferencing service</span></span></li></ul></td>
<td align="left"><span data-ttu-id="fb018-230">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-230">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-231"><strong>Лидер по качеству</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-231"><strong>Quality Champion</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="fb018-232">Следит за обеспечением качества, надежности и сбора отзывов пользователей</span><span class="sxs-lookup"><span data-stu-id="fb018-232">Drives quality, reliability and user feedback</span></span></li>
<li><span data-ttu-id="fb018-233">Определяет тенденции в отношении качества и вносит исправления вместе с соответствующими командами</span><span class="sxs-lookup"><span data-stu-id="fb018-233">Identifies the quality trends and drive remediation with the respective teams</span></span></li>
<li><span data-ttu-id="fb018-234">Направляет отчеты в управляющий комитет для дальнейшей передачи их руководству</span><span class="sxs-lookup"><span data-stu-id="fb018-234">Reports through the steering committee back to leadership</span></span></li>
<li><span data-ttu-id="fb018-235">Отчитывается о качестве, надежности и структуре поведения пользователей с помощью оценки звонков и индекса потребительской лояльности</span><span class="sxs-lookup"><span data-stu-id="fb018-235">Reports on quality, reliability, and user sentiment through Rate My Call and Net Promoter Score</span></span></li></ul></td>
<td align="left"><span data-ttu-id="fb018-236">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-236">TBA</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fb018-237">_Табл. 2. Шаблон спектра заинтересованных лиц_</span><span class="sxs-lookup"><span data-stu-id="fb018-237">_Table 2 Stakeholder matrix template example_</span></span>


> [!NOTE]
> <span data-ttu-id="fb018-238">Предыдущий пример таблицы и таблицы, приведенные ниже, служат в качестве шаблона.</span><span class="sxs-lookup"><span data-stu-id="fb018-238">The example table above and subsequent tables throughout this document serve as a template.</span></span> <span data-ttu-id="fb018-239">Вы увидите сообщение "Подлежит добавлению" на месте информации, которую вам нужно указать в рамках процесса планирования.</span><span class="sxs-lookup"><span data-stu-id="fb018-239">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>



<a name="define-objectives-and-key-results-key-success-indicators-and-risks"></a><span data-ttu-id="fb018-240">Определение целей, ключевых результатов, ключевых показателей успешности и рисков</span><span class="sxs-lookup"><span data-stu-id="fb018-240">Define objectives and key results, key success indicators, and risks</span></span>
--------------------------------------------------------------------

<span data-ttu-id="fb018-241">Собрав заинтересованных лиц по проекту, можно преобразовать варианты бизнес-использования, организационную среду и сроки по проекту в цели и ключевые результаты, а также определить меры успешности проекта в виде списка ключевых показателей успешности.</span><span class="sxs-lookup"><span data-stu-id="fb018-241">With the project stakeholders assembled, business use cases, organizational scope and project timelines can be translated into objectives and key results (OKRs) and the measures of project success can be defined into a list of key success indicators (KSIs).</span></span>

<span data-ttu-id="fb018-242">Полноценное участие заинтересованных лиц в определении целей и ключевых результатов, а также ключевых показателей успешности вызовет у них чувство причастности и обеспечит соответствие бизнес-требованиям организации.</span><span class="sxs-lookup"><span data-stu-id="fb018-242">Full participation from project stakeholders when defining the OKRs and KSIs will ensure sense of ownership and they are aligned to organizational business requirements.</span></span>

<span data-ttu-id="fb018-243">Цели и ключевые результаты будут содержать список целей, установленных в начале проекта, с измеримыми ключевыми результатами, определяемыми ежеквартально.</span><span class="sxs-lookup"><span data-stu-id="fb018-243">OKRs will contain the list of objectives set in the beginning of the project, with measurable key results defined in a quarterly basis.</span></span> <span data-ttu-id="fb018-244">Рассмотрение ключевых результатов проводится на ежемесячной основе, чтобы отслеживать ход всего проекта, а с учетом полученных данных в квартальные планы могут вноситься соответствующие коррективы.</span><span class="sxs-lookup"><span data-stu-id="fb018-244">The key results are reviewed monthly to track status of the overall project, and based on progress, adjustment to the quarterly plans can be made as needed.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><p><span data-ttu-id="fb018-245"><strong>Концепция</strong>: повышение производительности за счет максимальной отдачи от инвестиций в Office 365</span><span class="sxs-lookup"><span data-stu-id="fb018-245"><strong>Vision</strong>: Increase productivity by maximizing Office 365 investments</span></span></p>
</th>
<th align="left"></th>
<th align="left"></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-246"><strong>Цели</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-246"><strong>Objectives</strong></span></span></td>
<td align="left"><span data-ttu-id="fb018-247"><strong>Ключевые результаты</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-247"><strong>Key Results</strong></span></span></td>
<td align="left"><span data-ttu-id="fb018-248"><strong>Меры</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-248"><strong>To Do</strong></span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-249">Развертывание Аудиоконференций в Teams к концу 2018 финансового года</span><span class="sxs-lookup"><span data-stu-id="fb018-249">Deploy Audio Conferencing in Teams by end of fiscal year 2018</span></span></td>
<td align="left"><span data-ttu-id="fb018-250">1 квартал 2018 финансового года: глобальное развертывание Аудиоконференций в Teams</span><span class="sxs-lookup"><span data-stu-id="fb018-250">FY18Q1: Deploy Audio Conferencing in Teams globally</span></span></td>
<td align="left"><p><span data-ttu-id="fb018-251">Выработка концепции</span><span class="sxs-lookup"><span data-stu-id="fb018-251">Envision</span></span></p>
<ul><li><span data-ttu-id="fb018-252">Создание плана по достижению успеха</span><span class="sxs-lookup"><span data-stu-id="fb018-252">Create success plan</span></span></li>
<li><span data-ttu-id="fb018-253">Создание подробного плана по технической реализации</span><span class="sxs-lookup"><span data-stu-id="fb018-253">Create detailed technical implementation plan</span></span></li></ul>
<p><span data-ttu-id="fb018-254">Адаптация</span><span class="sxs-lookup"><span data-stu-id="fb018-254">Onboard</span></span></p>
<ul><li><span data-ttu-id="fb018-255">Выполнение плана по достижению успеха</span><span class="sxs-lookup"><span data-stu-id="fb018-255">Execute success plan</span></span></li>
<li><span data-ttu-id="fb018-256">Выполнение плана по технической реализации</span><span class="sxs-lookup"><span data-stu-id="fb018-256">Execute technical implementation plan</span></span></li></ul></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-257">Повсеместное прекращение использования устаревшей службы конференц-связи по ТСОП к середине 2018 финансового года</span><span class="sxs-lookup"><span data-stu-id="fb018-257">Decommission legacy PSTN Conferencing service globally by mid of fiscal year 2018</span></span></td>
<td align="left"><span data-ttu-id="fb018-258">2 квартал 2018 финансового года: повсеместное прекращение использования устаревшей службы конференц-связи по ТСОП</span><span class="sxs-lookup"><span data-stu-id="fb018-258">FY18Q2: Decommission legacy PSTN Conferencing service globally</span></span></td>
<td align="left"><p><span data-ttu-id="fb018-259">Извлечение выгоды</span><span class="sxs-lookup"><span data-stu-id="fb018-259">Drive Value</span></span></p>
<ul><li><span data-ttu-id="fb018-260">Повышение вовлеченности пользователей и стимулирование освоения</span><span class="sxs-lookup"><span data-stu-id="fb018-260">Boost user engagement and drive adoption</span></span></li>
<li><span data-ttu-id="fb018-261">Управление изменениями и подготовка к ним</span><span class="sxs-lookup"><span data-stu-id="fb018-261">Manage and prepare change</span></span></li>
<li><span data-ttu-id="fb018-262">Определение достигнутого успеха, распространение сведений о нем и повторение итерации</span><span class="sxs-lookup"><span data-stu-id="fb018-262">Measure, share success, and iterate</span></span></li></ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fb018-263">_Табл. 3. Пример целей и ключевых результатов_</span><span class="sxs-lookup"><span data-stu-id="fb018-263">_Table 3 Example of OKRs_</span></span>


<span data-ttu-id="fb018-264">Ключевые показатели успешности измеряют качество и успешность ключевых результатов и дополняют собой двоичный характер целей и ключевых результатов (достигнуто или нет), предоставляя сведения о положительных и (или) отрицательных результатах.</span><span class="sxs-lookup"><span data-stu-id="fb018-264">KSIs measure quality and success of the key results and complement the binary nature of OKRs (achieved or not achieved), by detailing the good and/or bad results.</span></span> <span data-ttu-id="fb018-265">При определении ключевых показателей успешности мы рекомендуем использовать "конкретные, измеримые, достижимые, актуальные и ограниченные по времени" или SMART-критерии.</span><span class="sxs-lookup"><span data-stu-id="fb018-265">When defining KSIs, we recommend leveraging the “specific, measurable, assignable, realistic, time-related” or SMART criteria.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fb018-266">Тип</span><span class="sxs-lookup"><span data-stu-id="fb018-266">Type</span></span></th>
<th align="left"><p><span data-ttu-id="fb018-267">Вопросы и критерии для &amp;</span><span class="sxs-lookup"><span data-stu-id="fb018-267">KSI questions &amp;</span></span></p>
<p><span data-ttu-id="fb018-268">ключевых показателей успешности</span><span class="sxs-lookup"><span data-stu-id="fb018-268">criteria</span></span></p></th>
<th align="left"><span data-ttu-id="fb018-269">Способ измерения</span><span class="sxs-lookup"><span data-stu-id="fb018-269">How measured</span></span></th>
<th align="left"><span data-ttu-id="fb018-270">Критерии успешности</span><span class="sxs-lookup"><span data-stu-id="fb018-270">Success criteria</span></span></th>
<th align="left"><span data-ttu-id="fb018-271">Измерение</span><span class="sxs-lookup"><span data-stu-id="fb018-271">Measured</span></span></th>
<th align="left"><span data-ttu-id="fb018-272">Ответственность</span><span class="sxs-lookup"><span data-stu-id="fb018-272">Responsible</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-273"><strong>Использование/освоение</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-273"><strong>Usage/adoption</strong></span></span></td>
<td align="left"><span data-ttu-id="fb018-274">Качество звонков не хуже, чем при использовании предыдущего решения</span><span class="sxs-lookup"><span data-stu-id="fb018-274">Call quality is equal to or better than the previous solution</span></span></td>
<td align="left"><span data-ttu-id="fb018-275">Опрос</span><span class="sxs-lookup"><span data-stu-id="fb018-275">Survey</span></span></td>
<td align="left"><span data-ttu-id="fb018-276">80 % пользователей согласны или безоговорочно согласны</span><span class="sxs-lookup"><span data-stu-id="fb018-276">80% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="fb018-277">После реализации и ежеквартально</span><span class="sxs-lookup"><span data-stu-id="fb018-277">After enablement and quarterly</span></span></td>
<td align="left"><span data-ttu-id="fb018-278">Команда по информационным технологиям</span><span class="sxs-lookup"><span data-stu-id="fb018-278">Information Technology team</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-279"><strong>Использование/освоение</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-279"><strong>Usage/adoption</strong></span></span></td>
<td align="left"><span data-ttu-id="fb018-280">Teams упрощает процесс взаимодействия</span><span class="sxs-lookup"><span data-stu-id="fb018-280">Teams made the communication process easier</span></span></td>
<td align="left"><span data-ttu-id="fb018-281">Опрос</span><span class="sxs-lookup"><span data-stu-id="fb018-281">Survey</span></span></td>
<td align="left"><span data-ttu-id="fb018-282">80 % пользователей согласны или безоговорочно согласны</span><span class="sxs-lookup"><span data-stu-id="fb018-282">80% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="fb018-283">После реализации и ежеквартально</span><span class="sxs-lookup"><span data-stu-id="fb018-283">After enablement and quarterly</span></span></td>
<td align="left"><span data-ttu-id="fb018-284">Команда по управлению изменениями</span><span class="sxs-lookup"><span data-stu-id="fb018-284">Change Management team</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-285"><strong>Использование/освоение</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-285"><strong>Usage/adoption</strong></span></span></td>
<td align="left"><span data-ttu-id="fb018-286">Работники активно используют продукт</span><span class="sxs-lookup"><span data-stu-id="fb018-286">Users actively use the solution</span></span></td>
<td align="left"><span data-ttu-id="fb018-287">Отчеты Office 365, Панель мониторинга качества звонка</span><span class="sxs-lookup"><span data-stu-id="fb018-287">Office 365 reports, Call Quality Dashboard</span></span></td>
<td align="left"><span data-ttu-id="fb018-288">80 % сотрудников активно используют продукт в повседневной работе</span><span class="sxs-lookup"><span data-stu-id="fb018-288">80% of users are active daily users</span></span></td>
<td align="left"><span data-ttu-id="fb018-289">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="fb018-289">Daily</span></span></td>
<td align="left"><span data-ttu-id="fb018-290">Команда по управлению изменениями</span><span class="sxs-lookup"><span data-stu-id="fb018-290">Change Management team</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-291"><strong>Использование/качество</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-291"><strong>Usage/quality</strong></span></span></td>
<td align="left"><span data-ttu-id="fb018-292">Процент звонков и конференций низкого качества должен быть минимальным</span><span class="sxs-lookup"><span data-stu-id="fb018-292">Percentage of poor calls/conferences should be minimal</span></span></td>
<td align="left"><span data-ttu-id="fb018-293">Панель мониторинга качества звонка</span><span class="sxs-lookup"><span data-stu-id="fb018-293">Call Quality Dashboard</span></span></td>
<td align="left"><span data-ttu-id="fb018-294">&lt; 5 % звонков низкого качества в месяц</span><span class="sxs-lookup"><span data-stu-id="fb018-294">&lt; 5% of poor calls per month</span></span></td>
<td align="left"><span data-ttu-id="fb018-295">Ежедневно</span><span class="sxs-lookup"><span data-stu-id="fb018-295">Daily</span></span></td>
<td align="left"><span data-ttu-id="fb018-296">Команда по информационным технологиям</span><span class="sxs-lookup"><span data-stu-id="fb018-296">Information Technology team</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-297"><strong>Использование/поддержка</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-297"><strong>Usage/support</strong></span></span></td>
<td align="left"><span data-ttu-id="fb018-298">Мне известно, как получить техническую поддержку</span><span class="sxs-lookup"><span data-stu-id="fb018-298">I know how to get technical support</span></span></td>
<td align="left"><span data-ttu-id="fb018-299">Опрос</span><span class="sxs-lookup"><span data-stu-id="fb018-299">Survey</span></span></td>
<td align="left"><span data-ttu-id="fb018-300">90% пользователей согласны или безоговорочно согласны</span><span class="sxs-lookup"><span data-stu-id="fb018-300">90% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="fb018-301">После реализации и ежеквартально</span><span class="sxs-lookup"><span data-stu-id="fb018-301">After enablement and quarterly</span></span></td>
<td align="left"><span data-ttu-id="fb018-302">Команда по управлению изменениями</span><span class="sxs-lookup"><span data-stu-id="fb018-302">Change Management team</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-303"><strong>Использование/поддержка</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-303"><strong>Usage/support</strong></span></span></td>
<td align="left"><span data-ttu-id="fb018-304">Меня удовлетворяет качество технической поддержки</span><span class="sxs-lookup"><span data-stu-id="fb018-304">I am satisfied with the quality of technical support</span></span></td>
<td align="left"><span data-ttu-id="fb018-305">Опрос</span><span class="sxs-lookup"><span data-stu-id="fb018-305">Survey</span></span></td>
<td align="left"><span data-ttu-id="fb018-306">80 % пользователей согласны или безоговорочно согласны</span><span class="sxs-lookup"><span data-stu-id="fb018-306">80% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="fb018-307">После каждого инцидента</span><span class="sxs-lookup"><span data-stu-id="fb018-307">After each incident</span></span></td>
<td align="left"><span data-ttu-id="fb018-308">Команда по информационным технологиям</span><span class="sxs-lookup"><span data-stu-id="fb018-308">Information Technology team</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-309"><strong>Финансы</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-309"><strong>Financial</strong></span></span></td>
<td align="left"><span data-ttu-id="fb018-310">Сокращение минут унаследованной конференц-связи</span><span class="sxs-lookup"><span data-stu-id="fb018-310">Reduction of legacy conferencing minutes</span></span></td>
<td align="left"><span data-ttu-id="fb018-311">Финансовая система</span><span class="sxs-lookup"><span data-stu-id="fb018-311">Financial system</span></span></td>
<td align="left"><span data-ttu-id="fb018-312">Обеспечение установленной рентабельности инвестиций</span><span class="sxs-lookup"><span data-stu-id="fb018-312">Meet defined ROI</span></span></td>
<td align="left"><span data-ttu-id="fb018-313">В зависимости от рентабельности инвестиций</span><span class="sxs-lookup"><span data-stu-id="fb018-313">Based on ROI</span></span></td>
<td align="left"><span data-ttu-id="fb018-314">Команда по управлению изменениями</span><span class="sxs-lookup"><span data-stu-id="fb018-314">Change Management team</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fb018-315">_Табл. 4. Пример ключевых показателей успешности_</span><span class="sxs-lookup"><span data-stu-id="fb018-315">_Table 4 Example of KSIs_</span></span>


<span data-ttu-id="fb018-316">В этом упражнении вам нужно определить бизнес-риски и разработать для каждого из них план по устранению рисков.</span><span class="sxs-lookup"><span data-stu-id="fb018-316">You need to identify business risks as part of this exercise and define a mitigation plan for each identified risk.</span></span> <span data-ttu-id="fb018-317">Эту информацию можно включить в план по рискам.</span><span class="sxs-lookup"><span data-stu-id="fb018-317">This information can be captured into a risk plan.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fb018-318">Риск</span><span class="sxs-lookup"><span data-stu-id="fb018-318">Risk</span></span></th>
<th align="left"><span data-ttu-id="fb018-319">Вероятность</span><span class="sxs-lookup"><span data-stu-id="fb018-319">Likelihood</span></span></th>
<th align="left"><span data-ttu-id="fb018-320">Влияние</span><span class="sxs-lookup"><span data-stu-id="fb018-320">Impact</span></span></th>
<th align="left"><span data-ttu-id="fb018-321">Общий уровень</span><span class="sxs-lookup"><span data-stu-id="fb018-321">Overall</span></span></th>
<th align="left"><span data-ttu-id="fb018-322">План по устранению рисков</span><span class="sxs-lookup"><span data-stu-id="fb018-322">Mitigation plan</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-323">Предстоящее слияние приведет к появлению до 1000 новых сотрудников</span><span class="sxs-lookup"><span data-stu-id="fb018-323">Upcoming merger will add up to 1,000 people</span></span></td>
<td align="left"><span data-ttu-id="fb018-324">Высокий уровень</span><span class="sxs-lookup"><span data-stu-id="fb018-324">High</span></span></td>
<td align="left"><span data-ttu-id="fb018-325">Высокий уровень</span><span class="sxs-lookup"><span data-stu-id="fb018-325">High</span></span></td>
<td align="left"><span data-ttu-id="fb018-326">Высокий уровень</span><span class="sxs-lookup"><span data-stu-id="fb018-326">High</span></span></td>
<td align="left"><p><span data-ttu-id="fb018-327">Для объединившихся организаций отделите задачи и ключевые результаты вместе с соответствующими процессами (выработка концепции, адаптация и извлечение выгоды).</span><span class="sxs-lookup"><span data-stu-id="fb018-327">For merged companies, separate OKR with own process (Envision, Onboard, Drive Value)</span></span></p>
<p><span data-ttu-id="fb018-328">Не включайте их в существующие задачи и ключевые результаты.</span><span class="sxs-lookup"><span data-stu-id="fb018-328">Do not include them in existing OKRs</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-329">Перенос телефонных номеров приведет к задержке проекта</span><span class="sxs-lookup"><span data-stu-id="fb018-329">Telephone number porting will delay project completion</span></span></td>
<td align="left"><span data-ttu-id="fb018-330">Высокий уровень</span><span class="sxs-lookup"><span data-stu-id="fb018-330">High</span></span></td>
<td align="left"><span data-ttu-id="fb018-331">Высокий уровень</span><span class="sxs-lookup"><span data-stu-id="fb018-331">High</span></span></td>
<td align="left"><span data-ttu-id="fb018-332">Высокий уровень</span><span class="sxs-lookup"><span data-stu-id="fb018-332">High</span></span></td>
<td align="left"><p><span data-ttu-id="fb018-333">Заранее подготовьте все данные, которые могут понадобиться для переноса телефонных номеров (например, запись из отдела обслуживания клиентов, сведения о выставлении счетов, Доверенность)</span><span class="sxs-lookup"><span data-stu-id="fb018-333">Prepare all the required information to support telephone number porting ahead of time (i.e.: customer service record, billing details, Letter of Authorization)</span></span></p>
<p><span data-ttu-id="fb018-334">Скорректируйте сроки проекта, чтобы заложить время на перенос телефонных номеров</span><span class="sxs-lookup"><span data-stu-id="fb018-334">Adjust project timeline to accommodate turnaround time of telephone number porting execution</span></span></p>
<p><span data-ttu-id="fb018-335">Сообщите внешним участникам об использовании новых номеров для конференц-связи с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="fb018-335">Communicate the use of new dial-in conferencing numbers to external participants</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-336">Запланированная реконструкция сети</span><span class="sxs-lookup"><span data-stu-id="fb018-336">Planned network redesign</span></span></td>
<td align="left"><span data-ttu-id="fb018-337">Высокий уровень</span><span class="sxs-lookup"><span data-stu-id="fb018-337">High</span></span></td>
<td align="left"><span data-ttu-id="fb018-338">Средний уровень</span><span class="sxs-lookup"><span data-stu-id="fb018-338">Medium</span></span></td>
<td align="left"><span data-ttu-id="fb018-339">Средний уровень</span><span class="sxs-lookup"><span data-stu-id="fb018-339">Medium</span></span></td>
<td align="left"><span data-ttu-id="fb018-340">Перед внедрением современной платформы для взаимодействия и совместной работы Teams проведите оценку готовности сети для сайтов, на которые распространяется этот проект</span><span class="sxs-lookup"><span data-stu-id="fb018-340">Before implementing Teams as modern communications and collaboration platform, run network readiness assessment for sites in scope of the project</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fb018-341">_Табл. 5. Пример плана по рискам_</span><span class="sxs-lookup"><span data-stu-id="fb018-341">_Table 5 Risk plan example_</span></span>


<a name="assess-environment-and-evaluate-adoption-readiness"></a><span data-ttu-id="fb018-342">Оценка среды и готовности к освоению</span><span class="sxs-lookup"><span data-stu-id="fb018-342">Assess environment and evaluate adoption readiness</span></span>
--------------------------------------------------

<span data-ttu-id="fb018-343">Чтобы выполнить поставленные задачи и обеспечить ключевые результаты, вам может потребоваться определить высокоуровневую архитектуру решения.</span><span class="sxs-lookup"><span data-stu-id="fb018-343">To achieve the intended OKRs, you may have to define the high-level architecture of the solution.</span></span> <span data-ttu-id="fb018-344">Для оценки всех аспектов, связанных с телефонной и ИТ-инфраструктурой, сетями и рабочими процессами, нужно провести исследование среды.</span><span class="sxs-lookup"><span data-stu-id="fb018-344">It takes environmental discovery to evaluate all aspects relating to IT and telephony infrastructure, networking, and operations.</span></span>

<span data-ttu-id="fb018-345">В это исследование включаются все факторы, связанные с вычислительной средой конечных пользователей, такие как оценка готовности персональных компьютеров и мобильных устройств для поддержки вариантов бизнес-использования Аудиоконференций, от требований к оборудованию до требований к программному обеспечению.</span><span class="sxs-lookup"><span data-stu-id="fb018-345">All matters related to end-user computing, such as readiness assessment of the personal computers and mobile devices to support Audio Conferencing business use cases, from hardware requirements to software requirements, will be included as part of the environmental discovery.</span></span>

<span data-ttu-id="fb018-346">Кроме того, исследование среды позволяет определить, имеется ли потребность в [переносе телефонных номеров в корпорацию Майкрософт](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).</span><span class="sxs-lookup"><span data-stu-id="fb018-346">Environmental discovery can also uncover if there are requirements to [transfer phone numbers to Microsoft](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).</span></span> <span data-ttu-id="fb018-347">Это поможет вашей организации соответствующим образом скорректировать план проекта и подготовить сведения, необходимые для переноса номеров.</span><span class="sxs-lookup"><span data-stu-id="fb018-347">This will help your organization to adjust the project plan accordingly and prepare the necessary information required for number porting.</span></span> <span data-ttu-id="fb018-348">Вы можете провести исследование среды с помощью этой [анкеты](https://go.microsoft.com/fwlink/?linkid=858995).</span><span class="sxs-lookup"><span data-stu-id="fb018-348">You can perform environmental discovery by leveraging the following [questionnaire](https://go.microsoft.com/fwlink/?linkid=858995).</span></span>

<span data-ttu-id="fb018-349">Исследование среды должно включать в себя оценку готовности среды, позволяющую убедиться, что сеть поддерживает внедрение службы Аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-349">Environmental discovery must include network readiness assessment to ensure the network is ready to support the implementation of the Audio Conferencing service.</span></span>

<span data-ttu-id="fb018-350">Готовность сети можно определить с помощью информации, собранной во время исследования среды (например, сведений о возможности подключения к Интернету и топологии глобальной сети, связях сайтов, доступной пропускной способности, а также аналитических данных о пользователях, на основе которых можно определить ожидаемое использование каждой рабочей нагрузки), в [средстве планировщика сети My Advisor Network Planner](https://go.microsoft.com/fwlink/?linkid=858999).</span><span class="sxs-lookup"><span data-stu-id="fb018-350">Network readiness to support the Audio Conferencing service can be determined by leveraging the information captured through the environmental discovery (such as details of internet connectivity and WAN topology, site links, available bandwidth, and persona analysis data (that can be translated into an expected usage of each workload) into the [My Advisor Network Planner tool](https://go.microsoft.com/fwlink/?linkid=858999).</span></span> <span data-ttu-id="fb018-351">Для дополнительной проверки сети можно смоделировать трафик мультимедиа реального времени с помощью решений, предоставляемых [корпорацией Майкрософт ](https://go.microsoft.com/fwlink/?linkid=859002) или [партнерами по средству для оценки готовности сети](https://go.microsoft.com/fwlink/?linkid=859003).</span><span class="sxs-lookup"><span data-stu-id="fb018-351">To further confirm network readiness, real-time media traffic simulation can be performed using the solutions provided by [Microsoft](https://go.microsoft.com/fwlink/?linkid=859002) or by [Network Readiness Assessment tools partners](https://go.microsoft.com/fwlink/?linkid=859003).</span></span>

<span data-ttu-id="fb018-352">Результаты оценки дадут более четкое представление об оптимизациях или исправлениях в сети, требуемых для успешного внедрения Аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-352">The results of the Network Readiness Assessment will paint a clearer picture of the required network optimization or remediation required for the success of Audio Conferencing implementation.</span></span>

<span data-ttu-id="fb018-353">Готовность к освоению можно оценить посредством анализа пользователей, позволяющего получить список сотрудников организации, на которых можно ориентироваться при внедрении службы Аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-353">Adoption readiness can be evaluated by executing persona analysis to come up with a list of personas in the organization who can be targeted for the implementation of Audio Conferencing service.</span></span> <span data-ttu-id="fb018-354">Анализ пользователей включает в себя определение дополнительных обычных или периферийных устройств, необходимых для обеспечения установленных бизнес-результатов.</span><span class="sxs-lookup"><span data-stu-id="fb018-354">The persona analysis includes the identification of additional peripherals or devices required to realize the intended business outcomes.</span></span>

<span data-ttu-id="fb018-355">Для анализа пользователей вы можете провести рабочее совещание с имеющими отношение к проекту заинтересованными лицами, используя [соотнесение пользователей](https://go.microsoft.com/fwlink/?linkid=859005) и [матрицу черт пользователей](https://go.microsoft.com/fwlink/?linkid=859006).</span><span class="sxs-lookup"><span data-stu-id="fb018-355">To perform persona analysis, you can conduct a workshop by involving relevant project stakeholders, leveraging the [Persona Alignment](https://go.microsoft.com/fwlink/?linkid=859005) workshop deck and [Persona Feature Matrix](https://go.microsoft.com/fwlink/?linkid=859006).</span></span> <span data-ttu-id="fb018-356">Результаты этого совещания можно внести в отчет с помощью шаблона [отчета по анализу пользователей](https://go.microsoft.com/fwlink/?linkid=859007).</span><span class="sxs-lookup"><span data-stu-id="fb018-356">The result of persona analysis workshop can be summarized into a report using the [Persona Analysis Report](https://go.microsoft.com/fwlink/?linkid=859007) template.</span></span>


> [!NOTE]
> <span data-ttu-id="fb018-357">Хотя примеры для анкеты по исследованию и анализа пользователей изначально составлялись для Skype для бизнеса Online, большинство этих материалов актуально и для Teams.</span><span class="sxs-lookup"><span data-stu-id="fb018-357">While the Discovery Questionnaire and Persona Analysis examples were initially written for Skype for Business Online, a majority of the content is relevant to Teams.</span></span> <span data-ttu-id="fb018-358">Вы можете свободно удалять и добавлять элементы, который не соотносятся с вашими целями проекта.</span><span class="sxs-lookup"><span data-stu-id="fb018-358">Feel free to modify and remove items that are not relevant to the project goals.</span></span>


<span data-ttu-id="fb018-359">В рамках оценки среды и готовности к освоению вы можете выявить технические риски и составить для каждого из них план по устранению рисков.</span><span class="sxs-lookup"><span data-stu-id="fb018-359">You can identify technical risks as part of an environmental assessment and adoption readiness evaluation and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="fb018-360">Эту информацию следует включить в план по рискам.</span><span class="sxs-lookup"><span data-stu-id="fb018-360">This information should be incorporated as part of the risk plan.</span></span>

<a name="map-operational-roles"></a><span data-ttu-id="fb018-361">Назначение ролей</span><span class="sxs-lookup"><span data-stu-id="fb018-361">Map operational roles</span></span>
---------------------

<span data-ttu-id="fb018-362">Планирование работы и определение команд, использующих службу Аудиоконференций, является важной задачей, так как работа должна начаться сразу после активации первых пилотных пользователей.</span><span class="sxs-lookup"><span data-stu-id="fb018-362">Planning for operations and identifying the teams that will operate the Audio Conferencing service is an important step, as operations must start when the first pilot users are enabled.</span></span> <span data-ttu-id="fb018-363">Каждая из определенных команд должна рассмотреть и согласовать задачи и обязанности, а также начать подготовку к использованию службы Аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-363">Each identified team must review and agree on the tasks and responsibilities identified and start the preparation to operate the Audio Conferencing service.</span></span> <span data-ttu-id="fb018-364">Эта подготовка может включать в себя обучение, подбор дополнительных кадров либо проверку готовности внешних поставщиков к предоставлению службы.</span><span class="sxs-lookup"><span data-stu-id="fb018-364">The preparation might include training and readiness, additional staffing, or ensuring external providers are set up to deliver the service.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fb018-365">Роль</span><span class="sxs-lookup"><span data-stu-id="fb018-365">Operational Role</span></span></th>
<th align="left"><span data-ttu-id="fb018-366">Описание</span><span class="sxs-lookup"><span data-stu-id="fb018-366">Description</span></span></th>
<th align="left"><span data-ttu-id="fb018-367">Команда</span><span class="sxs-lookup"><span data-stu-id="fb018-367">Team</span></span></th>
<th align="left"><span data-ttu-id="fb018-368">Контактные данные</span><span class="sxs-lookup"><span data-stu-id="fb018-368">Contact Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-369">Владелец службы</span><span class="sxs-lookup"><span data-stu-id="fb018-369">Service Owner</span></span></td>
<td align="left"><span data-ttu-id="fb018-370">Владелец службы, взаимодействие с подразделениями , стратегия</span><span class="sxs-lookup"><span data-stu-id="fb018-370">Service owner, interface to business divisions, strategy</span></span></td>
<td align="left"><span data-ttu-id="fb018-371">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-371">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-372">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-372">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-373">Работа с Аудиоконференциями</span><span class="sxs-lookup"><span data-stu-id="fb018-373">Audio Conferencing Operations</span></span></td>
<td align="left"><span data-ttu-id="fb018-374">Повседневная работа, перемещение, добавление и изменение учетных записей пользователей и устройств, мониторинг</span><span class="sxs-lookup"><span data-stu-id="fb018-374">Daily operations, user and device account move/add/change, monitoring</span></span></td>
<td align="left"><span data-ttu-id="fb018-375">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-375">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-376">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-376">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-377">Администратор клиента</span><span class="sxs-lookup"><span data-stu-id="fb018-377">Tenant Admin</span></span></td>
<td align="left"><span data-ttu-id="fb018-378">Изменение параметров на уровне клиента, включение новых функций</span><span class="sxs-lookup"><span data-stu-id="fb018-378">Change tenant-wide settings, enable new features</span></span></td>
<td align="left"><span data-ttu-id="fb018-379">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-379">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-380">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-380">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-381">Служба технической поддержки</span><span class="sxs-lookup"><span data-stu-id="fb018-381">Help Desk</span></span></td>
<td align="left"><span data-ttu-id="fb018-382">Взаимодействие с пользователями для обеспечения поддержки</span><span class="sxs-lookup"><span data-stu-id="fb018-382">Interface for end-users to get support</span></span></td>
<td align="left"><span data-ttu-id="fb018-383">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-383">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-384">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-384">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-385">Работа с сетями</span><span class="sxs-lookup"><span data-stu-id="fb018-385">Network Operations</span></span></td>
<td align="left"><span data-ttu-id="fb018-386">Обеспечение функционирования локальной сети, глобальной сети, Wi-Fi и доступа в Интернет</span><span class="sxs-lookup"><span data-stu-id="fb018-386">Runs LAN, WAN, Wi-Fi, and Internet Access</span></span></td>
<td align="left"><span data-ttu-id="fb018-387">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-387">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-388">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-388">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-389">Команда по клиентам &amp;и конечным точкам</span><span class="sxs-lookup"><span data-stu-id="fb018-389">Client &amp; Endpoints Team</span></span></td>
<td align="left"><span data-ttu-id="fb018-390">Управление развертываниями на настольных системах</span><span class="sxs-lookup"><span data-stu-id="fb018-390">Manage desktop deployments</span></span></td>
<td align="left"><span data-ttu-id="fb018-391">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-391">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-392">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-392">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-393">Работа с удостоверениями</span><span class="sxs-lookup"><span data-stu-id="fb018-393">Identity Operations</span></span></td>
<td align="left"><span data-ttu-id="fb018-394">Управление инфраструктурой удостоверений (AD, ADFS, Azure AD)</span><span class="sxs-lookup"><span data-stu-id="fb018-394">Manage identity infrastructure (AD, ADFS, Azure AD)</span></span></td>
<td align="left"><span data-ttu-id="fb018-395">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-395">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-396">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-396">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-397">Управление изменениями и освоением</span><span class="sxs-lookup"><span data-stu-id="fb018-397">Adoption/change management</span></span></td>
<td align="left"><span data-ttu-id="fb018-398">Управление информированием, обучением и освоением для решения</span><span class="sxs-lookup"><span data-stu-id="fb018-398">Manage awareness, training and adoption for the solution</span></span></td>
<td align="left"><span data-ttu-id="fb018-399">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-399">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-400">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-400">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-401">Работа с Exchange</span><span class="sxs-lookup"><span data-stu-id="fb018-401">Exchange Operations</span></span></td>
<td align="left"><span data-ttu-id="fb018-402">Управление средой Exchange</span><span class="sxs-lookup"><span data-stu-id="fb018-402">Manages the Exchange environment</span></span></td>
<td align="left"><span data-ttu-id="fb018-403">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-403">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-404">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-404">TBA</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fb018-405">_Табл. 6. Пример назначения ролей_</span><span class="sxs-lookup"><span data-stu-id="fb018-405">_Table 6 Example of operational roles mapping_</span></span>


<span data-ttu-id="fb018-406">Чтобы обеспечить более детальное назначение ролей, включая связанные с ними задачи, вы можете использовать [книгу назначения ролей](https://www.skypeoperationsframework.com/Downloads?SelectedIDs=4_4_0_16). Она позволяет собрать сведения, дающие более четкое представление о ролях и обязанностях, которые требуются для поддержки службы Аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-406">To facilitate a more detailed operational roles mapping, including the tasks associated with each operational role, you can use the [Operational Role Mapping Workbook](https://www.skypeoperationsframework.com/Downloads?SelectedIDs=4_4_0_16) to capture the details that will provide the clarity around roles and responsibilities to support Audio Conferencing service.</span></span>

<a name="document-success-plan"></a><span data-ttu-id="fb018-407">Документирование плана по достижению успеха</span><span class="sxs-lookup"><span data-stu-id="fb018-407">Document success plan</span></span>
---------------------

<span data-ttu-id="fb018-408">План достижения успеха представляет собой документацию, формируемую на стадии выработки концепции и состоящую из экономического обоснования, подтверждения готовности к службе, плана освоения и плана работ.</span><span class="sxs-lookup"><span data-stu-id="fb018-408">A success plan is the documentation created in the Envision phase that consists of business case, service readiness, adoption plan, and operational plan.</span></span>

<span data-ttu-id="fb018-409">План достижения успеха предоставит проектной группе, которая может включать в себя партнера по FastTrack или развертыванию, достаточно информации для достижения поставленных организацией целей для службы Аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-409">The success plan will provide the project team, which can include FastTrack or deployment partner, with sufficient information to realize the organization’s goals with Audio Conferencing service.</span></span>

<span data-ttu-id="fb018-410">В общем случае план по достижению успеха содержит следующие основные разделы:</span><span class="sxs-lookup"><span data-stu-id="fb018-410">In general, a success plan will contain the following main sections:</span></span>

-   <span data-ttu-id="fb018-411">Экономическое обоснование</span><span class="sxs-lookup"><span data-stu-id="fb018-411">Business case</span></span>

-   <span data-ttu-id="fb018-412">Готовность к службе</span><span class="sxs-lookup"><span data-stu-id="fb018-412">Service readiness</span></span>

-   <span data-ttu-id="fb018-413">План внедрения</span><span class="sxs-lookup"><span data-stu-id="fb018-413">Adoption plan</span></span>

-   <span data-ttu-id="fb018-414">План работ</span><span class="sxs-lookup"><span data-stu-id="fb018-414">Operational plan</span></span>

### <a name="business-case"></a><span data-ttu-id="fb018-415">Экономическое обоснование</span><span class="sxs-lookup"><span data-stu-id="fb018-415">Business case</span></span>

<span data-ttu-id="fb018-416">Основную часть сведений, требуемых для экономического обоснования, составляют варианты бизнес-использования, заинтересованные лица, задачи и ключевые результаты, ключевые показатели успешности, риски и сроки по проекту.</span><span class="sxs-lookup"><span data-stu-id="fb018-416">Business use cases, stakeholders, OKRs and KSIs, risks, and project timelines typically make up the bulk of information required for a business case.</span></span> <span data-ttu-id="fb018-417">Вам следует задокументировать их в рамках плана по достижению успеха.</span><span class="sxs-lookup"><span data-stu-id="fb018-417">You need to document them as part of the success plan.</span></span>

### <a name="service-readiness"></a><span data-ttu-id="fb018-418">Готовность к службе</span><span class="sxs-lookup"><span data-stu-id="fb018-418">Service readiness</span></span>

<span data-ttu-id="fb018-419">Оценка среды предоставляет начальные сведения для определения технической готовности организации к внедрению Аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-419">Environmental assessment provides the initial information required to determine technical readiness for the organization to implement Audio Conferencing.</span></span>

<span data-ttu-id="fb018-420">Сюда же входит и план по исправлению недочетов, выявленных в рамках оценки среды.</span><span class="sxs-lookup"><span data-stu-id="fb018-420">Included here is the plan to address areas needing remediation discovered through environmental assessment.</span></span> <span data-ttu-id="fb018-421">Вам следует включить оценку готовности к службе и план исправлений в план по достижению успеха.</span><span class="sxs-lookup"><span data-stu-id="fb018-421">You need to include the service readiness assessment and remediation plan as part of the success plan.</span></span>

### <a name="adoption-plan"></a><span data-ttu-id="fb018-422">План внедрения</span><span class="sxs-lookup"><span data-stu-id="fb018-422">Adoption plan</span></span>

<span data-ttu-id="fb018-423">После оценки готовности к освоению следует предпринять более детальное планирование для проектной группы, чтобы составить комплексный набор из планов взаимодействия, плана обучения, а также мероприятий, направленных на стимулирование освоения до, во время и после запуска.</span><span class="sxs-lookup"><span data-stu-id="fb018-423">Following an adoption readiness assessment, further detailed planning must be completed for the project team to come up with a comprehensive set of communication plans, training plan, and pre-launch, at-launch, and post-launch adoption activities.</span></span>

<span data-ttu-id="fb018-424">На каждом из шагов указаны ресурсы для подобных мероприятий, такие как рекламные листовки, приветственные сообщения электронной почты и учебные материалы, а также изменения, требуемые для соблюдения требований организации.</span><span class="sxs-lookup"><span data-stu-id="fb018-424">Resources to support adoption activities such as flyers, welcome emails, and training materials are identified at this step, along with any customizations needed to meet organizational requirements.</span></span>

<span data-ttu-id="fb018-425">Шаблоны для мероприятий по освоению представлены [здесь](https://www.microsoft.com/download/details.aspx?id=54244).</span><span class="sxs-lookup"><span data-stu-id="fb018-425">The templates for adoption activities are available [here](https://www.microsoft.com/download/details.aspx?id=54244).</span></span>

### <a name="operational-plan"></a><span data-ttu-id="fb018-426">План работ</span><span class="sxs-lookup"><span data-stu-id="fb018-426">Operational plan</span></span>

<span data-ttu-id="fb018-427">Упражнение по назначению ролей позволит установить роли и обязанности, а также команды, назначенные каждой из ролей для поддержки внедрения Аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-427">Operational roles mapping exercise will establish the roles and responsibilities, and the teams assigned to each operational role to support the implementation of Audio Conferencing.</span></span>

<span data-ttu-id="fb018-428">Вам нужно выполнить его и включить план работ в состав плана по достижению успеха, чтобы обеспечить готовность к работе с решением.</span><span class="sxs-lookup"><span data-stu-id="fb018-428">You need to complete this and include the operational plan as part of the success plan to ensure operational readiness of the solution.</span></span>

<span data-ttu-id="fb018-429">Планирование для внедрения Аудиоконференций в Teams  <a name="Planning_AudioConferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="fb018-429">Planning for Audio Conferencing in Teams  <a name="Planning_AudioConferencing"> </a></span></span>
========================================

<span data-ttu-id="fb018-430">При планировании внедрения Аудиоконференций в Teams нужно заранее принять ряд решений, чтобы лучше подготовиться к внедрению решения в соответствии с бизнес-требованиями.</span><span class="sxs-lookup"><span data-stu-id="fb018-430">To plan for the implementation of Audio Conferencing in Teams, a series of decisions must be made ahead of time to better prepare your organization to implement a solution that meets business requirements.</span></span> <span data-ttu-id="fb018-431">Эти решения будут внесены в план по технической реализации.</span><span class="sxs-lookup"><span data-stu-id="fb018-431">These decisions will be documented into a technical implementation plan.</span></span>

|  |  |
|---------|---------|
|  <iframe width="350" height="200" src="https://www.youtube.com/embed/AWbuvcWcYIc" frameborder="0" allowfullscreen></iframe>    | |


## <a name="availability-of-audio-conferencing"></a><span data-ttu-id="fb018-432">Доступность Аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="fb018-432">Availability of Audio Conferencing</span></span>

<span data-ttu-id="fb018-433">Служба Аудиоконференций доступна в этих [странах и регионах](https://support.office.com/article/Countries-and-regions-that-are-supported-for-Skype-for-Business-Online-PSTN-Services-6ba72f37-d303-4795-aa8f-7e1845078ed7?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="fb018-433">Audio Conferencing is available in these [countries and regions](https://support.office.com/article/Countries-and-regions-that-are-supported-for-Skype-for-Business-Online-PSTN-Services-6ba72f37-d303-4795-aa8f-7e1845078ed7?ui=en-US&rs=en-US&ad=US).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="fb018-434">В связи с правовыми ограничениями для доступа к Аудиоконференциям в международных организациях контракт на подписки Office 365 должен заключаться в странах и регионах, где предоставляется служба Аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-434">Due to legal constraints, for Audio Conferencing to be available to multinational organizations, the contract for Office 365 subscriptions must be sourced from countries and regions covered by Audio Conferencing service.</span></span>

<span data-ttu-id="fb018-435">После подтверждения права вашей организации на получение службы Аудиоконференций составьте список расположений пользователей или офисов, где указанная служба будет внедрена, основываясь на перечне доступных стран и регионов.</span><span class="sxs-lookup"><span data-stu-id="fb018-435">After confirming your organization’s eligibility for obtaining the Audio Conferencing service, compile the list of user locations or offices where Audio Conferencing service will be implemented based on the list of available countries and regions.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="fb018-436">Точки принятия решений</span><span class="sxs-lookup"><span data-stu-id="fb018-436">Decision Points</span></span></td>
<td align="left"><p><span data-ttu-id="fb018-437">Определите, в каких расположениях пользователей или офисах будет внедрена служба Аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-437">Decide which user locations or offices will implement the Audio Conferencing service.</span></span></p></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="fb018-438">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="fb018-438">Next Steps</span></span></td>
<td align="left"><p><span data-ttu-id="fb018-439">Задокументируйте расположения пользователей или офисы, где будет использоваться служба Аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-439">Document the user locations or offices to be enabled for the Audio Conferencing service.</span></span></p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fb018-440">Офис</span><span class="sxs-lookup"><span data-stu-id="fb018-440">Office</span></span></th>
<th align="left"><span data-ttu-id="fb018-441">Расположение</span><span class="sxs-lookup"><span data-stu-id="fb018-441">Location</span></span></th>
<th align="left"><span data-ttu-id="fb018-442">Служба конференц-связи по ТСОП</span><span class="sxs-lookup"><span data-stu-id="fb018-442">PSTN Conference Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-443">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="fb018-443">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="fb018-444">Австралия</span><span class="sxs-lookup"><span data-stu-id="fb018-444">Australia</span></span></td>
<td align="left"><span data-ttu-id="fb018-445">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="fb018-445">Audio Conferencing</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-446">100 Cyberport Road</span><span class="sxs-lookup"><span data-stu-id="fb018-446">100 Cyberport Road</span></span></td>
<td align="left"><span data-ttu-id="fb018-447">Гонконг (специальный административный район)</span><span class="sxs-lookup"><span data-stu-id="fb018-447">Hong Kong SAR</span></span></td>
<td align="left"><span data-ttu-id="fb018-448">Устаревшая служба конференц-связи по ТСОП</span><span class="sxs-lookup"><span data-stu-id="fb018-448">Legacy PSTN Conferencing</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-449">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="fb018-449">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="fb018-450">Сингапур</span><span class="sxs-lookup"><span data-stu-id="fb018-450">Singapore</span></span></td>
<td align="left"><span data-ttu-id="fb018-451">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="fb018-451">Audio Conferencing</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-452">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="fb018-452">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="fb018-453">Соединенное Королевство</span><span class="sxs-lookup"><span data-stu-id="fb018-453">United Kingdom</span></span></td>
<td align="left"><span data-ttu-id="fb018-454">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="fb018-454">Audio Conferencing</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-455">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="fb018-455">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="fb018-456">Франция</span><span class="sxs-lookup"><span data-stu-id="fb018-456">France</span></span></td>
<td align="left"><span data-ttu-id="fb018-457">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="fb018-457">Audio Conferencing</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fb018-458">_Табл. 7. Пример списка расположений для использования службы Аудиоконференций_</span><span class="sxs-lookup"><span data-stu-id="fb018-458">_Table 7 Example of Audio Conferencing service site enablement list_</span></span>


## <a name="licensing-for-audio-conferencing"></a><span data-ttu-id="fb018-459">Лицензирование Аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="fb018-459">Licensing for Audio Conferencing</span></span>

<span data-ttu-id="fb018-460">[Лицензия на Аудиоконференции](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7?ui=en-US&rs=en-US&ad=US), которая раньше называлась лицензией на конференц-связь по ТСОП Skype для бизнеса, доступна в составе планов подписки Office 365 E5, а также в виде надстройки для планов Office 365 E1 или Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="fb018-460">[Audio Conferencing license](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7?ui=en-US&rs=en-US&ad=US), formerly known as Skype for Business PSTN Conferencing license, is available as part of Office 365 E5 subscription plans, or as an add-on to Office 365 E1 or Office 365 E3 subscription plans.</span></span>

> [!NOTE]
> <span data-ttu-id="fb018-p120">Конференц-связь по ТСОП или с телефонным подключением в Teams не поддерживает <sup></sup>сторонних поставщиков услуг аудиоконференций (ACP). </span><span class="sxs-lookup"><span data-stu-id="fb018-p120">PSTN or dial-in conferencing in Teams does not support 3<sup>rd</sup>-party Audio Conferencing Providers (ACPs). </span></span><br><span data-ttu-id="fb018-462">Если вы уже используете конференц-связь по ТСОП Skype для бизнеса Online, то можете сразу же воспользоваться преимуществами Аудиоконференций в Teams.</span><span class="sxs-lookup"><span data-stu-id="fb018-462">If you already use Skype for Business Online PSTN Conferencing today, you can immediately take advantage of Audio Conferencing in Teams.</span></span>

<span data-ttu-id="fb018-463">Чтобы предоставить бесплатные телефонные номера для моста конференций и обеспечить присоединение к конференции обратным звонком на международные номера, следует настроить [Кредиты на связь](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) для своей организации.</span><span class="sxs-lookup"><span data-stu-id="fb018-463">To provide toll-free conference bridge phone numbers and to support conferencing dial-out to International phone numbers, you need to setup [Communications Credits](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) for your organization.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="fb018-464">В некоторых странах предоставляются только бесплатные телефонные номера для моста конференций. В этом случае использование Кредитов на связь является обязательным требованием для поддержки телефонных подключений в таких странах.</span><span class="sxs-lookup"><span data-stu-id="fb018-464">Some countries are serviced by toll-free conference bridge phone numbers only, and in this case the use of Communications Credits is a mandatory requirement to support dial in for such countries.</span></span>

<span data-ttu-id="fb018-465">При внедрении Кредитов на связь следует прежде всего определить начальный объем приобретаемых средств.</span><span class="sxs-lookup"><span data-stu-id="fb018-465">The first consideration to make when implementing Communications Credits is to decide the initial amount of funds to be purchased.</span></span> <span data-ttu-id="fb018-466">Рекомендуемые суммы указаны в документации по [Кредитам на связь](https://support.office.com/en-us/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059).</span><span class="sxs-lookup"><span data-stu-id="fb018-466">Recommended funding amounts can be referenced from the [Communications Credits](https://support.office.com/en-us/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) documentation.</span></span>

<span data-ttu-id="fb018-467">Если ваша организация решает использовать автоматическое пополнение счета, рекомендации по пороговому значению (минимальной сумме средств) также можно найти в указанной [документации](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059).</span><span class="sxs-lookup"><span data-stu-id="fb018-467">If your organization chooses to use auto-recharge, a recommendation on the trigger (lowest amount of funds) is also included in the [Communications Credits](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) documentation.</span></span> <span data-ttu-id="fb018-468">Сумму для автоматического пополнения счета следует определить на основе фактического использования.</span><span class="sxs-lookup"><span data-stu-id="fb018-468">Auto-recharge amount needs to be determined by the actual usage.</span></span> <span data-ttu-id="fb018-469">Следует регулярно отслеживать использование Кредитов на связь и при необходимости соответствующим образом корректировать сумму пополнения.</span><span class="sxs-lookup"><span data-stu-id="fb018-469">Communications Credits usage should be monitored over time and the recharge amount needs to be adjusted as required.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="fb018-470">Точки принятия решений</span><span class="sxs-lookup"><span data-stu-id="fb018-470">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="fb018-471">Если ваша организация еще не приобрела требуемые лицензии на Аудиоконференции, определите, будут ли они приобретены путем повышения уровня существующих подписок Office 365 либо в виде надстроек Аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-471">If your organization has not already purchased the required Audio Conferencing licensing, decide whether Audio Conferencing licenses will be acquired by stepping up existing Office 365 subscriptions or by acquiring Audio Conferencing add-ons.</span></span></li>
<li><span data-ttu-id="fb018-472">Определите, нужны ли Кредиты на связь для внедрения Аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-472">Decide if Communications Credits is required for Audio Conferencing implementation.</span></span> <span data-ttu-id="fb018-473">Если нужны, определите начальный объем приобретаемых средств.</span><span class="sxs-lookup"><span data-stu-id="fb018-473">If so, decide the initial amount of funds to be purchased.</span></span> <span data-ttu-id="fb018-474">При необходимости определите пороговую сумму и сумму для автоматического пополнения счета.</span><span class="sxs-lookup"><span data-stu-id="fb018-474">Where applicable, decide the trigger amount and auto-recharge amount.</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="fb018-475">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="fb018-475">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="fb018-476">Задокументируйте пользователей, которым будет назначена лицензия Аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-476">Document the users that will be assigned Audio Conferencing license.</span></span></li>
<li><span data-ttu-id="fb018-477">Задокументируйте план Кредитов на связь (начальную сумму, пороговую сумму и сумму для автоматического пополнения счета).</span><span class="sxs-lookup"><span data-stu-id="fb018-477">Document the Communications Credits plan (initial amount, trigger amount, auto-recharge amount).</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fb018-478">Пользователь</span><span class="sxs-lookup"><span data-stu-id="fb018-478">User</span></span></th>
<th align="left"><span data-ttu-id="fb018-479">Офис</span><span class="sxs-lookup"><span data-stu-id="fb018-479">Office</span></span></th>
<th align="left"><span data-ttu-id="fb018-480">Лицензия на Office 365</span><span class="sxs-lookup"><span data-stu-id="fb018-480">Office 365 License</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-481">Adele Vance</span><span class="sxs-lookup"><span data-stu-id="fb018-481">Adele Vance</span></span></td>
<td align="left"><span data-ttu-id="fb018-482">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="fb018-482">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="fb018-483">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="fb018-483">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-484">Alex Wilber</span><span class="sxs-lookup"><span data-stu-id="fb018-484">Alex Wilber</span></span></td>
<td align="left"><span data-ttu-id="fb018-485">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="fb018-485">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="fb018-486">Office 365 E3, надстройка Аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="fb018-486">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-487">Ben Walters</span><span class="sxs-lookup"><span data-stu-id="fb018-487">Ben Walters</span></span></td>
<td align="left"><span data-ttu-id="fb018-488">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="fb018-488">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="fb018-489">Office 365 E3, надстройка Аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="fb018-489">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-490">Christie Cline</span><span class="sxs-lookup"><span data-stu-id="fb018-490">Christie Cline</span></span></td>
<td align="left"><span data-ttu-id="fb018-491">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="fb018-491">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="fb018-492">Office 365 E3, надстройка Аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="fb018-492">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-493">Debra Berger</span><span class="sxs-lookup"><span data-stu-id="fb018-493">Debra Berger</span></span></td>
<td align="left"><span data-ttu-id="fb018-494">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="fb018-494">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="fb018-495">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="fb018-495">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-496">Lee Gu</span><span class="sxs-lookup"><span data-stu-id="fb018-496">Lee Gu</span></span></td>
<td align="left"><span data-ttu-id="fb018-497">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="fb018-497">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="fb018-498">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="fb018-498">Office 365 E5</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-499">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="fb018-499">Emily Braun</span></span></td>
<td align="left"><span data-ttu-id="fb018-500">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="fb018-500">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="fb018-501">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="fb018-501">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-502">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="fb018-502">Lidia Holloway</span></span></td>
<td align="left"><span data-ttu-id="fb018-503">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="fb018-503">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="fb018-504">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="fb018-504">Office 365 E5</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-505">Pradeep Gupta</span><span class="sxs-lookup"><span data-stu-id="fb018-505">Pradeep Gupta</span></span></td>
<td align="left"><span data-ttu-id="fb018-506">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="fb018-506">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="fb018-507">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="fb018-507">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-508">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="fb018-508">Marcel Beauchamp</span></span></td>
<td align="left"><span data-ttu-id="fb018-509">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="fb018-509">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="fb018-510">Office 365 E3, надстройка Аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="fb018-510">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-511">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="fb018-511">Rachelle Cormier</span></span></td>
<td align="left"><span data-ttu-id="fb018-512">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="fb018-512">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="fb018-513">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="fb018-513">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-514">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="fb018-514">Isabell Potvin</span></span></td>
<td align="left"><span data-ttu-id="fb018-515">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="fb018-515">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="fb018-516">Office 365 E3, надстройка Аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="fb018-516">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fb018-517">_Табл. 8. Пример списка назначения лицензий для организаторов собраний Аудиоконференций_</span><span class="sxs-lookup"><span data-stu-id="fb018-517">_Table 8 Example of license assignment list for Audio Conferencing meeting organizers_</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fb018-518">Начальная сумма</span><span class="sxs-lookup"><span data-stu-id="fb018-518">Initial amount</span></span></th>
<td align="left"><span data-ttu-id="fb018-519">1000 долл. США</span><span class="sxs-lookup"><span data-stu-id="fb018-519">$ 1,000</span></span></td>
</tr>
</thead>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fb018-520">Пороговая сумма</span><span class="sxs-lookup"><span data-stu-id="fb018-520">Trigger amount</span></span></th>
<td align="left"><span data-ttu-id="fb018-521">400 долл. США</span><span class="sxs-lookup"><span data-stu-id="fb018-521">$ 400</span></span></td>
</tr>
<tr class="header">
<th align="left"><span data-ttu-id="fb018-522">Сумма для автоматического пополнения счета</span><span class="sxs-lookup"><span data-stu-id="fb018-522">Auto-recharge amount</span></span></th>
<td align="left"><span data-ttu-id="fb018-523">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-523">TBA</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fb018-524">_Табл. 9. Пример цифр для планирования Кредитов на связь_</span><span class="sxs-lookup"><span data-stu-id="fb018-524">_Table 9 Example of Communications Credits planning numbers_</span></span>


## <a name="conference-bridge-phone-numbers"></a><span data-ttu-id="fb018-525">Телефонные номера для моста конференций</span><span class="sxs-lookup"><span data-stu-id="fb018-525">Conference bridge phone numbers</span></span>

<span data-ttu-id="fb018-526">Служба Аудиоконференций в Office 365 включает в себя следующее:</span><span class="sxs-lookup"><span data-stu-id="fb018-526">The Audio Conferencing service in Office 365 includes:</span></span>

-   <span data-ttu-id="fb018-527">Несколько типов телефонных номеров для моста конференций (платные и бесплатные)</span><span class="sxs-lookup"><span data-stu-id="fb018-527">Multiple types of conference bridge phone numbers (Toll and Toll-Free)</span></span>

-   <span data-ttu-id="fb018-528">Несколько категорий телефонного номера (выделенный и общий)</span><span class="sxs-lookup"><span data-stu-id="fb018-528">Multiple categories of the phone number (dedicated and shared)</span></span>

-   <span data-ttu-id="fb018-529">Поддержка нескольких языков для моста конференций (основной и дополнительный)</span><span class="sxs-lookup"><span data-stu-id="fb018-529">Support for multiple languages for the conference bridge (primary and secondary)</span></span>

-   <span data-ttu-id="fb018-530">Телефонный номер по умолчанию для клиента.</span><span class="sxs-lookup"><span data-stu-id="fb018-530">A default phone number for the tenant.</span></span>

<span data-ttu-id="fb018-531">Полное описание имеющихся возможностей см. в статьях [Настройка конференц-связи с телефонным подключением или по ТСОП в Skype для бизнеса](https://support.office.com/article/Set-up-dial-in-or-PSTN-conferencing-for-Skype-for-Business-d01954f1-4f37-4cf5-a636-20039e5c59e9?ui=en-US&rs=en-US&ad=US) и [Телефонные номера для конференц-связи с телефонным подключением](https://support.office.com/article/Phone-numbers-for-dial-in-conferencing-95a08f84-04e5-4f72-88a8-d6472a7c89d7?ui=en-US&rs=en-US&ad=US)**.**</span><span class="sxs-lookup"><span data-stu-id="fb018-531">Full description of the included capabilities can be referenced from [Set up dial-in or PSTN conferencing for Skype for Business](https://support.office.com/article/Set-up-dial-in-or-PSTN-conferencing-for-Skype-for-Business-d01954f1-4f37-4cf5-a636-20039e5c59e9?ui=en-US&rs=en-US&ad=US) and [Phone numbers for dial-in conferencing](https://support.office.com/article/Phone-numbers-for-dial-in-conferencing-95a08f84-04e5-4f72-88a8-d6472a7c89d7?ui=en-US&rs=en-US&ad=US)**.**</span></span>

> [!NOTE]
> <span data-ttu-id="fb018-532">Выделенные телефонные номера для моста конференций учитываются в предельном количестве номеров, которое можно получить на одного клиента, в зависимости от числа применяемых лицензий, как описано в статье [Получение телефонных номеров службы Skype для бизнеса](https://support.office.com/article/Getting-Skype-for-Business-service-phone-numbers-e434aeb2-af99-40e7-981e-a474f0383734).</span><span class="sxs-lookup"><span data-stu-id="fb018-532">Dedicated conference bridge phone numbers are counted towards the limit of phone numbers that can be acquired per tenant, based on the number of applicable licenses as described in [Getting Skype for Business service phone numbers](https://support.office.com/article/Getting-Skype-for-Business-service-phone-numbers-e434aeb2-af99-40e7-981e-a474f0383734).</span></span> <span data-ttu-id="fb018-533">Бесплатные телефонные номера для моста конференций требуют использования Кредитов на связь.</span><span class="sxs-lookup"><span data-stu-id="fb018-533">Toll-free conference bridge phone numbers require Communications Credits.</span></span>

<span data-ttu-id="fb018-534">Если имеются телефонные номера для моста конференций, которые требуется перенести в службу Аудиоконференций (при условии их соответствия требованиям для конкретной страны), их можно перенести в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="fb018-534">If there are existing conference bridge phone numbers that must be transferred to the Audio Conferencing service, assuming they are meeting the country-specific requirements, then the existing conference bridge phone numbers can be transferred to Microsoft.</span></span>


> [!NOTE]
> <span data-ttu-id="fb018-535">Сложность этой процедуры во многом зависит от конкретных стран или регионов, операторов, числа схем и множества других факторов.</span><span class="sxs-lookup"><span data-stu-id="fb018-535">Complexity of transferring phone numbers to Microsoft varies greatly based on the countries or regions, carriers, the number of circuits involved, and many other contributing factors.</span></span> <span data-ttu-id="fb018-536">Чтобы спланировать перенос телефонных номеров, см. соответствующее [руководство](https://go.microsoft.com/fwlink/?linkid=859011).</span><span class="sxs-lookup"><span data-stu-id="fb018-536">To plan for phone number porting, check out the [Number Porting Guide](https://go.microsoft.com/fwlink/?linkid=859011).</span></span>

|  |  |
|---------|---------|
| <iframe width="350" height="200" src="https://www.youtube.com/embed/5k0C21KAsns" frameborder="0" allowfullscreen></iframe>  |  |

<span data-ttu-id="fb018-537">Дополнительные сведения о переносе телефонных номеров в службу Аудиоконференций см. в статье [Перенос телефонных номеров в Skype для бизнеса Online](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).</span><span class="sxs-lookup"><span data-stu-id="fb018-537">Additional details on transferring phone numbers to Audio Conferencing service can be found in [Transfer phone numbers to Skype for Business Online](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="fb018-538">Точки принятия решений</span><span class="sxs-lookup"><span data-stu-id="fb018-538">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="fb018-539">Определите, нужны ли организации выделенные телефонные номера для моста конференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-539">Decide whether the organization requires dedicated conference bridge phone numbers</span></span></li>
<li><span data-ttu-id="fb018-540">Определите способ получения выделенных телефонных номеров для моста конференций для расположений пользователей или офисов, где внедряется служба Аудиоконференций (получение у корпорации Майкрософт или перенос существующих номеров).</span><span class="sxs-lookup"><span data-stu-id="fb018-540">Decide how the dedicated conference bridge phone numbers will be obtained for user locations or offices in-scope for the Audio Conferencing implementation (obtain from Microsoft or transfer existing phone numbers)</span></span></li>
<li><span data-ttu-id="fb018-541">При выборе корпорации Майкрософт определите формат получения номеров (с отправкой формы или автоматически).</span><span class="sxs-lookup"><span data-stu-id="fb018-541">If you choose to obtain from Microsoft, decide the method to obtain phone numbers (form submission or automated) for user locations or offices in-scope for the Audio Conferencing implementation</span></span></li>
<li><span data-ttu-id="fb018-542">Определите предпочитаемые языки для каждого выделенного телефонного номера для моста конференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-542">Decide the language preferences to be set up for each dedicated conference bridge phone number</span></span></li>
<li><span data-ttu-id="fb018-543">Определите телефонный номер для моста конференций, используемый по умолчанию для клиента.</span><span class="sxs-lookup"><span data-stu-id="fb018-543">Decide the tenant default conference bridge phone number</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="fb018-544">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="fb018-544">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="fb018-545">Задокументируйте сводный план по получению телефонных номеров, описав способ получения номеров для каждого из расположений пользователей или офисов, где внедряется служба Аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-545">Document the master plan for phone numbers acquisition, detailing how phone numbers will be obtained for each user location or office in-scope for the Audio Conferencing implementation.</span></span></li>
<li><span data-ttu-id="fb018-546">Если возможно, заполните <a href="https://support.office.com/article/Get-phone-numbers-for-Skype-for-Business-Online-6b61cb3c-361c-48a8-a9ef-d81bddde27bb?ui=en-US&amp;rs=en-US&amp;ad=US">форму на запрос новых телефонных номеров</a> — по одной форме для каждого расположения или офиса.</span><span class="sxs-lookup"><span data-stu-id="fb018-546">If applicable, complete <a href="https://support.office.com/article/Get-phone-numbers-for-Skype-for-Business-Online-6b61cb3c-361c-48a8-a9ef-d81bddde27bb?ui=en-US&amp;rs=en-US&amp;ad=US">the New Telephone Number Request form</a>, one form for each location or office</span></span></li>
<li><span data-ttu-id="fb018-547">Если вы решили перенести имеющиеся телефонные номера, ознакомьтесь с <a href="https://go.microsoft.com/fwlink/?linkid=859011">руководством по переносу номеров</a>, чтобы составить подходящий план и соответствующим образом скорректировать сроки внедрения Аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-547">If you choose to transfer existing phone numbers, check out the <a href="https://go.microsoft.com/fwlink/?linkid=859011">Number Porting Guide</a> to plan it and adjust Audio Conferencing implementation timeline accordingly.</span></span></li>
<li><span data-ttu-id="fb018-548">Задокументируйте подробные конфигурации телефонных номеров для моста конференций (общие и выделенные номера, предпочитаемые языки для каждого из выделенных номеров, телефонный номер для моста конференций, используемый по умолчанию для клиента).</span><span class="sxs-lookup"><span data-stu-id="fb018-548">Document the detailed conference bridge phone number configurations (shared and dedicated conference bridge phone numbers, language preferences for each dedicated conference bridge phone number, tenant default conference bridge phone number)</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fb018-549">Офис</span><span class="sxs-lookup"><span data-stu-id="fb018-549">Office</span></span></th>
<th align="left"><span data-ttu-id="fb018-550">Получение номеров моста и тип моста</span><span class="sxs-lookup"><span data-stu-id="fb018-550">Bridge Number Acquisition and Bridge Type</span></span></th>
<th align="left"><span data-ttu-id="fb018-551">Номер моста</span><span class="sxs-lookup"><span data-stu-id="fb018-551">Bridge Number</span></span></th>
<th align="left"><span data-ttu-id="fb018-552">Язык моста</span><span class="sxs-lookup"><span data-stu-id="fb018-552">Bridge Language</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-553">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="fb018-553">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="fb018-554">Новый, выделенный</span><span class="sxs-lookup"><span data-stu-id="fb018-554">Acquire new, dedicated</span></span></td>
<td align="left"><span data-ttu-id="fb018-555">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-555">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-556">Английский (Австралия)</span><span class="sxs-lookup"><span data-stu-id="fb018-556">English (Australia)</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-557">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="fb018-557">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="fb018-558">Новый, общий</span><span class="sxs-lookup"><span data-stu-id="fb018-558">Acquire new, shared</span></span></td>
<td align="left"><span data-ttu-id="fb018-559">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-559">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-560">Английский (США), китайский (упрощенное письмо, КНР)</span><span class="sxs-lookup"><span data-stu-id="fb018-560">English (United States), Chinese (Simplified, PRC)</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-561">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="fb018-561">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="fb018-562">Перенос, выделенный</span><span class="sxs-lookup"><span data-stu-id="fb018-562">Port existing, dedicated</span></span></td>
<td align="left"><span data-ttu-id="fb018-563">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="fb018-563">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="fb018-564">Английский (Соединенное Королевство)</span><span class="sxs-lookup"><span data-stu-id="fb018-564">English (United Kingdom)</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-565">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="fb018-565">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="fb018-566">Новый, выделенный</span><span class="sxs-lookup"><span data-stu-id="fb018-566">Acquire new, dedicated</span></span></td>
<td align="left"><span data-ttu-id="fb018-567">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-567">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-568">Французский (Франция), английский (Соединенное Королевство)</span><span class="sxs-lookup"><span data-stu-id="fb018-568">French (France), English (United Kingdom)</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fb018-569">_Табл. 10. Пример сведений о мосте конференций_</span><span class="sxs-lookup"><span data-stu-id="fb018-569">_Table 10 Example of conference bridge details_</span></span>


> [!NOTE]
> <span data-ttu-id="fb018-570">Предыдущий пример таблицы и таблицы, приведенные ниже, служат в качестве шаблона.</span><span class="sxs-lookup"><span data-stu-id="fb018-570">The example table above and subsequent tables throughout this document serve as a template.</span></span> <span data-ttu-id="fb018-571">Вы увидите сообщение "Подлежит добавлению" на месте информации, которую вам нужно указать в рамках процесса планирования.</span><span class="sxs-lookup"><span data-stu-id="fb018-571">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>

## <a name="conference-bridge-settings"></a><span data-ttu-id="fb018-572">Параметры моста конференций</span><span class="sxs-lookup"><span data-stu-id="fb018-572">Conference bridge settings</span></span>

<span data-ttu-id="fb018-573">Для дальнейшей настройки взаимодействия с пользователем доступны параметры конфигурации на уровне организации, определяющие порядок присоединения к собраниям Аудиоконференций (уведомление о входе на собрание и выходе из него, а также регистрация имени вызывающего абонента), настройка длины ПИН-кода у организатора собрания и уведомление по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="fb018-573">Organization-wide configuration options around Audio Conferencing meeting join experience (meeting entry and exit notification and caller name recording), meeting organizer’s PIN length, and email notification are available to further tailor the end-user experience.</span></span>

-   <span data-ttu-id="fb018-574">Уведомления о входе на собрание и выходе из него доступны в форме записанного имени, номера телефона и мелодий.</span><span class="sxs-lookup"><span data-stu-id="fb018-574">Meeting entry and exit notifications are available in the form of recorded name, phone number, and tones.</span></span>

-   <span data-ttu-id="fb018-575">Длина ПИН-кода настраивается в пределах от 4 до 12 цифр и по умолчанию равна 5 цифрам.</span><span class="sxs-lookup"><span data-stu-id="fb018-575">PIN length is configurable from 4 to 12 digits, with a 5-digit PIN as the default.</span></span>

-   <span data-ttu-id="fb018-576">Уведомления по электронной почте при активации лицензии на Аудиоконференции или любых других изменениях, внесенных администратором, включены по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fb018-576">Notification emails upon enablement of Audio Conferencing license or any other admin-driven changes are enabled by default.</span></span> <span data-ttu-id="fb018-577">Вы можете отключить эту функцию и самостоятельно управлять взаимодействием с пользователями в своей организации.</span><span class="sxs-lookup"><span data-stu-id="fb018-577">You can disable this feature and take control of your organization’s end-user communications.</span></span>

<span data-ttu-id="fb018-578">Для пользователей, которым назначается лицензия на Аудиоконференции, платные и бесплатные номера, указанные в Аудиоконференциях, можно настроить для использования:</span><span class="sxs-lookup"><span data-stu-id="fb018-578">For users who are assigned an Audio Conferencing license, the default toll/toll-free numbers, shown in the Audio Conferencing coordinates, are configurable to use:</span></span>

-   <span data-ttu-id="fb018-579">значения по умолчанию на уровне клиента;</span><span class="sxs-lookup"><span data-stu-id="fb018-579">the tenant-level default, or</span></span>

-   <span data-ttu-id="fb018-580">автоматически назначаемых телефонных номеров для моста конференций;</span><span class="sxs-lookup"><span data-stu-id="fb018-580">the automatically-assigned conference bridge phone numbers, or</span></span>

-   <span data-ttu-id="fb018-581">телефонных номеров для моста конференций, назначаемых вручную для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="fb018-581">manually defined conference bridge phone numbers for each user.</span></span>

<span data-ttu-id="fb018-582">Назначаемые отдельным пользователям телефонные номера для моста конференций обычно удобно использовать в международных или национальных организациях, где пользователи разнесены и должны указывать в приглашениях на собрания местные номера в качестве номеров для моста конференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-582">User-specific conference bridge phone numbers are typically useful in global or nationwide organizations where users are distributed and must provide local numbers as the default conference bridge phone numbers in the meeting invites.</span></span>

<span data-ttu-id="fb018-583">Присоединяющиеся участники из других городов или стран могут узнать дополнительные номера, настроенные на уровне клиента, однако эти номера не указываются в приглашениях на собрания явным образом.</span><span class="sxs-lookup"><span data-stu-id="fb018-583">Participants joining from different cities or overseas can look up additional numbers configured at the tenant-level, but these numbers do not appear directly in the meeting invites.</span></span> <span data-ttu-id="fb018-584">Приглашение содержит ссылку, направляющую участника на страницу Teams с номерами для конференц-связи с телефонным подключением, где он может найти ближайшие к его расположению телефонные номера для моста конференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-584">The meeting invites provide a link that will take participants to the Teams Conference Dial-in Numbers page for them to lookup the closest conference bridge phone numbers available from their location.</span></span>

<span data-ttu-id="fb018-585">Вы также можете настроить обработку вызывающих абонентов, не прошедших проверку подлинности, для каждого из организаторов собраний. Например, вы можете потребовать, чтобы организатор начал собрание, прежде чем непроверенные вызывающие абоненты смогут присоединиться к нему, либо разрешил им начать собрание самим.</span><span class="sxs-lookup"><span data-stu-id="fb018-585">You can also configure how unauthenticated callers are handled by each individual meeting organizer, whether to require meeting organizer to start the meeting before unauthenticated callers are admitted, or to allow unauthenticated callers to start a meeting.</span></span>

<span data-ttu-id="fb018-586">Кроме того, для каждого из пользователей можно управлять использованием бесплатных телефонных номеров для моста конференций и обратных звонков из конференции.</span><span class="sxs-lookup"><span data-stu-id="fb018-586">Additional configurations that can be applied for each user are available to control the use of toll-free conference bridge phone numbers and dial-out from a conference.</span></span>

> [!NOTE]
> <span data-ttu-id="fb018-587">Сейчас эти элементы управления затратами доступны только клиентам с предварительной версией.</span><span class="sxs-lookup"><span data-stu-id="fb018-587">These cost-related controls are currently available for preview customers only.</span></span> <span data-ttu-id="fb018-588">Вы можете зарегистрировать свою организацию в программе по ознакомлению с предварительной версией на сайте [https://www.skypepreview.com](https://go.microsoft.com/fwlink/?linkid=859013).</span><span class="sxs-lookup"><span data-stu-id="fb018-588">You can enroll your organization in the preview program from [https://www.skypepreview.com](https://go.microsoft.com/fwlink/?linkid=859013).</span></span>

<span data-ttu-id="fb018-589">Эти элементы позволяют определить, могут ли организаторы предоставлять для своих собраний бесплатные телефонные номера для моста конференций и управлять доступностью обратных звонков для участников.</span><span class="sxs-lookup"><span data-stu-id="fb018-589">With these controls, you can decide whether meeting organizers can provide toll-free conference bridge phone numbers for meetings organized by them, and to control whether participants can dial out from the meetings organized by them.</span></span> <span data-ttu-id="fb018-590">Функция управления обратными звонками допускает запрет обратных звонков, разрешение таких звонков только на внутренние номера и разрешение звонков как на внутренние, так и на международные номера.</span><span class="sxs-lookup"><span data-stu-id="fb018-590">The level of dial-out control spans from disallowing dial out, only allowing dial out to domestic numbers, to allowing dial out to both domestic and international numbers.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="fb018-591">Точки принятия решений</span><span class="sxs-lookup"><span data-stu-id="fb018-591">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="fb018-592">Определите, нужны ли организации уведомления о входе на собрание и выходе из него. Если нужны, определите тип этих уведомлений (мелодии, телефонный номер или записанное имя).</span><span class="sxs-lookup"><span data-stu-id="fb018-592">Decide whether the organization requires entry and exit notifications, and if yes, the type of notification to be implemented (tones, phone number, or recorded name).</span></span></li>
<li><span data-ttu-id="fb018-593">Определите длину ПИН-кода для Аудиоконференций, соответствующую требованиям безопасности в организации.</span><span class="sxs-lookup"><span data-stu-id="fb018-593">Decide the Audio Conferencing PIN length that meets the organizational security requirements.</span></span></li>
<li><span data-ttu-id="fb018-594">Определите, нужно ли организации управлять взаимодействием с пользователями, связанным со службой Аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-594">Decide if the organization wants to take control of end-user communications related to Audio Conferencing service.</span></span></li>
<li><span data-ttu-id="fb018-595">Определите телефонные номера для моста конференций, назначаемые каждому из организаторов собрания.</span><span class="sxs-lookup"><span data-stu-id="fb018-595">Decide the conference bridge phone numbers to be assigned to each meeting organizer.</span></span></li>
<li><span data-ttu-id="fb018-596">Определите, потребуется ли некоторым организаторам использовать бесплатные телефонные номера для моста конференций для своих собраний.</span><span class="sxs-lookup"><span data-stu-id="fb018-596">Decide whether some meeting organizers require the ability to use toll-free conference bridge phone numbers for their meeings</span></span></li>
<li><span data-ttu-id="fb018-597">Определите, потребуется ли некоторым организаторам разрешать вызывающим абонентам, не прошедшим проверку подлинности, начинать собрание.</span><span class="sxs-lookup"><span data-stu-id="fb018-597">Decide whether some meeting organizers require the ability to allow unauthenticated callers to start a meeting.</span></span></li>
<li><span data-ttu-id="fb018-598">Определите, потребуется ли некоторым организаторам управлять обратными звонками из конференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-598">Decide whether some meeting organizers require conference dial out to be controlled.</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="fb018-599">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="fb018-599">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="fb018-600">Задокументируйте подробные параметры моста конференций (уведомления о входе на собрание и выходе из него, длина ПИН-кода, уведомление по электронной почте об изменении конфигурации).</span><span class="sxs-lookup"><span data-stu-id="fb018-600">Document the detailed conference bridge settings (entry and exit notifications, PIN length, configuration change email notification).</span></span></li>
<li><span data-ttu-id="fb018-601">Задокументируйте телефонные номера для моста конференций, назначаемые каждому из организаторов собраний, и соответствующие параметры для политики управления непроверенными вызывающими абонентами, бесплатных номеров и обратных звонков.</span><span class="sxs-lookup"><span data-stu-id="fb018-601">Document the conference bridge phone numbers to be assinged to each meeting organizer and the corresponding setting to control unauthenticated caller’s policy, and toll-free and dial out controls.</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="left"><span data-ttu-id="fb018-602"><strong>Включить уведомления о входе на собрание и выходе из него</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-602"><strong>Enable meeting entry and exit notifications</strong></span></span></td>
<td align="left"><span data-ttu-id="fb018-603">Включено</span><span class="sxs-lookup"><span data-stu-id="fb018-603">Enabled</span></span></td>
</tr>
</thead>
<thead>
<tr class="header">
<td align="left"><span data-ttu-id="fb018-604"><strong>Entry/exit announcement type (Тип уведомления при входе и выходе)</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-604"><strong>Entry/exit announcement type</strong></span></span></td>
<td align="left"><span data-ttu-id="fb018-605">Мелодии</span><span class="sxs-lookup"><span data-stu-id="fb018-605">Tones</span></span></td>
</tr>
<tr class="header">
<td align="left"><span data-ttu-id="fb018-606"><strong>Попросите звонящих записывать свои имена перед присоединением к собранию</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-606"><strong>Ask callers to record their name before joining the meeting</strong></span></span></td>
<td align="left"><span data-ttu-id="fb018-607">Отключено</span><span class="sxs-lookup"><span data-stu-id="fb018-607">Disabled</span></span></td>
</tr>
<tr class="header">
<td align="left"><span data-ttu-id="fb018-608"><strong>Длина ПИН-кода</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-608"><strong>PIN length</strong></span></span></td>
<td align="left"><span data-ttu-id="fb018-609">5</span><span class="sxs-lookup"><span data-stu-id="fb018-609">5</span></span></td>
</tr>
<tr class="header">
<td align="left"><span data-ttu-id="fb018-610"><strong>Автоматически отправляйте электронную почту пользователям при изменении настроек набора номера</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-610"><strong>Automatically send emails to users if their dial-in settings change</strong></span></span></td>
<td align="left"><span data-ttu-id="fb018-611">Отключено</span><span class="sxs-lookup"><span data-stu-id="fb018-611">Disabled</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fb018-612">_Табл. 11. Пример параметров для моста конференций_</span><span class="sxs-lookup"><span data-stu-id="fb018-612">_Table 11 Example of conference bridge settings_</span></span>


<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fb018-613">Пользователь</span><span class="sxs-lookup"><span data-stu-id="fb018-613">User</span></span></th>
<th align="left"><span data-ttu-id="fb018-614">Офис</span><span class="sxs-lookup"><span data-stu-id="fb018-614">Office</span></span></th>
<th align="left"><span data-ttu-id="fb018-615">Платный номер по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fb018-615">Default toll number</span></span></th>
<th align="left"><span data-ttu-id="fb018-616">Бесплатный номер по умолчанию</span><span class="sxs-lookup"><span data-stu-id="fb018-616">Default toll-free number</span></span></th>
<th align="left"><span data-ttu-id="fb018-617">Разрешить бесплатные номера</span><span class="sxs-lookup"><span data-stu-id="fb018-617">Allow toll-free</span></span></th>
<th align="left"><span data-ttu-id="fb018-618">Непроверенные вызывающие абоненты минуют зал ожидания</span><span class="sxs-lookup"><span data-stu-id="fb018-618">Unauthenticated callers bypass lobby</span></span></th>
<th align="left"><span data-ttu-id="fb018-619">Обратный звонок из конференции</span><span class="sxs-lookup"><span data-stu-id="fb018-619">Conference dial out</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-620">Adele Vance</span><span class="sxs-lookup"><span data-stu-id="fb018-620">Adele Vance</span></span></td>
<td align="left"><span data-ttu-id="fb018-621">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="fb018-621">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="fb018-622">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-622">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-623">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-623">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-624">Да</span><span class="sxs-lookup"><span data-stu-id="fb018-624">Yes</span></span></td>
<td align="left"><span data-ttu-id="fb018-625">Включено</span><span class="sxs-lookup"><span data-stu-id="fb018-625">Enabled</span></span></td>
<td align="left"><span data-ttu-id="fb018-626">Международный и внутренний</span><span class="sxs-lookup"><span data-stu-id="fb018-626">International and domestic</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-627">Alex Wilber</span><span class="sxs-lookup"><span data-stu-id="fb018-627">Alex Wilber</span></span></td>
<td align="left"><span data-ttu-id="fb018-628">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="fb018-628">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="fb018-629">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-629">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-630">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-630">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-631">Нет</span><span class="sxs-lookup"><span data-stu-id="fb018-631">No</span></span></td>
<td align="left"><span data-ttu-id="fb018-632">Отключено</span><span class="sxs-lookup"><span data-stu-id="fb018-632">Disabled</span></span></td>
<td align="left"><span data-ttu-id="fb018-633">Запрещено</span><span class="sxs-lookup"><span data-stu-id="fb018-633">Not allowed</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-634">Ben Walters</span><span class="sxs-lookup"><span data-stu-id="fb018-634">Ben Walters</span></span></td>
<td align="left"><span data-ttu-id="fb018-635">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="fb018-635">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="fb018-636">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-636">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-637">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-637">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-638">Нет</span><span class="sxs-lookup"><span data-stu-id="fb018-638">No</span></span></td>
<td align="left"><span data-ttu-id="fb018-639">Отключено</span><span class="sxs-lookup"><span data-stu-id="fb018-639">Disabled</span></span></td>
<td align="left"><span data-ttu-id="fb018-640">Запрещено</span><span class="sxs-lookup"><span data-stu-id="fb018-640">Not allowed</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-641">Christie Cline</span><span class="sxs-lookup"><span data-stu-id="fb018-641">Christie Cline</span></span></td>
<td align="left"><span data-ttu-id="fb018-642">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="fb018-642">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="fb018-643">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-643">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-644">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-644">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-645">Да</span><span class="sxs-lookup"><span data-stu-id="fb018-645">Yes</span></span></td>
<td align="left"><span data-ttu-id="fb018-646">Отключено</span><span class="sxs-lookup"><span data-stu-id="fb018-646">Disabled</span></span></td>
<td align="left"><span data-ttu-id="fb018-647">Внутренний</span><span class="sxs-lookup"><span data-stu-id="fb018-647">Domestic</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-648">Debra Berger</span><span class="sxs-lookup"><span data-stu-id="fb018-648">Debra Berger</span></span></td>
<td align="left"><span data-ttu-id="fb018-649">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="fb018-649">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="fb018-650">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-650">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-651">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-651">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-652">Да</span><span class="sxs-lookup"><span data-stu-id="fb018-652">Yes</span></span></td>
<td align="left"><span data-ttu-id="fb018-653">Включено</span><span class="sxs-lookup"><span data-stu-id="fb018-653">Enabled</span></span></td>
<td align="left"><span data-ttu-id="fb018-654">Внутренний</span><span class="sxs-lookup"><span data-stu-id="fb018-654">Domestic</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-655">Lee Gu</span><span class="sxs-lookup"><span data-stu-id="fb018-655">Lee Gu</span></span></td>
<td align="left"><span data-ttu-id="fb018-656">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="fb018-656">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="fb018-657">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-657">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-658">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-658">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-659">Да</span><span class="sxs-lookup"><span data-stu-id="fb018-659">Yes</span></span></td>
<td align="left"><span data-ttu-id="fb018-660">Включено</span><span class="sxs-lookup"><span data-stu-id="fb018-660">Enabled</span></span></td>
<td align="left"><span data-ttu-id="fb018-661">Внутренний</span><span class="sxs-lookup"><span data-stu-id="fb018-661">Domestic</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-662">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="fb018-662">Emily Braun</span></span></td>
<td align="left"><span data-ttu-id="fb018-663">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="fb018-663">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="fb018-664">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="fb018-664">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="fb018-665">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-665">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-666">Да</span><span class="sxs-lookup"><span data-stu-id="fb018-666">Yes</span></span></td>
<td align="left"><span data-ttu-id="fb018-667">Включено</span><span class="sxs-lookup"><span data-stu-id="fb018-667">Enabled</span></span></td>
<td align="left"><span data-ttu-id="fb018-668">Запрещено</span><span class="sxs-lookup"><span data-stu-id="fb018-668">Not allowed</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-669">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="fb018-669">Lidia Holloway</span></span></td>
<td align="left"><span data-ttu-id="fb018-670">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="fb018-670">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="fb018-671">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="fb018-671">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="fb018-672">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-672">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-673">Да</span><span class="sxs-lookup"><span data-stu-id="fb018-673">Yes</span></span></td>
<td align="left"><span data-ttu-id="fb018-674">Отключено</span><span class="sxs-lookup"><span data-stu-id="fb018-674">Disabled</span></span></td>
<td align="left"><span data-ttu-id="fb018-675">Запрещено</span><span class="sxs-lookup"><span data-stu-id="fb018-675">Not allowed</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-676">Pradeep Gupta</span><span class="sxs-lookup"><span data-stu-id="fb018-676">Pradeep Gupta</span></span></td>
<td align="left"><span data-ttu-id="fb018-677">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="fb018-677">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="fb018-678">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="fb018-678">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="fb018-679">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-679">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-680">Да</span><span class="sxs-lookup"><span data-stu-id="fb018-680">Yes</span></span></td>
<td align="left"><span data-ttu-id="fb018-681">Отключено</span><span class="sxs-lookup"><span data-stu-id="fb018-681">Disabled</span></span></td>
<td align="left"><span data-ttu-id="fb018-682">Запрещено</span><span class="sxs-lookup"><span data-stu-id="fb018-682">Not allowed</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-683">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="fb018-683">Marcel Beauchamp</span></span></td>
<td align="left"><span data-ttu-id="fb018-684">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="fb018-684">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="fb018-685">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-685">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-686">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-686">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-687">Нет</span><span class="sxs-lookup"><span data-stu-id="fb018-687">No</span></span></td>
<td align="left"><span data-ttu-id="fb018-688">Отключено</span><span class="sxs-lookup"><span data-stu-id="fb018-688">Disabled</span></span></td>
<td align="left"><span data-ttu-id="fb018-689">Внутренний</span><span class="sxs-lookup"><span data-stu-id="fb018-689">Domestic</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-690">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="fb018-690">Rachelle Cormier</span></span></td>
<td align="left"><span data-ttu-id="fb018-691">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="fb018-691">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="fb018-692">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-692">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-693">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-693">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-694">Да</span><span class="sxs-lookup"><span data-stu-id="fb018-694">Yes</span></span></td>
<td align="left"><span data-ttu-id="fb018-695">Включено</span><span class="sxs-lookup"><span data-stu-id="fb018-695">Enabled</span></span></td>
<td align="left"><span data-ttu-id="fb018-696">Международный и внутренний</span><span class="sxs-lookup"><span data-stu-id="fb018-696">International and domestic</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-697">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="fb018-697">Isabell Potvin</span></span></td>
<td align="left"><span data-ttu-id="fb018-698">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="fb018-698">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="fb018-699">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-699">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-700">Подлежит добавлению</span><span class="sxs-lookup"><span data-stu-id="fb018-700">TBA</span></span></td>
<td align="left"><span data-ttu-id="fb018-701">Нет</span><span class="sxs-lookup"><span data-stu-id="fb018-701">No</span></span></td>
<td align="left"><span data-ttu-id="fb018-702">Отключено</span><span class="sxs-lookup"><span data-stu-id="fb018-702">Disabled</span></span></td>
<td align="left"><span data-ttu-id="fb018-703">Внутренний</span><span class="sxs-lookup"><span data-stu-id="fb018-703">Domestic</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fb018-704">_Табл. 12. Пример назначенных параметров для моста конференций_</span><span class="sxs-lookup"><span data-stu-id="fb018-704">_Table 12 Example of conference bridge settings assignments_</span></span>


## <a name="dial-plans"></a><span data-ttu-id="fb018-705">Абонентские группы</span><span class="sxs-lookup"><span data-stu-id="fb018-705">Dial plans</span></span>

<span data-ttu-id="fb018-706">[Абонентская группа](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b), функция Телефонной системы Office 365, представляет собой набор правил нормализации, который преобразует набираемые телефонные номера в альтернативный формат (обычно [E.164](https://go.microsoft.com/fwlink/?linkid=859014)) для авторизации и маршрутизации звонков.</span><span class="sxs-lookup"><span data-stu-id="fb018-706">A [Dial Plan](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b), a Phone System feature of Office 365, is a set of normalization rules that translates dialed phone numbers into an alternate format (typically [E.164](https://go.microsoft.com/fwlink/?linkid=859014) format) for call authorization and call routing.</span></span> <span data-ttu-id="fb018-707">Служба Аудиоконференций использует те же возможности, что и Телефонная система, для преобразования набираемых номеров в сценариях с обратными звонками из конференции.</span><span class="sxs-lookup"><span data-stu-id="fb018-707">Audio Conferencing service leverages the same capabilities used by Phone System to translate dialed phone numbers in conference dial out scenarios.</span></span>

<span data-ttu-id="fb018-708">Абонентская группа позволяет пользователям набирать телефонные номера привычным образом, например пропуская код города для местных звонков, код страны для внутренних звонков или даже используя сокращенные номера для обратных звонков.</span><span class="sxs-lookup"><span data-stu-id="fb018-708">A dial plan allows users to dial phone numbers the way they are accustomed to, such as omitting area code for local calls, omitting country code for domestic calls, or even using short digit dialing when performing conference dial out.</span></span>

<span data-ttu-id="fb018-709">В Телефонной системе Office 365 представлено два типа абонентских групп:</span><span class="sxs-lookup"><span data-stu-id="fb018-709">Within the Phone System feature of Office 365, there are two types of dial plans:</span></span>

-   <span data-ttu-id="fb018-710">**Служебная абонентская группа**.</span><span class="sxs-lookup"><span data-stu-id="fb018-710">**Service dial plan**.</span></span> <span data-ttu-id="fb018-711">Этот тип используется по умолчанию, применяется для пользователей в зависимости от места использования Office 365 и недоступен для изменения.</span><span class="sxs-lookup"><span data-stu-id="fb018-711">This is the default dial plan and applied to users based on Office 365 usage location, and it cannot be modified.</span></span>

<!-- -->

-   <span data-ttu-id="fb018-712">**Абонентская группа клиента**.</span><span class="sxs-lookup"><span data-stu-id="fb018-712">**Tenant dial plan**.</span></span> <span data-ttu-id="fb018-713">Это настраиваемая абонентская группа, действующая у клиента и подразделяемая на два типа:</span><span class="sxs-lookup"><span data-stu-id="fb018-713">This is a customizable dial plan within a tenant, and further divided into two types:</span></span>

    -   <span data-ttu-id="fb018-714">**Абонентская группа уровня клиента** — применяется ко всем пользователям клиента.</span><span class="sxs-lookup"><span data-stu-id="fb018-714">**Tenant-global dial plan**—the dial plan applies to all users within the tenant.</span></span>

    -   <span data-ttu-id="fb018-715">**Абонентская группа пользователя клиента** — применяется только к отдельным пользователям.</span><span class="sxs-lookup"><span data-stu-id="fb018-715">**Tenant-user dial plan**—the dial plan applies only to specific users.</span></span>


> [!NOTE]
> <span data-ttu-id="fb018-716">Дополнительные сведения и примеры см. в документации [Абонентские группы в Плане звонков Office 365](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b).</span><span class="sxs-lookup"><span data-stu-id="fb018-716">Check out the [Office 365 Calling Plan dial plans](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b) documentation for further details and examples.</span></span>

<span data-ttu-id="fb018-717">Фактическая абонентская группа, назначенная пользователям, представляет комбинацию из служебной абонентской группы (в зависимости от места использования Office 365 пользователя) и абонентской группы клиента (она может относиться как ко всему клиенту, так и к отдельным пользователям).</span><span class="sxs-lookup"><span data-stu-id="fb018-717">The effective dial plan assigned to users is the combination of service dial plan (based on user’s Office 365 usage location) and tenant dial plan (can be either tenant-global dial plan or tenant-user dial plan).</span></span>

![Таблица содержит три сочетания служебных абонентских групп и абонентских групп клиента.](media/audio_conferencing_image8.png)

<span data-ttu-id="fb018-719">Каждая абонентская группа клиента может содержать до 25 правил нормализации, поэтому нужно следить за отсутствием дублирования с правилами нормализации, которые уже доступны в служебной абонентской группе.</span><span class="sxs-lookup"><span data-stu-id="fb018-719">There is a maximum of 25 normalization rules in each tenant dial plan, and thus duplication with normalization rules already available as part of service dial plan needs to be avoided.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="fb018-720">Точки принятия решений</span><span class="sxs-lookup"><span data-stu-id="fb018-720">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="fb018-721">Определите, нуждается ли организация в настраиваемых абонентских группах (бизнес-требования, требования к освоению и т. д.).</span><span class="sxs-lookup"><span data-stu-id="fb018-721">Decide if your organization requires customized dial plans (business requirements, adoption requirements, etc.).</span></span></li>
<li><span data-ttu-id="fb018-722">Если возможно, определите область действия для абонентской группы клиента (на уровне клиента или отдельных пользователей), руководствуясь требованиями к настраиваемым абонентским группам.</span><span class="sxs-lookup"><span data-stu-id="fb018-722">If applicable, decide the scope of tenant dial plan (tenant-global or tenant-user) to support the requirements for customized dial plans.</span></span></li>
<li><span data-ttu-id="fb018-723">Если возможно, определите абонентские группы клиента, которые будут созданы для расположений пользователей или офисов, где внедряется служба Аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-723">If applicable, decide the tenant dial plans that will be created to support user locations or offices in-scope for the Audio Conferencing implementation.</span></span></li>
<li><span data-ttu-id="fb018-724">Если возможно, определите, какому пользователю требуется настраиваемая абонентская группа, а также выберите абонентскую группу клиента, применяемую ко всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="fb018-724">If applicable, decide which user require customized dial plan and the tenant dial plan to be assigned for each user.</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="fb018-725">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="fb018-725">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="fb018-726">Задокументируйте настраиваемые абонентские группы и связанные с ними правила нормализации, которые требуется задать в рамках внедрения службы Аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-726">Document the customized dial plans and the associated normalization rules to be configured as part of Audio Conferencing implementation.</span></span></li>
<li><span data-ttu-id="fb018-727">Задокументируйте пользователей, каждому из которых требуется назначить настраиваемую абонентскую группу, а также абонентскую группу клиента, применяемую ко всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="fb018-727">Document the users to be assigned with customized dial plan and the tenant dial plan to be assigned for each user.</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fb018-728">Имя и описание абонентской группы клиента</span><span class="sxs-lookup"><span data-stu-id="fb018-728">Tenant Dial Plan Name/Description</span></span></th>
<th align="left"><span data-ttu-id="fb018-729">Имя и описание правил нормализации</span><span class="sxs-lookup"><span data-stu-id="fb018-729">Normalization Rules Name/Description</span></span></th>
<th align="left"><span data-ttu-id="fb018-730">Шаблон</span><span class="sxs-lookup"><span data-stu-id="fb018-730">Pattern</span></span></th>
<th align="left"><span data-ttu-id="fb018-731">Преобразование</span><span class="sxs-lookup"><span data-stu-id="fb018-731">Translation</span></span></th>
<th align="left"><span data-ttu-id="fb018-732">IsInternalExtension</span><span class="sxs-lookup"><span data-stu-id="fb018-732">IsInternalExtension</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fb018-733"><strong>AU-NSW-NorthRyde-OER</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-733"><strong>AU-NSW-NorthRyde-OER</strong></span></span></p>
<p><span data-ttu-id="fb018-734"><em>Абонентская группа One Epping Road North Ryde, NSW, AU</em></span><span class="sxs-lookup"><span data-stu-id="fb018-734"><em>One Epping Road North Ryde, NSW, AU Dial Plan</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="fb018-735"><strong>AU-NSW-NorthRyde-OER-Internal</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-735"><strong>AU-NSW-NorthRyde-OER-Internal</strong></span></span></p>
<p><span data-ttu-id="fb018-736"><em>Внутренний номер (x7000–x7999) для офиса One Epping Road, North Ryde, NSW, Австралия</em></span><span class="sxs-lookup"><span data-stu-id="fb018-736"><em>Internal number (x7000 - x7999) for One Epping Road office, North Ryde, NSW, Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="fb018-737">^(7\d{3})$</span><span class="sxs-lookup"><span data-stu-id="fb018-737">^(7\d{3})$</span></span></td>
<td align="left"><span data-ttu-id="fb018-738">+6125550$1</span><span class="sxs-lookup"><span data-stu-id="fb018-738">+6125550$1</span></span></td>
<td align="left"><span data-ttu-id="fb018-739">True</span><span class="sxs-lookup"><span data-stu-id="fb018-739">True</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="fb018-740"><strong>AU-NSW-Local</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-740"><strong>AU-NSW-Local</strong></span></span></p>
<p><span data-ttu-id="fb018-741"><em>Нормализация местного номера для NSW, Австралия</em></span><span class="sxs-lookup"><span data-stu-id="fb018-741"><em>Local number normalization for NSW, Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="fb018-742">^([2-9]\d{7})$</span><span class="sxs-lookup"><span data-stu-id="fb018-742">^([2-9]\d{7})$</span></span></td>
<td align="left"><span data-ttu-id="fb018-743">+612$1</span><span class="sxs-lookup"><span data-stu-id="fb018-743">+612$1</span></span></td>
<td align="left"><span data-ttu-id="fb018-744">False</span><span class="sxs-lookup"><span data-stu-id="fb018-744">False</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="fb018-745"><strong>AU-TollFree</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-745"><strong>AU-TollFree</strong></span></span></p>
<p><span data-ttu-id="fb018-746"><em>Нормализация бесплатного номера для Австралии</em></span><span class="sxs-lookup"><span data-stu-id="fb018-746"><em>Toll Free number normalization for Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="fb018-747">^(1[38]\d{4,8})\d*$</span><span class="sxs-lookup"><span data-stu-id="fb018-747">^(1[38]\d{4,8})\d*$</span></span></td>
<td align="left"><span data-ttu-id="fb018-748">+61$1</span><span class="sxs-lookup"><span data-stu-id="fb018-748">+61$1</span></span></td>
<td align="left"><span data-ttu-id="fb018-749">False</span><span class="sxs-lookup"><span data-stu-id="fb018-749">False</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="fb018-750"><strong>AU-Service</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-750"><strong>AU-Service</strong></span></span></p>
<p><span data-ttu-id="fb018-751"><em>Нормализация номера службы для Австралии</em></span><span class="sxs-lookup"><span data-stu-id="fb018-751"><em>Service number normalization for Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="fb018-752">^(000|1[0125]\d{1,8})$</span><span class="sxs-lookup"><span data-stu-id="fb018-752">^(000|1[0125]\d{1,8})$</span></span></td>
<td align="left"><span data-ttu-id="fb018-753">$1</span><span class="sxs-lookup"><span data-stu-id="fb018-753">$1</span></span></td>
<td align="left"><span data-ttu-id="fb018-754">False</span><span class="sxs-lookup"><span data-stu-id="fb018-754">False</span></span></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fb018-755"><strong>SG-Singapore-OMB</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-755"><strong>SG-Singapore-OMB</strong></span></span></p>
<p><span data-ttu-id="fb018-756"><em>OMB в Сингапуре, абонентская группа SG</em></span><span class="sxs-lookup"><span data-stu-id="fb018-756"><em>OMB Singapore, SG Dial Plan</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="fb018-757"><strong>SG-OMB-Internal</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-757"><strong>SG-OMB-Internal</strong></span></span></p>
<p><span data-ttu-id="fb018-758"><em>Внутренний номер (x8000–x8999) для офиса OMB, Сингапур</em></span><span class="sxs-lookup"><span data-stu-id="fb018-758"><em>Internal number (x8000 – x8999) for OMB office, Singapore</em></span></span></p></td>
<td align="left"><span data-ttu-id="fb018-759">^(8\d{3})$</span><span class="sxs-lookup"><span data-stu-id="fb018-759">^(8\d{3})$</span></span></td>
<td align="left"><span data-ttu-id="fb018-760">+656888$1</span><span class="sxs-lookup"><span data-stu-id="fb018-760">+656888$1</span></span></td>
<td align="left"><span data-ttu-id="fb018-761">True</span><span class="sxs-lookup"><span data-stu-id="fb018-761">True</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="fb018-762"><strong>SG-TollFree</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-762"><strong>SG-TollFree</strong></span></span></p>
<p><span data-ttu-id="fb018-763"><em>Нормализация бесплатного номера для Сингапура</em></span><span class="sxs-lookup"><span data-stu-id="fb018-763"><em>Toll Free number normalization for Singapore</em></span></span></p></td>
<td align="left"><span data-ttu-id="fb018-764">^(1?800\d{7})\d*$</span><span class="sxs-lookup"><span data-stu-id="fb018-764">^(1?800\d{7})\d*$</span></span></td>
<td align="left"><span data-ttu-id="fb018-765">+65$1</span><span class="sxs-lookup"><span data-stu-id="fb018-765">+65$1</span></span></td>
<td align="left"><span data-ttu-id="fb018-766">False</span><span class="sxs-lookup"><span data-stu-id="fb018-766">False</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="fb018-767"><strong>SG-Service</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-767"><strong>SG-Service</strong></span></span></p>
<p><span data-ttu-id="fb018-768"><em>Нормализация номера службы для Сингапура</em></span><span class="sxs-lookup"><span data-stu-id="fb018-768"><em>Service number normalization for Singapore</em></span></span></p></td>
<td align="left"><span data-ttu-id="fb018-769">^(1\d{3,4}|9\d{2})$</span><span class="sxs-lookup"><span data-stu-id="fb018-769">^(1\d{3,4}|9\d{2})$</span></span></td>
<td align="left"><span data-ttu-id="fb018-770">$1</span><span class="sxs-lookup"><span data-stu-id="fb018-770">$1</span></span></td>
<td align="left"><span data-ttu-id="fb018-771">False</span><span class="sxs-lookup"><span data-stu-id="fb018-771">False</span></span></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fb018-772"><strong>FR-Paris-Issy-39qdPR</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-772"><strong>FR-Paris-Issy-39qdPR</strong></span></span></p>
<p><span data-ttu-id="fb018-773"><em>Абонентская группа 39 quai du Président Roosevelt Issy-les-Moulineaux, Франция</em></span><span class="sxs-lookup"><span data-stu-id="fb018-773"><em>39 quai du Président Roosevelt Issy-les-Moulineaux, France Dial Plan</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="fb018-774"><strong>FR-39qdPR-Internal</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-774"><strong>FR-39qdPR-Internal</strong></span></span></p>
<p><span data-ttu-id="fb018-775"><em>Внутренний номер (x7000–x7999) для офиса 39 quai du Président Roosevelt, Issy-les-Moulineaux, Франция</em></span><span class="sxs-lookup"><span data-stu-id="fb018-775"><em>Internal number (x7000 – x7999) for 39 quai du Président Roosevelt office, Issy-les-Moulineaux, France</em></span></span></p></td>
<td align="left"><span data-ttu-id="fb018-776">^(7\d{3})$</span><span class="sxs-lookup"><span data-stu-id="fb018-776">^(7\d{3})$</span></span></td>
<td align="left"><span data-ttu-id="fb018-777">+3319999$1</span><span class="sxs-lookup"><span data-stu-id="fb018-777">+3319999$1</span></span></td>
<td align="left"><span data-ttu-id="fb018-778">True</span><span class="sxs-lookup"><span data-stu-id="fb018-778">True</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="fb018-779"><strong>FR-TollFree</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-779"><strong>FR-TollFree</strong></span></span></p>
<p><span data-ttu-id="fb018-780"><em>Нормализация бесплатного номера для Франции</em></span><span class="sxs-lookup"><span data-stu-id="fb018-780"><em>Toll Free number normalization for France</em></span></span></p></td>
<td align="left"><span data-ttu-id="fb018-781">^0?(80\d{7})\d*$</span><span class="sxs-lookup"><span data-stu-id="fb018-781">^0?(80\d{7})\d*$</span></span></td>
<td align="left"><span data-ttu-id="fb018-782">+33$1</span><span class="sxs-lookup"><span data-stu-id="fb018-782">+33$1</span></span></td>
<td align="left"><span data-ttu-id="fb018-783">False</span><span class="sxs-lookup"><span data-stu-id="fb018-783">False</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="fb018-784"><strong>FR-Service</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-784"><strong>FR-Service</strong></span></span></p>
<p><span data-ttu-id="fb018-785"><em>Нормализация номера службы для Франции</em></span><span class="sxs-lookup"><span data-stu-id="fb018-785"><em>Service number normalization for France</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="fb018-786">^(1\d{1,2}|11[68]\d{3}|</span><span class="sxs-lookup"><span data-stu-id="fb018-786">^(1\d{1,2}|11[68]\d{3}|</span></span></p>
<p><span data-ttu-id="fb018-787">10\d{2}|3\d{3})$</span><span class="sxs-lookup"><span data-stu-id="fb018-787">10\d{2}|3\d{3})$</span></span></p></td>
<td align="left"><span data-ttu-id="fb018-788">$1</span><span class="sxs-lookup"><span data-stu-id="fb018-788">$1</span></span></td>
<td align="left"><span data-ttu-id="fb018-789">False</span><span class="sxs-lookup"><span data-stu-id="fb018-789">False</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fb018-790">_Табл. 13. Пример абонентских групп клиента_</span><span class="sxs-lookup"><span data-stu-id="fb018-790">_Table 13 Example of tenant dial plans_</span></span>


<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fb018-791">Пользователь</span><span class="sxs-lookup"><span data-stu-id="fb018-791">User</span></span></th>
<th align="left"><span data-ttu-id="fb018-792">Офис</span><span class="sxs-lookup"><span data-stu-id="fb018-792">Office</span></span></th>
<th align="left"><span data-ttu-id="fb018-793">Тип абонентской группы</span><span class="sxs-lookup"><span data-stu-id="fb018-793">Dial Plan Type</span></span></th>
<th align="left"><span data-ttu-id="fb018-794">Имя абонентской группы</span><span class="sxs-lookup"><span data-stu-id="fb018-794">Dial Plan Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-795">Adele Vance</span><span class="sxs-lookup"><span data-stu-id="fb018-795">Adele Vance</span></span></td>
<td align="left"><span data-ttu-id="fb018-796">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="fb018-796">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="fb018-797">Абонентская группа клиента</span><span class="sxs-lookup"><span data-stu-id="fb018-797">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="fb018-798">AU-NSW-NorthRyde-OER</span><span class="sxs-lookup"><span data-stu-id="fb018-798">AU-NSW-NorthRyde-OER</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-799">Alex Wilber</span><span class="sxs-lookup"><span data-stu-id="fb018-799">Alex Wilber</span></span></td>
<td align="left"><span data-ttu-id="fb018-800">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="fb018-800">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="fb018-801">Абонентская группа клиента</span><span class="sxs-lookup"><span data-stu-id="fb018-801">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="fb018-802">AU-NSW-NorthRyde-OER</span><span class="sxs-lookup"><span data-stu-id="fb018-802">AU-NSW-NorthRyde-OER</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-803">Ben Walters</span><span class="sxs-lookup"><span data-stu-id="fb018-803">Ben Walters</span></span></td>
<td align="left"><span data-ttu-id="fb018-804">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="fb018-804">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="fb018-805">Абонентская группа клиента</span><span class="sxs-lookup"><span data-stu-id="fb018-805">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="fb018-806">AU-NSW-NorthRyde-OER</span><span class="sxs-lookup"><span data-stu-id="fb018-806">AU-NSW-NorthRyde-OER</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-807">Christie Cline</span><span class="sxs-lookup"><span data-stu-id="fb018-807">Christie Cline</span></span></td>
<td align="left"><span data-ttu-id="fb018-808">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="fb018-808">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="fb018-809">Абонентская группа клиента</span><span class="sxs-lookup"><span data-stu-id="fb018-809">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="fb018-810">SG-Singapore-OMB</span><span class="sxs-lookup"><span data-stu-id="fb018-810">SG-Singapore-OMB</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-811">Debra Berger</span><span class="sxs-lookup"><span data-stu-id="fb018-811">Debra Berger</span></span></td>
<td align="left"><span data-ttu-id="fb018-812">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="fb018-812">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="fb018-813">Абонентская группа клиента</span><span class="sxs-lookup"><span data-stu-id="fb018-813">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="fb018-814">SG-Singapore-OMB</span><span class="sxs-lookup"><span data-stu-id="fb018-814">SG-Singapore-OMB</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-815">Lee Gu</span><span class="sxs-lookup"><span data-stu-id="fb018-815">Lee Gu</span></span></td>
<td align="left"><span data-ttu-id="fb018-816">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="fb018-816">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="fb018-817">Абонентская группа клиента</span><span class="sxs-lookup"><span data-stu-id="fb018-817">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="fb018-818">SG-Singapore-OMB</span><span class="sxs-lookup"><span data-stu-id="fb018-818">SG-Singapore-OMB</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-819">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="fb018-819">Emily Braun</span></span></td>
<td align="left"><span data-ttu-id="fb018-820">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="fb018-820">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="fb018-821">Служебная абонентская группа</span><span class="sxs-lookup"><span data-stu-id="fb018-821">Service dial plan</span></span></td>
<td align="left"><span data-ttu-id="fb018-822">Н/Д</span><span class="sxs-lookup"><span data-stu-id="fb018-822">N/A</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-823">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="fb018-823">Lidia Holloway</span></span></td>
<td align="left"><span data-ttu-id="fb018-824">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="fb018-824">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="fb018-825">Служебная абонентская группа</span><span class="sxs-lookup"><span data-stu-id="fb018-825">Service dial plan</span></span></td>
<td align="left"><span data-ttu-id="fb018-826">Н/Д</span><span class="sxs-lookup"><span data-stu-id="fb018-826">N/A</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-827">Pradeep Gupta</span><span class="sxs-lookup"><span data-stu-id="fb018-827">Pradeep Gupta</span></span></td>
<td align="left"><span data-ttu-id="fb018-828">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="fb018-828">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="fb018-829">Служебная абонентская группа</span><span class="sxs-lookup"><span data-stu-id="fb018-829">Service dial plan</span></span></td>
<td align="left"><span data-ttu-id="fb018-830">Н/Д</span><span class="sxs-lookup"><span data-stu-id="fb018-830">N/A</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-831">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="fb018-831">Marcel Beauchamp</span></span></td>
<td align="left"><span data-ttu-id="fb018-832">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="fb018-832">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="fb018-833">Абонентская группа клиента</span><span class="sxs-lookup"><span data-stu-id="fb018-833">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="fb018-834">FR-Paris-Issy-39qdPR</span><span class="sxs-lookup"><span data-stu-id="fb018-834">FR-Paris-Issy-39qdPR</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-835">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="fb018-835">Rachelle Cormier</span></span></td>
<td align="left"><span data-ttu-id="fb018-836">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="fb018-836">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="fb018-837">Абонентская группа клиента</span><span class="sxs-lookup"><span data-stu-id="fb018-837">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="fb018-838">FR-Paris-Issy-39qdPR</span><span class="sxs-lookup"><span data-stu-id="fb018-838">FR-Paris-Issy-39qdPR</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="fb018-839">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="fb018-839">Isabell Potvin</span></span></td>
<td align="left"><span data-ttu-id="fb018-840">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="fb018-840">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="fb018-841">Абонентская группа клиента</span><span class="sxs-lookup"><span data-stu-id="fb018-841">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="fb018-842">FR-Paris-Issy-39qdPR</span><span class="sxs-lookup"><span data-stu-id="fb018-842">FR-Paris-Issy-39qdPR</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fb018-843">_Табл. 14. Пример назначенных абонентских групп_</span><span class="sxs-lookup"><span data-stu-id="fb018-843">_Table 14 Example of dial plan assignments_</span></span>


## <a name="microsoft-teams-configurations"></a><span data-ttu-id="fb018-844">Конфигурации Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fb018-844">Microsoft Teams configurations</span></span>

<span data-ttu-id="fb018-845">Так как служба Аудиоконференций доступна только для запланированных собраний, нужно включить конфигурации на клиента, регулирующие планирование собраний (частные собрания и собрания канала).</span><span class="sxs-lookup"><span data-stu-id="fb018-845">Since Audio Conferencing is only available for scheduled meetings, tenant-level configurations that govern meeting scheduling (private and channel meetings) must be enabled.</span></span>


> [!NOTE]
> <span data-ttu-id="fb018-846">Если согласно применяемым в вашей организации требованиям соответствия все обсуждения на собраниях должны быть доступны для обнаружения, следует отключить частные собрания, когда организатор использует почтовый ящик в локальной организации Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="fb018-846">Currently, if your organization has compliance requirements to ensure all meeting discussions are discoverable, you should disable private meetings if the organizer has an Exchange on-premises mailbox.</span></span><br><br>
> <span data-ttu-id="fb018-847">При другом варианте использования, когда все собрания в организации должны быть видимы только <strong>приглашенным сторонам</strong>, во избежание раскрытия информации о собраниях неприглашенным сторонам рекомендуется запретить планирование собраний в <strong>каналах</strong>.</span><span class="sxs-lookup"><span data-stu-id="fb018-847">In another use case, if all meetings in the organization must be visible <strong>to invited parties</strong> only, to avoid disclosing meeting information to uninvited parties, we recommend that you disable the ability to schedule meetings in <strong>channels</strong>.</span></span>

<span data-ttu-id="fb018-848">Параметры, входящие в конфигурации на уровне клиента, применяются ко всем пользователям в организации и затронут все планирование собраний в Teams, а не только собрания Teams **со** службой Аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-848">The settings, available as tenant-level configurations, are applicable to all users in the organization, and will impact all meeting scheduling in Teams, not specific to Teams meetings **with** Audio Conferencing.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="fb018-849">Точка принятия решений</span><span class="sxs-lookup"><span data-stu-id="fb018-849">Decision Point</span></span></td>
<td align="left"><p><span data-ttu-id="fb018-850">Определите, нужно ли включить или отключить планирование частных собраний в организации.</span><span class="sxs-lookup"><span data-stu-id="fb018-850">Decide if the organization requires to enable or disable scheduling of private meetings.</span></span></p>
<p><span data-ttu-id="fb018-851">Определите, нужно ли включить или отключить планирование собраний канала в организации.</span><span class="sxs-lookup"><span data-stu-id="fb018-851">Decide if the organization requires to enable or disable scheduling of channel meetings.</span></span></p></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="fb018-852">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="fb018-852">Next Steps</span></span></td>
<td align="left"><p><span data-ttu-id="fb018-853">Задокументируйте конфигурации планирования собраний для Teams.</span><span class="sxs-lookup"><span data-stu-id="fb018-853">Document the meeting scheduling configurations for Teams.</span></span></p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="left"><span data-ttu-id="fb018-854"><strong>Allow scheduling for private meetings (Разрешить планирование для частных собраний)</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-854"><strong>Allow scheduling for private meetings</strong></span></span></td>
<td align="left"><span data-ttu-id="fb018-855">Включено</span><span class="sxs-lookup"><span data-stu-id="fb018-855">Enabled</span></span></td>
</tr>
</thead>
<thead>
<tr class="odd">
<td align="left"><span data-ttu-id="fb018-856"><strong>Allow scheduling for channel meetings (Разрешить планирование для собраний канала)</strong></span><span class="sxs-lookup"><span data-stu-id="fb018-856"><strong>Allow scheduling for channel meetings</strong></span></span></td>
<td align="left"><span data-ttu-id="fb018-857">Отключено</span><span class="sxs-lookup"><span data-stu-id="fb018-857">Disabled</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="fb018-858">_Табл. 15. Пример конфигураций собраний в Microsoft Teams_</span><span class="sxs-lookup"><span data-stu-id="fb018-858">_Table 15 Example of Microsoft Teams meetings configurations_</span></span>


## <a name="document-technical-implementation-plan"></a><span data-ttu-id="fb018-859">Документирование плана по технической реализации</span><span class="sxs-lookup"><span data-stu-id="fb018-859">Document technical implementation plan</span></span>

<span data-ttu-id="fb018-860">Используйте приведенные выше точки принятия решений для документирования плана по технической реализации.</span><span class="sxs-lookup"><span data-stu-id="fb018-860">Use the decision points above to document your technical implementation plan.</span></span>

<span data-ttu-id="fb018-861">Этот план по технической реализации предоставит проектной группе, которая может включать в себя партнера по FastTrack или развертыванию, необходимую информацию, позволяющую провести техническую адаптацию для внедрения Аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="fb018-861">This technical implementation plan will provide the project team, which can include FastTrack or a deployment partner, with the information required to execute the technical onboarding for the implementation of Audio Conferencing.</span></span>

<span data-ttu-id="fb018-862">В общем случае план по технической реализации содержит следующие основные разделы:</span><span class="sxs-lookup"><span data-stu-id="fb018-862">In general, a technical implementation plan will contain the following main sections:</span></span>

-   <span data-ttu-id="fb018-863">Список расположений для использования службы Аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="fb018-863">Audio Conferencing service site enablement list</span></span>

-   <span data-ttu-id="fb018-864">Список назначения лицензий для организаторов собраний Аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="fb018-864">License assignment list for Audio Conferencing meeting organizers</span></span>

-   <span data-ttu-id="fb018-865">Цифры для планирования Кредитов на связь</span><span class="sxs-lookup"><span data-stu-id="fb018-865">Communications Credits planning numbers</span></span>

-   <span data-ttu-id="fb018-866">Сведения о мосте конференций</span><span class="sxs-lookup"><span data-stu-id="fb018-866">Conference bridge details</span></span>

-   <span data-ttu-id="fb018-867">Параметры моста конференций</span><span class="sxs-lookup"><span data-stu-id="fb018-867">Conference bridge settings</span></span>

-   <span data-ttu-id="fb018-868">Назначенные параметры моста конференций</span><span class="sxs-lookup"><span data-stu-id="fb018-868">Conference bridge settings assignments</span></span>

-   <span data-ttu-id="fb018-869">Абонентские группы клиента</span><span class="sxs-lookup"><span data-stu-id="fb018-869">Tenant dial plans</span></span>

-   <span data-ttu-id="fb018-870">Назначенные абонентские группы</span><span class="sxs-lookup"><span data-stu-id="fb018-870">Dial plan assignments</span></span>

-   <span data-ttu-id="fb018-871">Конфигурации собраний Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fb018-871">Microsoft Teams meetings configurations</span></span>

<span data-ttu-id="fb018-872">После завершения работы над планами по достижению успеха и технической реализации ваша организация готова к переходу на следующий этап цикла взаимодействия с клиентом Office 365.</span><span class="sxs-lookup"><span data-stu-id="fb018-872">With the completion of success plan and technical implementation plan, you are now ready to take your organization to the next steps along the Office 365 customer journey.</span></span>

<a name="onboard"></a><span data-ttu-id="fb018-873">Адаптация</span><span class="sxs-lookup"><span data-stu-id="fb018-873">Onboard</span></span>
=======

<span data-ttu-id="fb018-874">*Ожидается в ближайшее время*.</span><span class="sxs-lookup"><span data-stu-id="fb018-874">*Coming soon.*</span></span>

<a name="drive-value"></a><span data-ttu-id="fb018-875">Извлечение выгоды</span><span class="sxs-lookup"><span data-stu-id="fb018-875">Drive Value</span></span>
===========

<span data-ttu-id="fb018-876">*Ожидается в ближайшее время*.</span><span class="sxs-lookup"><span data-stu-id="fb018-876">*Coming soon.*</span></span>



### <a name="see-also"></a><span data-ttu-id="fb018-877">См. также</span><span class="sxs-lookup"><span data-stu-id="fb018-877">See also</span></span>
[<span data-ttu-id="fb018-878">Настройка конференц-связи с телефонным подключением или по ТСОП в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="fb018-878">Set up dial-in or PSTN conferencing for Skype for Business</span></span>](https://support.office.com/article/Set-up-audio-conferencing-for-Skype-for-Business-and-Microsoft-Teams-d01954f1-4f37-4cf5-a636-20039e5c59e9)
