---
title: 'Lync Server 2013: Настройка добавочных номеров телефонов для вызовов парковки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure phone number extensions for parking calls
ms:assetid: fbf97624-9587-42a6-b276-1b69c574a74d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182611(v=OCS.15)
ms:contentKeyID: 48185980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39bd945f7e685965f892b3f3cab1be92bab73574
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-phone-number-extensions-for-parking-calls-in-lync-server-2013"></a><span data-ttu-id="d7fd0-102">Настройка добавочных номеров телефонов для вызовов парковки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7fd0-102">Configure phone number extensions for parking calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7fd0-103">_**Последнее изменение темы:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="d7fd0-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="d7fd0-104">Для приостановки вызовов приложение парковки вызовов использует добавочные номера в таблице орбит парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="d7fd0-104">The Call Park application uses extension numbers in the Call Park orbit table to park calls.</span></span> <span data-ttu-id="d7fd0-105">Необходимо настроить таблицу орбит парковки вызовов с диапазонами добавочных номеров, которые ваша организация резервирует для приостановленных звонков.</span><span class="sxs-lookup"><span data-stu-id="d7fd0-105">You need to configure the Call Park orbit table with the ranges of extension numbers that your organization reserves for parked calls.</span></span> <span data-ttu-id="d7fd0-106">Эти добавочные номера должны быть виртуальными (то есть не иметь назначенного пользователя или назначенный телефон).</span><span class="sxs-lookup"><span data-stu-id="d7fd0-106">These extensions need to be virtual extensions (that is, extensions that have no user or phone assigned to them).</span></span> <span data-ttu-id="d7fd0-107">Каждый пул Lync Server, в котором разворачивается и настраивается приложение парковки вызовов, может иметь один или несколько диапазонов орбиты.</span><span class="sxs-lookup"><span data-stu-id="d7fd0-107">Each Lync Server pool where a Call Park application is deployed and configured can have one or more orbit ranges.</span></span> <span data-ttu-id="d7fd0-108">Диапазоны орбиты должны быть глобально уникальными в развертывании Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d7fd0-108">Orbit ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d7fd0-109">Прежде чем использовать функцию парковки вызовов, необходимо установить флажок <STRONG>включить парковки вызовов</STRONG> в политике голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="d7fd0-109">You must select the <STRONG>Enable call park</STRONG> check box in your voice policy before you can use Call Park.</span></span> <span data-ttu-id="d7fd0-110">По умолчанию данный параметр не выбран.</span><span class="sxs-lookup"><span data-stu-id="d7fd0-110">By default, this option is not selected.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d7fd0-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="d7fd0-111">In This Section</span></span>

  - [<span data-ttu-id="d7fd0-112">Создание или изменение диапазона орбит для парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7fd0-112">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

  - [<span data-ttu-id="d7fd0-113">Удаление диапазона орбит парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7fd0-113">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

