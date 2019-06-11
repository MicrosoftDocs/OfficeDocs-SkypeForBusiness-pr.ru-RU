---
title: Введение
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d496d0aeaabd8ef7502cae8db89f2668d0574499
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction"></a><span data-ttu-id="ce248-102">Введение</span><span class="sxs-lookup"><span data-stu-id="ce248-102">Introduction</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce248-103">_**Тема последнего изменения:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="ce248-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="ce248-104">С помощью средства нагрузки и производительности Lync Server 2013 (называемого также Линкперфтул) можно смоделировать нагрузку на следующие типы:</span><span class="sxs-lookup"><span data-stu-id="ce248-104">The Lync Server 2013 Stress and Performance Tool (referred to as LyncPerfTool) can simulate user load of the following types:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce248-105">Обмен мгновенными сообщениями и присутствие</span><span class="sxs-lookup"><span data-stu-id="ce248-105">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="ce248-106">Голосовые конференции</span><span class="sxs-lookup"><span data-stu-id="ce248-106">Audio conferencing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce248-107">Общий доступ к приложениям</span><span class="sxs-lookup"><span data-stu-id="ce248-107">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="ce248-108">Голосовая связь по протоколу IP (VoIP), включая эмуляцию коммутируемой телефонной сети (PSTN)</span><span class="sxs-lookup"><span data-stu-id="ce248-108">Voice over IP (VoIP), including public switched telephone network (PSTN) simulation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce248-109">Конференции на клиентах веб-доступа к Интернету</span><span class="sxs-lookup"><span data-stu-id="ce248-109">Web Access Client conferencing</span></span></p></td>
<td><p><span data-ttu-id="ce248-110">Помощник Microsoft Lync 2013</span><span class="sxs-lookup"><span data-stu-id="ce248-110">Microsoft Lync 2013 Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce248-111">Группы ответа</span><span class="sxs-lookup"><span data-stu-id="ce248-111">Response Groups</span></span></p></td>
<td><p><span data-ttu-id="ce248-112">Развертывание списка рассылки</span><span class="sxs-lookup"><span data-stu-id="ce248-112">Distribution list expansion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce248-113">Запрос на загрузку и адресную книгу в адресной книге</span><span class="sxs-lookup"><span data-stu-id="ce248-113">Address book download and address book query</span></span></p></td>
<td><p><span data-ttu-id="ce248-114">Улучшенный 9-1-1 (E9-1-1) звонки и профили местоположения (абонентская группа)</span><span class="sxs-lookup"><span data-stu-id="ce248-114">Enhanced 9-1-1 (E9-1-1) calls and location profile (dial plan)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce248-115">Многорежимный Просмотр</span><span class="sxs-lookup"><span data-stu-id="ce248-115">MultiView</span></span></p></td>
<td><p><span data-ttu-id="ce248-116">Просмотр нескольких потоков на Конференции</span><span class="sxs-lookup"><span data-stu-id="ce248-116">Viewing multiple streams from a conference</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ce248-117">Инструмент Lync Server 2013 поддерживает создание и использование нагрузки между пулами и интеграцией только с помощью расширенной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ce248-117">The Lync Server 2013 Stress and Performance Tool supports cross-pool load generation and federation through advanced configuration only.</span></span>

<span data-ttu-id="ce248-118">Кроме того, это средство не моделирует загрузку пользователей для следующих клиентов:</span><span class="sxs-lookup"><span data-stu-id="ce248-118">The tool also does not simulate user load for the following clients:</span></span>

  - <span data-ttu-id="ce248-119">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="ce248-119">Office Live Meeting 2007</span></span>

  - <span data-ttu-id="ce248-120">Lync 2013 сохраняемый чат</span><span class="sxs-lookup"><span data-stu-id="ce248-120">Lync 2013 Persistent Chat</span></span>

<span data-ttu-id="ce248-121">В результате средство Lync Server 2013 и производительность не будут поддерживать тестирование следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="ce248-121">As a result, the Lync Server 2013 Stress and Performance Tool will not support testing the following components:</span></span>

  - <span data-ttu-id="ce248-122">Lync 2013 сохраняемый чат</span><span class="sxs-lookup"><span data-stu-id="ce248-122">Lync 2013 Persistent Chat</span></span>

  - <span data-ttu-id="ce248-123">Сценарии интеграции с Exchange</span><span class="sxs-lookup"><span data-stu-id="ce248-123">Exchange integration scenarios</span></span>

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="ce248-124">Приложения и файлы, входящие в состав средства быстрой и производительной нагрузки Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce248-124">Applications and Files Included with the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="ce248-125">Ниже перечислены приложения, которые входят в состав средства быстрой и высокопроизводительной нагрузки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce248-125">The following applications are included in the Lync Server 2013 Stress and Performance Tool:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce248-126">Средств</span><span class="sxs-lookup"><span data-stu-id="ce248-126">Tool</span></span></th>
<th><span data-ttu-id="ce248-127">Описание</span><span class="sxs-lookup"><span data-stu-id="ce248-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce248-128">Усерпровисионингтул. exe</span><span class="sxs-lookup"><span data-stu-id="ce248-128">UserProvisioningTool.exe</span></span></p></td>
<td><p><span data-ttu-id="ce248-129">Средство подготовки пользователей Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce248-129">The Lync Server 2013 User Provisioning tool.</span></span> <span data-ttu-id="ce248-130">Это средство используется для создания пользователей и контактов.</span><span class="sxs-lookup"><span data-stu-id="ce248-130">This tool is used to create users and contacts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce248-131">Усерпрофилеженератор. exe</span><span class="sxs-lookup"><span data-stu-id="ce248-131">UserProfileGenerator.exe</span></span></p></td>
<td><p><span data-ttu-id="ce248-132">Средство настройки загрузки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce248-132">The Lync Server 2013 Load Configuration Tool.</span></span> <span data-ttu-id="ce248-133">Это средство используется для настройки характеристик пользовательской нагрузки для имитации.</span><span class="sxs-lookup"><span data-stu-id="ce248-133">This tool is used to configure the characteristics of the user load to simulate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce248-134">Линкперфтул. exe</span><span class="sxs-lookup"><span data-stu-id="ce248-134">LyncPerfTool.exe</span></span></p></td>
<td><p><span data-ttu-id="ce248-135">Средство "стресс и производительность" Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce248-135">The Lync Server 2013 Stress and Performance Tool.</span></span> <span data-ttu-id="ce248-136">Линкперфтул — это инструмент, который имитирует пользовательскую нагрузку.</span><span class="sxs-lookup"><span data-stu-id="ce248-136">LyncPerfTool is the tool that simulates the user load.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce248-137">Default. тмкс</span><span class="sxs-lookup"><span data-stu-id="ce248-137">Default.tmx</span></span></p></td>
<td><p><span data-ttu-id="ce248-138">Значение Default. тмкс является обязательным для использования средства ведения журнала в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce248-138">Default.tmx is required to use the Lync Server 2013 Logging Tool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce248-139">Примеры сценариев подготовки</span><span class="sxs-lookup"><span data-stu-id="ce248-139">Example provisioning scripts</span></span></p></td>
<td><p><span data-ttu-id="ce248-140">Эти примеры используются для настройки топологии для выполняющихся нагрузочных тестов на основе определенных сценариев.</span><span class="sxs-lookup"><span data-stu-id="ce248-140">These examples are used to configure the topology for running load tests, based on specific scenarios</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

