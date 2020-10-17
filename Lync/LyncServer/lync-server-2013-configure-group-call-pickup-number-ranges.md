---
title: 'Lync Server 2013: Настройка диапазонов номеров для отправки групповых вызовов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Group Call Pickup number ranges
ms:assetid: f15f75f6-f965-4558-b612-f40cecdd5d8c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945657(v=OCS.15)
ms:contentKeyID: 51541529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d63ec2dcd4190be810d6296ffdafe58759efb68
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507686"
---
# <a name="configure-group-call-pickup-number-ranges-in-lync-server-2013"></a><span data-ttu-id="66308-102">Настройка диапазонов номеров для группового ответа на звонки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66308-102">Configure Group Call Pickup number ranges in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66308-103">_**Последнее изменение темы:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="66308-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="66308-104">Группа ответа на звонки основана на приложении парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="66308-104">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="66308-105">При развертывании группового ответа на звонки вы настраиваете таблицу орбит парковки вызовов с помощью диапазонов номеров телефонов, которые определены как номера групп ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="66308-105">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="66308-106">Эти номера групп — это номера, которые пользователи настроили для получения вызовов, которые вызывают звонок другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="66308-106">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="66308-107">Как и номера орбит для парковки вызовов, Номера групп для ответа на звонки должны быть виртуальными расширениями, которым не назначены пользователи или телефоны.</span><span class="sxs-lookup"><span data-stu-id="66308-107">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="66308-108">Каждый пул переднего плана, в котором развернута Групповая отправка звонков, может иметь один или несколько диапазонов номеров групп ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="66308-108">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="66308-109">Диапазоны номеров групп должны быть глобально уникальными в рамках развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="66308-109">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="66308-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="66308-110">In This Section</span></span>

  - [<span data-ttu-id="66308-111">Создание или изменение диапазона номеров для группового ответа на звонки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66308-111">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

  - [<span data-ttu-id="66308-112">Удаление диапазона номеров для группового ответа на звонки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66308-112">Delete a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-delete-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

