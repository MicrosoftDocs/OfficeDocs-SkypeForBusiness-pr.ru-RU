---
title: Введение
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 912c6a1704438106a3ffbb178d9f03a536489757
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="introduction"></a><span data-ttu-id="74c05-102">Введение</span><span class="sxs-lookup"><span data-stu-id="74c05-102">Introduction</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74c05-103">_**Последнее изменение темы:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="74c05-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="74c05-104">Средство нагрузки и производительности Lync Server 2013 (которое называется Линкперфтул) может имитировать нагрузку пользователей следующих типов:</span><span class="sxs-lookup"><span data-stu-id="74c05-104">The Lync Server 2013 Stress and Performance Tool (referred to as LyncPerfTool) can simulate user load of the following types:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74c05-105">Обмен мгновенными сообщениями и функция присутствия</span><span class="sxs-lookup"><span data-stu-id="74c05-105">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="74c05-106">Аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="74c05-106">Audio conferencing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74c05-107">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="74c05-107">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="74c05-108">Voice over IP (VoIP), включая имитацию телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="74c05-108">Voice over IP (VoIP), including public switched telephone network (PSTN) simulation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74c05-109">Конференц-связь по клиентам веб-доступа</span><span class="sxs-lookup"><span data-stu-id="74c05-109">Web Access Client conferencing</span></span></p></td>
<td><p><span data-ttu-id="74c05-110">Помощник Microsoft Lync 2013</span><span class="sxs-lookup"><span data-stu-id="74c05-110">Microsoft Lync 2013 Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74c05-111">Группы ответа</span><span class="sxs-lookup"><span data-stu-id="74c05-111">Response Groups</span></span></p></td>
<td><p><span data-ttu-id="74c05-112">Расширение списка рассылки</span><span class="sxs-lookup"><span data-stu-id="74c05-112">Distribution list expansion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74c05-113">Запрос на загрузку и адресную книгу адресной книги</span><span class="sxs-lookup"><span data-stu-id="74c05-113">Address book download and address book query</span></span></p></td>
<td><p><span data-ttu-id="74c05-114">Расширенные 9-1-1 (E9-1-1) вызовы и профиль расположения (абонентская план)</span><span class="sxs-lookup"><span data-stu-id="74c05-114">Enhanced 9-1-1 (E9-1-1) calls and location profile (dial plan)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74c05-115">Невозможность</span><span class="sxs-lookup"><span data-stu-id="74c05-115">MultiView</span></span></p></td>
<td><p><span data-ttu-id="74c05-116">Просмотр нескольких потоков из конференции</span><span class="sxs-lookup"><span data-stu-id="74c05-116">Viewing multiple streams from a conference</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="74c05-117">Средство нагрузки и производительности Lync Server 2013 поддерживает создание и Федерацию нагрузки между пулами с помощью расширенной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="74c05-117">The Lync Server 2013 Stress and Performance Tool supports cross-pool load generation and federation through advanced configuration only.</span></span>

<span data-ttu-id="74c05-118">Кроме того, средство не моделирует нагрузку для следующих клиентов:</span><span class="sxs-lookup"><span data-stu-id="74c05-118">The tool also does not simulate user load for the following clients:</span></span>

  - <span data-ttu-id="74c05-119">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="74c05-119">Office Live Meeting 2007</span></span>

  - <span data-ttu-id="74c05-120">Lync 2013 сохраняемый чат</span><span class="sxs-lookup"><span data-stu-id="74c05-120">Lync 2013 Persistent Chat</span></span>

<span data-ttu-id="74c05-121">В результате средство нагрузки и производительности Lync Server 2013 не будет поддерживать тестирование следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="74c05-121">As a result, the Lync Server 2013 Stress and Performance Tool will not support testing the following components:</span></span>

  - <span data-ttu-id="74c05-122">Lync 2013 сохраняемый чат</span><span class="sxs-lookup"><span data-stu-id="74c05-122">Lync 2013 Persistent Chat</span></span>

  - <span data-ttu-id="74c05-123">Сценарии интеграции с Exchange</span><span class="sxs-lookup"><span data-stu-id="74c05-123">Exchange integration scenarios</span></span>

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="74c05-124">Приложения и файлы, включенные в средство нагрузки и производительности Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74c05-124">Applications and Files Included with the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="74c05-125">Следующие приложения включены в средство нагрузки и производительности Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="74c05-125">The following applications are included in the Lync Server 2013 Stress and Performance Tool:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74c05-126">Средство</span><span class="sxs-lookup"><span data-stu-id="74c05-126">Tool</span></span></th>
<th><span data-ttu-id="74c05-127">Описание</span><span class="sxs-lookup"><span data-stu-id="74c05-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74c05-128">Усерпровисионингтул. exe</span><span class="sxs-lookup"><span data-stu-id="74c05-128">UserProvisioningTool.exe</span></span></p></td>
<td><p><span data-ttu-id="74c05-129">Средство подготовки пользователей Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74c05-129">The Lync Server 2013 User Provisioning tool.</span></span> <span data-ttu-id="74c05-130">Это средство используется для создания пользователей и контактов.</span><span class="sxs-lookup"><span data-stu-id="74c05-130">This tool is used to create users and contacts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74c05-131">Усерпрофилеженератор. exe</span><span class="sxs-lookup"><span data-stu-id="74c05-131">UserProfileGenerator.exe</span></span></p></td>
<td><p><span data-ttu-id="74c05-132">Средство настройки нагрузки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74c05-132">The Lync Server 2013 Load Configuration Tool.</span></span> <span data-ttu-id="74c05-133">Это средство используется для настройки параметров пользовательской нагрузки для имитации.</span><span class="sxs-lookup"><span data-stu-id="74c05-133">This tool is used to configure the characteristics of the user load to simulate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74c05-134">Линкперфтул. exe</span><span class="sxs-lookup"><span data-stu-id="74c05-134">LyncPerfTool.exe</span></span></p></td>
<td><p><span data-ttu-id="74c05-135">Средство нагрузочного тестирования и производительности Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74c05-135">The Lync Server 2013 Stress and Performance Tool.</span></span> <span data-ttu-id="74c05-136">Линкперфтул — это средство, моделирующее пользовательскую нагрузку.</span><span class="sxs-lookup"><span data-stu-id="74c05-136">LyncPerfTool is the tool that simulates the user load.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74c05-137">По умолчанию. тмкс</span><span class="sxs-lookup"><span data-stu-id="74c05-137">Default.tmx</span></span></p></td>
<td><p><span data-ttu-id="74c05-138">Для использования средства ведения журнала Lync Server 2013 требуется значение Default. тмкс.</span><span class="sxs-lookup"><span data-stu-id="74c05-138">Default.tmx is required to use the Lync Server 2013 Logging Tool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74c05-139">Пример сценариев подготовки</span><span class="sxs-lookup"><span data-stu-id="74c05-139">Example provisioning scripts</span></span></p></td>
<td><p><span data-ttu-id="74c05-140">Эти примеры используются для настройки топологии для запуска нагрузочных тестов на основе определенных сценариев.</span><span class="sxs-lookup"><span data-stu-id="74c05-140">These examples are used to configure the topology for running load tests, based on specific scenarios</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

