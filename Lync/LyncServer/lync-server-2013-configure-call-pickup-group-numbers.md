---
title: 'Lync Server 2013: Настройка номеров групп для ответа на звонки'
description: 'Lync Server 2013: Настройка номеров групп ответа на звонки.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call pickup group numbers
ms:assetid: 5cc67f0b-d70d-446a-8db1-befda8671121
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945631(v=OCS.15)
ms:contentKeyID: 51541479
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ddffae2e385ce6c3fd7a700a9b94a89b1b6679f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565095"
---
# <a name="configure-call-pickup-group-numbers-in-lync-server-2013"></a><span data-ttu-id="cbdbb-103">Настройка номеров групп для ответа на звонки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbdbb-103">Configure call pickup group numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbdbb-104">_**Последнее изменение темы:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="cbdbb-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="cbdbb-105">Группа ответа на звонки основана на приложении парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="cbdbb-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="cbdbb-106">При развертывании группового ответа на звонки вы настраиваете таблицу орбит парковки вызовов с помощью диапазонов номеров телефонов, которые определены как номера групп ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="cbdbb-106">When you deploy Group Call Pickup, you configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="cbdbb-107">Эти номера групп — это номера, которые пользователи настроили для получения вызовов, которые вызывают звонок другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="cbdbb-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="cbdbb-108">Как и номера орбит для парковки вызовов, Номера групп для ответа на звонки должны быть виртуальными расширениями, которым не назначены пользователи или телефоны.</span><span class="sxs-lookup"><span data-stu-id="cbdbb-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="cbdbb-109">Каждый пул переднего плана, в котором развернута Групповая отправка звонков, может иметь один или несколько диапазонов номеров групп ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="cbdbb-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="cbdbb-110">Диапазоны номеров групп должны быть глобально уникальными в рамках развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cbdbb-110">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cbdbb-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="cbdbb-111">In This Section</span></span>

[<span data-ttu-id="cbdbb-112">Создание или изменение диапазона номеров для группового ответа на звонки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbdbb-112">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-group-call-pickup-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

