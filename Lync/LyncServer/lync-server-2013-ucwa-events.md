---
title: 'Lync Server 2013: события УКВА'
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
ms.openlocfilehash: b5063aca74fe3454569a2b2309be584a4ca11d13
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744859"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="9bc05-102">События УКВА в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9bc05-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bc05-103">_**Тема последнего изменения:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="9bc05-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="9bc05-104">Lync Server 2013 использует веб-API единой системы обмена сообщениями (УКВА) в нескольких целях, от доступа к Microsoft Exchange для поиска контактов для обновления сведений о присутствии для мобильных клиентов.</span><span class="sxs-lookup"><span data-stu-id="9bc05-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="9bc05-p101">UCWA занесет записи о рабочем поведении с типами событий "Информационный", "Предупреждение" и "Ошибка". В следующей таблице описываются события, которые могут регистрироваться компонентами UCWA.</span><span class="sxs-lookup"><span data-stu-id="9bc05-p101">UCWA will write records of operational behavior as event types Informational, Warning, and Error. The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9bc05-107">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="9bc05-107">Event ID</span></span></th>
<th><span data-ttu-id="9bc05-108">Тип события</span><span class="sxs-lookup"><span data-stu-id="9bc05-108">Event Type</span></span></th>
<th><span data-ttu-id="9bc05-109">Заключение</span><span class="sxs-lookup"><span data-stu-id="9bc05-109">Summary</span></span></th>
<th><span data-ttu-id="9bc05-110">Причина и решение проблемы</span><span class="sxs-lookup"><span data-stu-id="9bc05-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9bc05-111">20001</span><span class="sxs-lookup"><span data-stu-id="9bc05-111">20001</span></span></p></td>
<td><p><span data-ttu-id="9bc05-112">Информационный</span><span class="sxs-lookup"><span data-stu-id="9bc05-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="9bc05-113">Инициализировано UCWA</span><span class="sxs-lookup"><span data-stu-id="9bc05-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="9bc05-114">Н/Д</span><span class="sxs-lookup"><span data-stu-id="9bc05-114">N/A</span></span></p>
<p><span data-ttu-id="9bc05-115">Н/Д</span><span class="sxs-lookup"><span data-stu-id="9bc05-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bc05-116">20002</span><span class="sxs-lookup"><span data-stu-id="9bc05-116">20002</span></span></p></td>
<td><p><span data-ttu-id="9bc05-117">Ошибка</span><span class="sxs-lookup"><span data-stu-id="9bc05-117">Error</span></span></p></td>
<td><p><span data-ttu-id="9bc05-118">Во время инициализации UCWA возникло неожиданное исключение</span><span class="sxs-lookup"><span data-stu-id="9bc05-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="9bc05-119">Во время инициализации возникла неожиданная ошибка</span><span class="sxs-lookup"><span data-stu-id="9bc05-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="9bc05-120">Изучите сведения об исключении в соответствующей записи журнала событий, чтобы определить возможную причину</span><span class="sxs-lookup"><span data-stu-id="9bc05-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bc05-121">20003</span><span class="sxs-lookup"><span data-stu-id="9bc05-121">20003</span></span></p></td>
<td><p><span data-ttu-id="9bc05-122">Ошибка</span><span class="sxs-lookup"><span data-stu-id="9bc05-122">Error</span></span></p></td>
<td><p><span data-ttu-id="9bc05-123">В UCWA возникло необработанное исключение</span><span class="sxs-lookup"><span data-stu-id="9bc05-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="9bc05-124">Возникло необработанное исключение</span><span class="sxs-lookup"><span data-stu-id="9bc05-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="9bc05-p102">Перезапустите сервер. Если проблема не устранена, обратитесь в службу поддержки продукта.</span><span class="sxs-lookup"><span data-stu-id="9bc05-p102">Restart the server. If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bc05-127">20004</span><span class="sxs-lookup"><span data-stu-id="9bc05-127">20004</span></span></p></td>
<td><p><span data-ttu-id="9bc05-128">Ошибка</span><span class="sxs-lookup"><span data-stu-id="9bc05-128">Error</span></span></p></td>
<td><p><span data-ttu-id="9bc05-129">Не удается получить доступ к Exchange для фотографии с высоким разрешением</span><span class="sxs-lookup"><span data-stu-id="9bc05-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="9bc05-130">Недоступно подключение к Exchange</span><span class="sxs-lookup"><span data-stu-id="9bc05-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="9bc05-131">Убедитесь в доступности соединения с Exchange</span><span class="sxs-lookup"><span data-stu-id="9bc05-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bc05-132">20005</span><span class="sxs-lookup"><span data-stu-id="9bc05-132">20005</span></span></p></td>
<td><p><span data-ttu-id="9bc05-133">Информационный</span><span class="sxs-lookup"><span data-stu-id="9bc05-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="9bc05-134">Восстановление после сбоя доступа к Exchange для фотографии с высоким разрешением</span><span class="sxs-lookup"><span data-stu-id="9bc05-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="9bc05-135">Н/Д</span><span class="sxs-lookup"><span data-stu-id="9bc05-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bc05-136">20006</span><span class="sxs-lookup"><span data-stu-id="9bc05-136">20006</span></span></p></td>
<td><p><span data-ttu-id="9bc05-137">Ошибка</span><span class="sxs-lookup"><span data-stu-id="9bc05-137">Error</span></span></p></td>
<td><p><span data-ttu-id="9bc05-138">Не удается получить доступ к Exchange для поиска контакта</span><span class="sxs-lookup"><span data-stu-id="9bc05-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="9bc05-139">Недоступно подключение к Exchange</span><span class="sxs-lookup"><span data-stu-id="9bc05-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="9bc05-140">Убедитесь в доступности соединения с Exchange</span><span class="sxs-lookup"><span data-stu-id="9bc05-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bc05-141">20007</span><span class="sxs-lookup"><span data-stu-id="9bc05-141">20007</span></span></p></td>
<td><p><span data-ttu-id="9bc05-142">Информационный</span><span class="sxs-lookup"><span data-stu-id="9bc05-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="9bc05-143">Восстановление после сбоя поиска контакта в Exchange</span><span class="sxs-lookup"><span data-stu-id="9bc05-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="9bc05-144">Н/Д</span><span class="sxs-lookup"><span data-stu-id="9bc05-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bc05-145">20008</span><span class="sxs-lookup"><span data-stu-id="9bc05-145">20008</span></span></p></td>
<td><p><span data-ttu-id="9bc05-146">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="9bc05-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="9bc05-147">Попытка оформления числа подписок, превышающего допустимое количество подписок на сведения о присутствии для приложения</span><span class="sxs-lookup"><span data-stu-id="9bc05-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="9bc05-148">Попытка оформления числа подписок, превышающего допустимое количество подписок на сведения о присутствии для приложения</span><span class="sxs-lookup"><span data-stu-id="9bc05-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="9bc05-149">Проверьте клиенты на наличие лишних подписок</span><span class="sxs-lookup"><span data-stu-id="9bc05-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bc05-150">20009</span><span class="sxs-lookup"><span data-stu-id="9bc05-150">20009</span></span></p></td>
<td><p><span data-ttu-id="9bc05-151">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="9bc05-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="9bc05-152">Попытка оформления числа подписок, превышающего допустимое количество подписок на сведения о присутствии для пакета</span><span class="sxs-lookup"><span data-stu-id="9bc05-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="9bc05-153">Попытка оформления числа подписок, превышающего допустимое количество подписок на сведения о присутствии для пакета</span><span class="sxs-lookup"><span data-stu-id="9bc05-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="9bc05-154">Проверьте клиенты на наличие лишних подписок</span><span class="sxs-lookup"><span data-stu-id="9bc05-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bc05-155">20010</span><span class="sxs-lookup"><span data-stu-id="9bc05-155">20010</span></span></p></td>
<td><p><span data-ttu-id="9bc05-156">Ошибка</span><span class="sxs-lookup"><span data-stu-id="9bc05-156">Error</span></span></p></td>
<td><p><span data-ttu-id="9bc05-157">Не удается получить внутриполосные данные</span><span class="sxs-lookup"><span data-stu-id="9bc05-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="9bc05-158">Не удается получить внутриполосные данные</span><span class="sxs-lookup"><span data-stu-id="9bc05-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="9bc05-159">Если проблема не устранена, обратитесь в службу поддержки продукта.</span><span class="sxs-lookup"><span data-stu-id="9bc05-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bc05-160">20011</span><span class="sxs-lookup"><span data-stu-id="9bc05-160">20011</span></span></p></td>
<td><p><span data-ttu-id="9bc05-161">Ошибка</span><span class="sxs-lookup"><span data-stu-id="9bc05-161">Error</span></span></p></td>
<td><p><span data-ttu-id="9bc05-162">Не удается подписаться на сведения о присутствии</span><span class="sxs-lookup"><span data-stu-id="9bc05-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="9bc05-163">Не удается подписаться на сведения о присутствии</span><span class="sxs-lookup"><span data-stu-id="9bc05-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="9bc05-164">Если проблема не устранена, обратитесь в службу поддержки продукта.</span><span class="sxs-lookup"><span data-stu-id="9bc05-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bc05-165">20012</span><span class="sxs-lookup"><span data-stu-id="9bc05-165">20012</span></span></p></td>
<td><p><span data-ttu-id="9bc05-166">Ошибка</span><span class="sxs-lookup"><span data-stu-id="9bc05-166">Error</span></span></p></td>
<td><p><span data-ttu-id="9bc05-167">Не удалось зарегистрировать конечную точку</span><span class="sxs-lookup"><span data-stu-id="9bc05-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="9bc05-168">Не удалось зарегистрировать конечную точку</span><span class="sxs-lookup"><span data-stu-id="9bc05-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="9bc05-169">Если проблема не устранена, обратитесь в службу поддержки продукта.</span><span class="sxs-lookup"><span data-stu-id="9bc05-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bc05-170">20013</span><span class="sxs-lookup"><span data-stu-id="9bc05-170">20013</span></span></p></td>
<td><p><span data-ttu-id="9bc05-171">Ошибка</span><span class="sxs-lookup"><span data-stu-id="9bc05-171">Error</span></span></p></td>
<td><p><span data-ttu-id="9bc05-172">IM MCU недоступен</span><span class="sxs-lookup"><span data-stu-id="9bc05-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="9bc05-173">IM MCU недоступен</span><span class="sxs-lookup"><span data-stu-id="9bc05-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="9bc05-174">Проверьте, запущен ли IM MCU</span><span class="sxs-lookup"><span data-stu-id="9bc05-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bc05-175">20014</span><span class="sxs-lookup"><span data-stu-id="9bc05-175">20014</span></span></p></td>
<td><p><span data-ttu-id="9bc05-176">Информационный</span><span class="sxs-lookup"><span data-stu-id="9bc05-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="9bc05-177">Восстановление после сбоя подключения к IM MCU</span><span class="sxs-lookup"><span data-stu-id="9bc05-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="9bc05-178">Н/Д</span><span class="sxs-lookup"><span data-stu-id="9bc05-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bc05-179">20015</span><span class="sxs-lookup"><span data-stu-id="9bc05-179">20015</span></span></p></td>
<td><p><span data-ttu-id="9bc05-180">Ошибка</span><span class="sxs-lookup"><span data-stu-id="9bc05-180">Error</span></span></p></td>
<td><p><span data-ttu-id="9bc05-181">AV MCU недоступен</span><span class="sxs-lookup"><span data-stu-id="9bc05-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="9bc05-182">AV MCU недоступен</span><span class="sxs-lookup"><span data-stu-id="9bc05-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="9bc05-183">Проверьте, запущен ли AV MCU</span><span class="sxs-lookup"><span data-stu-id="9bc05-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bc05-184">20016</span><span class="sxs-lookup"><span data-stu-id="9bc05-184">20016</span></span></p></td>
<td><p><span data-ttu-id="9bc05-185">Информационный</span><span class="sxs-lookup"><span data-stu-id="9bc05-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="9bc05-186">Восстановление после сбоя подключения к AV MCU</span><span class="sxs-lookup"><span data-stu-id="9bc05-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="9bc05-187">Н/Д</span><span class="sxs-lookup"><span data-stu-id="9bc05-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bc05-188">20017</span><span class="sxs-lookup"><span data-stu-id="9bc05-188">20017</span></span></p></td>
<td><p><span data-ttu-id="9bc05-189">Ошибка</span><span class="sxs-lookup"><span data-stu-id="9bc05-189">Error</span></span></p></td>
<td><p><span data-ttu-id="9bc05-190">AS MCU недоступен</span><span class="sxs-lookup"><span data-stu-id="9bc05-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="9bc05-191">AS MCU недоступен</span><span class="sxs-lookup"><span data-stu-id="9bc05-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="9bc05-192">Проверьте, запущен ли AS MCU</span><span class="sxs-lookup"><span data-stu-id="9bc05-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bc05-193">20018</span><span class="sxs-lookup"><span data-stu-id="9bc05-193">20018</span></span></p></td>
<td><p><span data-ttu-id="9bc05-194">Информационный</span><span class="sxs-lookup"><span data-stu-id="9bc05-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="9bc05-195">Восстановление после сбоя подключения к AS MCU</span><span class="sxs-lookup"><span data-stu-id="9bc05-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="9bc05-196">Н/Д</span><span class="sxs-lookup"><span data-stu-id="9bc05-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bc05-197">20019</span><span class="sxs-lookup"><span data-stu-id="9bc05-197">20019</span></span></p></td>
<td><p><span data-ttu-id="9bc05-198">Ошибка</span><span class="sxs-lookup"><span data-stu-id="9bc05-198">Error</span></span></p></td>
<td><p><span data-ttu-id="9bc05-199">MCU данных недоступен</span><span class="sxs-lookup"><span data-stu-id="9bc05-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="9bc05-200">MCU данных недоступен</span><span class="sxs-lookup"><span data-stu-id="9bc05-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="9bc05-201">Проверьте, запущен ли MCU данных</span><span class="sxs-lookup"><span data-stu-id="9bc05-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bc05-202">20020</span><span class="sxs-lookup"><span data-stu-id="9bc05-202">20020</span></span></p></td>
<td><p><span data-ttu-id="9bc05-203">Информационный</span><span class="sxs-lookup"><span data-stu-id="9bc05-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="9bc05-204">Восстановление после сбоя подключения к MCU данных</span><span class="sxs-lookup"><span data-stu-id="9bc05-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="9bc05-205">Н/Д</span><span class="sxs-lookup"><span data-stu-id="9bc05-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bc05-206">20021</span><span class="sxs-lookup"><span data-stu-id="9bc05-206">20021</span></span></p></td>
<td><p><span data-ttu-id="9bc05-207">Ошибка</span><span class="sxs-lookup"><span data-stu-id="9bc05-207">Error</span></span></p></td>
<td><p><span data-ttu-id="9bc05-208">Не удается присоединиться к IM MCU</span><span class="sxs-lookup"><span data-stu-id="9bc05-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="9bc05-209">Не удается присоединиться к IM MCU</span><span class="sxs-lookup"><span data-stu-id="9bc05-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="9bc05-210">Проверьте, запущен ли IM MCU</span><span class="sxs-lookup"><span data-stu-id="9bc05-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bc05-211">20022</span><span class="sxs-lookup"><span data-stu-id="9bc05-211">20022</span></span></p></td>
<td><p><span data-ttu-id="9bc05-212">Ошибка</span><span class="sxs-lookup"><span data-stu-id="9bc05-212">Error</span></span></p></td>
<td><p><span data-ttu-id="9bc05-213">Не удается присоединиться к AV MCU</span><span class="sxs-lookup"><span data-stu-id="9bc05-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="9bc05-214">Не удается присоединиться к AV MCU</span><span class="sxs-lookup"><span data-stu-id="9bc05-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="9bc05-215">Проверьте, запущен ли AV MCU</span><span class="sxs-lookup"><span data-stu-id="9bc05-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bc05-216">20023</span><span class="sxs-lookup"><span data-stu-id="9bc05-216">20023</span></span></p></td>
<td><p><span data-ttu-id="9bc05-217">Ошибка</span><span class="sxs-lookup"><span data-stu-id="9bc05-217">Error</span></span></p></td>
<td><p><span data-ttu-id="9bc05-218">Не удается присоединиться к AS MCU</span><span class="sxs-lookup"><span data-stu-id="9bc05-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="9bc05-219">Не удается присоединиться к AS MCU</span><span class="sxs-lookup"><span data-stu-id="9bc05-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="9bc05-220">Проверьте, запущен ли AS MCU</span><span class="sxs-lookup"><span data-stu-id="9bc05-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bc05-221">20024</span><span class="sxs-lookup"><span data-stu-id="9bc05-221">20024</span></span></p></td>
<td><p><span data-ttu-id="9bc05-222">Ошибка</span><span class="sxs-lookup"><span data-stu-id="9bc05-222">Error</span></span></p></td>
<td><p><span data-ttu-id="9bc05-223">Не удается присоединиться к MCU данных</span><span class="sxs-lookup"><span data-stu-id="9bc05-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="9bc05-224">Не удается присоединиться к MCU данных</span><span class="sxs-lookup"><span data-stu-id="9bc05-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="9bc05-225">Проверьте, запущен ли MCU данных</span><span class="sxs-lookup"><span data-stu-id="9bc05-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bc05-226">20025</span><span class="sxs-lookup"><span data-stu-id="9bc05-226">20025</span></span></p></td>
<td><p><span data-ttu-id="9bc05-227">Ошибка</span><span class="sxs-lookup"><span data-stu-id="9bc05-227">Error</span></span></p></td>
<td><p><span data-ttu-id="9bc05-228">Не удается получить доступ к Active Directory для фотографии</span><span class="sxs-lookup"><span data-stu-id="9bc05-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="9bc05-229">Недоступно подключение к Active Directory</span><span class="sxs-lookup"><span data-stu-id="9bc05-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="9bc05-230">Убедитесь в доступности соединения с Active Directory</span><span class="sxs-lookup"><span data-stu-id="9bc05-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bc05-231">20026</span><span class="sxs-lookup"><span data-stu-id="9bc05-231">20026</span></span></p></td>
<td><p><span data-ttu-id="9bc05-232">Информационный</span><span class="sxs-lookup"><span data-stu-id="9bc05-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="9bc05-233">Восстановление после сбоя доступа к Active Directory для фотографии</span><span class="sxs-lookup"><span data-stu-id="9bc05-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="9bc05-234">Н/Д</span><span class="sxs-lookup"><span data-stu-id="9bc05-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bc05-235">20027</span><span class="sxs-lookup"><span data-stu-id="9bc05-235">20027</span></span></p></td>
<td><p><span data-ttu-id="9bc05-236">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="9bc05-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="9bc05-237">Не удается выполнить десериализацию</span><span class="sxs-lookup"><span data-stu-id="9bc05-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="9bc05-238">Не удается выполнить десериализацию</span><span class="sxs-lookup"><span data-stu-id="9bc05-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="9bc05-239">Если проблема не устранена, обратитесь в службу поддержки продукта.</span><span class="sxs-lookup"><span data-stu-id="9bc05-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

