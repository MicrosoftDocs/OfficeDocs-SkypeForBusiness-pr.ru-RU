---
title: 'Lync Server 2013: события УКВА'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0671b51e5fbd4b5f072676855d9e8f5201b3e04
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="d5f33-102">События УКВА в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5f33-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5f33-103">_**Тема последнего изменения:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="d5f33-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="d5f33-104">Lync Server 2013 использует веб-API единой системы обмена сообщениями (УКВА) в нескольких целях, от доступа к Microsoft Exchange для поиска контактов для обновления сведений о присутствии для мобильных клиентов.</span><span class="sxs-lookup"><span data-stu-id="d5f33-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="d5f33-p101">UCWA занесет записи о рабочем поведении с типами событий "Информационный", "Предупреждение" и "Ошибка". В следующей таблице описываются события, которые могут регистрироваться компонентами UCWA.</span><span class="sxs-lookup"><span data-stu-id="d5f33-p101">UCWA will write records of operational behavior as event types Informational, Warning, and Error. The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d5f33-107">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="d5f33-107">Event ID</span></span></th>
<th><span data-ttu-id="d5f33-108">Тип события</span><span class="sxs-lookup"><span data-stu-id="d5f33-108">Event Type</span></span></th>
<th><span data-ttu-id="d5f33-109">Заключение</span><span class="sxs-lookup"><span data-stu-id="d5f33-109">Summary</span></span></th>
<th><span data-ttu-id="d5f33-110">Причина и решение проблемы</span><span class="sxs-lookup"><span data-stu-id="d5f33-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5f33-111">20001</span><span class="sxs-lookup"><span data-stu-id="d5f33-111">20001</span></span></p></td>
<td><p><span data-ttu-id="d5f33-112">Информационный</span><span class="sxs-lookup"><span data-stu-id="d5f33-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="d5f33-113">Инициализировано UCWA</span><span class="sxs-lookup"><span data-stu-id="d5f33-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="d5f33-114">Н/Д</span><span class="sxs-lookup"><span data-stu-id="d5f33-114">N/A</span></span></p>
<p><span data-ttu-id="d5f33-115">Н/Д</span><span class="sxs-lookup"><span data-stu-id="d5f33-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5f33-116">20002</span><span class="sxs-lookup"><span data-stu-id="d5f33-116">20002</span></span></p></td>
<td><p><span data-ttu-id="d5f33-117">Ошибка</span><span class="sxs-lookup"><span data-stu-id="d5f33-117">Error</span></span></p></td>
<td><p><span data-ttu-id="d5f33-118">Во время инициализации UCWA возникло неожиданное исключение</span><span class="sxs-lookup"><span data-stu-id="d5f33-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="d5f33-119">Во время инициализации возникла неожиданная ошибка</span><span class="sxs-lookup"><span data-stu-id="d5f33-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="d5f33-120">Изучите сведения об исключении в соответствующей записи журнала событий, чтобы определить возможную причину</span><span class="sxs-lookup"><span data-stu-id="d5f33-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5f33-121">20003</span><span class="sxs-lookup"><span data-stu-id="d5f33-121">20003</span></span></p></td>
<td><p><span data-ttu-id="d5f33-122">Ошибка</span><span class="sxs-lookup"><span data-stu-id="d5f33-122">Error</span></span></p></td>
<td><p><span data-ttu-id="d5f33-123">В UCWA возникло необработанное исключение</span><span class="sxs-lookup"><span data-stu-id="d5f33-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="d5f33-124">Возникло необработанное исключение</span><span class="sxs-lookup"><span data-stu-id="d5f33-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="d5f33-p102">Перезапустите сервер. Если проблема не устранена, обратитесь в службу поддержки продукта.</span><span class="sxs-lookup"><span data-stu-id="d5f33-p102">Restart the server. If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5f33-127">20004</span><span class="sxs-lookup"><span data-stu-id="d5f33-127">20004</span></span></p></td>
<td><p><span data-ttu-id="d5f33-128">Ошибка</span><span class="sxs-lookup"><span data-stu-id="d5f33-128">Error</span></span></p></td>
<td><p><span data-ttu-id="d5f33-129">Не удается получить доступ к Exchange для фотографии с высоким разрешением</span><span class="sxs-lookup"><span data-stu-id="d5f33-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="d5f33-130">Недоступно подключение к Exchange</span><span class="sxs-lookup"><span data-stu-id="d5f33-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="d5f33-131">Убедитесь в доступности соединения с Exchange</span><span class="sxs-lookup"><span data-stu-id="d5f33-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5f33-132">20005</span><span class="sxs-lookup"><span data-stu-id="d5f33-132">20005</span></span></p></td>
<td><p><span data-ttu-id="d5f33-133">Информационный</span><span class="sxs-lookup"><span data-stu-id="d5f33-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="d5f33-134">Восстановление после сбоя доступа к Exchange для фотографии с высоким разрешением</span><span class="sxs-lookup"><span data-stu-id="d5f33-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="d5f33-135">Н/Д</span><span class="sxs-lookup"><span data-stu-id="d5f33-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5f33-136">20006</span><span class="sxs-lookup"><span data-stu-id="d5f33-136">20006</span></span></p></td>
<td><p><span data-ttu-id="d5f33-137">Ошибка</span><span class="sxs-lookup"><span data-stu-id="d5f33-137">Error</span></span></p></td>
<td><p><span data-ttu-id="d5f33-138">Не удается получить доступ к Exchange для поиска контакта</span><span class="sxs-lookup"><span data-stu-id="d5f33-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="d5f33-139">Недоступно подключение к Exchange</span><span class="sxs-lookup"><span data-stu-id="d5f33-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="d5f33-140">Убедитесь в доступности соединения с Exchange</span><span class="sxs-lookup"><span data-stu-id="d5f33-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5f33-141">20007</span><span class="sxs-lookup"><span data-stu-id="d5f33-141">20007</span></span></p></td>
<td><p><span data-ttu-id="d5f33-142">Информационный</span><span class="sxs-lookup"><span data-stu-id="d5f33-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="d5f33-143">Восстановление после сбоя поиска контакта в Exchange</span><span class="sxs-lookup"><span data-stu-id="d5f33-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="d5f33-144">Н/Д</span><span class="sxs-lookup"><span data-stu-id="d5f33-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5f33-145">20008</span><span class="sxs-lookup"><span data-stu-id="d5f33-145">20008</span></span></p></td>
<td><p><span data-ttu-id="d5f33-146">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="d5f33-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="d5f33-147">Попытка оформления числа подписок, превышающего допустимое количество подписок на сведения о присутствии для приложения</span><span class="sxs-lookup"><span data-stu-id="d5f33-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="d5f33-148">Попытка оформления числа подписок, превышающего допустимое количество подписок на сведения о присутствии для приложения</span><span class="sxs-lookup"><span data-stu-id="d5f33-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="d5f33-149">Проверьте клиенты на наличие лишних подписок</span><span class="sxs-lookup"><span data-stu-id="d5f33-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5f33-150">20009</span><span class="sxs-lookup"><span data-stu-id="d5f33-150">20009</span></span></p></td>
<td><p><span data-ttu-id="d5f33-151">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="d5f33-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="d5f33-152">Попытка оформления числа подписок, превышающего допустимое количество подписок на сведения о присутствии для пакета</span><span class="sxs-lookup"><span data-stu-id="d5f33-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="d5f33-153">Попытка оформления числа подписок, превышающего допустимое количество подписок на сведения о присутствии для пакета</span><span class="sxs-lookup"><span data-stu-id="d5f33-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="d5f33-154">Проверьте клиенты на наличие лишних подписок</span><span class="sxs-lookup"><span data-stu-id="d5f33-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5f33-155">20010</span><span class="sxs-lookup"><span data-stu-id="d5f33-155">20010</span></span></p></td>
<td><p><span data-ttu-id="d5f33-156">Ошибка</span><span class="sxs-lookup"><span data-stu-id="d5f33-156">Error</span></span></p></td>
<td><p><span data-ttu-id="d5f33-157">Не удается получить внутриполосные данные</span><span class="sxs-lookup"><span data-stu-id="d5f33-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="d5f33-158">Не удается получить внутриполосные данные</span><span class="sxs-lookup"><span data-stu-id="d5f33-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="d5f33-159">Если проблема не устранена, обратитесь в службу поддержки продукта.</span><span class="sxs-lookup"><span data-stu-id="d5f33-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5f33-160">20011</span><span class="sxs-lookup"><span data-stu-id="d5f33-160">20011</span></span></p></td>
<td><p><span data-ttu-id="d5f33-161">Ошибка</span><span class="sxs-lookup"><span data-stu-id="d5f33-161">Error</span></span></p></td>
<td><p><span data-ttu-id="d5f33-162">Не удается подписаться на сведения о присутствии</span><span class="sxs-lookup"><span data-stu-id="d5f33-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="d5f33-163">Не удается подписаться на сведения о присутствии</span><span class="sxs-lookup"><span data-stu-id="d5f33-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="d5f33-164">Если проблема не устранена, обратитесь в службу поддержки продукта.</span><span class="sxs-lookup"><span data-stu-id="d5f33-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5f33-165">20012</span><span class="sxs-lookup"><span data-stu-id="d5f33-165">20012</span></span></p></td>
<td><p><span data-ttu-id="d5f33-166">Ошибка</span><span class="sxs-lookup"><span data-stu-id="d5f33-166">Error</span></span></p></td>
<td><p><span data-ttu-id="d5f33-167">Не удалось зарегистрировать конечную точку</span><span class="sxs-lookup"><span data-stu-id="d5f33-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="d5f33-168">Не удалось зарегистрировать конечную точку</span><span class="sxs-lookup"><span data-stu-id="d5f33-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="d5f33-169">Если проблема не устранена, обратитесь в службу поддержки продукта.</span><span class="sxs-lookup"><span data-stu-id="d5f33-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5f33-170">20013</span><span class="sxs-lookup"><span data-stu-id="d5f33-170">20013</span></span></p></td>
<td><p><span data-ttu-id="d5f33-171">Ошибка</span><span class="sxs-lookup"><span data-stu-id="d5f33-171">Error</span></span></p></td>
<td><p><span data-ttu-id="d5f33-172">IM MCU недоступен</span><span class="sxs-lookup"><span data-stu-id="d5f33-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="d5f33-173">IM MCU недоступен</span><span class="sxs-lookup"><span data-stu-id="d5f33-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="d5f33-174">Проверьте, запущен ли IM MCU</span><span class="sxs-lookup"><span data-stu-id="d5f33-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5f33-175">20014</span><span class="sxs-lookup"><span data-stu-id="d5f33-175">20014</span></span></p></td>
<td><p><span data-ttu-id="d5f33-176">Информационный</span><span class="sxs-lookup"><span data-stu-id="d5f33-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="d5f33-177">Восстановление после сбоя подключения к IM MCU</span><span class="sxs-lookup"><span data-stu-id="d5f33-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="d5f33-178">Н/Д</span><span class="sxs-lookup"><span data-stu-id="d5f33-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5f33-179">20015</span><span class="sxs-lookup"><span data-stu-id="d5f33-179">20015</span></span></p></td>
<td><p><span data-ttu-id="d5f33-180">Ошибка</span><span class="sxs-lookup"><span data-stu-id="d5f33-180">Error</span></span></p></td>
<td><p><span data-ttu-id="d5f33-181">AV MCU недоступен</span><span class="sxs-lookup"><span data-stu-id="d5f33-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="d5f33-182">AV MCU недоступен</span><span class="sxs-lookup"><span data-stu-id="d5f33-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="d5f33-183">Проверьте, запущен ли AV MCU</span><span class="sxs-lookup"><span data-stu-id="d5f33-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5f33-184">20016</span><span class="sxs-lookup"><span data-stu-id="d5f33-184">20016</span></span></p></td>
<td><p><span data-ttu-id="d5f33-185">Информационный</span><span class="sxs-lookup"><span data-stu-id="d5f33-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="d5f33-186">Восстановление после сбоя подключения к AV MCU</span><span class="sxs-lookup"><span data-stu-id="d5f33-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="d5f33-187">Н/Д</span><span class="sxs-lookup"><span data-stu-id="d5f33-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5f33-188">20017</span><span class="sxs-lookup"><span data-stu-id="d5f33-188">20017</span></span></p></td>
<td><p><span data-ttu-id="d5f33-189">Ошибка</span><span class="sxs-lookup"><span data-stu-id="d5f33-189">Error</span></span></p></td>
<td><p><span data-ttu-id="d5f33-190">AS MCU недоступен</span><span class="sxs-lookup"><span data-stu-id="d5f33-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="d5f33-191">AS MCU недоступен</span><span class="sxs-lookup"><span data-stu-id="d5f33-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="d5f33-192">Проверьте, запущен ли AS MCU</span><span class="sxs-lookup"><span data-stu-id="d5f33-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5f33-193">20018</span><span class="sxs-lookup"><span data-stu-id="d5f33-193">20018</span></span></p></td>
<td><p><span data-ttu-id="d5f33-194">Информационный</span><span class="sxs-lookup"><span data-stu-id="d5f33-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="d5f33-195">Восстановление после сбоя подключения к AS MCU</span><span class="sxs-lookup"><span data-stu-id="d5f33-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="d5f33-196">Н/Д</span><span class="sxs-lookup"><span data-stu-id="d5f33-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5f33-197">20019</span><span class="sxs-lookup"><span data-stu-id="d5f33-197">20019</span></span></p></td>
<td><p><span data-ttu-id="d5f33-198">Ошибка</span><span class="sxs-lookup"><span data-stu-id="d5f33-198">Error</span></span></p></td>
<td><p><span data-ttu-id="d5f33-199">MCU данных недоступен</span><span class="sxs-lookup"><span data-stu-id="d5f33-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="d5f33-200">MCU данных недоступен</span><span class="sxs-lookup"><span data-stu-id="d5f33-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="d5f33-201">Проверьте, запущен ли MCU данных</span><span class="sxs-lookup"><span data-stu-id="d5f33-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5f33-202">20020</span><span class="sxs-lookup"><span data-stu-id="d5f33-202">20020</span></span></p></td>
<td><p><span data-ttu-id="d5f33-203">Информационный</span><span class="sxs-lookup"><span data-stu-id="d5f33-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="d5f33-204">Восстановление после сбоя подключения к MCU данных</span><span class="sxs-lookup"><span data-stu-id="d5f33-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="d5f33-205">Н/Д</span><span class="sxs-lookup"><span data-stu-id="d5f33-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5f33-206">20021</span><span class="sxs-lookup"><span data-stu-id="d5f33-206">20021</span></span></p></td>
<td><p><span data-ttu-id="d5f33-207">Ошибка</span><span class="sxs-lookup"><span data-stu-id="d5f33-207">Error</span></span></p></td>
<td><p><span data-ttu-id="d5f33-208">Не удается присоединиться к IM MCU</span><span class="sxs-lookup"><span data-stu-id="d5f33-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="d5f33-209">Не удается присоединиться к IM MCU</span><span class="sxs-lookup"><span data-stu-id="d5f33-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="d5f33-210">Проверьте, запущен ли IM MCU</span><span class="sxs-lookup"><span data-stu-id="d5f33-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5f33-211">20022</span><span class="sxs-lookup"><span data-stu-id="d5f33-211">20022</span></span></p></td>
<td><p><span data-ttu-id="d5f33-212">Ошибка</span><span class="sxs-lookup"><span data-stu-id="d5f33-212">Error</span></span></p></td>
<td><p><span data-ttu-id="d5f33-213">Не удается присоединиться к AV MCU</span><span class="sxs-lookup"><span data-stu-id="d5f33-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="d5f33-214">Не удается присоединиться к AV MCU</span><span class="sxs-lookup"><span data-stu-id="d5f33-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="d5f33-215">Проверьте, запущен ли AV MCU</span><span class="sxs-lookup"><span data-stu-id="d5f33-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5f33-216">20023</span><span class="sxs-lookup"><span data-stu-id="d5f33-216">20023</span></span></p></td>
<td><p><span data-ttu-id="d5f33-217">Ошибка</span><span class="sxs-lookup"><span data-stu-id="d5f33-217">Error</span></span></p></td>
<td><p><span data-ttu-id="d5f33-218">Не удается присоединиться к AS MCU</span><span class="sxs-lookup"><span data-stu-id="d5f33-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="d5f33-219">Не удается присоединиться к AS MCU</span><span class="sxs-lookup"><span data-stu-id="d5f33-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="d5f33-220">Проверьте, запущен ли AS MCU</span><span class="sxs-lookup"><span data-stu-id="d5f33-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5f33-221">20024</span><span class="sxs-lookup"><span data-stu-id="d5f33-221">20024</span></span></p></td>
<td><p><span data-ttu-id="d5f33-222">Ошибка</span><span class="sxs-lookup"><span data-stu-id="d5f33-222">Error</span></span></p></td>
<td><p><span data-ttu-id="d5f33-223">Не удается присоединиться к MCU данных</span><span class="sxs-lookup"><span data-stu-id="d5f33-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="d5f33-224">Не удается присоединиться к MCU данных</span><span class="sxs-lookup"><span data-stu-id="d5f33-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="d5f33-225">Проверьте, запущен ли MCU данных</span><span class="sxs-lookup"><span data-stu-id="d5f33-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5f33-226">20025</span><span class="sxs-lookup"><span data-stu-id="d5f33-226">20025</span></span></p></td>
<td><p><span data-ttu-id="d5f33-227">Ошибка</span><span class="sxs-lookup"><span data-stu-id="d5f33-227">Error</span></span></p></td>
<td><p><span data-ttu-id="d5f33-228">Не удается получить доступ к Active Directory для фотографии</span><span class="sxs-lookup"><span data-stu-id="d5f33-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="d5f33-229">Недоступно подключение к Active Directory</span><span class="sxs-lookup"><span data-stu-id="d5f33-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="d5f33-230">Убедитесь в доступности соединения с Active Directory</span><span class="sxs-lookup"><span data-stu-id="d5f33-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5f33-231">20026</span><span class="sxs-lookup"><span data-stu-id="d5f33-231">20026</span></span></p></td>
<td><p><span data-ttu-id="d5f33-232">Информационный</span><span class="sxs-lookup"><span data-stu-id="d5f33-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="d5f33-233">Восстановление после сбоя доступа к Active Directory для фотографии</span><span class="sxs-lookup"><span data-stu-id="d5f33-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="d5f33-234">Н/Д</span><span class="sxs-lookup"><span data-stu-id="d5f33-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5f33-235">20027</span><span class="sxs-lookup"><span data-stu-id="d5f33-235">20027</span></span></p></td>
<td><p><span data-ttu-id="d5f33-236">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="d5f33-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="d5f33-237">Не удается выполнить десериализацию</span><span class="sxs-lookup"><span data-stu-id="d5f33-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="d5f33-238">Не удается выполнить десериализацию</span><span class="sxs-lookup"><span data-stu-id="d5f33-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="d5f33-239">Если проблема не устранена, обратитесь в службу поддержки продукта.</span><span class="sxs-lookup"><span data-stu-id="d5f33-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

