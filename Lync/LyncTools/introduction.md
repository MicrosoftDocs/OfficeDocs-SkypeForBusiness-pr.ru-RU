---
title: Введение
description: Началь.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb847c499bde077ccaf2aa050de801ceeedcc6f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565285"
---
# <a name="introduction"></a><span data-ttu-id="187c6-103">Введение</span><span class="sxs-lookup"><span data-stu-id="187c6-103">Introduction</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="187c6-104">_**Последнее изменение темы:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="187c6-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="187c6-105">Средство нагрузки и производительности Lync Server 2013 (которое называется Линкперфтул) может имитировать нагрузку пользователей следующих типов:</span><span class="sxs-lookup"><span data-stu-id="187c6-105">The Lync Server 2013 Stress and Performance Tool (referred to as LyncPerfTool) can simulate user load of the following types:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="187c6-106">Обмен мгновенными сообщениями и функция присутствия</span><span class="sxs-lookup"><span data-stu-id="187c6-106">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="187c6-107">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="187c6-107">Audio conferencing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="187c6-108">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="187c6-108">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="187c6-109">Voice over IP (VoIP), включая имитацию телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="187c6-109">Voice over IP (VoIP), including public switched telephone network (PSTN) simulation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="187c6-110">Конференц-связь по клиентам веб-доступа</span><span class="sxs-lookup"><span data-stu-id="187c6-110">Web Access Client conferencing</span></span></p></td>
<td><p><span data-ttu-id="187c6-111">Помощник Microsoft Lync 2013</span><span class="sxs-lookup"><span data-stu-id="187c6-111">Microsoft Lync 2013 Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="187c6-112">Группы ответа</span><span class="sxs-lookup"><span data-stu-id="187c6-112">Response Groups</span></span></p></td>
<td><p><span data-ttu-id="187c6-113">Расширение списка рассылки</span><span class="sxs-lookup"><span data-stu-id="187c6-113">Distribution list expansion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="187c6-114">Запрос на загрузку и адресную книгу адресной книги</span><span class="sxs-lookup"><span data-stu-id="187c6-114">Address book download and address book query</span></span></p></td>
<td><p><span data-ttu-id="187c6-115">Расширенные 9-1-1 (E9-1-1) вызовы и профиль расположения (абонентская план)</span><span class="sxs-lookup"><span data-stu-id="187c6-115">Enhanced 9-1-1 (E9-1-1) calls and location profile (dial plan)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="187c6-116">Невозможность</span><span class="sxs-lookup"><span data-stu-id="187c6-116">MultiView</span></span></p></td>
<td><p><span data-ttu-id="187c6-117">Просмотр нескольких потоков из конференции</span><span class="sxs-lookup"><span data-stu-id="187c6-117">Viewing multiple streams from a conference</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="187c6-118">Средство нагрузки и производительности Lync Server 2013 поддерживает создание и Федерацию нагрузки между пулами с помощью расширенной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="187c6-118">The Lync Server 2013 Stress and Performance Tool supports cross-pool load generation and federation through advanced configuration only.</span></span>

<span data-ttu-id="187c6-119">Кроме того, средство не моделирует нагрузку для следующих клиентов:</span><span class="sxs-lookup"><span data-stu-id="187c6-119">The tool also does not simulate user load for the following clients:</span></span>

  - <span data-ttu-id="187c6-120">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="187c6-120">Office Live Meeting 2007</span></span>

  - <span data-ttu-id="187c6-121">Lync 2013 сохраняемый чат</span><span class="sxs-lookup"><span data-stu-id="187c6-121">Lync 2013 Persistent Chat</span></span>

<span data-ttu-id="187c6-122">В результате средство нагрузки и производительности Lync Server 2013 не будет поддерживать тестирование следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="187c6-122">As a result, the Lync Server 2013 Stress and Performance Tool will not support testing the following components:</span></span>

  - <span data-ttu-id="187c6-123">Lync 2013 сохраняемый чат</span><span class="sxs-lookup"><span data-stu-id="187c6-123">Lync 2013 Persistent Chat</span></span>

  - <span data-ttu-id="187c6-124">Сценарии интеграции с Exchange</span><span class="sxs-lookup"><span data-stu-id="187c6-124">Exchange integration scenarios</span></span>

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="187c6-125">Приложения и файлы, включенные в средство нагрузки и производительности Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="187c6-125">Applications and Files Included with the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="187c6-126">Следующие приложения включены в средство нагрузки и производительности Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="187c6-126">The following applications are included in the Lync Server 2013 Stress and Performance Tool:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="187c6-127">Средство</span><span class="sxs-lookup"><span data-stu-id="187c6-127">Tool</span></span></th>
<th><span data-ttu-id="187c6-128">Описание</span><span class="sxs-lookup"><span data-stu-id="187c6-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="187c6-129">UserProvisioningTool.exe</span><span class="sxs-lookup"><span data-stu-id="187c6-129">UserProvisioningTool.exe</span></span></p></td>
<td><p><span data-ttu-id="187c6-130">Средство подготовки пользователей Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="187c6-130">The Lync Server 2013 User Provisioning tool.</span></span> <span data-ttu-id="187c6-131">Это средство используется для создания пользователей и контактов.</span><span class="sxs-lookup"><span data-stu-id="187c6-131">This tool is used to create users and contacts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="187c6-132">UserProfileGenerator.exe</span><span class="sxs-lookup"><span data-stu-id="187c6-132">UserProfileGenerator.exe</span></span></p></td>
<td><p><span data-ttu-id="187c6-133">Средство настройки нагрузки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="187c6-133">The Lync Server 2013 Load Configuration Tool.</span></span> <span data-ttu-id="187c6-134">Это средство используется для настройки параметров пользовательской нагрузки для имитации.</span><span class="sxs-lookup"><span data-stu-id="187c6-134">This tool is used to configure the characteristics of the user load to simulate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="187c6-135">LyncPerfTool.exe</span><span class="sxs-lookup"><span data-stu-id="187c6-135">LyncPerfTool.exe</span></span></p></td>
<td><p><span data-ttu-id="187c6-136">Средство нагрузочного тестирования и производительности Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="187c6-136">The Lync Server 2013 Stress and Performance Tool.</span></span> <span data-ttu-id="187c6-137">Линкперфтул — это средство, моделирующее пользовательскую нагрузку.</span><span class="sxs-lookup"><span data-stu-id="187c6-137">LyncPerfTool is the tool that simulates the user load.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="187c6-138">По умолчанию. тмкс</span><span class="sxs-lookup"><span data-stu-id="187c6-138">Default.tmx</span></span></p></td>
<td><p><span data-ttu-id="187c6-139">Для использования средства ведения журнала Lync Server 2013 требуется значение Default. тмкс.</span><span class="sxs-lookup"><span data-stu-id="187c6-139">Default.tmx is required to use the Lync Server 2013 Logging Tool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="187c6-140">Пример сценариев подготовки</span><span class="sxs-lookup"><span data-stu-id="187c6-140">Example provisioning scripts</span></span></p></td>
<td><p><span data-ttu-id="187c6-141">Эти примеры используются для настройки топологии для запуска нагрузочных тестов на основе определенных сценариев.</span><span class="sxs-lookup"><span data-stu-id="187c6-141">These examples are used to configure the topology for running load tests, based on specific scenarios</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

