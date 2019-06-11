---
title: 'Lync Server 2013: Мониторинг производительности сервера Lync Server Storage'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4c63956cebc7f532f92b6e0729bdfe811d0fdfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a><span data-ttu-id="7d217-102">Мониторинг производительности сервера Lync Server 2013 в серверной части</span><span class="sxs-lookup"><span data-stu-id="7d217-102">Monitoring back end Lync Server 2013 storage performance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d217-103">_**Тема последнего изменения:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="7d217-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="7d217-104">Серверные базы данных Lync Server 2013 являются важной частью развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7d217-104">The Lync Server 2013 back-end databases are a very important part of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="7d217-105">Мы рекомендуем постоянно отслеживать базы данных и соответствующие журналы транзакций, чтобы обеспечить оптимальное выполнение серверной части Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7d217-105">We recommend constantly monitoring the databases and respective transaction logs to help to make sure that the Lync Server 2013 back end is performing optimally.</span></span>

<span data-ttu-id="7d217-106">В приведенной ниже таблице указаны счетчики производительности, которые необходимо отслеживать для получения сведений о производительности хранилища.</span><span class="sxs-lookup"><span data-stu-id="7d217-106">The following table identifies performance counters that should be monitored to learn information about Storage Performance.</span></span> <span data-ttu-id="7d217-107">Базовые значения для этих счетчиков должны определяться первыми (когда система находится в обычном режиме, ожидаемая загрузка) для понимания изменений производительности при напряжении системы.</span><span class="sxs-lookup"><span data-stu-id="7d217-107">The baseline values for these counters must be determined first (when system is at its normal, expected load) to understand the performance changes when system is stressed.</span></span>

### <a name="performance-counters-to-be-monitored"></a><span data-ttu-id="7d217-108">Наблюдаемые счетчики производительности</span><span class="sxs-lookup"><span data-stu-id="7d217-108">Performance counters to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7d217-109">Счетчик производительности</span><span class="sxs-lookup"><span data-stu-id="7d217-109">Performance Counter</span></span></th>
<th><span data-ttu-id="7d217-110">Пороговые значения базового плана</span><span class="sxs-lookup"><span data-stu-id="7d217-110">Baseline thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7d217-111">Транзакций в секунду (RTC)</span><span class="sxs-lookup"><span data-stu-id="7d217-111">Transactions/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d217-112">Транзакций в секунду (рткдин)</span><span class="sxs-lookup"><span data-stu-id="7d217-112">Transactions/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d217-113">Транзакций в секунду (база данных tempdb)</span><span class="sxs-lookup"><span data-stu-id="7d217-113">Transactions/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d217-114">Сбросов журнала в секунду (RTC)</span><span class="sxs-lookup"><span data-stu-id="7d217-114">Log Flushes/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d217-115">Сбросов журнала в секунду (рткдин)</span><span class="sxs-lookup"><span data-stu-id="7d217-115">Log Flushes/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d217-116">Сбросов журнала в секунду (tempdb)</span><span class="sxs-lookup"><span data-stu-id="7d217-116">Log Flushes/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d217-117">Обращений к диску/сек (чтение и запись) — запись данных RTC.</span><span class="sxs-lookup"><span data-stu-id="7d217-117">Disk Transfers/sec (read+write) - RTC db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d217-118">Обмен данными с диском/сек-журнал событий реального времени</span><span class="sxs-lookup"><span data-stu-id="7d217-118">Disk Transfers/sec - RTC log</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7d217-119">Обращений к диску в секунду — рткдин DB</span><span class="sxs-lookup"><span data-stu-id="7d217-119">Disk Transfers/sec - rtcdyn db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7d217-120">Обращений к диску/сек-журнал рткдин</span><span class="sxs-lookup"><span data-stu-id="7d217-120">Disk Transfers/sec - rtcdyn log</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

