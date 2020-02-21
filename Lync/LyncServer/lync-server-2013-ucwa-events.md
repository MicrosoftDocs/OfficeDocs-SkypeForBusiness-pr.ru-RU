---
title: 'Lync Server 2013: события UCWA'
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
ms.openlocfilehash: 950d52dfe86ebf4d5b8b53677248528f1ef49047
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a><span data-ttu-id="28a9f-102">События UCWA в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28a9f-102">UCWA events in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28a9f-103">_**Последнее изменение темы:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="28a9f-103">_**Topic Last Modified:** 2013-02-15_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="28a9f-104">Lync Server 2013 использует веб-API объединенных коммуникаций (UCWA) для выполнения различных задач, от доступа к Microsoft Exchange для поиска контактов для обновления сведений о присутствии для мобильных клиентов.</span><span class="sxs-lookup"><span data-stu-id="28a9f-104">Lync Server 2013 uses the Unified Communications Web API (UCWA) for a number of purposes, from accessing Microsoft Exchange for contact searches to updating presence for mobile clients.</span></span>

<span data-ttu-id="28a9f-105">UCWA будет записывать записи оперативного поведения в виде информационных, предупреждений и ошибок типов событий.</span><span class="sxs-lookup"><span data-stu-id="28a9f-105">UCWA will write records of operational behavior as event types Informational, Warning, and Error.</span></span> <span data-ttu-id="28a9f-106">В следующей таблице описываются события, которые могут быть записаны компонентами UCWA.</span><span class="sxs-lookup"><span data-stu-id="28a9f-106">The following table describes the events that can be written by the UCWA components.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="28a9f-107">Код события</span><span class="sxs-lookup"><span data-stu-id="28a9f-107">Event ID</span></span></th>
<th><span data-ttu-id="28a9f-108">Тип события</span><span class="sxs-lookup"><span data-stu-id="28a9f-108">Event Type</span></span></th>
<th><span data-ttu-id="28a9f-109">Сводка</span><span class="sxs-lookup"><span data-stu-id="28a9f-109">Summary</span></span></th>
<th><span data-ttu-id="28a9f-110">Причина и решение</span><span class="sxs-lookup"><span data-stu-id="28a9f-110">Cause and Resolution</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28a9f-111">20001</span><span class="sxs-lookup"><span data-stu-id="28a9f-111">20001</span></span></p></td>
<td><p><span data-ttu-id="28a9f-112">Справоч</span><span class="sxs-lookup"><span data-stu-id="28a9f-112">Informational</span></span></p></td>
<td><p><span data-ttu-id="28a9f-113">UCWA инициализировано</span><span class="sxs-lookup"><span data-stu-id="28a9f-113">UCWA initialized</span></span></p></td>
<td><p><span data-ttu-id="28a9f-114">Н/Д</span><span class="sxs-lookup"><span data-stu-id="28a9f-114">N/A</span></span></p>
<p><span data-ttu-id="28a9f-115">Н/Д</span><span class="sxs-lookup"><span data-stu-id="28a9f-115">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28a9f-116">20002</span><span class="sxs-lookup"><span data-stu-id="28a9f-116">20002</span></span></p></td>
<td><p><span data-ttu-id="28a9f-117">Error</span><span class="sxs-lookup"><span data-stu-id="28a9f-117">Error</span></span></p></td>
<td><p><span data-ttu-id="28a9f-118">В UCWA возникло неожиданное исключение во время инициализации</span><span class="sxs-lookup"><span data-stu-id="28a9f-118">UCWA encountered an unexpected exception during initialization</span></span></p></td>
<td><p><span data-ttu-id="28a9f-119">Произошла непредвиденная ошибка во время инициализации</span><span class="sxs-lookup"><span data-stu-id="28a9f-119">An unexpected error has occurred during initialization</span></span></p>
<p><span data-ttu-id="28a9f-120">Изучите сведения об исключении в связанной записи журнала событий, чтобы определить возможную причину</span><span class="sxs-lookup"><span data-stu-id="28a9f-120">Examine the exception details in the associated event log entry to determine the possible cause</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28a9f-121">20003</span><span class="sxs-lookup"><span data-stu-id="28a9f-121">20003</span></span></p></td>
<td><p><span data-ttu-id="28a9f-122">Error</span><span class="sxs-lookup"><span data-stu-id="28a9f-122">Error</span></span></p></td>
<td><p><span data-ttu-id="28a9f-123">В UCWA возникло необработанное исключение</span><span class="sxs-lookup"><span data-stu-id="28a9f-123">UCWA encountered an unhandled exception</span></span></p></td>
<td><p><span data-ttu-id="28a9f-124">Произошло необработанное исключение</span><span class="sxs-lookup"><span data-stu-id="28a9f-124">An unhandled exception happened</span></span></p>
<p><span data-ttu-id="28a9f-125">Перезапустите сервер.</span><span class="sxs-lookup"><span data-stu-id="28a9f-125">Restart the server.</span></span> <span data-ttu-id="28a9f-126">Если проблема не исчезнет, обратитесь в службу технической поддержки</span><span class="sxs-lookup"><span data-stu-id="28a9f-126">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28a9f-127">20004</span><span class="sxs-lookup"><span data-stu-id="28a9f-127">20004</span></span></p></td>
<td><p><span data-ttu-id="28a9f-128">Error</span><span class="sxs-lookup"><span data-stu-id="28a9f-128">Error</span></span></p></td>
<td><p><span data-ttu-id="28a9f-129">Не удается получить доступ к Exchange для фото в формате HD</span><span class="sxs-lookup"><span data-stu-id="28a9f-129">Cannot access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="28a9f-130">Подключение к Exchange недоступно</span><span class="sxs-lookup"><span data-stu-id="28a9f-130">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="28a9f-131">Убедитесь, что подключение к Exchange доступно.</span><span class="sxs-lookup"><span data-stu-id="28a9f-131">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28a9f-132">20005</span><span class="sxs-lookup"><span data-stu-id="28a9f-132">20005</span></span></p></td>
<td><p><span data-ttu-id="28a9f-133">Справоч</span><span class="sxs-lookup"><span data-stu-id="28a9f-133">Informational</span></span></p></td>
<td><p><span data-ttu-id="28a9f-134">Восстановление после отказа в доступе к Exchange для фотографии HD</span><span class="sxs-lookup"><span data-stu-id="28a9f-134">Recovered from failing to access Exchange for HD photo</span></span></p></td>
<td><p><span data-ttu-id="28a9f-135">Н/Д</span><span class="sxs-lookup"><span data-stu-id="28a9f-135">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28a9f-136">20006</span><span class="sxs-lookup"><span data-stu-id="28a9f-136">20006</span></span></p></td>
<td><p><span data-ttu-id="28a9f-137">Error</span><span class="sxs-lookup"><span data-stu-id="28a9f-137">Error</span></span></p></td>
<td><p><span data-ttu-id="28a9f-138">Не удается получить доступ к Exchange для поиска контактов</span><span class="sxs-lookup"><span data-stu-id="28a9f-138">Cannot access Exchange for contact search</span></span></p></td>
<td><p><span data-ttu-id="28a9f-139">Подключение к Exchange недоступно</span><span class="sxs-lookup"><span data-stu-id="28a9f-139">Connection to Exchange is not available</span></span></p>
<p><span data-ttu-id="28a9f-140">Убедитесь, что подключение к Exchange доступно.</span><span class="sxs-lookup"><span data-stu-id="28a9f-140">Make sure the connection to Exchange is available</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28a9f-141">20007</span><span class="sxs-lookup"><span data-stu-id="28a9f-141">20007</span></span></p></td>
<td><p><span data-ttu-id="28a9f-142">Справоч</span><span class="sxs-lookup"><span data-stu-id="28a9f-142">Informational</span></span></p></td>
<td><p><span data-ttu-id="28a9f-143">Восстановление после отказа поиска контакта в Exchange</span><span class="sxs-lookup"><span data-stu-id="28a9f-143">Recovered from failing to search contact in Exchange</span></span></p></td>
<td><p><span data-ttu-id="28a9f-144">Н/Д</span><span class="sxs-lookup"><span data-stu-id="28a9f-144">N/A</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28a9f-145">20008</span><span class="sxs-lookup"><span data-stu-id="28a9f-145">20008</span></span></p></td>
<td><p><span data-ttu-id="28a9f-146">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="28a9f-146">Warning</span></span></p></td>
<td><p><span data-ttu-id="28a9f-147">Попытка подписки на приложение более чем разрешенных подписок на присутствие</span><span class="sxs-lookup"><span data-stu-id="28a9f-147">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p></td>
<td><p><span data-ttu-id="28a9f-148">Попытка подписки на приложение более чем разрешенных подписок на присутствие</span><span class="sxs-lookup"><span data-stu-id="28a9f-148">Attempt to subscribe more than the allowed presence subscriptions per application</span></span></p>
<p><span data-ttu-id="28a9f-149">Проверка клиентов на наличие ненужных подписок</span><span class="sxs-lookup"><span data-stu-id="28a9f-149">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28a9f-150">20009</span><span class="sxs-lookup"><span data-stu-id="28a9f-150">20009</span></span></p></td>
<td><p><span data-ttu-id="28a9f-151">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="28a9f-151">Warning</span></span></p></td>
<td><p><span data-ttu-id="28a9f-152">Попытка подписки на пакет больше чем разрешенных подписок на присутствие</span><span class="sxs-lookup"><span data-stu-id="28a9f-152">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p></td>
<td><p><span data-ttu-id="28a9f-153">Попытка подписки на пакет больше чем разрешенных подписок на присутствие</span><span class="sxs-lookup"><span data-stu-id="28a9f-153">Attempt to subscribe more than the allowed presence subscriptions per batch</span></span></p>
<p><span data-ttu-id="28a9f-154">Проверка клиентов на наличие ненужных подписок</span><span class="sxs-lookup"><span data-stu-id="28a9f-154">Check the clients for unnecessary subscriptions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28a9f-155">20010</span><span class="sxs-lookup"><span data-stu-id="28a9f-155">20010</span></span></p></td>
<td><p><span data-ttu-id="28a9f-156">Error</span><span class="sxs-lookup"><span data-stu-id="28a9f-156">Error</span></span></p></td>
<td><p><span data-ttu-id="28a9f-157">Не удается получить данные из диапазона</span><span class="sxs-lookup"><span data-stu-id="28a9f-157">Cannot retrieve inband data</span></span></p></td>
<td><p><span data-ttu-id="28a9f-158">Не удается получить данные из диапазона</span><span class="sxs-lookup"><span data-stu-id="28a9f-158">Cannot retrieve inband data</span></span></p>
<p><span data-ttu-id="28a9f-159">Если проблема не исчезнет, обратитесь в службу технической поддержки</span><span class="sxs-lookup"><span data-stu-id="28a9f-159">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28a9f-160">20011</span><span class="sxs-lookup"><span data-stu-id="28a9f-160">20011</span></span></p></td>
<td><p><span data-ttu-id="28a9f-161">Error</span><span class="sxs-lookup"><span data-stu-id="28a9f-161">Error</span></span></p></td>
<td><p><span data-ttu-id="28a9f-162">Не удается подписать сведения о присутствии</span><span class="sxs-lookup"><span data-stu-id="28a9f-162">Cannot subscribe presence</span></span></p></td>
<td><p><span data-ttu-id="28a9f-163">Не удается подписать сведения о присутствии</span><span class="sxs-lookup"><span data-stu-id="28a9f-163">Cannot subscribe presence</span></span></p>
<p><span data-ttu-id="28a9f-164">Если проблема не исчезнет, обратитесь в службу технической поддержки</span><span class="sxs-lookup"><span data-stu-id="28a9f-164">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28a9f-165">20012</span><span class="sxs-lookup"><span data-stu-id="28a9f-165">20012</span></span></p></td>
<td><p><span data-ttu-id="28a9f-166">Error</span><span class="sxs-lookup"><span data-stu-id="28a9f-166">Error</span></span></p></td>
<td><p><span data-ttu-id="28a9f-167">Не удалось зарегистрировать конечную точку</span><span class="sxs-lookup"><span data-stu-id="28a9f-167">Failed to register endpoint</span></span></p></td>
<td><p><span data-ttu-id="28a9f-168">Не удалось зарегистрировать конечную точку</span><span class="sxs-lookup"><span data-stu-id="28a9f-168">Failed to register endpoint</span></span></p>
<p><span data-ttu-id="28a9f-169">Если проблема не исчезнет, обратитесь в службу технической поддержки</span><span class="sxs-lookup"><span data-stu-id="28a9f-169">If the problem persists contact product support</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28a9f-170">20013</span><span class="sxs-lookup"><span data-stu-id="28a9f-170">20013</span></span></p></td>
<td><p><span data-ttu-id="28a9f-171">Error</span><span class="sxs-lookup"><span data-stu-id="28a9f-171">Error</span></span></p></td>
<td><p><span data-ttu-id="28a9f-172">MCU IM недоступен</span><span class="sxs-lookup"><span data-stu-id="28a9f-172">IM MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="28a9f-173">MCU IM недоступен</span><span class="sxs-lookup"><span data-stu-id="28a9f-173">IM MCU is unavailable</span></span></p>
<p><span data-ttu-id="28a9f-174">Проверьте, запущена ли служба мгновенных сообщений MCU</span><span class="sxs-lookup"><span data-stu-id="28a9f-174">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28a9f-175">20014</span><span class="sxs-lookup"><span data-stu-id="28a9f-175">20014</span></span></p></td>
<td><p><span data-ttu-id="28a9f-176">Справоч</span><span class="sxs-lookup"><span data-stu-id="28a9f-176">Informational</span></span></p></td>
<td><p><span data-ttu-id="28a9f-177">Восстановление после отказа к подключению к IM MCU</span><span class="sxs-lookup"><span data-stu-id="28a9f-177">Recovered from failing to connect to IM MCU</span></span></p></td>
<td><p><span data-ttu-id="28a9f-178">Н/Д</span><span class="sxs-lookup"><span data-stu-id="28a9f-178">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28a9f-179">20015</span><span class="sxs-lookup"><span data-stu-id="28a9f-179">20015</span></span></p></td>
<td><p><span data-ttu-id="28a9f-180">Error</span><span class="sxs-lookup"><span data-stu-id="28a9f-180">Error</span></span></p></td>
<td><p><span data-ttu-id="28a9f-181">AV MCU недоступен</span><span class="sxs-lookup"><span data-stu-id="28a9f-181">AV MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="28a9f-182">AV MCU недоступен</span><span class="sxs-lookup"><span data-stu-id="28a9f-182">AV MCU is unavailable</span></span></p>
<p><span data-ttu-id="28a9f-183">Проверьте, работает ли AV MCU</span><span class="sxs-lookup"><span data-stu-id="28a9f-183">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28a9f-184">20016</span><span class="sxs-lookup"><span data-stu-id="28a9f-184">20016</span></span></p></td>
<td><p><span data-ttu-id="28a9f-185">Справоч</span><span class="sxs-lookup"><span data-stu-id="28a9f-185">Informational</span></span></p></td>
<td><p><span data-ttu-id="28a9f-186">Восстановление после отказа подключения к AV MCU</span><span class="sxs-lookup"><span data-stu-id="28a9f-186">Recovered from failing to connect to AV MCU</span></span></p></td>
<td><p><span data-ttu-id="28a9f-187">Н/Д</span><span class="sxs-lookup"><span data-stu-id="28a9f-187">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28a9f-188">20017</span><span class="sxs-lookup"><span data-stu-id="28a9f-188">20017</span></span></p></td>
<td><p><span data-ttu-id="28a9f-189">Error</span><span class="sxs-lookup"><span data-stu-id="28a9f-189">Error</span></span></p></td>
<td><p><span data-ttu-id="28a9f-190">Так как MCU недоступен</span><span class="sxs-lookup"><span data-stu-id="28a9f-190">AS MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="28a9f-191">Так как MCU недоступен</span><span class="sxs-lookup"><span data-stu-id="28a9f-191">AS MCU is unavailable</span></span></p>
<p><span data-ttu-id="28a9f-192">Проверьте, работает ли как MCU</span><span class="sxs-lookup"><span data-stu-id="28a9f-192">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28a9f-193">20018</span><span class="sxs-lookup"><span data-stu-id="28a9f-193">20018</span></span></p></td>
<td><p><span data-ttu-id="28a9f-194">Справоч</span><span class="sxs-lookup"><span data-stu-id="28a9f-194">Informational</span></span></p></td>
<td><p><span data-ttu-id="28a9f-195">Восстановление после отказа к подключению в качестве MCU</span><span class="sxs-lookup"><span data-stu-id="28a9f-195">Recovered from failing to connect to AS MCU</span></span></p></td>
<td><p><span data-ttu-id="28a9f-196">Н/Д</span><span class="sxs-lookup"><span data-stu-id="28a9f-196">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28a9f-197">20019</span><span class="sxs-lookup"><span data-stu-id="28a9f-197">20019</span></span></p></td>
<td><p><span data-ttu-id="28a9f-198">Error</span><span class="sxs-lookup"><span data-stu-id="28a9f-198">Error</span></span></p></td>
<td><p><span data-ttu-id="28a9f-199">MCU данных недоступен</span><span class="sxs-lookup"><span data-stu-id="28a9f-199">Data MCU is unavailable</span></span></p></td>
<td><p><span data-ttu-id="28a9f-200">MCU данных недоступен</span><span class="sxs-lookup"><span data-stu-id="28a9f-200">Data MCU is unavailable</span></span></p>
<p><span data-ttu-id="28a9f-201">Проверьте, работает ли MCU данных</span><span class="sxs-lookup"><span data-stu-id="28a9f-201">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28a9f-202">20020</span><span class="sxs-lookup"><span data-stu-id="28a9f-202">20020</span></span></p></td>
<td><p><span data-ttu-id="28a9f-203">Справоч</span><span class="sxs-lookup"><span data-stu-id="28a9f-203">Informational</span></span></p></td>
<td><p><span data-ttu-id="28a9f-204">Восстановление после отказа подключения к данным MCU</span><span class="sxs-lookup"><span data-stu-id="28a9f-204">Recovered from failing to connect to Data MCU</span></span></p></td>
<td><p><span data-ttu-id="28a9f-205">Н/Д</span><span class="sxs-lookup"><span data-stu-id="28a9f-205">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28a9f-206">20021</span><span class="sxs-lookup"><span data-stu-id="28a9f-206">20021</span></span></p></td>
<td><p><span data-ttu-id="28a9f-207">Error</span><span class="sxs-lookup"><span data-stu-id="28a9f-207">Error</span></span></p></td>
<td><p><span data-ttu-id="28a9f-208">Не удается присоединиться к IM MCU</span><span class="sxs-lookup"><span data-stu-id="28a9f-208">Cannot join IM MCU</span></span></p></td>
<td><p><span data-ttu-id="28a9f-209">Не удается присоединиться к IM MCU</span><span class="sxs-lookup"><span data-stu-id="28a9f-209">Cannot join IM MCU</span></span></p>
<p><span data-ttu-id="28a9f-210">Проверьте, запущена ли служба мгновенных сообщений MCU</span><span class="sxs-lookup"><span data-stu-id="28a9f-210">See whether IM MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28a9f-211">20022</span><span class="sxs-lookup"><span data-stu-id="28a9f-211">20022</span></span></p></td>
<td><p><span data-ttu-id="28a9f-212">Error</span><span class="sxs-lookup"><span data-stu-id="28a9f-212">Error</span></span></p></td>
<td><p><span data-ttu-id="28a9f-213">Не удается присоединиться к AV MCU</span><span class="sxs-lookup"><span data-stu-id="28a9f-213">Cannot join AV MCU</span></span></p></td>
<td><p><span data-ttu-id="28a9f-214">Не удается присоединиться к AV MCU</span><span class="sxs-lookup"><span data-stu-id="28a9f-214">Cannot join AV MCU</span></span></p>
<p><span data-ttu-id="28a9f-215">Проверьте, работает ли AV MCU</span><span class="sxs-lookup"><span data-stu-id="28a9f-215">See whether AV MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28a9f-216">20023</span><span class="sxs-lookup"><span data-stu-id="28a9f-216">20023</span></span></p></td>
<td><p><span data-ttu-id="28a9f-217">Error</span><span class="sxs-lookup"><span data-stu-id="28a9f-217">Error</span></span></p></td>
<td><p><span data-ttu-id="28a9f-218">Не удается присоединиться к MCU</span><span class="sxs-lookup"><span data-stu-id="28a9f-218">Cannot join AS MCU</span></span></p></td>
<td><p><span data-ttu-id="28a9f-219">Не удается присоединиться к MCU</span><span class="sxs-lookup"><span data-stu-id="28a9f-219">Cannot join AS MCU</span></span></p>
<p><span data-ttu-id="28a9f-220">Проверьте, работает ли как MCU</span><span class="sxs-lookup"><span data-stu-id="28a9f-220">See whether AS MCU is running</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28a9f-221">20024</span><span class="sxs-lookup"><span data-stu-id="28a9f-221">20024</span></span></p></td>
<td><p><span data-ttu-id="28a9f-222">Error</span><span class="sxs-lookup"><span data-stu-id="28a9f-222">Error</span></span></p></td>
<td><p><span data-ttu-id="28a9f-223">Не удается присоединиться к данным MCU</span><span class="sxs-lookup"><span data-stu-id="28a9f-223">Cannot join Data MCU</span></span></p></td>
<td><p><span data-ttu-id="28a9f-224">Не удается присоединиться к данным MCU</span><span class="sxs-lookup"><span data-stu-id="28a9f-224">Cannot join Data MCU</span></span></p>
<p><span data-ttu-id="28a9f-225">Проверьте, работает ли MCU данных</span><span class="sxs-lookup"><span data-stu-id="28a9f-225">See whether Data MCU is running</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28a9f-226">20025</span><span class="sxs-lookup"><span data-stu-id="28a9f-226">20025</span></span></p></td>
<td><p><span data-ttu-id="28a9f-227">Error</span><span class="sxs-lookup"><span data-stu-id="28a9f-227">Error</span></span></p></td>
<td><p><span data-ttu-id="28a9f-228">Не удается получить доступ к Active Directory для фото</span><span class="sxs-lookup"><span data-stu-id="28a9f-228">Cannot access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="28a9f-229">Подключение к Active Directory недоступно</span><span class="sxs-lookup"><span data-stu-id="28a9f-229">Connection to active directory is not available</span></span></p>
<p><span data-ttu-id="28a9f-230">Убедитесь, что подключение к Active Directory доступно.</span><span class="sxs-lookup"><span data-stu-id="28a9f-230">Make sure the connection to active directory is available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28a9f-231">20026</span><span class="sxs-lookup"><span data-stu-id="28a9f-231">20026</span></span></p></td>
<td><p><span data-ttu-id="28a9f-232">Справоч</span><span class="sxs-lookup"><span data-stu-id="28a9f-232">Informational</span></span></p></td>
<td><p><span data-ttu-id="28a9f-233">Восстановление из строя доступа к Active Directory для фотографии</span><span class="sxs-lookup"><span data-stu-id="28a9f-233">Recovered from failing to access active directory for photo</span></span></p></td>
<td><p><span data-ttu-id="28a9f-234">Н/Д</span><span class="sxs-lookup"><span data-stu-id="28a9f-234">N/A</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="28a9f-235">20027</span><span class="sxs-lookup"><span data-stu-id="28a9f-235">20027</span></span></p></td>
<td><p><span data-ttu-id="28a9f-236">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="28a9f-236">Warning</span></span></p></td>
<td><p><span data-ttu-id="28a9f-237">Не удается десериализовать</span><span class="sxs-lookup"><span data-stu-id="28a9f-237">Cannot deserialize</span></span></p></td>
<td><p><span data-ttu-id="28a9f-238">Не удается десериализовать</span><span class="sxs-lookup"><span data-stu-id="28a9f-238">Cannot deserialize</span></span></p>
<p><span data-ttu-id="28a9f-239">Если проблема не исчезнет, обратитесь в службу технической поддержки</span><span class="sxs-lookup"><span data-stu-id="28a9f-239">If the problem persists contact product support</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

