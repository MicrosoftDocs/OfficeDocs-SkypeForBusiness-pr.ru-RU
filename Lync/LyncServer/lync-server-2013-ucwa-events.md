---
title: 'Lync Server 2013: события UCWA'
description: 'Lync Server 2013: события UCWA.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8104ce9c7533350f40ce194e1cde205bc3692792
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548855"
---
# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="fecb1-103">События UCWA в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fecb1-103">UCWA events in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fecb1-104">_**Последнее изменение темы:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="fecb1-104">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="fecb1-105">Lync Server 2013 использует веб-API объединенных коммуникаций (UCWA) для выполнения различных задач, от доступа к Microsoft Exchange для поиска контактов для обновления сведений о присутствии для мобильных клиентов.</span><span class="sxs-lookup"><span data-stu-id="fecb1-105">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="fecb1-106">UCWA будет записывать записи оперативного поведения в виде информационных, предупреждений и ошибок типов событий.</span><span class="sxs-lookup"><span data-stu-id="fecb1-106">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="fecb1-107">В следующей таблице описываются события, которые могут быть записаны компонентами UCWA.</span><span class="sxs-lookup"><span data-stu-id="fecb1-107">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fecb1-108">Код события</span><span class="sxs-lookup"><span data-stu-id="fecb1-108">Event ID</span></span></th>
<th><span data-ttu-id="fecb1-109">Тип события</span><span class="sxs-lookup"><span data-stu-id="fecb1-109">Event Type</span></span></th>
<th><span data-ttu-id="fecb1-110">Аннотация</span><span class="sxs-lookup"><span data-stu-id="fecb1-110">Summary</span></span></th>
<th><span data-ttu-id="fecb1-111">Причина и решение</span><span class="sxs-lookup"><span data-stu-id="fecb1-111">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fecb1-112">20001</span><span class="sxs-lookup"><span data-stu-id="fecb1-112">20001</span></span></p></td>
<td><p><span data-ttu-id="fecb1-113">Справоч</span><span class="sxs-lookup"><span data-stu-id="fecb1-113">Informational</span></span></p></td>
<td><p><span data-ttu-id="fecb1-114">UCWA инициализировано</span><span class="sxs-lookup"><span data-stu-id="fecb1-114">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="fecb1-115">Н/Д</span><span class="sxs-lookup"><span data-stu-id="fecb1-115">N/A</span></span></p>
<p><span data-ttu-id="fecb1-116">Н/Д</span><span class="sxs-lookup"><span data-stu-id="fecb1-116">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fecb1-117">20002</span><span class="sxs-lookup"><span data-stu-id="fecb1-117">20002</span></span></p></td>
<td><p><span data-ttu-id="fecb1-118">Error</span><span class="sxs-lookup"><span data-stu-id="fecb1-118">Error</span></span></p></td>
<td><p><span data-ttu-id="fecb1-119">В UCWA возникло неожиданное исключение во время инициализации</span><span class="sxs-lookup"><span data-stu-id="fecb1-119">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="fecb1-120">Произошла непредвиденная ошибка во время инициализации</span><span class="sxs-lookup"><span data-stu-id="fecb1-120">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="fecb1-121">Изучите сведения об исключении в связанной записи журнала событий, чтобы определить возможную причину</span><span class="sxs-lookup"><span data-stu-id="fecb1-121">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fecb1-122">20003</span><span class="sxs-lookup"><span data-stu-id="fecb1-122">20003</span></span></p></td>
<td><p><span data-ttu-id="fecb1-123">Error</span><span class="sxs-lookup"><span data-stu-id="fecb1-123">Error</span></span></p></td>
<td><p><span data-ttu-id="fecb1-124">В UCWA возникло необработанное исключение</span><span class="sxs-lookup"><span data-stu-id="fecb1-124">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="fecb1-125">Произошло необработанное исключение</span><span class="sxs-lookup"><span data-stu-id="fecb1-125">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="fecb1-126">Перезапустите сервер.</span><span class="sxs-lookup"><span data-stu-id="fecb1-126">Restart the server.</span></span> <span data-ttu-id="fecb1-127">Если проблема не исчезнет, обратитесь в службу технической поддержки</span><span class="sxs-lookup"><span data-stu-id="fecb1-127">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fecb1-128">20004</span><span class="sxs-lookup"><span data-stu-id="fecb1-128">20004</span></span></p></td>
<td><p><span data-ttu-id="fecb1-129">Error</span><span class="sxs-lookup"><span data-stu-id="fecb1-129">Error</span></span></p></td>
<td><p><span data-ttu-id="fecb1-130">Не удается получить доступ к Exchange для фото в формате HD</span><span class="sxs-lookup"><span data-stu-id="fecb1-130">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="fecb1-131">Подключение к Exchange недоступно</span><span class="sxs-lookup"><span data-stu-id="fecb1-131">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="fecb1-132">Убедитесь, что подключение к Exchange доступно.</span><span class="sxs-lookup"><span data-stu-id="fecb1-132">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fecb1-133">20005</span><span class="sxs-lookup"><span data-stu-id="fecb1-133">20005</span></span></p></td>
<td><p><span data-ttu-id="fecb1-134">Справоч</span><span class="sxs-lookup"><span data-stu-id="fecb1-134">Informational</span></span></p></td>
<td><p><span data-ttu-id="fecb1-135">Восстановление после отказа в доступе к Exchange для фотографии HD</span><span class="sxs-lookup"><span data-stu-id="fecb1-135">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="fecb1-136">Недоступно</span><span class="sxs-lookup"><span data-stu-id="fecb1-136">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fecb1-137">20006</span><span class="sxs-lookup"><span data-stu-id="fecb1-137">20006</span></span></p></td>
<td><p><span data-ttu-id="fecb1-138">Error</span><span class="sxs-lookup"><span data-stu-id="fecb1-138">Error</span></span></p></td>
<td><p><span data-ttu-id="fecb1-139">Не удается получить доступ к Exchange для поиска контактов</span><span class="sxs-lookup"><span data-stu-id="fecb1-139">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="fecb1-140">Подключение к Exchange недоступно</span><span class="sxs-lookup"><span data-stu-id="fecb1-140">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="fecb1-141">Убедитесь, что подключение к Exchange доступно.</span><span class="sxs-lookup"><span data-stu-id="fecb1-141">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fecb1-142">20007</span><span class="sxs-lookup"><span data-stu-id="fecb1-142">20007</span></span></p></td>
<td><p><span data-ttu-id="fecb1-143">Справоч</span><span class="sxs-lookup"><span data-stu-id="fecb1-143">Informational</span></span></p></td>
<td><p><span data-ttu-id="fecb1-144">Восстановление после отказа поиска контакта в Exchange</span><span class="sxs-lookup"><span data-stu-id="fecb1-144">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="fecb1-145">Недоступно</span><span class="sxs-lookup"><span data-stu-id="fecb1-145">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fecb1-146">20008</span><span class="sxs-lookup"><span data-stu-id="fecb1-146">20008</span></span></p></td>
<td><p><span data-ttu-id="fecb1-147">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="fecb1-147">Warning</span></span></p></td>
<td><p><span data-ttu-id="fecb1-148">Попытка подписки на приложение более чем разрешенных подписок на присутствие</span><span class="sxs-lookup"><span data-stu-id="fecb1-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="fecb1-149">Попытка подписки на приложение более чем разрешенных подписок на присутствие</span><span class="sxs-lookup"><span data-stu-id="fecb1-149">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="fecb1-150">Проверка клиентов на наличие ненужных подписок</span><span class="sxs-lookup"><span data-stu-id="fecb1-150">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fecb1-151">20009</span><span class="sxs-lookup"><span data-stu-id="fecb1-151">20009</span></span></p></td>
<td><p><span data-ttu-id="fecb1-152">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="fecb1-152">Warning</span></span></p></td>
<td><p><span data-ttu-id="fecb1-153">Попытка подписки на пакет больше чем разрешенных подписок на присутствие</span><span class="sxs-lookup"><span data-stu-id="fecb1-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="fecb1-154">Попытка подписки на пакет больше чем разрешенных подписок на присутствие</span><span class="sxs-lookup"><span data-stu-id="fecb1-154">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="fecb1-155">Проверка клиентов на наличие ненужных подписок</span><span class="sxs-lookup"><span data-stu-id="fecb1-155">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fecb1-156">20010</span><span class="sxs-lookup"><span data-stu-id="fecb1-156">20010</span></span></p></td>
<td><p><span data-ttu-id="fecb1-157">Error</span><span class="sxs-lookup"><span data-stu-id="fecb1-157">Error</span></span></p></td>
<td><p><span data-ttu-id="fecb1-158">Не удается получить данные из диапазона</span><span class="sxs-lookup"><span data-stu-id="fecb1-158">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="fecb1-159">Не удается получить данные из диапазона</span><span class="sxs-lookup"><span data-stu-id="fecb1-159">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="fecb1-160">Если проблема не исчезнет, обратитесь в службу технической поддержки</span><span class="sxs-lookup"><span data-stu-id="fecb1-160">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fecb1-161">20011</span><span class="sxs-lookup"><span data-stu-id="fecb1-161">20011</span></span></p></td>
<td><p><span data-ttu-id="fecb1-162">Error</span><span class="sxs-lookup"><span data-stu-id="fecb1-162">Error</span></span></p></td>
<td><p><span data-ttu-id="fecb1-163">Не удается подписать сведения о присутствии</span><span class="sxs-lookup"><span data-stu-id="fecb1-163">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="fecb1-164">Не удается подписать сведения о присутствии</span><span class="sxs-lookup"><span data-stu-id="fecb1-164">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="fecb1-165">Если проблема не исчезнет, обратитесь в службу технической поддержки</span><span class="sxs-lookup"><span data-stu-id="fecb1-165">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fecb1-166">20012</span><span class="sxs-lookup"><span data-stu-id="fecb1-166">20012</span></span></p></td>
<td><p><span data-ttu-id="fecb1-167">Error</span><span class="sxs-lookup"><span data-stu-id="fecb1-167">Error</span></span></p></td>
<td><p><span data-ttu-id="fecb1-168">Не удалось зарегистрировать конечную точку</span><span class="sxs-lookup"><span data-stu-id="fecb1-168">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="fecb1-169">Не удалось зарегистрировать конечную точку</span><span class="sxs-lookup"><span data-stu-id="fecb1-169">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="fecb1-170">Если проблема не исчезнет, обратитесь в службу технической поддержки</span><span class="sxs-lookup"><span data-stu-id="fecb1-170">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fecb1-171">20013</span><span class="sxs-lookup"><span data-stu-id="fecb1-171">20013</span></span></p></td>
<td><p><span data-ttu-id="fecb1-172">Error</span><span class="sxs-lookup"><span data-stu-id="fecb1-172">Error</span></span></p></td>
<td><p><span data-ttu-id="fecb1-173">MCU IM недоступен</span><span class="sxs-lookup"><span data-stu-id="fecb1-173">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="fecb1-174">MCU IM недоступен</span><span class="sxs-lookup"><span data-stu-id="fecb1-174">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="fecb1-175">Проверьте, запущена ли служба мгновенных сообщений MCU</span><span class="sxs-lookup"><span data-stu-id="fecb1-175">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fecb1-176">20014</span><span class="sxs-lookup"><span data-stu-id="fecb1-176">20014</span></span></p></td>
<td><p><span data-ttu-id="fecb1-177">Справоч</span><span class="sxs-lookup"><span data-stu-id="fecb1-177">Informational</span></span></p></td>
<td><p><span data-ttu-id="fecb1-178">Восстановление после отказа к подключению к IM MCU</span><span class="sxs-lookup"><span data-stu-id="fecb1-178">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="fecb1-179">Недоступно</span><span class="sxs-lookup"><span data-stu-id="fecb1-179">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fecb1-180">20015</span><span class="sxs-lookup"><span data-stu-id="fecb1-180">20015</span></span></p></td>
<td><p><span data-ttu-id="fecb1-181">Error</span><span class="sxs-lookup"><span data-stu-id="fecb1-181">Error</span></span></p></td>
<td><p><span data-ttu-id="fecb1-182">AV MCU недоступен</span><span class="sxs-lookup"><span data-stu-id="fecb1-182">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="fecb1-183">AV MCU недоступен</span><span class="sxs-lookup"><span data-stu-id="fecb1-183">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="fecb1-184">Проверьте, работает ли AV MCU</span><span class="sxs-lookup"><span data-stu-id="fecb1-184">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fecb1-185">20016</span><span class="sxs-lookup"><span data-stu-id="fecb1-185">20016</span></span></p></td>
<td><p><span data-ttu-id="fecb1-186">Справоч</span><span class="sxs-lookup"><span data-stu-id="fecb1-186">Informational</span></span></p></td>
<td><p><span data-ttu-id="fecb1-187">Восстановление после отказа подключения к AV MCU</span><span class="sxs-lookup"><span data-stu-id="fecb1-187">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="fecb1-188">Недоступно</span><span class="sxs-lookup"><span data-stu-id="fecb1-188">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fecb1-189">20017</span><span class="sxs-lookup"><span data-stu-id="fecb1-189">20017</span></span></p></td>
<td><p><span data-ttu-id="fecb1-190">Error</span><span class="sxs-lookup"><span data-stu-id="fecb1-190">Error</span></span></p></td>
<td><p><span data-ttu-id="fecb1-191">Так как MCU недоступен</span><span class="sxs-lookup"><span data-stu-id="fecb1-191">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="fecb1-192">Так как MCU недоступен</span><span class="sxs-lookup"><span data-stu-id="fecb1-192">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="fecb1-193">Проверьте, работает ли как MCU</span><span class="sxs-lookup"><span data-stu-id="fecb1-193">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fecb1-194">20018</span><span class="sxs-lookup"><span data-stu-id="fecb1-194">20018</span></span></p></td>
<td><p><span data-ttu-id="fecb1-195">Справоч</span><span class="sxs-lookup"><span data-stu-id="fecb1-195">Informational</span></span></p></td>
<td><p><span data-ttu-id="fecb1-196">Восстановление после отказа к подключению в качестве MCU</span><span class="sxs-lookup"><span data-stu-id="fecb1-196">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="fecb1-197">Недоступно</span><span class="sxs-lookup"><span data-stu-id="fecb1-197">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fecb1-198">20019</span><span class="sxs-lookup"><span data-stu-id="fecb1-198">20019</span></span></p></td>
<td><p><span data-ttu-id="fecb1-199">Error</span><span class="sxs-lookup"><span data-stu-id="fecb1-199">Error</span></span></p></td>
<td><p><span data-ttu-id="fecb1-200">MCU данных недоступен</span><span class="sxs-lookup"><span data-stu-id="fecb1-200">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="fecb1-201">MCU данных недоступен</span><span class="sxs-lookup"><span data-stu-id="fecb1-201">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="fecb1-202">Проверьте, работает ли MCU данных</span><span class="sxs-lookup"><span data-stu-id="fecb1-202">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fecb1-203">20020</span><span class="sxs-lookup"><span data-stu-id="fecb1-203">20020</span></span></p></td>
<td><p><span data-ttu-id="fecb1-204">Справоч</span><span class="sxs-lookup"><span data-stu-id="fecb1-204">Informational</span></span></p></td>
<td><p><span data-ttu-id="fecb1-205">Восстановление после отказа подключения к данным MCU</span><span class="sxs-lookup"><span data-stu-id="fecb1-205">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="fecb1-206">Недоступно</span><span class="sxs-lookup"><span data-stu-id="fecb1-206">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fecb1-207">20021</span><span class="sxs-lookup"><span data-stu-id="fecb1-207">20021</span></span></p></td>
<td><p><span data-ttu-id="fecb1-208">Error</span><span class="sxs-lookup"><span data-stu-id="fecb1-208">Error</span></span></p></td>
<td><p><span data-ttu-id="fecb1-209">Не удается присоединиться к IM MCU</span><span class="sxs-lookup"><span data-stu-id="fecb1-209">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="fecb1-210">Не удается присоединиться к IM MCU</span><span class="sxs-lookup"><span data-stu-id="fecb1-210">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="fecb1-211">Проверьте, запущена ли служба мгновенных сообщений MCU</span><span class="sxs-lookup"><span data-stu-id="fecb1-211">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fecb1-212">20022</span><span class="sxs-lookup"><span data-stu-id="fecb1-212">20022</span></span></p></td>
<td><p><span data-ttu-id="fecb1-213">Error</span><span class="sxs-lookup"><span data-stu-id="fecb1-213">Error</span></span></p></td>
<td><p><span data-ttu-id="fecb1-214">Не удается присоединиться к AV MCU</span><span class="sxs-lookup"><span data-stu-id="fecb1-214">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="fecb1-215">Не удается присоединиться к AV MCU</span><span class="sxs-lookup"><span data-stu-id="fecb1-215">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="fecb1-216">Проверьте, работает ли AV MCU</span><span class="sxs-lookup"><span data-stu-id="fecb1-216">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fecb1-217">20023</span><span class="sxs-lookup"><span data-stu-id="fecb1-217">20023</span></span></p></td>
<td><p><span data-ttu-id="fecb1-218">Error</span><span class="sxs-lookup"><span data-stu-id="fecb1-218">Error</span></span></p></td>
<td><p><span data-ttu-id="fecb1-219">Не удается присоединиться к MCU</span><span class="sxs-lookup"><span data-stu-id="fecb1-219">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="fecb1-220">Не удается присоединиться к MCU</span><span class="sxs-lookup"><span data-stu-id="fecb1-220">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="fecb1-221">Проверьте, работает ли как MCU</span><span class="sxs-lookup"><span data-stu-id="fecb1-221">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fecb1-222">20024</span><span class="sxs-lookup"><span data-stu-id="fecb1-222">20024</span></span></p></td>
<td><p><span data-ttu-id="fecb1-223">Error</span><span class="sxs-lookup"><span data-stu-id="fecb1-223">Error</span></span></p></td>
<td><p><span data-ttu-id="fecb1-224">Не удается присоединиться к данным MCU</span><span class="sxs-lookup"><span data-stu-id="fecb1-224">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="fecb1-225">Не удается присоединиться к данным MCU</span><span class="sxs-lookup"><span data-stu-id="fecb1-225">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="fecb1-226">Проверьте, работает ли MCU данных</span><span class="sxs-lookup"><span data-stu-id="fecb1-226">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fecb1-227">20025</span><span class="sxs-lookup"><span data-stu-id="fecb1-227">20025</span></span></p></td>
<td><p><span data-ttu-id="fecb1-228">Error</span><span class="sxs-lookup"><span data-stu-id="fecb1-228">Error</span></span></p></td>
<td><p><span data-ttu-id="fecb1-229">Не удается получить доступ к Active Directory для фото</span><span class="sxs-lookup"><span data-stu-id="fecb1-229">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="fecb1-230">Подключение к Active Directory недоступно</span><span class="sxs-lookup"><span data-stu-id="fecb1-230">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="fecb1-231">Убедитесь, что подключение к Active Directory доступно.</span><span class="sxs-lookup"><span data-stu-id="fecb1-231">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fecb1-232">20026</span><span class="sxs-lookup"><span data-stu-id="fecb1-232">20026</span></span></p></td>
<td><p><span data-ttu-id="fecb1-233">Справоч</span><span class="sxs-lookup"><span data-stu-id="fecb1-233">Informational</span></span></p></td>
<td><p><span data-ttu-id="fecb1-234">Восстановление из строя доступа к Active Directory для фотографии</span><span class="sxs-lookup"><span data-stu-id="fecb1-234">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="fecb1-235">Недоступно</span><span class="sxs-lookup"><span data-stu-id="fecb1-235">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fecb1-236">20027</span><span class="sxs-lookup"><span data-stu-id="fecb1-236">20027</span></span></p></td>
<td><p><span data-ttu-id="fecb1-237">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="fecb1-237">Warning</span></span></p></td>
<td><p><span data-ttu-id="fecb1-238">Не удается десериализовать</span><span class="sxs-lookup"><span data-stu-id="fecb1-238">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="fecb1-239">Не удается десериализовать</span><span class="sxs-lookup"><span data-stu-id="fecb1-239">Cannot deserialize</span></span></p>
<p><span data-ttu-id="fecb1-240">Если проблема не исчезнет, обратитесь в службу технической поддержки</span><span class="sxs-lookup"><span data-stu-id="fecb1-240">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

