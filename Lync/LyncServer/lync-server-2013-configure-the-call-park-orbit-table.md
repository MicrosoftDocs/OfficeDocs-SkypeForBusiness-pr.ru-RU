---
title: 'Lync Server 2013: Настройка таблицы орбит парковки вызовов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the Call Park orbit table
ms:assetid: e5cc0c19-7b2c-48e7-a21d-cfb23c842f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399020(v=OCS.15)
ms:contentKeyID: 48185666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03cb3556ab0111d7bc61de6bc0914b5a3514a7cd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-call-park-orbit-table-in-lync-server-2013"></a><span data-ttu-id="eddde-102">Настройка таблицы орбит парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eddde-102">Configure the Call Park orbit table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eddde-103">_**Последнее изменение темы:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="eddde-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="eddde-104">Парковки вызовов использует орбиты для вызовов парковки.</span><span class="sxs-lookup"><span data-stu-id="eddde-104">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="eddde-105">Чтобы пользователи могли приостанавливать и получать вызовы, необходимо настроить таблицу орбит парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="eddde-105">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="eddde-106">Необходимо указать диапазоны добавочных номеров (орбиты), которые ваша организация будет резервировать для вызовов парковки, и определить маршрутизацию для этих диапазонов, указав, какой пул парковки вызовов обрабатывает каждый диапазон.</span><span class="sxs-lookup"><span data-stu-id="eddde-106">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="eddde-107">При определении диапазонов орбит требуется обеспечить достаточное число орбит, чтобы ни одна из орбит не использовалась повторно слишком часто, и одновременно не использовать слишком много орбит, чтобы не ограничивать количество добавочных номеров для пользователей и других служб.</span><span class="sxs-lookup"><span data-stu-id="eddde-107">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="eddde-108">Вы можете создать несколько диапазонов орбит парковки вызовов для каждого пула Lync Server, в котором развернуто приложение парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="eddde-108">You can create multiple Call Park orbit ranges for each Lync Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="eddde-109">Каждый диапазон орбит приостановки вызовов должен иметь глобальное уникальное имя и уникальный набор расширений.</span><span class="sxs-lookup"><span data-stu-id="eddde-109">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="eddde-p102">Обычно диапазон орбит содержит 100 или менее орбит. Каждый из диапазонов может быть значительно больше, максимальные значения составляют не более 10000 орбит на диапазон и менее 50000 орбит на пул. Если диапазон слишком мал, орбиты используются повторно с большей частотой.</span><span class="sxs-lookup"><span data-stu-id="eddde-p102">An orbit range typically encompasses 100 or fewer orbits. Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool. If a range is too small, the orbits are reused more quickly.</span></span>



</div>

<span data-ttu-id="eddde-113">Для своих диапазонов орбит используйте блоки виртуальных добавочных номеров (которым не назначен телефон или пользователь).</span><span class="sxs-lookup"><span data-stu-id="eddde-113">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eddde-114">Назначение номеров прямой связи (не) в качестве номеров орбит в таблице орбит парковки вызовов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="eddde-114">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="eddde-115">Содержание</span><span class="sxs-lookup"><span data-stu-id="eddde-115">In This Section</span></span>

[<span data-ttu-id="eddde-116">Создание или изменение диапазона орбит для парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eddde-116">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

