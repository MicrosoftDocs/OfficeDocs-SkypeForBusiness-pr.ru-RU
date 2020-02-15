---
title: 'Lync Server 2013: Мониторинг производительности сервера внешнего хранилища Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 760e66403fd1da2b5a45cf0db065dc201e1fd02a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a><span data-ttu-id="6f50e-102">Мониторинг производительности сервера внешней системы хранения данных Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f50e-102">Monitoring back end Lync Server 2013 storage performance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f50e-103">_**Последнее изменение темы:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="6f50e-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="6f50e-104">Серверные базы данных Lync Server 2013 являются очень важной частью развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f50e-104">The Lync Server 2013 back-end databases are a very important part of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="6f50e-105">Рекомендуется постоянно отслеживать базы данных и соответствующие журналы транзакций, чтобы обеспечить оптимальное выполнение серверного сервера Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6f50e-105">We recommend constantly monitoring the databases and respective transaction logs to help to make sure that the Lync Server 2013 back end is performing optimally.</span></span>

<span data-ttu-id="6f50e-106">В следующей таблице указаны счетчики производительности, которые необходимо отслеживать для получения сведений о производительности хранилища.</span><span class="sxs-lookup"><span data-stu-id="6f50e-106">The following table identifies performance counters that should be monitored to learn information about Storage Performance.</span></span> <span data-ttu-id="6f50e-107">Базовые значения для этих счетчиков необходимо определить первыми (когда система находится на нормальной, ожидаемой нагрузке), чтобы оценить изменения производительности при напряжении системы.</span><span class="sxs-lookup"><span data-stu-id="6f50e-107">The baseline values for these counters must be determined first (when system is at its normal, expected load) to understand the performance changes when system is stressed.</span></span>

### <a name="performance-counters-to-be-monitored"></a><span data-ttu-id="6f50e-108">Наблюдаемые счетчики производительности</span><span class="sxs-lookup"><span data-stu-id="6f50e-108">Performance counters to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f50e-109">Счетчик производительности</span><span class="sxs-lookup"><span data-stu-id="6f50e-109">Performance Counter</span></span></th>
<th><span data-ttu-id="6f50e-110">Базовые пороговые значения</span><span class="sxs-lookup"><span data-stu-id="6f50e-110">Baseline thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f50e-111">Транзакций в секунду (RTC)</span><span class="sxs-lookup"><span data-stu-id="6f50e-111">Transactions/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f50e-112">Транзакций в секунду (журнал RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="6f50e-112">Transactions/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f50e-113">Транзакций в секунду (tempdb)</span><span class="sxs-lookup"><span data-stu-id="6f50e-113">Transactions/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f50e-114">Сбросов журнала в секунду (RTC)</span><span class="sxs-lookup"><span data-stu-id="6f50e-114">Log Flushes/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f50e-115">Сбросов журнала/сек (журнал RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="6f50e-115">Log Flushes/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f50e-116">Очисток журнала в секунду (tempdb)</span><span class="sxs-lookup"><span data-stu-id="6f50e-116">Log Flushes/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f50e-117">Обращений к диску/сек (чтение и запись), RTC DB</span><span class="sxs-lookup"><span data-stu-id="6f50e-117">Disk Transfers/sec (read+write) - RTC db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f50e-118">Обращений к диску/сек-журнал RTC</span><span class="sxs-lookup"><span data-stu-id="6f50e-118">Disk Transfers/sec - RTC log</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f50e-119">Обращений к диску/сек-журнал RTCDyn DB</span><span class="sxs-lookup"><span data-stu-id="6f50e-119">Disk Transfers/sec - rtcdyn db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f50e-120">Обращений к диску/сек-журнал журнал RTCDyn</span><span class="sxs-lookup"><span data-stu-id="6f50e-120">Disk Transfers/sec - rtcdyn log</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

